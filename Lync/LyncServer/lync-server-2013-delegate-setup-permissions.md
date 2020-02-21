---
title: Lync Server 2013：委派安装程序权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0fcf148e5e3cc4003dac97e8ef5ca9f1b2e678a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中委派安装程序权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

如果您不想向正在部署 lync server 2013 的用户或组授予 Domain Admins 组成员身份，则可以启用 RTCUniversalServerAdmins 组的成员，以便在运行 Lync server 2013 的服务器上运行**enable-cstopology** Windows PowerShell cmdlet。 默认情况下，RTCUniversalServerAdmins 组的成员无法运行此 cmdlet。 通过使用**CsSetupPermission** cmdlet 并指定运行 lync server 2013 的服务器的计算机对象所在的组织单位（OU），您可以授予管理员对运行 lync server 的服务器上运行**enable-cstopology**的权限。

在安装 Lync Server 时进行的域准备不会自动添加允许 RTCUniversalServerAdmins 组成员运行 Enable-cstopology cmdlet 的权限。 这意味着，默认情况下，只有域管理员才能启用拓扑。 要授予 RTCUniversalServerAdmins 组的成员启用拓扑的权限，必须运行 Grant-CsSetupPermissions cmdlet。 此外，还需要对驻留运行 Lync Server 的计算机的每个 Active Directory 容器运行此 cmdlet。

请记住，此 cmdlet 仅向 RTCUniversalServerAdmins 组授予权限；此 cmdlet 不能用于向其他安全组或向单个用户授予权限。

<div>


> [!NOTE]  
> <STRONG>Enable-enable-cstopology</STRONG>是允许 RTCUniversalServerAdmins 组成员设置和部署 Lync Server 2013 的关键 cmdlet。



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>向 RTCUniversalServerAdmins 组添加运行 Enable-CsTopology 的权限

1.  以委派用户将在其上运行 **Enable-CsTopology** 的域的 Domain Admins 组成员身份登录服务器。

2.  打开 Lync Server 2013 命令行管理程序。 Lync Server 2013 命令行管理程序将自动安装在每台前端服务器或安装了 Lync Server 2013 管理工具的任何计算机上。 有关 Lync Server 2013 命令行管理程序的详细信息，请参阅操作文档中的[Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序。

3.  从 Lync Server 2013 命令行管理程序运行以下 cmdlet：
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > 如果 OU 不是最高级别，则必须提供完整的域名。

    
    </div>
    
    在以下示例中，OU 是位于 contoso.com 域中的“Lync Servers”。
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

