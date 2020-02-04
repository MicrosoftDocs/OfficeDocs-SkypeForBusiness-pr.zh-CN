---
title: 发布拓扑选择 CMS 页面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 你可以使用拓扑生成器发布已配置的拓扑。 系统将要求你从列表中选择前端服务器或前端池将承担拥有中央管理存储的角色。 在任何给定时间，只有一个前端服务器或前端池可以持有此角色。
ms.openlocfilehash: 9cecdc170934f7359597484e56299e2fe76499b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701667"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="e33c3-105">发布拓扑选择 CMS 页面</span><span class="sxs-lookup"><span data-stu-id="e33c3-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="e33c3-106">你可以使用拓扑生成器发布已配置的拓扑。</span><span class="sxs-lookup"><span data-stu-id="e33c3-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="e33c3-107">系统将要求你从列表中选择前端服务器或前端池将承担拥有中央管理存储的角色。</span><span class="sxs-lookup"><span data-stu-id="e33c3-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="e33c3-108">在任何给定时间，只有一个前端服务器或前端池可以持有此角色。</span><span class="sxs-lookup"><span data-stu-id="e33c3-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="e33c3-109">关于中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="e33c3-109">About the Central Management Server</span></span>
<span data-ttu-id="e33c3-110">中央管理服务器是单个主/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。</span><span class="sxs-lookup"><span data-stu-id="e33c3-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="e33c3-111">拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）在安装期间，在计算机上安装了 SQL Server 数据库中的中央管理存储数据的只读副本（默认情况下称为 RTCLOCAL）。部署.</span><span class="sxs-lookup"><span data-stu-id="e33c3-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="e33c3-112">本地数据库通过在所有计算机上作为服务运行的 Lync Server 副本复制程序代理来接收副本更新。</span><span class="sxs-lookup"><span data-stu-id="e33c3-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="e33c3-113">中央管理服务器和本地副本上的实际数据库的名称是 XDS，它由 XDS 和 XDS 文件组成。</span><span class="sxs-lookup"><span data-stu-id="e33c3-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="e33c3-114">Master 数据库位置由 Active Directory 域服务中的服务控制点（SCP）引用。</span><span class="sxs-lookup"><span data-stu-id="e33c3-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="e33c3-115">使用 "中央管理" 服务器管理和配置 Lync 服务器的所有工具均使用 SCP 查找中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="e33c3-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e33c3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e33c3-116">See also</span></span>

[<span data-ttu-id="e33c3-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="e33c3-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
