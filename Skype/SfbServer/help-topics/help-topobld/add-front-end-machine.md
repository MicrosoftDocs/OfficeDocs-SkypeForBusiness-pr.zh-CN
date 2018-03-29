---
title: 添加前端机
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: 指定您想要添加作为前端服务器在此池中的每台计算机的完全限定的域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑之后，更改 FQDN 需要删除拓扑生成器中的服务器，然后将新服务器添加到具有新的 FQDN 的池。 有关添加到拓扑结构中的前端池的详细信息，请参阅定义和配置部署文档中前结束池。
ms.openlocfilehash: f4d8b197592a68cd3d19ba1bc2741b9f4743d19c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-machine"></a><span data-ttu-id="4689f-106">添加前端机</span><span class="sxs-lookup"><span data-stu-id="4689f-106">Add Front End Machine</span></span>
 
<span data-ttu-id="4689f-107">指定您想要添加作为前端服务器在此池中的每台计算机的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="4689f-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="4689f-108">将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。</span><span class="sxs-lookup"><span data-stu-id="4689f-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="4689f-109">发布拓扑之后，更改 FQDN 需要删除拓扑生成器中的服务器，然后将新服务器添加到具有新的 FQDN 的池。</span><span class="sxs-lookup"><span data-stu-id="4689f-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="4689f-110">有关添加到拓扑结构中的前端池的详细信息，请参阅部署文档中的[定义和配置前结束池](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4689f-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4689f-111">请注意，拓扑生成器可以在池中有最多 20 个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="4689f-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="4689f-112">服务器支持的最大数目为 12。</span><span class="sxs-lookup"><span data-stu-id="4689f-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="4689f-113">您可以定义在结构中，其中 12 可以是活动的且在线在任何一个时候最多 20 个 statefull 服务器。</span><span class="sxs-lookup"><span data-stu-id="4689f-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span> 
  

