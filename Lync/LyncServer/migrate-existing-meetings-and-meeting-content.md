---
title: 迁移现有会议和会议内容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa0b83e2e206421300d16faf220b3fa0bb81503
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="a92f2-102">迁移现有会议和会议内容</span><span class="sxs-lookup"><span data-stu-id="a92f2-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a92f2-103">_**主题上次修改时间：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a92f2-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a92f2-104">当用户帐户从 Lync Server 2010 移动到 Lync Server 2013 服务器时，以下信息将与该用户帐户一起移动：</span><span class="sxs-lookup"><span data-stu-id="a92f2-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="a92f2-105">**已由用户安排的会议**。</span><span class="sxs-lookup"><span data-stu-id="a92f2-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="a92f2-106">这包括移动会议目录和会议数据。</span><span class="sxs-lookup"><span data-stu-id="a92f2-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="a92f2-107">**用户的个人识别码（PIN）**。</span><span class="sxs-lookup"><span data-stu-id="a92f2-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="a92f2-108">用户的当前 PIN 将继续工作，直到过期或用户请求新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="a92f2-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="a92f2-109">以下用户帐户信息不会移动到新服务器。</span><span class="sxs-lookup"><span data-stu-id="a92f2-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="a92f2-110">**会议内容**。</span><span class="sxs-lookup"><span data-stu-id="a92f2-110">**Meeting content**.</span></span> <span data-ttu-id="a92f2-111">为了移动在会议期间共享的内容（例如 PowerPoint、白板、附件或投票数据），请使用 **-MoveConferenceData**参数作为**move-csuser** cmdlet 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a92f2-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

