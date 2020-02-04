---
title: Lync Server 2013：委派安装权限
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
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Lync Server 2013 中的委派安装权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-05_

如果你不想向正在部署 lync server 2013 的用户或组授予域管理员组成员身份，你可以启用 RTCUniversalServerAdmins 组的成员在运行 Lync server 2013 的服务器上运行**enable-CsTopology** Windows PowerShell cmdlet。 默认情况下，RTCUniversalServerAdmins 组的成员不具备运行此 cmdlet 的能力。 通过使用**CsSetupPermission** cmdlet 授予管理员权限，在运行 lync server 的服务器上运行**CsTopology** ，并指定运行 lync server 2013 的服务器的计算机对象所在的组织单位（OU）。

安装 Lync Server 时进行的域准备不会自动添加允许 RTCUniversalServerAdmins 组成员运行 Enable-CsTopology cmdlet 的权限。 这意味着，默认情况下，您必须是域管理员才能启用拓扑。 若要为 RTCUniversalServerAdmins 组的成员授予启用拓扑的权限，您必须运行 CsSetupPermissions cmdlet。 此外，你将需要针对驻留运行 Lync Server 的计算机的每个 Active Directory 容器运行此 cmdlet。

请记住，此 cmdlet 仅向 RTCUniversalServerAdmins 组授予权限;该 cmdlet 不能用于向其他安全组或单个用户授予权限。

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG>是允许 RTCUniversalServerAdmins 组成员设置和部署 Lync Server 2013 的关键 cmdlet。



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>添加对 RTCUniversalServerAdmins 组运行 Enable-CsTopology 的能力

1.  以委派用户将在其上运行的域的域管理员组的成员身份登录到服务器 **-CsTopology**。

2.  打开 Lync Server 2013 命令行管理程序。 Lync Server 2013 命令行管理程序自动安装在每个前端服务器或安装了 Lync Server 2013 管理工具的任何计算机上。 有关 Lync Server 2013 命令行管理程序的详细信息，请参阅操作文档中的[Lync server 2013 管理外壳](lync-server-2013-lync-server-management-shell.md)。

3.  从 Lync Server 2013 命令行管理程序运行以下 cmdlet：
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > 如果 OU 不在顶层，则必须提供完整的域名。

    
    </div>
    
    在以下示例中，OU 是 "Lync 服务器"，它位于 contoso.com 域中。
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

