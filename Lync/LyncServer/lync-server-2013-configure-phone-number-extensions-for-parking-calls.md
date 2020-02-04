---
title: Lync Server 2013：配置停车通话的电话号码扩展
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
ms.openlocfilehash: ba64f4f622a6f9ae9e134b2447abe21bc99ec62c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="7bd96-102">在 Lync Server 2013 中配置停车通话的电话号码扩展</span><span class="sxs-lookup"><span data-stu-id="7bd96-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bd96-103">_**主题上次修改时间：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="7bd96-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="7bd96-104">呼叫驻留应用程序将 "呼叫驻留" 轨道表中的分机号码用于寄存呼叫。</span><span class="sxs-lookup"><span data-stu-id="7bd96-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="7bd96-105">您需要配置 "呼叫驻留" 轨道表，其中包含您的组织为寄存通话保留的分机号码范围。</span><span class="sxs-lookup"><span data-stu-id="7bd96-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="7bd96-106">这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。</span><span class="sxs-lookup"><span data-stu-id="7bd96-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="7bd96-107">在其中部署和配置呼叫驻留应用程序的每个 Lync 服务器池都可以有一个或多个轨道范围。</span><span class="sxs-lookup"><span data-stu-id="7bd96-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="7bd96-108">在 Lync 服务器部署中，轨道范围必须全局唯一。</span><span class="sxs-lookup"><span data-stu-id="7bd96-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7bd96-109">您必须先选中语音策略中的 "<STRONG>启用呼叫驻留</STRONG>" 复选框，然后才能使用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="7bd96-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="7bd96-110">默认情况下，此选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="7bd96-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7bd96-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="7bd96-111">In This Section</span></span>

  - [<span data-ttu-id="7bd96-112">在 Lync Server 2013 中创建或修改呼叫寄存的轨道范围</span><span class="sxs-lookup"><span data-stu-id="7bd96-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="7bd96-113">在 Lync Server 2013 中删除呼叫寄存轨道范围</span><span class="sxs-lookup"><span data-stu-id="7bd96-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

