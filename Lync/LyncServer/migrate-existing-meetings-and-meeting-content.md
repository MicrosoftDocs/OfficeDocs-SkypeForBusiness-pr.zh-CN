---
title: 迁移现有会议和会议内容
description: 迁移现有会议和会议内容。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94dd35063a121a057a218c27fdb36e42a155b77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579308"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="c1534-103">迁移现有会议和会议内容</span><span class="sxs-lookup"><span data-stu-id="c1534-103">Migrate existing meetings and meeting content</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1534-104">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c1534-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c1534-105">将用户帐户从 Lync Server 2010 移动到 Lync Server 2013 服务器时，将使用该用户帐户移动以下信息：</span><span class="sxs-lookup"><span data-stu-id="c1534-105">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="c1534-p101">**用户已安排的会议**。这包括移动会议目录和会议数据。</span><span class="sxs-lookup"><span data-stu-id="c1534-p101">**Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="c1534-p102">**用户的个人标识号 (PIN)**。用户的当前 PIN 在到期或用户请求新 PIN 之前仍然有效。</span><span class="sxs-lookup"><span data-stu-id="c1534-p102">**User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="c1534-110">以下用户帐户信息不会移至新服务器。</span><span class="sxs-lookup"><span data-stu-id="c1534-110">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="c1534-p103">**会议内容**。若要移动在会议期间共享的内容（例如 PowerPoint、白板、附件或投票数据），请使用 **-MoveConferenceData** 参数作为 **Move-CsUser** cmdlet 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c1534-p103">**Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

