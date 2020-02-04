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
ms.openlocfilehash: ccfdf804fc9052ac69b383d0f8cd3321222e79a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授予权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-15_

对于设置，你可以向特定 Active Directory 组织单位（OU）的 RTCUniversalServerAdmins 通用组授予权限，从而允许该 OU 中的 RTCUniversalServerAdmins 组成员在指定域中安装 Lync Server 2013。 为 OU 授予权限时，授予以下权限：

  - 继续

  - 记录

  - ReadSPN

  - WriteSPN

对于 "管理"，你可以向指定的 Ou 添加权限，以便林准备创建的 RTC 通用组的成员可以访问 Ou，而无需成为域管理员组的成员。 添加到指定 OU 的权限与**Enable CsAdDomain** cmdlet 添加到计算机和用户 OU 容器的权限相同。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中授予安装权限](lync-server-2013-granting-setup-permissions.md)

  - [在 Lync Server 2013 中授予组织单位权限](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

