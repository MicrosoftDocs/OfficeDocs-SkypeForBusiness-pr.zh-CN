---
title: Lync Server 2013 电话拨入式会议概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d6717f183066688fdf94d0fc83e0e662c9a6b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的电话拨入式会议概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-30_

如果贵组织的用户在外出时需要出席 Lync Server 2013 本地会议或无法访问计算机，则可以部署电话拨入式会议，以便他们可以使用公开交换电话加入会议网络（PSTN）电话。

电话拨入式会议是一项可选功能，可在部署 Lync Server 2013 会议时进行配置。 虽然电话拨入式会议使用企业语音使用的一些相同的 Lync Server 2013 组件，但即使不部署企业语音，也可以部署电话拨入式会议。

<div>


> [!NOTE]  
> 如果要部署电话拨入式会议，则必须在部署 Lync Server 2013 会议的每个池中部署它。 无需在每个池中分配访问号码，但必须在每个池中部署拨入功能。 当用户从一个池中调用访问号码以在不同的池中加入 Lync Server 2013 会议时，此要求支持所记录的名称功能。



</div>

在会议策略中，会议必须支持拨入访问。默认情况下，允许拨入访问的会议会在会议邀请中包括以下信息：

  - 用于标识会议的数字会议 ID。

  - 一个或多个 PSTN 接入号码。

  - 指向 "电话拨入式会议设置" 页的链接，其中包含访问号码及其关联语言的完整列表;用于创建、重置或取消阻止个人识别码（Pin）的位置;以及其他信息，如双音多频（DTMF）控件。

电话拨入式会议支持企业用户和匿名用户。 企业用户在其组织中具有 Active Directory 域服务凭据和 Lync Server 2013 帐户。 匿名用户在组织内不具有企业凭据。 在电话拨入式会议环境中，联盟伙伴组织中使用 PSTN 连接至会议的用户被视为匿名用户。 对于电话拨入式会议（不同于其他环境），联盟用户都未经过身份验证。

参加允许拨入访问会议的企业用户或会议主持人拨打一个会议访问号码后，系统会提示他们输入会议 ID。 如果主持人尚未参加会议，则用户可以输入其统一通信 (UC) 分机号（或完整电话号码）和 PIN，或者等待主持人准许其参加会议。 通过只输入其 PIN，会议组织者就可以以主持人身份参加会议。 前端服务器使用完整的电话号码或分机和 PIN 的组合，将企业用户唯一映射到其 Active Directory 凭据。 因此，在会议中是按名称对企业用户进行身份验证和标识的。 企业用户还可以担任由组织者预定义的会议角色。

<div>


> [!NOTE]  
> 从 office IP 手机或从 Lync Server 2013 或 Lync 2010 助理拨入的企业用户不会收到其电话号码的提示，因为它们已经过身份验证。



</div>

要参加电话拨入式会议的匿名用户拨打一个会议接入号码后，系统会提示他们输入会议 ID。还会提示未经身份验证的匿名用户记录其名称。记录的名称用于在会议中标识未经身份验证的用户。除非至少一个主持人或经过身份验证的用户已参加会议，否则不允许匿名用户参加会议，且无法向其分配预定义角色。

<div>


> [!NOTE]  
> 选择不输入其电话号码和 PIN 的企业用户未经过身份验证。系统会提示他们记录其名称，并在会议中将他们视为匿名用户。



</div>

到预定时间时，会议组织者可选择通过关闭或锁定会议来限制对会议的访问。在这种情况下，系统会请求电话拨入用户进行身份验证。如果电话拨入用户身份验证失败或选择不进行身份验证，他们会被转移到会议厅中等待，直到主持人接受或拒绝他们，或者连接超时并断开连接。他们在会议厅中等待获准加入会议时，电话拨入用户将听到音乐。一旦被允许加入会议，电话拨入用户就可以参与会议的音频部分，并可使用电话键盘执行双音多频 (DTMF) 命令。电话拨入主持人可以使用 DTMF 命令打开或关闭参与者的取消静音功能、锁定或解锁会议、允许会议厅中的人加入会议、打开或关闭进入和退出通知。主持人还可以使用 DTMF 命令允许会议厅中的每个人加入会议，从而更改会议的权限以允许随后的任何人加入会议。所有电话拨入参与者都可以使用 DTMF 命令收听帮助，收听会议名单，以及使自己静音。

电话拨入参与者（即，无论他们是否从 PSTN 拨号）在会议期间收听个人通知，例如，是否已将其静音或取消静音，是否记录会议，或者是否有人在会议厅中等待。

<div>


> [!NOTE]  
> 通过单击链接（而不是电话拨入）参加会议的与会者不会听到个人通知。



</div>

</div>

<span> </span>

</div>

</div>

</div>

