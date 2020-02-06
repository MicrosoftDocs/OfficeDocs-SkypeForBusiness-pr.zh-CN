---
title: 添加前端机器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: 指定要添加为此池中的前端服务器的每台计算机的完全限定的域名（FQDN）。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后，更改 FQDN 需要先在拓扑生成器中删除服务器，然后使用新的 FQDN 将新服务器添加到池中。 有关将前端池添加到拓扑的详细信息，请参阅在部署文档中定义和配置前端池。
ms.openlocfilehash: 7c97a0f1d1b22bd79e1ac234ba419a919b9067b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820864"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="6270a-106">添加前端机器</span><span class="sxs-lookup"><span data-stu-id="6270a-106">Add Front End Machine</span></span>

<span data-ttu-id="6270a-107">指定要添加为此池中的前端服务器的每台计算机的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="6270a-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="6270a-108">将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。</span><span class="sxs-lookup"><span data-stu-id="6270a-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="6270a-109">发布拓扑后，更改 FQDN 需要先在拓扑生成器中删除服务器，然后使用新的 FQDN 将新服务器添加到池中。</span><span class="sxs-lookup"><span data-stu-id="6270a-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="6270a-110">有关将前端池添加到拓扑的详细信息，请参阅在部署文档中[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6270a-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6270a-111">请注意，拓扑生成器指示池中最多可以有20个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="6270a-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="6270a-112">支持的最大服务器数为12。</span><span class="sxs-lookup"><span data-stu-id="6270a-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="6270a-113">结构中最多可以有20个 statefull 服务器，其中12个服务器在任何时间都处于活动状态且处于联机状态。</span><span class="sxs-lookup"><span data-stu-id="6270a-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


