---
title: Lync Server 2013：授予权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20679f910ead1f1b7cab45fde658b38233c644f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授予权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-15_

对于安装程序，可以为特定 Active Directory 组织单位（OU）授予对 RTCUniversalServerAdmins 通用组的权限，从而使该 OU 中的 RTCUniversalServerAdmins 组成员能够在指定的域中安装 Lync Server 2013。 为 OU 授予权限时，授予的权限包括：

  - 读取

  - 写入

  - ReadSPN

  - WriteSPN

对于管理，可将权限添加到指定 OU 以便林准备过程创建的 RTC 通用组成员可以访问 OU，而不必是 Domain Admins 组成员。 添加到指定 OU 的权限与 **Enable-CsAdDomain** cmdlet 添加到计算机和用户 OU 容器的权限相同。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中授予安装程序权限](lync-server-2013-granting-setup-permissions.md)

  - [在 Lync Server 2013 中授予组织单位权限](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

