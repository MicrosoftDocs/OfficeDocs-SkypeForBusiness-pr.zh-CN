---
title: 部署 Skype for Business Server 的统计信息管理器
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要：阅读本主题，了解如何为Skype for Business Server部署统计信息管理器。
ms.openlocfilehash: 1debe0c38b3e3df0b6be193e892991c09e15fb61
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675984"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>部署 Skype for Business Server 的统计信息管理器

**总结：** 阅读本主题，了解如何为Skype for Business Server部署统计信息管理器。

 Skype for Business Server统计信息管理器是一种功能强大的工具，可用于实时查看Skype for Business Server运行状况和性能数据。 可以每隔几秒钟轮询数百台服务器的性能数据，并立即在 Statistics Manager 网站上查看结果。

在尝试安装 Statistics Manager 之前，请确保熟悉软件、网络和硬件要求。 有关详细信息，请参阅[计划统计信息管理器Skype for Business Server](plan.md)。

> [!NOTE]
> 如果要从以前版本的 Statistics Manager 升级，请参阅[适用于 Skype for Business Server 的升级统计信息管理器](upgrade.md)。

> [!NOTE]
> 统计信息管理器网站已在 Internet Explorer 11+、Edge 20.10240 和 Chrome 46+ (当前常青版本) 上进行了测试并正常工作。

你可以在以下位置找到统计信息管理器可 [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)下载。

本主题包含以下各部分：

- [部署统计信息管理器](deploy.md#BKMK_Deploy)

- [排查部署问题](deploy.md#BKMK_Troubleshoot)

- [创建自签名证书](deploy.md#BKMK_SelfCert)

## <a name="deploy-statistics-manager"></a>部署统计信息管理器
<a name="BKMK_Deploy"> </a>

若要部署 Statistics Manager，请执行以下步骤：

1. 通过安装 Redis 内存中缓存系统，并确保已安装相应的证书来准备侦听器主机。

2. 在主机上安装侦听器服务。

3. 在主机上安装网站。

4. 在要监视的每台Skype for Business Server计算机上安装代理。

5. 导入要监视的服务器的拓扑。

> [!NOTE]
> Redis、Listener 服务和网站都必须安装在同一台主机上。 请确保主机未安装Skype for Business Server。

### <a name="prepare-the-listener-host-machine"></a>准备侦听器主机

若要准备主机，需要安装 Redis 内存中缓存系统，并确保计算机上存在有效的证书。 Microsoft 建议安装最新稳定的 Redis 3.0 版本。 使用 Redis 3.2.100 测试了 Statistics Manager 版本 2.0。

1. 从以下网站下载 Redis： [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).

    可以从中下载未签名的安装程序 [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)

    已签名的二进制文件可通过常用包管理器提供： [Nuget](https://www.nuget.org/packages/Redis-64/) 和 [Choclatey](https://chocolatey.org/packages/redis-64)。

   - 运行提供的 msi 并按照提示操作。

   - 请勿选中该框以添加防火墙规则。

2. 侦听器服务需要证书。 Microsoft 强烈建议你拥有由受信任的证书颁发机构签名的证书。

    如果要使用自签名证书（例如实验室中的测试目的）请参阅 [“创建自签名证书](deploy.md#BKMK_SelfCert)”。

    代理使用证书指纹验证 (而不是链验证) 。 它不会执行完整的证书验证，因为可以使用自签名证书。

### <a name="install-the-listener-service"></a>安装侦听器服务

通过运行StatsManPerfAgentListener.msi并在主机上安装侦听器服务，并指定以下内容：

1. 查看许可协议，如果同意，请选择 **我接受许可协议中的条款**，然后单击 **“下一步**”。

2. 在下一页上，指定以下信息：

   - **服务密码：** 远程代理使用此密码向侦听器服务进行身份验证。

   - **服务端口：** 侦听器使用此 HTTPS 端口号与代理通信。 在安装期间，将允许通过本地防火墙使用此端口，将创建 URL ACL，并将 SSL 证书绑定到此端口。 默认值为 8443。

   - **证书指纹：** 侦听器使用此证书来加密 HTTPS 协议。 网络服务必须具有对私钥的读取访问权限。

     单击“ **选择...** ”按钮以选择指纹。

     可以使用证书管理器或使用以下 PowerShell 命令查找证书指纹：

      ```PowerShell
      Get-ChildItem -path cert:\LocalMachine\My
      ```

   - **安装 Dir：** 此目录是将安装二进制文件的位置。 可以使用 **“浏览...** ”按钮从默认值更改它。

   - **AppData Dir：** 此目录是日志文件夹和其他数据的存储位置。 可以从默认值更改它。 卸载时不会将其删除。

3. 单击“**安装**”。

若要验证安装，请执行以下步骤：

1. 打开浏览器，导航到 `https://localhost:<service-port>/healthcheck/`。

    默认情况下，服务端口为 8443 (，除非你指定了另一个端口) 。

2. 若要确保侦听器已正确安装，请查找以下内容：

   - 如果显示运行状况检查页，侦听器安装成功。

   - 如果 KnownServerCount 为 1 或更高版本，则会建立与 Redis 的连接。

   - 等待几分钟后，至少安装了一个代理后，请检查 ValuesWritten 计数器是否在递增。

### <a name="install-the-website"></a>安装网站

通过运行包含在 Skype for Business Server Real-Time [Statistics Manager (64 位) ) 的StatsManWebSite.msi (](https://www.microsoft.com/download/details.aspx?id=57518) ，在主机上安装网站：

1. 查看许可协议，如果同意，请选择 **我接受许可协议中的条款**，然后单击 **“下一步**”。

2. 在下一页上，指定以下信息：

   - **服务端口：** 此 TCP 端口是网站将侦听的位置。 稍后可以使用 IIS 管理器绑定来更改它。 在安装期间，将允许通过本地防火墙使用此端口。

   - **安装 Dir：** 此目录是将安装二进制文件的位置。 可以使用 **“浏览...** ”按钮从默认值更改它。

   - **AppData Dir：** 此目录是将存储 Logs 文件夹和其他数据的位置。 可以从默认值更改它。 卸载时不会将其删除。

3. 单击“**安装**”。

若要查看网站，请打开浏览器并导航到： `http://<localhost:webport/>`

若要仅查看运行状况信息，请打开浏览器并导航到： `http://localhost:<webport>/healthcheck/`。

默认情况下，Web 端口号为 8080。 可以使用 IIS 管理器更改网站的端口绑定。

Web 安装程序添加了一个名为 StatsManWebSiteUsers 的本地安全组。 可以将帐户添加到此安全组以授予对网站的访问权限。

### <a name="install-the-agents"></a>安装代理

通过运行StatsManPerfAgent.msi，在要监视的每个Skype for Business Server上安装代理：

1. 查看许可协议，如果同意，请选择 **我接受许可协议中的条款**，然后单击 **“下一步**”。

2. 在下一页上，指定以下信息：

   - **服务密码：** 远程代理使用此密码向侦听器服务进行身份验证。

   - **服务 URI：** 此 URL 是侦听器所在的位置。 使用格式 `https://name:port` 。

     可以使用 NETBIOS 名称或 FQDN。 可以使用也指定为侦听器服务上证书 **的主题** 或 **使用者可选名称** 的名称，但这不是一项要求。

   - **服务指纹：** 此 SS：侦听器使用证书。 代理将使用此指纹向侦听器进行身份验证。 它不会执行完整的证书验证，因为可以使用自签名证书。

   - **安装 Dir：** 此目录是将安装二进制文件的位置。 可以使用 **“浏览...** ”按钮从默认值更改它。

   - **AppData Dir：** 此目录是将存储 Logs 文件夹和加密password.txt文件的位置。 你可能感谢从默认值更改它。 卸载时不会将其删除。

3. 单击“**安装**”。

如果要在许多计算机上安装代理，则可能需要在无人参与模式下执行此操作。 例如：

```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>导入拓扑
<a name="BKMK_ImportTopology"> </a>

安装并运行统计信息管理器后，需要导入Skype for Business Server拓扑，以便统计信息管理器知道每个服务器的站点、池和角色。 若要导入Skype for Business Server拓扑，你将使用 [Get-CsPool](/powershell/module/skype/get-cspool) cmdlet 检索有关组织中使用的每个池的信息，然后将此信息导入到 Statistics Manager 中。

若要导入Skype for Business Server拓扑，请执行以下步骤：

1. 在具有 Skype for Business Server PowerShell cmdlet 的主机上：

    a. 运行以下命令：

   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```

    b. 将“mypoolinfo.xml”文件复制到运行侦听器的服务器。

2. 在运行侦听器的主机上：

   a. 运行 PowerShell。

   b. 导航到安装侦听器的目录。 默认值为：

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. 若要确认要添加和更新哪些服务器，请运行以下命令：

   ```console
   .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

使用以下命令可以查看所有选项：

```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed
```

若要查看当前导入的服务器信息，请运行以下脚本：

```powershell
.\Get-StatsManServerInfo.ps1
```

如果想要监视不在Skype for Business Server拓扑中的服务器（例如Exchange Server），则可以在运行侦听器的主机上执行单服务器导入。 若要执行单服务器导入，请执行以下步骤：

1. 导航到安装侦听器的目录。 默认值为：

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 运行以下命令：

   ```powershell
   .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>排查部署问题
<a name="BKMK_Troubleshoot"> </a>

如果代理无法启动，请检查以下问题：

- 代理是否已在 Statistics Manager 中注册？

   1. 请确保按照有关导入拓扑的说明操作。 请参阅 [“导入拓扑](deploy.md#BKMK_ImportTopology)”。

   2. 例如，如果代理位于拓扑 (中未列出的服务器上，SQL AlwaysOn 群集中的节点) ，则需要按照导入[拓扑](deploy.md#BKMK_ImportTopology)中的说明手动添加代理。

- 代理是否可以联系侦听器？

   1. 确保侦听器服务正在运行。

      如果它未运行，请确保 Redis 正在运行，然后尝试重启侦听器。

   2. 确保端口对侦听器服务开放，并且代理计算机可以与端口通信。

- 若要确保 Statistics Manager 正在收集数据，可以按如下所示检查 CSV 文件。

    以下命令检索计数器存储名称：

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    下一个命令检索指定计数器的值：

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

有关在应用程序事件日志中可能看到的所有事件的信息，请参阅[有关Skype for Business Server的统计信息管理器故障排除](troubleshoot.md)。

## <a name="create-a-self-signed-certificate"></a>"创建自签名证书"
<a name="BKMK_SelfCert"> </a>

Microsoft 强烈建议使用由受信任的证书颁发机构签名的证书。 但是，如果要将自签名证书用于测试目的，请执行以下步骤：

1. 在以管理员身份登录时，从 PowerShell 控制台运行以下命令：

   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 类型  `certlm.msc`。 这将打开本地计算机的证书管理器。

3. 导航到 **“个人**”，然后打开 **“证书**”。

4. 右键单击 **StatsManListener - \> 所有任务 - \>管理私钥...**

5. 单击“**添加**”。

6. 在 **“输入要选择的对象名称** ”框中，键入以下文本：网络服务

7. 单击“确定”。

8. 在 **“完全控制**”下，取消选中 **“允许** ”复选框。  (仅限读取访问权限是必需的。) 

9. 单击“确定”。

## <a name="for-more-information"></a>更多详细信息
<a name="BKMK_SelfCert"> </a>

有关详细信息，请参阅下列主题：

- [Skype for Business Server 的统计信息管理器规划](plan.md)

- [更新 Skype for Business Server 的统计信息管理器](upgrade.md)

- [对 Skype for Business Server 的统计信息管理器进行故障排除](troubleshoot.md)
