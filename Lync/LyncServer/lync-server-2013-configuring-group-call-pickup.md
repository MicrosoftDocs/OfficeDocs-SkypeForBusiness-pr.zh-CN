---
title: Lync Server 2013：配置组呼叫装货
description: Lync Server 2013：配置组呼叫装货。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff6be1ea20a98cfaf2addf32c7767940b420c5c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575908"
---
# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="fb56b-103">在 Lync Server 2013 中配置组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="fb56b-103">Configuring Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb56b-104">_**上次修改的主题：** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="fb56b-104">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="fb56b-105">Lync Server 2013 的累积更新：2月2013将组呼叫应答引入为新的企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="fb56b-105">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="fb56b-106">组内呼叫应答允许用户通过拨打呼叫应答组号码来接听其他用户拨打的电话。</span><span class="sxs-lookup"><span data-stu-id="fb56b-106">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="fb56b-107">在部署企业语音时，会自动在前端服务器或 Standard Edition 服务器上安装和启用组呼叫应答使用的组件。</span><span class="sxs-lookup"><span data-stu-id="fb56b-107">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fb56b-108">但是，必须先配置组呼叫应答，然后才能供用户使用。</span><span class="sxs-lookup"><span data-stu-id="fb56b-108">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="fb56b-109">本部分将指导您完成组呼叫应答的配置。</span><span class="sxs-lookup"><span data-stu-id="fb56b-109">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb56b-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="fb56b-110">In This Section</span></span>

[<span data-ttu-id="fb56b-111">Lync Server 2013 中的组内呼叫装货配置先决条件和用户权限</span><span class="sxs-lookup"><span data-stu-id="fb56b-111">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="fb56b-112">Lync Server 2013 中组呼叫应答的部署过程</span><span class="sxs-lookup"><span data-stu-id="fb56b-112">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="fb56b-113">在 Lync Server 2013 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="fb56b-113">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="fb56b-114">在 Lync Server 2013 中配置呼叫应答组号码</span><span class="sxs-lookup"><span data-stu-id="fb56b-114">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="fb56b-115">为 Lync Server 2013 中的用户启用组内呼叫应答并分配组号码</span><span class="sxs-lookup"><span data-stu-id="fb56b-115">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="fb56b-116">在 Lync Server 2013 中向用户传达组呼叫装货分配</span><span class="sxs-lookup"><span data-stu-id="fb56b-116">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="fb56b-117"> (可选) 在 Lync Server 2013 中验证组内呼叫应答部署</span><span class="sxs-lookup"><span data-stu-id="fb56b-117">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

