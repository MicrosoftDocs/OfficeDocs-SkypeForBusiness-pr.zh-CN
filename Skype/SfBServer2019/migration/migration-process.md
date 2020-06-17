---
title: 迁移过程
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
description: Skype for Business Server 2019 的推荐和受支持的迁移过程是并行迁移。 本主题介绍为什么应使用并行迁移，并包括有关共存测试的信息。
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752634"
---
# <a name="migration-process"></a><span data-ttu-id="ab270-104">迁移过程</span><span class="sxs-lookup"><span data-stu-id="ab270-104">Migration process</span></span>

<span data-ttu-id="ab270-105">Skype for Business Server 2019 的推荐和受支持的迁移过程是并行迁移。</span><span class="sxs-lookup"><span data-stu-id="ab270-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="ab270-106">本主题介绍为什么应使用并行迁移，并包括有关共存测试的信息。</span><span class="sxs-lookup"><span data-stu-id="ab270-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="ab270-107">并行迁移</span><span class="sxs-lookup"><span data-stu-id="ab270-107">Side-By-Side Migration</span></span>

<span data-ttu-id="ab270-108">在几乎每个迁移中，都应该使用并行迁移路径。</span><span class="sxs-lookup"><span data-stu-id="ab270-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="ab270-109">在并行迁移中，使用 Skype for Business Server 2019 和运行早期版本的相应服务器一起部署新的服务器，然后将操作转移到新服务器。</span><span class="sxs-lookup"><span data-stu-id="ab270-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="ab270-110">如果有必要回滚到以前的版本，则只需将操作转移回原始服务器。</span><span class="sxs-lookup"><span data-stu-id="ab270-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="ab270-111">请注意，在此情况下，使用升级的客户端安排的任何新会议将不会工作，并且客户端也将需要降级。</span><span class="sxs-lookup"><span data-stu-id="ab270-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="ab270-112">共存测试</span><span class="sxs-lookup"><span data-stu-id="ab270-112">Coexistence Testing</span></span>

<span data-ttu-id="ab270-113">在将 Skype for Business Server 2019 与以前的版本并行部署后，该部署表示 Skype for Business Server 2019 和以前版本的共存测试状态。</span><span class="sxs-lookup"><span data-stu-id="ab270-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="ab270-114">在此状态下，必须测试和确保服务已启动，可以管理每个站点，并且客户端可以与当前用户和旧用户通信。</span><span class="sxs-lookup"><span data-stu-id="ab270-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="ab270-115">在迁移所有用户之前，必须了解每个部署的状态并确保每个部署正常运行。</span><span class="sxs-lookup"><span data-stu-id="ab270-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="ab270-116">通常情况下，共存测试阶段在 Skype for business Server 2019 的试点测试过程中存在。</span><span class="sxs-lookup"><span data-stu-id="ab270-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="ab270-117">旧版用户在一段时间内被移动到 Skype for Business Server 2019，以确保应用程序兼容性和功能和功能正常运行。</span><span class="sxs-lookup"><span data-stu-id="ab270-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="ab270-118">完成试点测试后，用户和应用程序将移至 Skype for Business Server 2019 的生产版本，旧版本的旧池和应用程序将停用。</span><span class="sxs-lookup"><span data-stu-id="ab270-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
