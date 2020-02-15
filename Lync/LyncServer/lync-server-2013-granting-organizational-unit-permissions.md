---
title: Lync Server 2013：授予组织单位权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 945fdfcb6b1f8e8a977bec079b920e13e932e942
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授予组织单位权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-05-14_

您可以使用**CsOuPermission** cmdlet 向指定组织单位（ou）中的对象授予权限，以便林准备创建的 RTC 通用组的成员可以在不是 Domain Admins 组成员的情况下对其进行访问。 添加到指定 OU 的权限与**CsAdDomain** cmdlet 在域准备期间添加到计算机和用户容器的权限相同。

使用**CsOuPermission** cmdlet 可以验证您使用**CsOuPermission** cmdlet 设置的权限。

您可以使用**CsOuPermission** cmdlet 删除通过使用**CsOuPermission** cmdlet 授予的权限。

<div>

## <a name="to-grant-ou-permissions"></a>授予 OU 权限

1.  登录到要在其中授予 OU 权限的域中运行 Lync Server 2013 的计算机。 如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。

</div>

<div>

## <a name="to-verify-ou-permissions"></a>验证 OU 权限

1.  在要验证您使用**CsOuPermission** cmdlet 授予的 OU 权限的域中，登录到运行 Lync Server 2013 的计算机。 如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>撤消 OU 权限

1.  登录到要撤消**CsOuPermission** cmdlet 授予的 OU 权限的域中运行 Lync Server 2013 的计算机。 如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。

</div>

</div>

<span> </span>

</div>

</div>

</div>

