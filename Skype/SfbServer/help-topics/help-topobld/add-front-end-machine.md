---
title: 添加前端计算机
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: 指定在该池中要添加为前端服务器的每台计算机的完全限定域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后，更改 FQDN 要求在拓扑生成器中删除相应的服务器，然后向池中添加具有新 FQDN 的新服务器。 有关向拓扑中添加前端池的详细信息，请参阅部署文档中的定义和配置前端池。
ms.openlocfilehash: 4582aa09527dbc2e663dd6986772b5e88f980a0f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800143"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="8c2a0-106">添加前端计算机</span><span class="sxs-lookup"><span data-stu-id="8c2a0-106">Add Front End Machine</span></span>

<span data-ttu-id="8c2a0-107">指定在该池中要添加为前端服务器的每台计算机的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="8c2a0-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="8c2a0-108">将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。</span><span class="sxs-lookup"><span data-stu-id="8c2a0-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="8c2a0-109">发布拓扑后，更改 FQDN 要求在拓扑生成器中删除相应的服务器，然后向池中添加具有新 FQDN 的新服务器。</span><span class="sxs-lookup"><span data-stu-id="8c2a0-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="8c2a0-110">有关向拓扑中添加前端池的详细信息，请参阅部署文档中的[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8c2a0-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c2a0-111">请注意，拓扑生成器指示池中可以有最多 20 台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="8c2a0-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="8c2a0-112">支持的最大服务器数为 12。</span><span class="sxs-lookup"><span data-stu-id="8c2a0-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="8c2a0-113">您可以在结构中定义最多 20 个状态服务器，其中 12 个服务器可同时处于活动状态和联机。</span><span class="sxs-lookup"><span data-stu-id="8c2a0-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


