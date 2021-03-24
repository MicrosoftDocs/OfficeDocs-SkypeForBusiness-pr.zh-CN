---
title: 发布拓扑选择 CMS 页面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 发布已使用拓扑生成器配置的拓扑。 要求您从将承担中央管理存储角色的前端服务器或前端池列表中选择该列表。 在任何给定时间，只有一个前端服务器或前端池可以保留此角色。
ms.openlocfilehash: fe3e7ed8c0a58b0547ede0eb02f0ea476bce94bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096878"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="2dcd0-105">发布拓扑选择 CMS 页面</span><span class="sxs-lookup"><span data-stu-id="2dcd0-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="2dcd0-106">发布已使用拓扑生成器配置的拓扑。</span><span class="sxs-lookup"><span data-stu-id="2dcd0-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="2dcd0-107">要求您从将承担中央管理存储角色的前端服务器或前端池列表中选择该列表。</span><span class="sxs-lookup"><span data-stu-id="2dcd0-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="2dcd0-108">在任何给定时间，只有一个前端服务器或前端池可以保留此角色。</span><span class="sxs-lookup"><span data-stu-id="2dcd0-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="2dcd0-109">关于中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="2dcd0-109">About the Central Management Server</span></span>
<span data-ttu-id="2dcd0-110">中央管理服务器是单一主副本/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。</span><span class="sxs-lookup"><span data-stu-id="2dcd0-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="2dcd0-111">拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）在 SQL Server 数据库 (中具有中央管理存储数据的只读副本，默认情况下，) 在安装和部署过程中安装在该计算机上。</span><span class="sxs-lookup"><span data-stu-id="2dcd0-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="2dcd0-112">本地数据库通过作为服务在所有计算机上运行的 Lync Server 副本复制程序代理接收副本更新。</span><span class="sxs-lookup"><span data-stu-id="2dcd0-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="2dcd0-113">中央管理服务器上实际数据库和本地副本的名称为 XDS，它由 xds.mdf 和 xds.ldf 文件决定。</span><span class="sxs-lookup"><span data-stu-id="2dcd0-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="2dcd0-114">主数据库位置由 Active Directory 域服务中 SCP (服务) 引用。</span><span class="sxs-lookup"><span data-stu-id="2dcd0-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="2dcd0-115">使用中央管理服务器管理和配置 Lync Server 的所有工具都使用 SCP 查找中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="2dcd0-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2dcd0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2dcd0-116">See also</span></span>

[<span data-ttu-id="2dcd0-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="2dcd0-117">Move-CsManagementServer</span></span>](/powershell/module/skype/move-csmanagementserver?view=skype-ps)