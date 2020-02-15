---
title: Lync Server 2013：（可选）验证呼叫寄存部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05b18de4af492fb45ef37e64cca45cc2d3d2b965
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="9eaf6-102">Optional在 Lync Server 2013 中验证呼叫寄存部署</span><span class="sxs-lookup"><span data-stu-id="9eaf6-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eaf6-103">_**上次修改的主题：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="9eaf6-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="9eaf6-104">在安装和配置呼叫寄存之后，需要验证配置，以确保停车和检索呼叫按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="9eaf6-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="9eaf6-105">至少必须验证以下内容：</span><span class="sxs-lookup"><span data-stu-id="9eaf6-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="9eaf6-106">呼叫已启用呼叫寄存且用户寄存呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="9eaf6-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9eaf6-107">如果您在执行此测试之前在语音策略中启用了呼叫寄存，则寄存呼叫的用户需要注销 Lync Server，然后重新登录，才能在转移呼叫列表中查看呼叫寄存选项。</span><span class="sxs-lookup"><span data-stu-id="9eaf6-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="9eaf6-108">拨打通道号码以取回此呼叫。</span><span class="sxs-lookup"><span data-stu-id="9eaf6-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="9eaf6-p102">寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。</span><span class="sxs-lookup"><span data-stu-id="9eaf6-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

