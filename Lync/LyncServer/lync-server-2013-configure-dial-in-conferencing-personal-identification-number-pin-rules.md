---
title: 将电话拨入式会议个人识别码 (PIN) 规则配置
description: " (PIN) 规则配置电话拨入式会议个人识别码。"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 799092ba57e9a85cd196840fc81c1f46b96e9900
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565048"
---
# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a>在 Lync Server 2013 中配置电话拨入式会议个人标识号码 (PIN) 规则

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-19_

具有 Active Directory 域服务 (组织中的 AD DS) 凭据的 Lync Server 2013 用户可以通过使用 (PIN) 的个人标识号将电话拨入式会议作为经过身份验证的用户加入。 PIN 策略定义电话拨入式会议 PIN 工作方式的规则。

如果要将特定策略应用于某个站点或某个用户组，可以创建新的 PIN 策略。如果要在整个组织中使用相同的 PIN 策略，则可以使用全局 PIN 策略并根据需要对其进行修改。PIN 策略既可以应用于少数用户，也可以应用于众多用户。如果为用户分配用户级别的 PIN 策略，则优先应用这些设置。如果没有分配用户策略，则将应用站点级别的 PIN 策略（如果存在）。如果未应用用户策略或站点策略，则全局 PIN 策略会提供默认设置。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中修改默认电话拨入式会议 PIN 设置](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [在 Lync Server 2013 中为一个站点或一组用户创建或修改电话拨入式会议 PIN 设置](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [删除 Lync Server 2013 中某一网站或一组用户的电话拨入式会议 PIN 设置](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

