---
title: Lync Server 2013：授予安装程序权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 647590131702addb8363b42aaa7d49e299b63a47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授予安装程序权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-08-27_

您可使用 **Grant-CsSetupPermission** cmdlet 为指定 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 组添加读取、写入、ReadSPN 和 WriteSPN 权限。 然后，该 OU 中的 RTCUniversalServerAdmins 组的成员可以在不是 Domain Admins 组成员的情况下，在指定域中安装运行 Lync Server 2013 的服务器。

使用 **Test-CsSetupPermission** cmdlet 验证您使用 **Grant-CsSetupPermission** cmdlet 设置的权限。

可以使用 **Revoke-CsSetupPermission** cmdlet 删除您使用 **Grant-CsSetupPermission** cmdlet 授予的权限。

<div>

## <a name="to-grant-setup-permissions"></a>授予安装权限

1.  登录到要在其中授予安装程序权限的域中运行 Lync Server 2013 的计算机。 如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。
    
    如果不指定 Domain 参数，则默认值为本地域。

</div>

<div>

## <a name="to-verify-setup-permissions"></a>验证安装权限

1.  在您想要验证您使用**CsSetupPermission** cmdlet 授予的安装程序权限的域中，登录到运行 Lync Server 2013 的计算机。 如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。
    
    如果不指定 Domain 参数，则默认值为本地域。

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>撤消安装权限

1.  登录到要吊销**CsSetupPermission** cmdlet 授予的安装程序权限的域中运行 Lync Server 2013 的计算机。 如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。
    
    如果不指定 Domain 参数，则默认值为本地域。

</div>

</div>

<span> </span>

</div>

</div>

</div>

