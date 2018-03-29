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
description: 摘要： 阅读本主题，以了解如何部署为 Skype 业务服务器 2015年统计数据管理器。
ms.openlocfilehash: 7730a6b933bbe1d627bffe175a24a60273be3a88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-statistics-manager-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 部署统计信息管理器
 
**摘要：**阅读本主题，以了解如何部署为 Skype 业务服务器 2015年统计数据管理器。
  
 Skype 业务服务器的统计信息管理器是一个强大的工具，允许您查看 Skype 实时业务服务器运行状况和性能数据。 可以跨数百个服务器每隔几秒钟轮询性能数据和统计数据管理器网站上可立即查看结果。
  
您尝试安装统计管理器之前，请确保您熟悉的软件、 网络和硬件要求。 有关详细信息，请参阅[规划的业务服务器 2015年的 Skype 统计信息经理](plan.md)。
  
> [!NOTE]
> 如果您要从以前的版本的统计数据管理器升级，请参阅[升级业务服务器 2015年的 Skype 统计管理](upgrade.md)。 
  
> [!NOTE]
> 统计信息管理器网站已经过测试，可以在 Internet Explorer 11+、Edge 20.10240+ 和 Chrome 46+（当前 Evergreen 版本）上正确运行。 
  
您可以找到统计管理器即可下载[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)。 
  
本主题包括以下部分：
  
- [部署统计信息管理器](deploy.md#BKMK_Deploy)
    
- [对你的部署进行故障排除](deploy.md#BKMK_Troubleshoot)
    
- [创建自签名证书](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>部署统计信息管理器
<a name="BKMK_Deploy"> </a>

若要部署统计信息管理器，请执行以下步骤：
  
1. 通过安装 Redis 内存中缓存系统，并确保你已安装合适的证书，准备侦听器主机。
    
2. 在主机上安装侦听器服务。 
    
3. 在主机上安装网站。
    
4. 在每个 Skype 为想要监视的业务服务器计算机上安装代理。
    
5. 为你监视的服务器导入拓扑。
    
> [!NOTE]
> Redis、侦听器服务和网站必须安装在同一台主机上。 请确保主机安装业务服务器没有 Skype。 
  
### <a name="prepare-the-listener-host-machine"></a>准备侦听器主机。

要准备主机，你将需要安装 Redis 内存中缓存系统，并确保该计算机上存在有效证书。 Microsoft 建议安装稳定的最新 Redis 3.0 内部版本。 统计管理器版本 1.1 的经 Redis 3.0.501，Redis 2.8.2400。 
  
1. 从以下站点下载 Redis: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)。 
    
    可以从下载未签名的安装程序[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    如有必要，已签名的二进制文件都可以通过常用的包管理器： [Nuget](https://www.nuget.org/packages/Redis-64/)和[Choclatey](https://chocolatey.org/packages/redis-64)。
    
   - 运行提供的 msi 并按照提示操作。
    
   - 请勿选中用于添加防火墙规则的复选框。
    
2. 侦听器服务要求有证书。 Microsoft 强烈建议必须由受信任的证书颁发机构签名的证书。 
    
    如果你要使用自签名证书（例如，用于在实验室中进行测试），请参阅[创建自签名证书](deploy.md#BKMK_SelfCert)。
    
    请注意，代理使用证书指纹验证（而不是链验证）。由于可能使用自签名证书，因此它不会执行完整证书验证。
    
### <a name="install-the-listener-service"></a>安装侦听器服务

通过运行 StatsManPerfAgentListener.msi，并指定以下主机上安装侦听器服务：
  
1. 阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。 
    
2. 在下一页上，指定以下信息：
    
    - **服务密码：**这是远程代理将用于向侦听服务进行身份验证的密码。
    
    - **服务端口：**这是该侦听器将使用与代理进行通信的 HTTPS 端口号。 在安装期间，此端口将允许本地防火墙，通过 URL ACL 将被创建，并将此端口绑定 SSL 证书。 默认值为 8443。
    
    - **证书指纹：**这是监听器将使用加密的 HTTPS 协议的证书指纹。 网络服务必须具有读取访问权限的专用密钥。
    
    单击“**选择...**”按钮选择指纹。
    
    可以通过使用证书管理器或通过使用以下 PowerShell 命令来查找证书指纹：
    
  ```
  Get-ChildItem -path cert:\LocalMachine\My
  ```

   - **安装目录：**这是将在其安装二进制文件的目录。 可以更改该默认值使用**浏览...**按钮。
    
   - **应用程序数据目录：**这是存储日志文件夹和其他数据的目录。 您可以更改其默认值。 它不会删除在卸载时。
    
3. 单击“**安装**”。
    
要验证安装，请执行以下步骤：
  
1. 打开浏览器并定位到https://localhost:\<服务端口\>/healthcheck/
    
    默认情况下，服务端口为 8443（除非你指定了其他端口）。
    
2. 为了确保正确安装了侦听器，请查看以下内容：
    
   - 如果运行状况检查页面显示，则表示已成功安装侦听器。
    
   - 如果 KnownServersCount 为 1 或更高，则表示已建立与 Redis 的连接。
    
   - 等待几分钟，且至少安装了一个代理后，检查 ValuesWritten 计数器是否在递增。
    
### <a name="install-the-website"></a>安装网站

通过运行 StatsManWebSite.msi，并指定以下安装在主机上的网站：
  
1. 阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。 
    
2. 在下一页上，指定以下信息：
    
   - **服务端口：**这是 web 站点将侦听的端口号。 您可以使用 IIS 管理器绑定以后更改它。 在安装期间，将通过本地防火墙允许此端口。
    
   - **安装目录：**这是二进制文件的安装的目录。 可以更改该默认值使用**浏览...**按钮。
    
   - **应用程序数据目录：**这是存储日志文件夹和其他数据的目录。 您可以更改其默认值。 它不会删除在卸载时。
    
3. 单击“**安装**”。
    
若要查看该网站，打开浏览器，然后定位到： http://localhost，webport\>/。
  
若要查看运行状况的信息、 打开浏览器，然后定位到： http://localhost: \<webport\>/运行状况检查 /。
  
默认情况下，Web 端口号为 8080。 你可以使用 IIS 管理器更改网站的端口绑定。
  
Web 安装程序会添加名为 StatsManWebSiteUsers 的本地安全组。 你可以向此安全组添加帐户以授予对网站的访问权限。 
  
### <a name="install-the-agents"></a>安装代理

在每个 Skype 上安装代理，为您想要监视运行 StatsManPerfAgent.msi，并指定以下的业务服务器：
  
1. 阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。 
    
2. 在下一页上，指定以下信息：
    
   - **服务密码：**这是远程代理将用于向侦听器服务进行身份验证的密码。
    
   - **服务 URI:**这是监听器所处的位置的 URI。 它应该使用https://name:port格式。
    
    可以使用 NETBIOS 名称或 FQDN。 您可以使用也被指定为**主题**或**主题备用名称**的侦听器服务，证书的名称，但这并不是必需。
    
   - **服务指纹：**这是使用监听器的 SSL 证书的指纹。 （由于可能使用自签名证书，因此它不会执行完整证书验证。 ）
    
   - **安装目录：**这是将在其安装二进制文件的目录。 可以更改该默认值使用**浏览...**按钮。
    
   - **应用程序数据目录：**这是存储日志文件夹和加密的 password.txt 文件的目录。 您可能会感谢您更改默认值。 它不会删除在卸载时。
    
3. 单击“**安装**”。
    
如果你要在多台计算机上安装代理，你可能想以无人参与模式进行。例如： 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>导入拓扑
<a name="BKMK_ImportTopology"> </a>

因此统计管理器已安装并运行，您需要导入的业务服务器拓扑 Skype 之后该统计信息经理知道站点、 池和每个服务器的角色。 要导入的业务服务器拓扑结构您 Skype，您将使用[Get CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet 来检索有关您的组织中使用的每个池的信息，然后将此信息导入到统计信息管理器。
  
要导入的业务服务器拓扑 Skype，请执行以下步骤：
  
1. 在主机上具有业务服务器 PowerShell cmdlet 的 Skype:
    
    a. 运行以下命令： 
    
  ```
  Get-CsPool | Export-Clixml -Path mypoolinfo.xml
  ```
    b. "Mypoolinfo.xml"文件复制到运行侦听器的服务器。
    
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

要查看你当前导入的服务器信息，请运行以下脚本： 
  
```
.\Get-StatsManServerInfo.ps1
```

如果您想要监视服务器不属于您的业务服务器拓扑结构-Exchange Server，Skype 的-可以做运行侦听器的主机上的单个服务器导入。 要执行单服务器导入操作，请按照下列步骤操作：
  
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
  
- 在统计信息管理器代理注册？
    
1. 	确保遵循导入拓扑的说明。请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)。  
    
2. 如果代理位于拓扑中未列出的服务器上（例如，SQL AlwaysOn 群集内的节点），你将需要按照[导入拓扑](deploy.md#BKMK_ImportTopology)中的说明手动添加代理。
    
- 代理是否可以联系侦听器？
    
1. 确保侦听器服务正在运行。 
    
    如果侦听器服务未运行，请确保 Redis 正在运行，然后尝试重新启动侦听器。
    
2. 请确保端口已打开侦听器服务，并代理计算机可以进行通信的端口。
    
- 为确保统计数据管理器正在收集数据，可以按如下所述检查 CSV 文件。 
    
    以下命令检索计数器存储名称： 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    下一个命令检索指定计数器的值： 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

您可能会看到在应用程序事件日志中的所有事件的信息，请参阅[有关业务服务器 2015年的 Skype 解决统计数据管理器](troubleshoot.md)。
  
## <a name="create-a-self-signed-certificate"></a>创建自签名证书
<a name="BKMK_SelfCert"> </a>

Microsoft 强烈建议你使用受信任的证书颁发机构签发的证书。 但是，如果你要使用自签名证书以进行测试，请执行以下操作： 
  
1. 以管理员身份登录时，在 PowerShell 控制台中键入以下内容：
    
  ```
  New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
  ```

2. 类型`certlm.msc`。 这将为本地计算机打开证书管理器。
    
3. 导航到**个人**，然后再打开**证书**。
    
4. 右键单击**StatsManListener-\>所有任务-\>管理私钥...**
    
5. 单击“**添加**”。
    
6. 在“**输入要选择的对象名称**”框中，键入以下内容：网络服务
    
7. 单击“**确定**”。
    
8. 在“**完全控制**”下方，取消选中“**允许**”复选框。（只需要读取权限。）
    
9. 单击“**确定**”。
    
## <a name="for-more-information"></a>有关详细信息
<a name="BKMK_SelfCert"> </a>

有关详细信息，请参阅以下文章：
  
- [为业务服务器 2015年计划为 Skype 统计信息经理](plan.md)
    
- [为业务服务器 2015年升级为 Skype 的统计信息管理器](upgrade.md)
    
- [解决业务服务器 2015年的 Skype 的统计信息管理器](troubleshoot.md)
    
- [Skype 业务服务器统计信息管理器日志](https://blogs.technet.microsoft.com/skypestatsman/)
    

