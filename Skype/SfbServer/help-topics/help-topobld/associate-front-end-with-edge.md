---
title: 将前端与边缘关联
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: 每个前端池只能有一个与之关联的边缘服务器或边缘池。 为网站启用外部用户访问时，可以为远程用户提供支持。 您还可以启用对联盟用户的支持，包括对特定公共即时消息 (IM) 连接提供程序 (（如 Windows Live) ）的用户的支持，以及对匿名用户的支持。
ms.openlocfilehash: dcef84fdf63dc03c35a33650cca7f0f7c5de5900
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103218"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="dc74a-105">将前端与边缘关联</span><span class="sxs-lookup"><span data-stu-id="dc74a-105">Associate Front End With Edge</span></span>

<span data-ttu-id="dc74a-106">每个前端池只能有一个与之关联的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="dc74a-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="dc74a-107">为网站启用外部用户访问时，可以为远程用户提供支持。</span><span class="sxs-lookup"><span data-stu-id="dc74a-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="dc74a-108">您还可以启用对联盟用户的支持，包括对特定公共即时消息 (IM) 连接提供程序 (（如 Windows Live) ）的用户的支持，以及对匿名用户的支持。</span><span class="sxs-lookup"><span data-stu-id="dc74a-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="dc74a-109">站点中的所有池和多个中央站点的池可以使用同一边缘服务器，前提是使用量不超过边缘服务器的容量。</span><span class="sxs-lookup"><span data-stu-id="dc74a-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="dc74a-110">有关监控的详细信息（包括伸缩），请参阅规划文档中的[Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)。</span><span class="sxs-lookup"><span data-stu-id="dc74a-110">For details about monitoring, including scaling, see [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) in the Planning documentation.</span></span> <span data-ttu-id="dc74a-111">有关设计支持外部用户访问的拓扑的详细信息，请参阅部署文档中的[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。</span><span class="sxs-lookup"><span data-stu-id="dc74a-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in the Deployment documentation.</span></span>