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
ms.openlocfilehash: 3096c468b478da365bcfa0e38fa287a5c2ab57a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="2b6b8-102">在 Lync Server 2013 中配置组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="2b6b8-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b6b8-103">_**主题上次修改时间：** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="2b6b8-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="2b6b8-104">Lync Server 2013 的累积更新：2月2013将组呼叫挑选引入为新的企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="2b6b8-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="2b6b8-105">组呼叫分拣允许用户通过拨打呼叫装货组号码来接听另一个用户拨打的电话。</span><span class="sxs-lookup"><span data-stu-id="2b6b8-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="2b6b8-106">部署企业语音时，将在前端服务器或标准版服务器上自动安装和启用组呼叫拾取使用的组件。</span><span class="sxs-lookup"><span data-stu-id="2b6b8-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="2b6b8-107">但是，你必须先配置组呼叫挑选，然后才能供用户使用。</span><span class="sxs-lookup"><span data-stu-id="2b6b8-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="2b6b8-108">本部分将指导你完成组呼叫装货的配置。</span><span class="sxs-lookup"><span data-stu-id="2b6b8-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2b6b8-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="2b6b8-109">In This Section</span></span>

[<span data-ttu-id="2b6b8-110">组呼叫在 Lync Server 2013 中的装货配置先决条件和用户权限</span><span class="sxs-lookup"><span data-stu-id="2b6b8-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="2b6b8-111">Lync Server 2013 中的组呼叫装货的部署过程</span><span class="sxs-lookup"><span data-stu-id="2b6b8-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="2b6b8-112">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b6b8-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="2b6b8-113">在 Lync Server 2013 中配置呼叫装货组号码</span><span class="sxs-lookup"><span data-stu-id="2b6b8-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="2b6b8-114">为 Lync Server 2013 中的用户启用组呼叫装货和分配组号码</span><span class="sxs-lookup"><span data-stu-id="2b6b8-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="2b6b8-115">向 Lync Server 2013 中的用户传达组呼叫装货作业</span><span class="sxs-lookup"><span data-stu-id="2b6b8-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="2b6b8-116">可选验证 Lync Server 2013 中的组呼叫装货部署</span><span class="sxs-lookup"><span data-stu-id="2b6b8-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

