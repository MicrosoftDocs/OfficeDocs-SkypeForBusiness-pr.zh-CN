---
title: 'Lync Server 2013: 管理呼叫寄存'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Call Park
ms:assetid: 9554cdf6-8e7c-48c8-94dd-f28e2befefdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688140(v=OCS.15)
ms:contentKeyID: 49733740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30a92ef7f6f3cba14577e50f33fd1215f94711bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-park-in-lync-server-2013"></a><span data-ttu-id="3e917-102">在 Lync Server 2013 中管理呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="3e917-102">Managing Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e917-103">_**主题上次修改时间:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="3e917-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="3e917-104">"呼叫驻留" 应用程序使企业语音用户可以通过一条电话将呼叫置于保持状态, 然后稍后通过任何电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="3e917-104">The Call Park application enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later from any telephone.</span></span> <span data-ttu-id="3e917-105">当用户公园呼叫时, Lync 服务器将呼叫转移到一个名为 "*轨道*" 的临时号码上, 呼叫将一直保持, 直到有人检索它或超时。</span><span class="sxs-lookup"><span data-stu-id="3e917-105">When the user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until someone retrieves it or it times out.</span></span>

<span data-ttu-id="3e917-106">本节中的主题提供了可执行的任务的分步过程, 可用于自定义和维护部署中的调用寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e917-106">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Call Park application in your deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3e917-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="3e917-107">In This Section</span></span>

  - [<span data-ttu-id="3e917-108">在 Lync Server 2013 中配置停车通话的电话号码扩展</span><span class="sxs-lookup"><span data-stu-id="3e917-108">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

  - [<span data-ttu-id="3e917-109">在 Lync Server 2013 中配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="3e917-109">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="3e917-110">在 Lync Server 2013 中自定义呼叫寄存音乐处于暂停状态</span><span class="sxs-lookup"><span data-stu-id="3e917-110">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="3e917-111">在 Lync Server 2013 中灾难恢复期间管理呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="3e917-111">Manage Call Park during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-call-park-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

