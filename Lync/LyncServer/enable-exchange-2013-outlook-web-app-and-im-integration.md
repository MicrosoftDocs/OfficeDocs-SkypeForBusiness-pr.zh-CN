---
title: 启用 Exchange 2013 Outlook Web App 和 IM 集成
TOCTitle: 启用 Exchange 2013 Outlook Web App 和 IM 集成
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204857(v=OCS.15)
ms:contentKeyID: 49312694
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用 Exchange 2013 Outlook Web App 和 IM 集成

 

_**上一次修改主题：** 2012-10-19_

若要启用 Exchange 2013 Outlook Web Access (OWA) 并与 Lync Server 2013 的即时消息 (IM) 集成，必须将 Exchange 2013 客户端访问服务器 (CAS) 服务器作为受信任应用程序服务器添加到 Lync Server 2013 拓扑。

## 创建受信任应用程序池

1.  启动 Lync Server 2013 命令行管理程序。

2.  运行以下 cmdlet：
    
        Get-CsSite
    
    这将返回要在其中创建池的 siteName 的 siteID。有关详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的 [Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite)。

3.  运行以下 cmdlet：
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    有关详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的 [New-CsTrustedApplicationPool](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplicationPool)。
    
    应将 Exchange Server FQDN 配置为 Exchange OWA 证书使用者名称 (SN) 或使用者替代名称 (SAN)。
    
    此外，在 Exchange OWA 中验证池的 FQDN 是否受信任。
    
    > [!IMPORTANT]  
    > 如果 CAS 服务器<em>未</em> 并置在运行 Exchange 2013 统一消息 (UM) 的同一服务器上，请跳过此过程中的其余步骤并执行本主题后面的“为 Exchange 2013 CAS 服务器创建受信任应用程序”过程。如果 CAS 服务器并置在运行 Exchange 2013 统一消息 (UM) 的同一服务器上，请完成此过程中的步骤且不要执行本主题后面的“为 Exchange 2013 CAS 服务器创建受信任应用程序”过程。


4.  运行“Enable-CsTopology”。

5.  打开拓扑生成器并下载现有拓扑。

6.  在左窗格中，展开树直至达到“受信任的应用程序服务器”。

7.  展开“受信任的应用程序服务器”节点。

8.  现在应看到 Exchange 2013 CAS 服务器列为受信任应用程序服务器。

## 为 Exchange 2013 CAS 服务器创建受信任应用程序

1.  启动 Lync Server 2013 命令行管理程序。

2.  如果 CAS 服务器 *未* 并置在运行 Exchange 2013 统一消息 (UM) 的同一服务器上，请运行以下 cmdlet：
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    有关详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的主题 [New-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplication)。

3.  运行“Enable-CsTopology”。

4.  从拓扑生成器的左窗格中，展开树直至到达“受信任的应用程序服务器”。

5.  展开“受信任的应用程序服务器”节点。

6.  现在应看到 Exchange 2013 CAS 服务器列为受信任应用程序服务器。

