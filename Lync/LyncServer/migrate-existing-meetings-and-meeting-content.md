---
title: 迁移现有会议和会议内容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38b4f374aef66fa95d49b2330a07f9def4135328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a>迁移现有会议和会议内容

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-22_

当用户帐户从 Lync Server 2010 移动到 Lync Server 2013 服务器时, 以下信息将与该用户帐户一起移动:

  - **已由用户安排的会议**。 这包括移动会议目录和会议数据。

  - **用户的个人识别码 (PIN)**。 用户的当前 PIN 将继续工作, 直到过期或用户请求新的 PIN。

以下用户帐户信息不会移动到新服务器。

  - **会议内容**。 为了移动在会议期间共享的内容 (例如 PowerPoint、白板、附件或投票数据), 请使用 **-MoveConferenceData**参数作为**move-csuser** cmdlet 的一部分。

</div>

<span> </span>

</div>

</div>

</div>

