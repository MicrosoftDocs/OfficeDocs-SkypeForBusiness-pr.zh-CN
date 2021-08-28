---
title: 部署 Skype for Business Server 的统计信息管理器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要：阅读本主题，了解如何为组织部署统计信息Skype for Business Server。
ms.openlocfilehash: 966d6aa71eff93f616ae0eb1a7443aebab600016
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612091"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>部署 Skype for Business Server 的统计信息管理器
 
**摘要：** 阅读本主题，了解如何为组织部署统计信息Skype for Business Server。
  
 统计数据管理器Skype for Business Server一个强大的工具，可用于实时Skype for Business Server运行状况和性能数据。 你可以每隔几秒钟轮询数百台服务器的性能数据，并立即在统计信息管理器网站上查看结果。
  
在尝试安装统计信息管理器之前，请确保你熟悉软件、网络和硬件要求。 有关详细信息，请参阅规划统计信息[管理器Skype for Business Server。](plan.md)
  
> [!NOTE]
> 如果要从以前的统计信息管理器版本升级，请参阅升级统计信息[管理器了解Skype for Business Server。](upgrade.md) 
  
> [!NOTE]
> 统计信息管理器网站已经过测试，在 Internet Explorer 11+、Edge 20.10240+ 和 Chrome 46+ (当前常青版本) 。 
  
可在 上找到可下载的统计信息管理器 [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) 。 
  
本主题包含以下各部分：
  
- [部署统计信息管理器](deploy.md#BKMK_Deploy)
    
- [部署疑难解答](deploy.md#BKMK_Troubleshoot)
    
- [创建自签名证书](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>部署统计信息管理器
<a name="BKMK_Deploy"> </a>

若要部署统计信息管理器，请按照以下步骤操作：
  
1. 通过安装 Redis 内存中缓存系统以及确保已安装相应的证书来准备侦听器主机。
    
2. 在主机上安装侦听器服务。 
    
3. 在主机上安装网站。
    
4. 在你要监视的每台Skype for Business Server安装代理。
    
5. 导入要监视的服务器拓扑。
    
> [!NOTE]
> Redis、侦听器服务和网站必须全部安装在同一台主机上。 请确保主机未安装Skype for Business Server。 
  
### <a name="prepare-the-listener-host-machine"></a>准备侦听器主机

要准备主机，你需要安装 Redis 内存中缓存系统，并确保计算机上有有效的证书。 Microsoft 建议你安装 Redis 3.0 的最新稳定内部版本。 统计信息管理器版本 2.0 已使用 Redis 3.2.100 进行了测试。 
  
1. 从以下网站下载 [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) Redis：。 
    
    可以从下载未签名的安装程序 [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    如果需要，可以通过热门程序包管理器使用已签名的二进制文件 [：Nuget](https://www.nuget.org/packages/Redis-64/) 和 [Choclatey](https://chocolatey.org/packages/redis-64)。
    
   - 运行提供的 msi 并按照提示执行。
    
   - 不要选中添加防火墙规则框。
    
2. 侦听器服务需要证书。 Microsoft 强烈建议你拥有由受信任的证书颁发机构签名的证书。 
    
    如果要使用自签名证书（例如，在实验室中进行测试，请参阅 [创建自签名证书](deploy.md#BKMK_SelfCert)）。
    
    请注意，代理使用证书指纹验证 (而不是链验证) 。 它将不会执行完整证书验证，因为可以使用自签名证书。
    
### <a name="install-the-listener-service"></a>安装侦听器服务

通过运行安装程序并指定以下内容，在StatsManPerfAgentListener.msi安装侦听器服务：
  
1. 查看许可协议，如果同意，请选择"**我接受许可协议中的条款"，** 然后单击"下一步 **"。** 
    
2. 下一页上，指定以下信息：
    
   - **服务密码：** 这是远程代理用于对侦听器服务进行身份验证的密码。
    
   - **服务端口：** 这是侦听器用于与代理通信的 HTTPS 端口号。 在安装过程中，将允许通过本地防火墙访问此端口，将创建 URL ACL，并且 SSL 证书将绑定到此端口。 默认值为 8443。
    
   - **证书指纹：** 这是侦听器用于加密 HTTPS 协议的证书指纹。 网络服务必须具有对私钥的读取访问权限。
    
     单击" **选择..."** 按钮以选择指纹。
    
     可以使用证书管理器或以下 PowerShell 命令查找证书指纹：
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - **安装目录：** 这是将安装二进制文件的目录。 可以使用"浏览..."按钮更改默认值。 
    
   - **AppData 目录：** 这是将存储 Logs 文件夹和其他数据的目录。 你可以更改默认值。 卸载时不会删除它。
    
3. 单击“**安装**”。
    
若要验证安装，请执行以下步骤：
  
1. 打开浏览器并导航到 https://localhost: \<service-port\> /healthcheck/
    
    默认情况下，服务端口为 8443 (，除非您指定了其他端口) 。
    
2. 若要确保侦听器安装正确，请查找以下内容：
    
   - 如果显示运行状况检查页，则表明侦听器安装成功。
    
   - 如果 KnownServerCount 为 1 或更高，则建立与 Redis 的连接。
    
   - 等待几分钟，并安装至少一个代理后，检查值已写入计数器是否正在递增。
    
### <a name="install-the-website"></a>安装网站

通过运行 Skype for Business Server、Real-Time 统计信息管理器[ (64](https://www.microsoft.com/en-in/download/details.aspx?id=57518)位 () ) 中包含的 StatsManWebSite.msi (并指定以下内容，在主机上安装网站：
  
1. 查看许可协议，如果同意，请选择"**我接受许可协议中的条款"，** 然后单击"下一步 **"。** 
    
2. 下一页上，指定以下信息：
    
   - **服务端口：** 这是网站将侦听的端口号。 稍后可以使用 IIS 管理器绑定更改它。 在安装过程中，将允许此端口通过本地防火墙。
    
   - **安装目录：** 这是将安装二进制文件的目录。 可以使用"浏览..."按钮更改默认值。 
    
   - **AppData 目录：** 这是将存储 Logs 文件夹和其他数据的目录。 你可以更改默认值。 卸载时不会删除它。
    
3. 单击“**安装**”。
    
若要查看网站，请打开浏览器并导航到 http://localhost ：，webport \> /。
  
若要仅查看运行状况信息，请打开浏览器并导航到 http://localhost: \<webport\> ：/healthcheck/。
  
默认情况下，Web 端口号为 8080。 可以使用 IIS 管理器更改网站的端口绑定。
  
Web 安装程序添加本地安全组，称为 StatsManWebSiteUsers。 你可以向此安全组添加帐户以授予对网站的访问权限。 
  
### <a name="install-the-agents"></a>安装代理

通过运行 Skype for Business Server并指定以下内容，在要监视的每个StatsManPerfAgent.msi安装代理：
  
1. 查看许可协议，如果同意，请选择"**我接受许可协议中的条款"，** 然后单击"下一步 **"。** 
    
2. 下一页上，指定以下信息：
    
   - **服务密码：** 这是远程代理向侦听器服务进行身份验证时将使用的密码。
    
   - **服务 URI：** 这是侦听器所在的 URI。 它应使用该 https://name:port 格式。
    
     可以使用 NETBIOS 名称或 FQDN。 您可以使用指定为侦听器服务上证书的 Subject 或 **Subject Alternative Names** 的名称，但这不是一项要求。
    
   - **服务指纹：** 这是侦听器使用的 SSL 证书的指纹。 代理将使用此指纹向侦听器进行身份验证。  (不会执行完整证书验证，因为可以使用自签名证书。) 
    
   - **安装目录：** 这是将安装二进制文件的目录。 可以使用"浏览..."按钮更改默认值。 
    
   - **AppData 目录：** 这是将存储 Logs 文件夹和加密文件password.txt目录。 你可能需要更改默认值。 卸载时不会删除它。
    
3. 单击“**安装**”。
    
如果要在多台计算机中安装代理，你可能希望以无人参与模式进行安装。 例如： 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>导入拓扑
<a name="BKMK_ImportTopology"> </a>

安装并运行统计信息管理器后，您需要导入Skype for Business Server拓扑，以便统计信息管理器知道每台服务器的站点、池和角色。 若要导入Skype for Business Server拓扑，您将使用[Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) cmdlet 检索有关组织使用的每个池的信息，然后将此信息导入统计信息管理器。
  
若要导入Skype for Business Server拓扑，请按照以下步骤操作：
  
1. 在具有 PowerShell cmdlet Skype for Business Server主机上：
    
    a. 运行以下命令： 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. 将"mypoolinfo.xml"文件复制到运行侦听器的服务器。
    
2. 在运行侦听器的主机上：
    
   a. 运行 PowerShell。
    
   b. 导航到安装侦听器的目录。 默认值为： 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. 若要确认要添加和更新的服务器，请运行以下命令：
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

通过以下命令可以查看所有选项：
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

若要查看当前导入的服务器信息，请运行以下脚本： 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

如果要监视不在 Skype for Business Server 拓扑中的服务器（例如 Exchange Server）可以在运行侦听器的主机上执行单服务器导入。 若要执行单服务器导入，请按照以下步骤操作：
  
1. 导航到安装侦听器的目录。 默认值为： 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 运行以下命令：
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>部署疑难解答
<a name="BKMK_Troubleshoot"> </a>

如果代理无法启动，请检查以下各项： 
  
- 代理是否注册到统计信息管理器中？
    
    1. 确保按照导入拓扑的说明进行操作。 请参阅 [导入拓扑](deploy.md#BKMK_ImportTopology)。
        
    2. 如果代理位于拓扑中未列出的服务器上 (例如 SQL AlwaysOn 群集) 中的节点，则需要按照导入拓扑中的说明手动添加[代理](deploy.md#BKMK_ImportTopology)。
    
- 代理能否与侦听器联系？
    
    1. 确保侦听器服务正在运行。 
        
        如果它未运行，请确保 Redis 正在运行，然后尝试重新启动侦听器。
        
    2. 确保端口对侦听器服务开放，并且代理计算机可以与端口通信。
    
- 若要确保统计信息管理器正在收集数据，可以按如下所示检查 CSV 文件。 
    
    以下命令检索计数器存储名称： 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    下一个命令检索指定计数器的值： 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

有关您可能在应用程序事件日志中看到的所有事件的信息，请参阅 Troubleshoot Statistics [Manager for Skype for Business Server](troubleshoot.md)。
  
## <a name="create-a-self-signed-certificate"></a>"创建自签名证书"
<a name="BKMK_SelfCert"> </a>

Microsoft 强烈建议使用由受信任的证书颁发机构签名的证书。 但是，如果要将自签名证书用于测试目的，请执行下列操作： 
  
1. 以管理员身份登录时，从 PowerShell 控制台中键入以下内容：
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 键入  `certlm.msc` 。 这将打开本地计算机证书管理器。
    
3. 导航到 **"个人"，** 然后打开"**证书"。**
    
4. 右键单击 **StatsManListener- \> 所有任务 - \> 管理私钥...**
    
5. 单击“**添加**”。
    
6. 在 **"输入要选择的对象名称"框中** ，键入以下内容：Network Service
    
7. 单击“**确定**”。
    
8. 在 **"完全控制**"下，取消选中 **"允许** "复选框。  (只有读取权限是必需的。) 
    
9. 单击“**确定**”。
    
## <a name="for-more-information"></a>更多详细信息
<a name="BKMK_SelfCert"> </a>

有关详细信息，请参阅：
  
- [Skype for Business Server 的统计信息管理器规划](plan.md)
    
- [更新 Skype for Business Server 的统计信息管理器](upgrade.md)
    
- [统计信息管理器疑难解答 Skype for Business Server](troubleshoot.md)操作