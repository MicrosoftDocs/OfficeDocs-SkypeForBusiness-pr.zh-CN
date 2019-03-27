---
title: 迁移存档和监控服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果旧环境中部署存档服务器与监控服务器，可以在迁移前端池后在您 Skype 业务服务器 2019年环境中部署这些服务器。 但是，如果存档和监控功能对组织至关重要，应添加存档和监控业务服务器 2019年试点池您 Skype 到迁移，以便该功能，在迁移过程之前。
ms.openlocfilehash: 24dc3e3007fd9a58c23f9c15a31cccc766d45e83
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896090"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="ed1a6-104">迁移存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="ed1a6-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="ed1a6-105">如果旧环境中部署存档服务器与监控服务器，可以在迁移前端池后在您 Skype 业务服务器 2019年环境中部署这些服务器。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="ed1a6-106">但是，如果存档和监控功能对组织至关重要，应添加存档和监控业务服务器 2019年试点池您 Skype 到迁移，以便该功能，在迁移过程之前。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="ed1a6-107">如果您希望在迁移过程中的存档和监控功能，请记住以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="ed1a6-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="ed1a6-108">存档数据和监控数据不移到 Skype 业务服务器 2019年部署。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="ed1a6-109">停用旧环境之前备份的数据将旧环境中的活动的历史记录。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="ed1a6-110">存档服务器与监控服务器的旧版本可以仅与旧的前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="ed1a6-111">中的业务服务器 2019 Skype，存档和监控不再服务器角色，但集成到业务 Server 2019 前端池的 Skype 的服务。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="ed1a6-112">在时间的旧式和 Skype 业务服务器 2019年部署共存，存档服务器与监控服务器的旧版本的用户驻留在旧池上收集数据。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="ed1a6-113">存档和监控业务服务器 2019年的 Skype 中收集用户的数据的业务服务器 2019年池驻留在 Skype。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ed1a6-114">阶段的迁移后仍使用与业务服务器 2019 试点池，存档服务器的旧版本继续收集用户的数据的新 Skype 旧版边缘服务器驻留在旧池和 Skype for Business 中的存档服务器 2019年收集用户的数据的业务服务器 2019年池驻留在 Skype。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="ed1a6-115">如果您使用第三方存档和监控业务服务器 2019年与存档和监控 Skype 中的结合使用的解决方案，请咨询您供应商联系时间和方式需要与 Skype 的第三方解决方案集成的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="ed1a6-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

