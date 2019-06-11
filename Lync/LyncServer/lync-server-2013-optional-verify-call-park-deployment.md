---
title: 'Lync Server 2013: (可选) 验证呼叫驻留部署'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110617bbd77da0efb8802c6aba401f2ea5075b01
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="d3aa3-102">可选在 Lync Server 2013 中验证呼叫寄存部署</span><span class="sxs-lookup"><span data-stu-id="d3aa3-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3aa3-103">_**主题上次修改时间:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="d3aa3-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="d3aa3-104">安装并配置呼叫寄存后, 您需要验证配置, 以确保停车和检索呼叫按预期工作。</span><span class="sxs-lookup"><span data-stu-id="d3aa3-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="d3aa3-105">至少必须验证以下内容：</span><span class="sxs-lookup"><span data-stu-id="d3aa3-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="d3aa3-106">呼叫已启用呼叫寄存并让用户寄存呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="d3aa3-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3aa3-107">如果在执行此测试之前已在语音策略中启用了呼叫寄存, 则离开呼叫的用户需要注销 Lync 服务器, 然后重新登录, 以便能够在转接呼叫列表中看到呼叫寄存选项。</span><span class="sxs-lookup"><span data-stu-id="d3aa3-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="d3aa3-108">拨打通道号码以取回此呼叫。</span><span class="sxs-lookup"><span data-stu-id="d3aa3-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="d3aa3-p102">寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。</span><span class="sxs-lookup"><span data-stu-id="d3aa3-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

