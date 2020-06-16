---
title: 迁移现有会议和会议内容
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
ms.openlocfilehash: 9d811a9e66f368752107020de48e5e09dd641115
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="ed1c1-102">迁移现有会议和会议内容</span><span class="sxs-lookup"><span data-stu-id="ed1c1-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed1c1-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ed1c1-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ed1c1-104">将用户帐户从 Lync Server 2010 移动到 Lync Server 2013 服务器时，将使用该用户帐户移动以下信息：</span><span class="sxs-lookup"><span data-stu-id="ed1c1-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="ed1c1-105">**Meetings already scheduled by the user**.</span><span class="sxs-lookup"><span data-stu-id="ed1c1-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="ed1c1-106">This includes moving the conferencing directories and conferencing data.</span><span class="sxs-lookup"><span data-stu-id="ed1c1-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="ed1c1-107">**User’s personal identification number (PIN)**.</span><span class="sxs-lookup"><span data-stu-id="ed1c1-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="ed1c1-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span><span class="sxs-lookup"><span data-stu-id="ed1c1-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="ed1c1-109">以下用户帐户信息不会移至新服务器。</span><span class="sxs-lookup"><span data-stu-id="ed1c1-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="ed1c1-110">**Meeting content**.</span><span class="sxs-lookup"><span data-stu-id="ed1c1-110">**Meeting content**.</span></span> <span data-ttu-id="ed1c1-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed1c1-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

