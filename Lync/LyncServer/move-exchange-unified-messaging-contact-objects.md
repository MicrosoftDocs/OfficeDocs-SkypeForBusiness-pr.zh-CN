---
title: 移动 Exchange 统一消息联系人对象
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c9a16251ca49d4d5179ed3ad72e4d0307beb4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>移动 Exchange 统一消息联系人对象

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

若要将自动助理（AA）和订阅者访问（SA）联系人对象迁移到新的 Lync Server 2013 部署，您首先要使用**CsExUmContact**和**CsExUmContact** cmdlet 将对象从旧版 Office 通信服务器 2007 R2 部署移动到新的 lync server 2013 部署。 在 Exchange 服务器上，您可以运行**Exchucutil.ps1** Windows PowerShell 脚本，为新部署的 Lync pool 执行以下操作：

  - 将其添加到统一消息 IP 网关。

  - 将其添加到统一消息智能寻线。

<div>


> [!NOTE]  
> 若要使用 <STRONG>Get-CsExUmContact</STRONG> 和 <STRONG>Move-CsExUmContact</STRONG> cmdlet，您必须是 RTCUniversalUserAdmins 组的成员，并且拥有存储联系对象的组织单位 (OU) 的 OU 权限。可以使用 <STRONG>Grant-OUPermission</STRONG> cmdlet 授予 OU 权限。



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序移动联系对象

1.  打开 Lync Server 命令行管理程序。

2.  对于在 Exchange UM 中注册的每个池（其中 pool1.contoso.net 是 Office 通信服务器 2007 R2 部署中的池，而 pool2.contoso.net 是来自 Lync Server 2013 部署的池），请键入以下命令：
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    若要验证是否已移动联系对象，请运行 **Get-CsExumContact** cmdlet，并确认“RegistrarPool”**** 现在是否指向新池。

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>运行 ExchUCUtil Windows PowerShell 脚本

1.  以具有 Exchange 组织管理员权限的用户身份登录到 Exchange UM 服务器。

2.  导航到 Exchucutil.ps1 Windows PowerShell 脚本。
    
    在 Exchange 2007 中，Exchucutil.ps1 位于： **%\\Program Files%\\Microsoft Exchange Server\\Scripts exchucutil.ps1\\**
    
    在 Exchange 2010 中，Exchucutil.ps1 位于： **%\\Program Files% Microsoft\\Exchange Server\\V14\\Scripts exchucutil.ps1\\**

3.  如果 Exchange 部署在单个林中，请键入：
    
        exchucutil.ps1
    
    否则，如果 Exchange 部署在多个林中，则键入：
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    其中，林 FQDN 指定在其中部署 Lync Server 2013 的林。
    
    <div>
    

    > [!IMPORTANT]  
    > 运行 exchucutil.ps1 后<EM></EM>，请确保重新启动“Lync Server 前端”<STRONG></STRONG>服务 (rtcsrv.exe)。 否则，Lync Server 2013 将不会在拓扑中检测到统一消息。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

