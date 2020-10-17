---
title: Lync Server 2013：配置组呼叫装货
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
ms.openlocfilehash: b994415be41abe0f534f4120b2411b1f6b9beb0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517412"
---
# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="fa33d-102">在 Lync Server 2013 中配置组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="fa33d-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa33d-103">_**上次修改的主题：** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="fa33d-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="fa33d-104">Lync Server 2013 的累积更新：2月2013将组呼叫应答引入为新的企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="fa33d-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="fa33d-105">组内呼叫应答允许用户通过拨打呼叫应答组号码来接听其他用户拨打的电话。</span><span class="sxs-lookup"><span data-stu-id="fa33d-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="fa33d-106">在部署企业语音时，会自动在前端服务器或 Standard Edition 服务器上安装和启用组呼叫应答使用的组件。</span><span class="sxs-lookup"><span data-stu-id="fa33d-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fa33d-107">但是，必须先配置组呼叫应答，然后才能供用户使用。</span><span class="sxs-lookup"><span data-stu-id="fa33d-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="fa33d-108">本部分将指导您完成组呼叫应答的配置。</span><span class="sxs-lookup"><span data-stu-id="fa33d-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fa33d-109">本部分内容</span><span class="sxs-lookup"><span data-stu-id="fa33d-109">In This Section</span></span>

[<span data-ttu-id="fa33d-110">Lync Server 2013 中的组内呼叫装货配置先决条件和用户权限</span><span class="sxs-lookup"><span data-stu-id="fa33d-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="fa33d-111">Lync Server 2013 中组呼叫应答的部署过程</span><span class="sxs-lookup"><span data-stu-id="fa33d-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="fa33d-112">在 Lync Server 2013 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="fa33d-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="fa33d-113">在 Lync Server 2013 中配置呼叫应答组号码</span><span class="sxs-lookup"><span data-stu-id="fa33d-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="fa33d-114">为 Lync Server 2013 中的用户启用组内呼叫应答并分配组号码</span><span class="sxs-lookup"><span data-stu-id="fa33d-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="fa33d-115">在 Lync Server 2013 中向用户传达组呼叫装货分配</span><span class="sxs-lookup"><span data-stu-id="fa33d-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="fa33d-116"> (可选) 在 Lync Server 2013 中验证组内呼叫应答部署</span><span class="sxs-lookup"><span data-stu-id="fa33d-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

