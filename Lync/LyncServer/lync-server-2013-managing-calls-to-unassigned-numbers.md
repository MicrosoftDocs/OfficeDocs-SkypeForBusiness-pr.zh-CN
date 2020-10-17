---
title: Lync Server 2013：管理对未分配号码的呼叫
description: Lync Server 2013：管理对未分配号码的呼叫。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a91c1ec30ea1e942fa3ea27fbcd369572884a52a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569148"
---
# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="17545-103">在 Lync Server 2013 中管理对未分配号码的呼叫</span><span class="sxs-lookup"><span data-stu-id="17545-103">Managing calls to unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17545-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="17545-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="17545-105">Lync Server 允许您配置在拨入的电话号码对您的组织有效但未分配给用户或电话时对传入电话呼叫的处理。</span><span class="sxs-lookup"><span data-stu-id="17545-105">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="17545-106">您可以使用通知应用程序将这些呼叫转移到预先确定的目标 (电话号码、SIP URI 或语音邮件) 或播放音频通知，或同时进行这两种工作。</span><span class="sxs-lookup"><span data-stu-id="17545-106">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="17545-107">您也可以将这些呼叫转接到 Exchange UM 自动助理电话号码。</span><span class="sxs-lookup"><span data-stu-id="17545-107">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="17545-108">通过其中一种方式处理对未分配的号码的呼叫，可有助于避免呼叫者拨错号并听到忙音或 SIP 客户端收到错误消息的情况。</span><span class="sxs-lookup"><span data-stu-id="17545-108">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="17545-p102">本节介绍如何管理未分配的号码范围以处理对未分配的电话号码的呼叫。此外还介绍如何在灾难恢复过程中管理通知（如果您想要在中断期间使用此功能）。</span><span class="sxs-lookup"><span data-stu-id="17545-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17545-111">在中断期间使用未分配的号码处理是可选的。</span><span class="sxs-lookup"><span data-stu-id="17545-111">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="17545-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="17545-112">In This Section</span></span>

  - [<span data-ttu-id="17545-113">在 Lync Server 2013 中创建通知</span><span class="sxs-lookup"><span data-stu-id="17545-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="17545-114">在 Lync Server 2013 中配置未分配的电话号码</span><span class="sxs-lookup"><span data-stu-id="17545-114">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="17545-115">在 Lync Server 2013 中管理灾难恢复期间的通知</span><span class="sxs-lookup"><span data-stu-id="17545-115">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

