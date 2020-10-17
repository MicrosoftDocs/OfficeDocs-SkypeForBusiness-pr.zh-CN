---
title: Lync Server 2013：管理呼叫寄存
description: Lync Server 2013：管理呼叫寄存。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Call Park
ms:assetid: 9554cdf6-8e7c-48c8-94dd-f28e2befefdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688140(v=OCS.15)
ms:contentKeyID: 49733740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6540cc6d4df06b3eaadd78dce8fe01990928045a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569158"
---
# <a name="managing-call-park-in-lync-server-2013"></a><span data-ttu-id="a37b3-103">在 Lync Server 2013 中管理呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="a37b3-103">Managing Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a37b3-104">_**上次修改的主题：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="a37b3-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="a37b3-105">呼叫寄存应用程序允许企业语音用户将呼叫置于保持状态，然后从任何电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="a37b3-105">The Call Park application enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later from any telephone.</span></span> <span data-ttu-id="a37b3-106">当用户公园某个呼叫时，Lync Server 会将呼叫转移到一个临时号码（称为 " *轨道*"），其中呼叫将一直保留，直到有人将其检索或超时。</span><span class="sxs-lookup"><span data-stu-id="a37b3-106">When the user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until someone retrieves it or it times out.</span></span>

<span data-ttu-id="a37b3-107">本节中的主题提供了可执行的任务的分步过程，可用于在部署中自定义和维护呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="a37b3-107">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Call Park application in your deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a37b3-108">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a37b3-108">In This Section</span></span>

  - [<span data-ttu-id="a37b3-109">在 Lync Server 2013 中配置停车呼叫的电话号码分机</span><span class="sxs-lookup"><span data-stu-id="a37b3-109">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

  - [<span data-ttu-id="a37b3-110">在 Lync Server 2013 中配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="a37b3-110">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="a37b3-111">在 Lync Server 2013 中自定义呼叫寄存暂停音乐</span><span class="sxs-lookup"><span data-stu-id="a37b3-111">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="a37b3-112">在 Lync Server 2013 中的灾难恢复期间管理呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="a37b3-112">Manage Call Park during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-call-park-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

