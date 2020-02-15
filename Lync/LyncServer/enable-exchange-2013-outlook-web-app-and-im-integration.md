---
title: 启用 Exchange 2013 Outlook Web App 和 IM 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a67dd3c18525d7a39678b5871d087ea79c502fce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>启用 Exchange 2013 Outlook Web App 和 IM 集成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

若要启用与 Lync Server 2013 的 Exchange 2013 Outlook Web Access （OWA）和即时消息（IM）集成，您必须将 Exchange 2013 客户端访问服务器（CAS）服务器作为受信任的应用程序服务器添加到 Lync Server 2013 拓扑中。

<div>

## <a name="to-create-a-trusted-application-pool"></a>创建受信任应用程序池

1.  启动 Lync Server 2013 命令行管理程序。

2.  运行以下 cmdlet：
    
        Get-CsSite
    
    这将返回要在其中创建池的 siteName 的 siteID。 有关详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的[get-cssite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 。

3.  运行以下 cmdlet：
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    有关详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的[CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 。
    
    应将 Exchange Server FQDN 配置为 Exchange OWA 证书使用者名称 (SN) 或使用者替代名称 (SAN)。
    
    此外，在 Exchange OWA 中验证池的 FQDN 是否受信任。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的 CAS 服务器<EM>未</EM>在运行 Exchange 2013 统一消息（UM）的同一台服务器上并置，请跳过此过程中的其余步骤并执行本主题后面的 "为 EXCHANGE 2013 CAS 服务器创建受信任的应用程序" 过程。 如果 CAS 服务器在运行 Exchange 2013 统一消息（UM）的同一台服务器上并置，请完成此过程中的步骤，不要执行本主题后面部分的 "为 Exchange 2013 CAS 服务器创建受信任的应用程序" 过程。

    
    </div>

4.  运行“Enable-CsTopology”****。

5.  打开拓扑生成器并下载现有拓扑。

6.  在左窗格中，展开树直至达到“受信任的应用程序服务器”****。

7.  展开“受信任的应用程序服务器”**** 节点。

8.  现在，您应该会看到作为受信任应用程序服务器列出的 Exchange 2013 CAS 服务器。

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>为 Exchange 2013 CAS 服务器创建受信任的应用程序

1.  启动 Lync Server 2013 命令行管理程序。

2.  如果 CAS 服务器*不*是在运行 Exchange 2013 统一消息（UM）的同一台服务器上并置，请运行以下 cmdlet：
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    有关详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的 " [CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) " 主题。

3.  运行“Enable-CsTopology”****。

4.  从拓扑生成器的左窗格中，展开树直至到达“受信任的应用程序服务器”****。

5.  展开“受信任的应用程序服务器”**** 节点。

6.  现在，您应该会看到作为受信任应用程序服务器列出的 Exchange 2013 CAS 服务器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

