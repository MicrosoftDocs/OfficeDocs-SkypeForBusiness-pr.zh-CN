---
title: 组呼叫装货配置先决条件和用户权限
description: 组调用装货配置先决条件和用户权限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554448"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="f7eac-103">Lync Server 2013 中的组内呼叫装货配置先决条件和用户权限</span><span class="sxs-lookup"><span data-stu-id="f7eac-103">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7eac-104">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f7eac-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f7eac-105">组呼叫装货是在部署企业语音时默认安装的呼叫管理功能。</span><span class="sxs-lookup"><span data-stu-id="f7eac-105">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f7eac-106">本主题介绍在配置组内呼叫应答和执行配置任务所需的用户权限之前，您需要进行的操作。</span><span class="sxs-lookup"><span data-stu-id="f7eac-106">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="f7eac-107">本节假定您已阅读与组内呼叫应答相关的规划文档 (请参阅 [在 Lync Server 2013) 中规划组内呼叫装货](lync-server-2013-planning-for-group-call-pickup.md) 。</span><span class="sxs-lookup"><span data-stu-id="f7eac-107">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="f7eac-108">组呼叫装货配置先决条件</span><span class="sxs-lookup"><span data-stu-id="f7eac-108">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="f7eac-109">组呼叫应答需要以下组件：</span><span class="sxs-lookup"><span data-stu-id="f7eac-109">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="f7eac-110">应用程序服务</span><span class="sxs-lookup"><span data-stu-id="f7eac-110">Application service</span></span>

  - <span data-ttu-id="f7eac-111">Call Park 应用程序</span><span class="sxs-lookup"><span data-stu-id="f7eac-111">Call Park application</span></span>

<span data-ttu-id="f7eac-112">当您部署企业语音时，会自动安装这些组件。</span><span class="sxs-lookup"><span data-stu-id="f7eac-112">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="f7eac-113">组呼叫装货配置用户权限</span><span class="sxs-lookup"><span data-stu-id="f7eac-113">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="f7eac-114">您可以使用以下管理工具配置组呼叫装货：</span><span class="sxs-lookup"><span data-stu-id="f7eac-114">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="f7eac-115">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="f7eac-115">Lync Server Management Shell</span></span>

  - <span data-ttu-id="f7eac-116">SEFAUtil 资源工具包工具</span><span class="sxs-lookup"><span data-stu-id="f7eac-116">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="f7eac-117">使用 Lync Server 命令行管理程序可以在呼叫寄存通道表中创建和管理呼叫应答组。</span><span class="sxs-lookup"><span data-stu-id="f7eac-117">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="f7eac-118">使用 SEFAUtil 资源工具包工具分配呼叫应答组并为用户启用组呼叫应答，或为用户禁用组呼叫挑选。</span><span class="sxs-lookup"><span data-stu-id="f7eac-118">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="f7eac-119">配置组呼叫应答需要以下管理角色中的任何一个，具体取决于任务：</span><span class="sxs-lookup"><span data-stu-id="f7eac-119">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="f7eac-120">**CsVoiceAdministrator：** 此管理员角色可以创建、配置和管理所有与语音相关的设置和策略。</span><span class="sxs-lookup"><span data-stu-id="f7eac-120">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="f7eac-121">**CsUserAdministrator：** 此管理员角色可以为用户启用组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="f7eac-121">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="f7eac-122">此管理员角色还具有对所有语音配置的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="f7eac-122">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="f7eac-123">**CsServerAdministrator：** 此管理员角色可以管理和监视服务器和服务并对其进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="f7eac-123">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="f7eac-124">**CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator、CsServerAdministrator 和 CsUserAdministrator 的所有任务。</span><span class="sxs-lookup"><span data-stu-id="f7eac-124">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f7eac-125">有关管理权限的详细信息，请参阅规划文档中的在 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="f7eac-125">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7eac-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7eac-126">See Also</span></span>


[<span data-ttu-id="f7eac-127">在 Lync Server 2013 中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="f7eac-127">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="f7eac-128">在 Lync Server 2013 中规划呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="f7eac-128">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

