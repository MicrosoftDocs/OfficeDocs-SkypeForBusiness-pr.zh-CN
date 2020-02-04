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
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授予组织单位权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-05-14_

你可以使用**CsOuPermission** cmdlet 向指定组织单位（ou）中的对象授予权限，以便林准备创建的 RTC 通用组的成员可以访问它们，而不是域管理员组的成员。 添加到指定 OU 的权限与**Enable-CsAdDomain** cmdlet 在域准备期间添加到计算机和用户容器的权限相同。

使用**CsOuPermission** cmdlet 验证你通过使用**CsOuPermission** cmdlet 设置的权限。

你可以使用**CsOuPermission** cmdlet 删除你使用**CsOuPermission** cmdlet 授予的权限。

<div>

## <a name="to-grant-ou-permissions"></a>授予 OU 权限

1.  在要向其授予 OU 权限的域中登录到运行 Lync Server 2013 的计算机。 如果 OU 位于不同的子域中，请使用作为域管理员组成员或企业管理员组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。

</div>

<div>

## <a name="to-verify-ou-permissions"></a>验证 OU 权限

1.  在要验证你使用**CsOuPermission** cmdlet 授予的 OU 权限的域中，登录到运行 Lync Server 2013 的计算机。 如果 OU 位于不同的子域中，请使用作为域管理员组成员或企业管理员组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>撤消 OU 权限

1.  在要吊销**CsOuPermission** cmdlet 授予的 OU 权限的域中，登录到运行 Lync Server 2013 的计算机。 如果 OU 位于不同的子域中，请使用作为域管理员组成员或企业管理员组成员的帐户。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。

</div>

</div>

<span> </span>

</div>

</div>

</div>

