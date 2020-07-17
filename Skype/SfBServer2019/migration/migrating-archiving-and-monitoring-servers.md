---
title: 迁移存档和监控服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果您在旧版环境中部署了存档服务器和监视服务器，则可以在迁移前端池后将这些服务器部署在 Skype for Business Server 2019 环境中。 但是，如果存档和监视功能对您的组织至关重要，那么在迁移之前，应在您的 Skype for business Server 2019 试点池中添加存档和监控功能，以便在迁移过程中使用该功能。
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752664"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="ee92c-104">迁移存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="ee92c-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="ee92c-105">如果您在旧版环境中部署了存档服务器和监视服务器，则可以在迁移前端池后将这些服务器部署在 Skype for Business Server 2019 环境中。</span><span class="sxs-lookup"><span data-stu-id="ee92c-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="ee92c-106">但是，如果存档和监视功能对您的组织至关重要，那么在迁移之前，应在您的 Skype for business Server 2019 试点池中添加存档和监控功能，以便在迁移过程中使用该功能。</span><span class="sxs-lookup"><span data-stu-id="ee92c-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="ee92c-107">如果迁移过程中需要存档和监控功能，应注意以下问题：</span><span class="sxs-lookup"><span data-stu-id="ee92c-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="ee92c-108">存档数据和监控数据不会移动到 Skype for Business Server 2019 部署。</span><span class="sxs-lookup"><span data-stu-id="ee92c-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="ee92c-109">在取消旧环境之前备份的数据将是旧环境中活动的历史记录。</span><span class="sxs-lookup"><span data-stu-id="ee92c-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="ee92c-110">旧版本的存档服务器和监视服务器只能与旧版前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="ee92c-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="ee92c-111">在 Skype for Business Server 2019 中，存档和监控不再是服务器角色，而是集成到 Skype for Business Server 2019 前端池的服务。</span><span class="sxs-lookup"><span data-stu-id="ee92c-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="ee92c-112">在旧版和 Skype for business Server 2019 部署共存期间，旧版本的存档服务器和监视服务器会为驻留在旧版池中的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="ee92c-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="ee92c-113">Skype for business Server 2019 中的存档和监控为驻留在 Skype for business Server 2019 池上的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="ee92c-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ee92c-114">在迁移阶段，当您仍在使用新的 Skype for business Server 2019 试点池时，旧版本的存档服务器将继续为驻留在旧版池和存档中的用户收集数据，并在 Skype for Business Server 2019 中为驻留在 Skype for business Server 2019 池中的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="ee92c-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="ee92c-115">如果将第三方存档和监控解决方案与 Skype for business Server 2019 中的存档和监控结合使用，请咨询供应商，了解何时以及如何将第三方解决方案与 Skype for business Server 2019 集成。</span><span class="sxs-lookup"><span data-stu-id="ee92c-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

