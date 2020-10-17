---
title: Lync Server 2013：委派安装程序权限
description: Lync Server 2013：委派安装程序权限。
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
ms.openlocfilehash: a7038cf729bad459dbcd2a84a308b14aa56b68dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545338"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中委派安装程序权限

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

如果您不想向正在部署 Lync Server 2013 的用户或组授予 Domain Admins 组成员身份，则可以启用 RTCUniversalServerAdmins 组的成员，以便**Enable-CsTopology**   在运行 Lync server 2013 的服务器上运行 enable-cstopology Windows PowerShell cmdlet。 默认情况下，RTCUniversalServerAdmins 组的成员无法运行此 cmdlet。 在运行 Lync Server 的服务器上，通过使用**CsSetupPermission** cmdlet 并指定 () OU 中运行 lync server 2013 的计算机对象所在的组织单位授予管理员权限，以在运行 lync server 的服务器上运行**Enable-enable-cstopology** 。

在安装 Lync Server 时进行的域准备工作不会自动添加允许 RTCUniversalServerAdmins 组成员运行 Enable-CsTopology cmdlet 的权限。 这意味着，默认情况下，只有域管理员才能启用拓扑。 要授予 RTCUniversalServerAdmins 组的成员启用拓扑的权限，必须运行 Grant-CsSetupPermissions cmdlet。 此外，还需要对驻留运行 Lync Server 的计算机的每个 Active Directory 容器运行此 cmdlet。

请记住，此 cmdlet 仅向 RTCUniversalServerAdmins 组授予权限；此 cmdlet 不能用于向其他安全组或向单个用户授予权限。

<div>


> [!NOTE]  
> <STRONG>Enable-enable-cstopology</STRONG> 是允许 RTCUniversalServerAdmins 组成员设置和部署 Lync Server 2013 的关键 cmdlet。



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>向 RTCUniversalServerAdmins 组添加运行 Enable-CsTopology 的权限

1.  以委派用户将在其上运行 **Enable-CsTopology** 的域的 Domain Admins 组成员身份登录服务器。

2.  打开 Lync Server 2013 命令行管理程序。 Lync Server 2013 命令行管理程序将自动安装在每台前端服务器或安装了 Lync Server 2013 管理工具的任何计算机上。 有关 Lync Server 2013 命令行管理程序的详细信息，请参阅操作文档中的 [Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md) 程序。

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

