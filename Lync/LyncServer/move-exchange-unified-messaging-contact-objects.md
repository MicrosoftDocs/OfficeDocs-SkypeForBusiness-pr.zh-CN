---
title: 移动 Exchange 统一消息联系人对象
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>移动 Exchange 统一消息联系人对象

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

若要将自动助理 (AA) 和订阅者访问 (SA) 的联系人对象迁移到新的 Lync Server 2013 部署, 首先首先将旧 Office 通信服务器 2007 R2 部署中的对象移动到新的 Lync Server 2013 部署, 使用**CsExUmContact**和**CsExUmContact** cmdlet。 在 Exchange 服务器上, 然后运行**ExchUCUtil** Windows PowerShell 脚本, 为新部署的 Lync pool 执行以下操作:

  - 将其添加到统一消息 IP 网关。

  - 将其添加到统一邮件查寻组。

<div>


> [!NOTE]  
> 若要使用<STRONG>CsExUmContact</STRONG>和<STRONG>CsExUmContact</STRONG> cmdlet, 您必须是 RTCUniversalUserAdmins 组的成员, 并对存储联系人对象的 OU 拥有组织单位 (OU) 权限。 可以使用<STRONG>OUPermission</STRONG> CMDLET 授予 OU 权限。



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序移动联系人对象

1.  打开 Lync Server 命令行管理程序。

2.  对于使用 Exchange UM 注册的每个池 (其中 pool1.contoso.net 是 Office 通信服务器 2007 R2 部署的池, 而 pool2.contoso.net 是 Lync Server 2013 部署中的池), 请键入以下命令:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    若要验证联系人对象是否已移动, 请运行**CsExumContact** cmdlet, 确认**RegistrarPool**现在指向新池。

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>运行 ExchUCUtil Windows PowerShell 脚本

1.  以具有 Exchange 组织管理员权限的用户身份登录 Exchange UM 服务器。

2.  导航到 ExchUCUtil Windows PowerShell 脚本。
    
    在 Exchange 2007 中, ExchUCUtil 位于: **%\\程序文件%\\Microsoft Exchange Server\\脚本 ExchUCUtil\\**
    
    在 Exchange 2010 中, ExchUCUtil 位于: **%\\程序文件% Microsoft\\Exchange Server\\V14\\脚本 ExchUCUtil\\**

3.  如果在单个林中部署了 Exchange, 请键入:
    
        exchucutil.ps1
    
    或者, 如果 Exchange 是在多个目录林中部署的, 请键入:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    其中, 林 FQDN 指定了在其中部署 Lync Server 2013 的林。
    
    <div>
    

    > [!IMPORTANT]  
    > 请确保在运行 exchucutil<EM>后</EM>重新启动<STRONG>Lync Server 前端</STRONG>服务 (rtcsrv)。 否则, Lync Server 2013 将不会在拓扑中检测到统一消息。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

