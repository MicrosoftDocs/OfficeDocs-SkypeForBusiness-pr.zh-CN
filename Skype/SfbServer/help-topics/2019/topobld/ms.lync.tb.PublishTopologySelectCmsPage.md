---
title: 发布拓扑选择 CMS 页面
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 发布已配置使用拓扑生成器的拓扑。 您需要从前端服务器或前端池，则假定按住中央管理存储的角色的列表中选择。 只有一个前端服务器或前端池可以在任何给定时间保留此角色。
ms.openlocfilehash: 0c80fa30721fe47fc3bc4725ca4f50f8a75f7009
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873827"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="668d4-105">发布拓扑选择 CMS 页面</span><span class="sxs-lookup"><span data-stu-id="668d4-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="668d4-106">发布已配置使用拓扑生成器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="668d4-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="668d4-107">您需要从前端服务器或前端池，则假定按住中央管理存储的角色的列表中选择。</span><span class="sxs-lookup"><span data-stu-id="668d4-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="668d4-108">只有一个前端服务器或前端池可以在任何给定时间保留此角色。</span><span class="sxs-lookup"><span data-stu-id="668d4-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="668d4-109">有关中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="668d4-109">About the Central Management Server</span></span>
<span data-ttu-id="668d4-110">中央管理服务器是单个母版/多副本系统，数据库的读/写副本由前端服务器包含中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="668d4-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="668d4-111">在拓扑中，包括前端服务器包含中央管理服务器，每台计算机都安装过程中的计算机上安装 SQL Server 数据库 （名为默认情况下 RTCLOCAL） 中的中央管理存储数据的只读副本和部署。</span><span class="sxs-lookup"><span data-stu-id="668d4-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="668d4-112">本地数据库接收通过作为服务的所有计算机运行 Lync Server 副本复制程序代理的副本更新。</span><span class="sxs-lookup"><span data-stu-id="668d4-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="668d4-113">在中央管理服务器和的本地副本的实际数据库的名称为 XDS，组成 xds.mdf 和 xds.ldf 文件。</span><span class="sxs-lookup"><span data-stu-id="668d4-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="668d4-114">服务控制点 (SCP) Active Directory 域服务中被引用的主数据库位置。</span><span class="sxs-lookup"><span data-stu-id="668d4-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="668d4-115">中央管理服务器用于管理和配置 Lync Server 的所有工具都使用 SCP 查找中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="668d4-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="668d4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="668d4-116">See also</span></span>

[<span data-ttu-id="668d4-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="668d4-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
