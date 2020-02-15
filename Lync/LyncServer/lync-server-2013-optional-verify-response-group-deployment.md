---
title: Lync Server 2013：（可选）验证响应组部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b99d5d2f1800a4d7d16b1d3fdf4d0aab213fd0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="c9db8-102">Optional在 Lync Server 2013 中验证响应组部署</span><span class="sxs-lookup"><span data-stu-id="c9db8-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9db8-103">_**上次修改的主题：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="c9db8-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="c9db8-104">配置响应组之后，需要验证配置，以确保您的响应组按预期工作。</span><span class="sxs-lookup"><span data-stu-id="c9db8-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="c9db8-105">至少应使用以下用户类型验证以下方案：</span><span class="sxs-lookup"><span data-stu-id="c9db8-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="c9db8-106">**用户**</span><span class="sxs-lookup"><span data-stu-id="c9db8-106">**Users**</span></span>

  - <span data-ttu-id="c9db8-107">在 Lync Server 2013 上托管的用户</span><span class="sxs-lookup"><span data-stu-id="c9db8-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="c9db8-108">使用公用电话交换网 (PSTN) 的外部用户</span><span class="sxs-lookup"><span data-stu-id="c9db8-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="c9db8-109">在 Lync Server 2013 上托管的代理</span><span class="sxs-lookup"><span data-stu-id="c9db8-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="c9db8-110">**Scenarios**</span><span class="sxs-lookup"><span data-stu-id="c9db8-110">**Scenarios**</span></span>

  - <span data-ttu-id="c9db8-111">Lync Server 2013 用户呼叫响应组。</span><span class="sxs-lookup"><span data-stu-id="c9db8-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="c9db8-112">外部用户呼叫响应组。</span><span class="sxs-lookup"><span data-stu-id="c9db8-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="c9db8-113">用户在代理处理其他呼叫时呼叫响应组，并进入队列。</span><span class="sxs-lookup"><span data-stu-id="c9db8-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

