---
title: 添加前端计算机
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: 指定要添加为此池中前端服务器的每台计算机的完全限定的域名 (FQDN)。 将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。 发布拓扑后，更改 FQDN，必须删除拓扑生成器中的服务器，然后将新服务器添加到新的 FQDN 与池。 有关向拓扑添加前端池的详细信息，请参阅 Define and Configure a Front End Pool 部署文档中。
ms.openlocfilehash: 17ba2dfed9e43ab9414935fd765ad4f4469a9843
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21060883"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="1bf8b-106">添加前端计算机</span><span class="sxs-lookup"><span data-stu-id="1bf8b-106">Add Front End Machine</span></span>
 
<span data-ttu-id="1bf8b-107">指定要添加为此池中前端服务器的每台计算机的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="1bf8b-108">将计算机添加到列表中后，可以更新计算机的 FQDN 或在发布拓扑前随时将其从池中删除。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="1bf8b-109">发布拓扑后，更改 FQDN，必须删除拓扑生成器中的服务器，然后将新服务器添加到新的 FQDN 与池。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="1bf8b-110">有关向拓扑添加前端池的详细信息，请参阅部署文档中的[Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1bf8b-111">请注意，拓扑生成器指示您可以在池中具有最多 20 个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="1bf8b-112">服务器支持的最大数目为 12。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="1bf8b-113">您可以定义在结构中，其中 12 可以是活动和联机任何时候最多为 20 statefull 服务器。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span> 
  

