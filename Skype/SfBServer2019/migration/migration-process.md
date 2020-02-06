---
title: 迁移过程
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
description: Skype for business Server 2019 的推荐和支持的迁移过程是并行迁移。 本主题介绍了应使用并行迁移的原因，还包括有关共存测试的信息。
ms.openlocfilehash: 7d8ce6513535871939894092850ad0526b1b6a63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813410"
---
# <a name="migration-process"></a><span data-ttu-id="99f1f-104">迁移过程</span><span class="sxs-lookup"><span data-stu-id="99f1f-104">Migration process</span></span>

<span data-ttu-id="99f1f-105">Skype for business Server 2019 的推荐和支持的迁移过程是并行迁移。</span><span class="sxs-lookup"><span data-stu-id="99f1f-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="99f1f-106">本主题介绍了应使用并行迁移的原因，还包括有关共存测试的信息。</span><span class="sxs-lookup"><span data-stu-id="99f1f-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="99f1f-107">并行迁移</span><span class="sxs-lookup"><span data-stu-id="99f1f-107">Side-By-Side Migration</span></span>

<span data-ttu-id="99f1f-108">在几乎所有迁移中，都应使用并行迁移路径。</span><span class="sxs-lookup"><span data-stu-id="99f1f-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="99f1f-109">在并行迁移中，你可以使用 Skype for Business Server 2019 与运行早期版本的相应服务器一起部署新的服务器，然后将操作转移到新服务器。</span><span class="sxs-lookup"><span data-stu-id="99f1f-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="99f1f-110">如果需要回滚到以前的版本，你只能将操作转移回原始服务器。</span><span class="sxs-lookup"><span data-stu-id="99f1f-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="99f1f-111">请注意，在这种情况下，使用升级的客户安排的新会议将不起作用，并且客户端也需要降级。</span><span class="sxs-lookup"><span data-stu-id="99f1f-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="99f1f-112">共存测试</span><span class="sxs-lookup"><span data-stu-id="99f1f-112">Coexistence Testing</span></span>

<span data-ttu-id="99f1f-113">在与早期版本并行部署了 Skype for Business Server 2019 后，部署表示 Skype for Business Server 2019 和早期版本的共存测试状态。</span><span class="sxs-lookup"><span data-stu-id="99f1f-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="99f1f-114">在此状态下，测试和确保服务已启动、可管理每个网站，并且客户端可以与当前用户和旧版用户进行通信非常重要。</span><span class="sxs-lookup"><span data-stu-id="99f1f-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="99f1f-115">在迁移所有用户之前，了解每个部署的状态非常重要，并确保每个部署都能正常运行。</span><span class="sxs-lookup"><span data-stu-id="99f1f-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="99f1f-116">通常，共存测试阶段存在于 Skype for business Server 2019 的试点测试中。</span><span class="sxs-lookup"><span data-stu-id="99f1f-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="99f1f-117">旧版用户在一段时间内被移动到 Skype for Business 服务器2019，以确保应用程序兼容性和功能和功能正常工作。</span><span class="sxs-lookup"><span data-stu-id="99f1f-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="99f1f-118">试点测试后，用户和应用程序将移动到 Skype for Business Server 2019 的生产版本，并且旧版本的旧池和应用程序将被停用。</span><span class="sxs-lookup"><span data-stu-id="99f1f-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
