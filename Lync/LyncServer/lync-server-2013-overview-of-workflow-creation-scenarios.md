---
title: Lync Server 2013：工作流创建方案概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc785392c50ea0ea1babe79ca5d30b455844ecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="daea1-102">Lync Server 2013 中的工作流创建方案概述</span><span class="sxs-lookup"><span data-stu-id="daea1-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daea1-103">_**主题上次修改时间:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="daea1-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="daea1-104">创建工作流时，可以采用两种方案：</span><span class="sxs-lookup"><span data-stu-id="daea1-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="daea1-105">**管理员创建和配置工作流** — CsResponseGroupAdministrator 角色成员（或等效身份）创建和激活工作流以及工作流中的所有元素，例如代理组、队列、假日和工作时间、保持音乐等等。</span><span class="sxs-lookup"><span data-stu-id="daea1-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="daea1-p101">**管理员创建工作流，经理配置选项** — CsResponseGroupAdministrator 角色成员（或等效身份）定义主要的 SIP URI 和显示名称，分配 CsResponseGroupManager 角色的成员并选择队列和激活工作流。CsResponseGroupManager 然后可以登录，并且通过创建代理组并将组分配给队列，配置电话号码、假日和工作时间以及保持音乐等来编辑工作流的配置。</span><span class="sxs-lookup"><span data-stu-id="daea1-p101">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow. The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="daea1-p102">如果想要创建托管工作流，则需要创建活动状态的工作流。保存活动状态的托管工作流后，即可修改和停用该工作流。</span><span class="sxs-lookup"><span data-stu-id="daea1-p102">When you want to create a managed workflow, you need to create the workflow as active. After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

