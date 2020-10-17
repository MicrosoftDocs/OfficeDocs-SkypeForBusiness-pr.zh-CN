---
title: Lync Server 2013：配置停车呼叫的电话号码扩展
description: Lync Server 2013：配置停车呼叫的电话号码扩展。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6219e04243d0c19bc37251f7d113f7ebdd09fb72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548828"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="7a2a7-103">在 Lync Server 2013 中配置停车呼叫的电话号码分机</span><span class="sxs-lookup"><span data-stu-id="7a2a7-103">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a2a7-104">_**上次修改的主题：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="7a2a7-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="7a2a7-105">呼叫寄存应用程序使用呼叫寄存通道表中的分机号码来寄存呼叫。</span><span class="sxs-lookup"><span data-stu-id="7a2a7-105">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="7a2a7-106">您需要将呼叫寄存通道表配置为您的组织为寄存呼叫保留的分机号码范围。</span><span class="sxs-lookup"><span data-stu-id="7a2a7-106">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="7a2a7-107">这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。</span><span class="sxs-lookup"><span data-stu-id="7a2a7-107">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="7a2a7-108">在其中部署和配置呼叫寄存应用程序的每个 Lync Server 池都可以有一个或多个轨道范围。</span><span class="sxs-lookup"><span data-stu-id="7a2a7-108">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="7a2a7-109">在 Lync Server 部署中，轨道范围必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="7a2a7-109">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7a2a7-110">您必须先选中语音策略中的 " <STRONG>启用呼叫寄存</STRONG> " 复选框，然后才能使用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="7a2a7-110">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="7a2a7-111">默认情况下，此选项未选中。</span><span class="sxs-lookup"><span data-stu-id="7a2a7-111">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7a2a7-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="7a2a7-112">In This Section</span></span>

  - [<span data-ttu-id="7a2a7-113">在 Lync Server 2013 中创建或修改呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="7a2a7-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="7a2a7-114">在 Lync Server 2013 中删除呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="7a2a7-114">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

