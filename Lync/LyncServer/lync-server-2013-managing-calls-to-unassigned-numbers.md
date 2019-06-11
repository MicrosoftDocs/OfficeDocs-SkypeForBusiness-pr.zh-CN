---
title: 'Lync Server 2013: 管理未分配号码的呼叫'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50a6c7fe05729f705bd7ea752658f7c890188159
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="9534c-102">管理 Lync Server 2013 中未分配号码的呼叫</span><span class="sxs-lookup"><span data-stu-id="9534c-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9534c-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9534c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9534c-104">Lync Server 让你可以配置当拨出的号码对你的组织有效, 但未分配给用户或电话时对传入电话呼叫的处理。</span><span class="sxs-lookup"><span data-stu-id="9534c-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="9534c-105">你可以使用公告应用程序将这些呼叫转移到预先确定的目的地 (电话号码、SIP URI 或语音邮件), 或播放音频公告, 或两者都播放。</span><span class="sxs-lookup"><span data-stu-id="9534c-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="9534c-106">您还可以将这些呼叫转移到 Exchange UM 自动助理电话号码。</span><span class="sxs-lookup"><span data-stu-id="9534c-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="9534c-107">通过以下方法之一处理对未分配号码的调用可帮助你避免呼叫者 misdials 的情况, 然后听到占线音, 或者 SIP 客户端收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="9534c-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="9534c-108">本部分介绍如何管理未分配的号码范围以处理未分配电话号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9534c-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="9534c-109">本部分还介绍了如何在中断期间需要此功能的情况下管理灾难恢复期间的公告。</span><span class="sxs-lookup"><span data-stu-id="9534c-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9534c-110">在中断期间使用未分配的号码处理是可选的。</span><span class="sxs-lookup"><span data-stu-id="9534c-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9534c-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="9534c-111">In This Section</span></span>

  - [<span data-ttu-id="9534c-112">在 Lync Server 2013 中创建公告</span><span class="sxs-lookup"><span data-stu-id="9534c-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="9534c-113">在 Lync Server 2013 中配置未分配的电话号码</span><span class="sxs-lookup"><span data-stu-id="9534c-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="9534c-114">在 Lync Server 2013 中灾难恢复期间管理通知</span><span class="sxs-lookup"><span data-stu-id="9534c-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

