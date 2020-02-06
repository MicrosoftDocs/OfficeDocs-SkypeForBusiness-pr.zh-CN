---
title: 迁移存档和监视服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果你在旧版环境中部署了存档服务器和监视服务器，则可以在迁移前端池后在 Skype for Business Server 2019 环境中部署这些服务器。 但是，如果存档和监视功能对你的组织至关重要，则应在迁移之前将存档和监视添加到 Skype for business Server 2019 试验池，以便在迁移过程中使用该功能。
ms.openlocfilehash: 5088f4b4f72ddc083cf2868df893946561eb2469
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813450"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="a18ba-104">迁移存档和监视服务器</span><span class="sxs-lookup"><span data-stu-id="a18ba-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="a18ba-105">如果你在旧版环境中部署了存档服务器和监视服务器，则可以在迁移前端池后在 Skype for Business Server 2019 环境中部署这些服务器。</span><span class="sxs-lookup"><span data-stu-id="a18ba-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="a18ba-106">但是，如果存档和监视功能对你的组织至关重要，则应在迁移之前将存档和监视添加到 Skype for business Server 2019 试验池，以便在迁移过程中使用该功能。</span><span class="sxs-lookup"><span data-stu-id="a18ba-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="a18ba-107">如果在迁移过程中需要存档和监视功能，请记住以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="a18ba-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="a18ba-108">存档数据和监视数据不会迁移到 Skype for business Server 2019 部署。</span><span class="sxs-lookup"><span data-stu-id="a18ba-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="a18ba-109">您在取消旧版环境之前备份的数据将成为旧环境中的活动历史记录。</span><span class="sxs-lookup"><span data-stu-id="a18ba-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="a18ba-110">旧版本的存档服务器和监视服务器只能与旧版前端池关联。</span><span class="sxs-lookup"><span data-stu-id="a18ba-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="a18ba-111">在 Skype for Business Server 2019 中，存档和监控不再是服务器角色，而是集成到 Skype for business Server 2019 前端池的服务。</span><span class="sxs-lookup"><span data-stu-id="a18ba-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="a18ba-112">在旧版本和 Skype for business Server 2019 部署共存期间，旧版本的存档服务器和监视服务器会为驻留在旧版池中的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="a18ba-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="a18ba-113">Skype for business Server 2019 中的存档和监视为驻留在 Skype for business Server 2019 池中的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="a18ba-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a18ba-114">在迁移阶段，当你仍将旧式 Edge 服务器与新的 Skype for business Server 2019 试验池配合使用时，旧版本的存档服务器会继续为驻留在旧版池中的用户收集数据，并在 Skype for business 中存档服务器2019为驻留在 Skype for business Server 2019 池的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="a18ba-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="a18ba-115">如果在 Skype for business Server 2019 中结合使用第三方存档和监视解决方案，请与供应商联系，了解何时以及如何使用 Skype for business Server 2019 集成第三方解决方案。</span><span class="sxs-lookup"><span data-stu-id="a18ba-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

