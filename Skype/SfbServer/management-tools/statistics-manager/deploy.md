---
title: 为 Skype for Business Server 2015 部署统计信息管理器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要： 阅读本主题可了解如何为业务服务器 2015年部署 for Skype 的统计信息管理器。
ms.openlocfilehash: 28ee68cc8770660587cb7d22d2ddd68c754a4fca
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838576"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server-2015"></a>Deploy Statistics Manager for Skype for Business Server 2015
 
**摘要：** 阅读本主题可了解如何为业务服务器 2015年部署 for Skype 的统计信息管理器。
  
 适用于业务服务器 Skype 的统计信息管理器是一个强大的工具，允许您查看 Skype 的实时业务服务器运行状况和性能数据。 可以跨服务器数百每隔几秒钟轮询性能数据，并立即统计信息管理器网站上查看结果。
  
您尝试安装统计信息管理器之前，请确保您熟悉的软件、 网络和硬件要求。 有关详细信息，请参阅[计划为统计信息管理器中的业务服务器 2015年的 Skype](plan.md)。
  
> [!NOTE]
> 如果您要从早期版本的统计信息管理器中进行升级，请参阅[适用于业务服务器 2015年的 Skype 升级统计信息管理器](upgrade.md)。 
  
> [!NOTE]
> 统计信息管理器网站已经过测试，可以在 Internet Explorer 11+、Edge 20.10240+ 和 Chrome 46+（当前 Evergreen 版本）上正确运行。 
  
您可以找到统计信息管理器在可下载[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)。 
  
本主题包括以下部分：
  
- [部署统计信息管理器](deploy.md#BKMK_Deploy)
    
- [对你的部署进行故障排除](deploy.md#BKMK_Troubleshoot)
    
- [创建自签名证书](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>部署统计信息管理器
<a name="BKMK_Deploy"> </a>

若要部署的统计信息管理器，请按照下列步骤：
  
1. 通过安装 Redis 内存中缓存系统，并确保你已安装合适的证书，准备侦听器主机。
    
2. 在主机上安装侦听器服务。 
    
3. 在主机上安装网站。
    
4. 在每个 Skype 要监控的企业服务器计算机上安装代理。
    
5. 为你监视的服务器导入拓扑。
    
> [!NOTE]
> Redis、侦听器服务和网站必须安装在同一台主机上。 确保主机计算机的业务服务器安装没有 Skype。 
  
### <a name="prepare-the-listener-host-machine"></a>准备侦听器主机。

要准备主机，你将需要安装 Redis 内存中缓存系统，并确保该计算机上存在有效证书。 Microsoft 建议安装稳定的最新 Redis 3.0 内部版本。 统计信息管理器版本 1.1 的经 Redis 3.0.501 和 Redis 2.8.2400。 
  
1. 从以下网站下载 Redis: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)。 
    
    可以从下载未签名安装程序[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    如果需要，可通过以下常用程序包管理器获取签名的二进制文件：[Nuget](https://www.nuget.org/packages/Redis-64/) 和 [Choclatey](https://chocolatey.org/packages/redis-64)。
    
   - 运行提供的 msi 并按照提示操作。
    
   - 请勿选中用于添加防火墙规则的复选框。
    
2. 侦听器服务要求有证书。 Microsoft 强烈建议您有由受信任的证书颁发机构签名的证书。 
    
    如果你要使用自签名证书（例如，用于在实验室中进行测试），请参阅[创建自签名证书](deploy.md#BKMK_SelfCert)。
    
    请注意，代理使用证书指纹验证（而不是链验证）。由于可能使用自签名证书，因此它不会执行完整证书验证。
    
### <a name="install-the-listener-service"></a>安装侦听器服务

通过运行 StatsManPerfAgentListener.msi 并指定以下安装在主机上的侦听器服务：
  
1. 阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。 
    
2. 在下一页上，指定以下信息：
    
   - **服务密码：** 这是远程代理将用于向侦听服务进行身份验证的密码。
    
   - **服务端口：** 这是在侦听器将使用与代理进行通信的 HTTPS 端口号。 安装过程中，此端口将允许通过本地防火墙，将创建 URL ACL，并且将 SSL 证书绑定到此端口。 默认值为 8443。
    
   - **证书指纹：** 这是在侦听器将使用加密 HTTPS 协议的证书指纹。 网络服务必须具有读取访问权限的私钥。
    
     单击“**选择...**”按钮选择指纹。
    
     可以通过使用证书管理器或通过使用以下 PowerShell 命令来查找证书指纹：
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **安装目录：** 这是将在其安装二进制文件的目录。 您可以从默认更改它通过使用**浏览...** 按钮。
    
   - **应用程序数据 Dir:** 这是存储的 Logs 文件夹和其他数据的目录。 您可以从默认更改它。 它不会删除在卸载。
    
3. 单击“**安装**”。
    
要验证安装，请执行以下步骤：
  
1. 打开浏览器并导航到https://localhost:\<service-port\>/healthcheck/
    
    默认情况下，服务端口为 8443（除非你指定了其他端口）。
    
2. 为了确保正确安装了侦听器，请查看以下内容：
    
   - 如果运行状况检查页面显示，则表示已成功安装侦听器。
    
   - 如果 KnownServersCount 为 1 或更高，则表示已建立与 Redis 的连接。
    
   - 等待几分钟，且至少安装了一个代理后，检查 ValuesWritten 计数器是否在递增。
    
### <a name="install-the-website"></a>安装网站

通过运行 StatsManWebSite.msi 并指定以下安装在主机上的网站：
  
1. 阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。 
    
2. 在下一页上，指定以下信息：
    
   - **服务端口：** 这是网站将侦听的端口号。 您可以通过使用 IIS 管理器绑定更高版本更改它。 安装过程中，将通过本地防火墙允许此端口。
    
   - **安装目录：** 这是安装二进制文件的目录。 您可以从默认更改它通过使用**浏览...** 按钮。
    
   - **应用程序数据 Dir:** 这是存储的 Logs 文件夹和其他数据的目录。 您可以从默认更改它。 它不会删除在卸载。
    
3. 单击“**安装**”。
    
若要查看网站，请打开浏览器中，并导航到： http://localhost，webport\>/。
  
若要查看运行状况的信息、 打开浏览器中，并导航到： http://localhost:\<webport\>/healthcheck/。
  
默认情况下，Web 端口号为 8080。 你可以使用 IIS 管理器更改网站的端口绑定。
  
Web 安装程序会添加名为 StatsManWebSiteUsers 的本地安全组。 你可以向此安全组添加帐户以授予对网站的访问权限。 
  
### <a name="install-the-agents"></a>安装代理

您希望通过运行 StatsManPerfAgent.msi 并指定以下监控的企业服务器，请在每个 Skype 上上安装代理：
  
1. 阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。 
    
2. 在下一页上，指定以下信息：
    
   - **服务密码：** 这是远程代理将用于向侦听器服务进行身份验证的密码。
    
   - **服务 URI:** 这是在侦听器所在的 URI。 它应使用https://name:port格式。
    
     可以使用 NETBIOS 名称或 FQDN。 您可以使用也被指定为**主题**或的侦听器服务上的证书的**使用者替代名称**的名称，但这不是要求。
    
   - **服务指纹：** 这是使用侦听器 SSL 证书的指纹。 （由于可能使用自签名证书，因此它不会执行完整证书验证。 ）
    
   - **安装目录：** 这是将在其安装二进制文件的目录。 您可以从默认更改它通过使用**浏览...** 按钮。
    
   - **应用程序数据 Dir:** 这是存储日志文件夹和加密的 password.txt 文件的目录。 您可能感谢您更改其默认值。 它不会删除在卸载。
    
3. 单击“**安装**”。
    
如果你要在多台计算机上安装代理，你可能想以无人参与模式进行。例如： 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>导入拓扑
<a name="BKMK_ImportTopology"> </a>

统计信息管理器安装并运行，您需要导入的企业服务器拓扑 Skype 之后，以便该统计信息管理器知道站点、 池和每个服务器角色。 要导入您的企业服务器拓扑的 Skype，将使用[Get-cspool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet 可以检索有关组织中使用的每个池的信息，然后将此信息导入统计信息管理器。
  
要导入的企业服务器拓扑 Skype，请按照下列步骤：
  
1. 主机上具有业务 Server PowerShell cmdlet Skype:
    
    a. 运行以下命令： 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. 将"mypoolinfo.xml"文件复制到运行侦听器的服务器。
    
2. 在运行侦听器的主机上：
    
   a. 运行 PowerShell。
    
   b. 导航到安装侦听器的目录。 默认值为： 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. 要确认添加和更新哪些服务器，请运行以下命令：
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

使用以下命令可以查看所有选项：
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

若要查看您导入当前服务器的信息，请运行以下脚本： 
  
```
.\Get-StatsManServerInfo.ps1
```

如果您想要监控的企业服务器拓扑-Exchange 服务器，您 Skype 中的服务器，例如-您可以执行运行侦听器的主机上的单服务器导入。 要执行单服务器导入操作，请按照下列步骤操作：
  
1. 导航到安装侦听器的目录。 默认值为： 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 运行以下命令：
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>对你的部署进行故障排除
<a name="BKMK_Troubleshoot"> </a>

如果代理无法启动，请检查以下各项： 
  
- 代理已注册统计信息管理器中？
    
1. 	确保遵循导入拓扑的说明。请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)。  
    
2. 如果代理位于拓扑中未列出的服务器上（例如，SQL AlwaysOn 群集内的节点），你将需要按照[导入拓扑](deploy.md#BKMK_ImportTopology)中的说明手动添加代理。
    
- 代理是否可以联系侦听器？
    
1. 确保侦听器服务正在运行。 
    
    如果侦听器服务未运行，请确保 Redis 正在运行，然后尝试重新启动侦听器。
    
2. 确保端口已打开到侦听器服务，并且代理计算机可以进行通信的端口。
    
- 若要确保统计信息管理器收集数据，您可以如下所示检查 CSV 文件。 
    
    以下命令检索计数器存储名称： 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    下一个命令检索指定计数器的值： 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

您可能会看到应用程序事件日志中的所有事件的信息，请参阅[适用于业务服务器 2015年的 Skype 解决统计信息管理器](troubleshoot.md)。
  
## <a name="create-a-self-signed-certificate"></a>创建自签名证书
<a name="BKMK_SelfCert"> </a>

Microsoft 强烈建议你使用受信任的证书颁发机构签发的证书。 但是，如果你要使用自签名证书以进行测试，请执行以下操作： 
  
1. 以管理员身份登录时，在 PowerShell 控制台中键入以下内容：
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 键入`certlm.msc`。 这将为本地计算机打开证书管理器。
    
3. 导航到**个人**，然后打开**证书**。
    
4. 右键单击**StatsManListener-\>所有任务-\>管理私钥...**
    
5. 单击“**添加**”。
    
6. 在“**输入要选择的对象名称**”框中，键入以下内容：网络服务
    
7. 单击“**确定**”。
    
8. 在“**完全控制**”下方，取消选中“**允许**”复选框。（只需要读取权限。）
    
9. 单击“**确定**”。
    
## <a name="for-more-information"></a>有关详细信息
<a name="BKMK_SelfCert"> </a>

有关详细信息，请参阅以下文章：
  
- [Plan for Statistics Manager for Skype for Business Server 2015](plan.md)
    
- [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md)
    
- [Troubleshoot Statistics Manager for Skype for Business Server 2015](troubleshoot.md)
    
- [Skype for Business Server 统计信息管理器博客](https://blogs.technet.microsoft.com/skypestatsman/)
    

