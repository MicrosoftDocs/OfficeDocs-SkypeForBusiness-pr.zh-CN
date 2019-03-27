---
title: 迁移过程
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 为业务服务器 2019 Skype 的建议和受支持的迁移过程是-并行迁移。 本主题介绍原因应使用-并行迁移和还包括有关共存测试信息。
ms.openlocfilehash: e14226721cbc09bd1f0ac66b47dbd1710712eb17
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876290"
---
# <a name="migration-process"></a><span data-ttu-id="28c0f-104">迁移过程</span><span class="sxs-lookup"><span data-stu-id="28c0f-104">Migration process</span></span>

<span data-ttu-id="28c0f-105">为业务服务器 2019 Skype 的建议和受支持的迁移过程是-并行迁移。</span><span class="sxs-lookup"><span data-stu-id="28c0f-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="28c0f-106">本主题介绍原因应使用-并行迁移和还包括有关共存测试信息。</span><span class="sxs-lookup"><span data-stu-id="28c0f-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="28c0f-107">并行迁移</span><span class="sxs-lookup"><span data-stu-id="28c0f-107">Side-By-Side Migration</span></span>

<span data-ttu-id="28c0f-108">在几乎在每个迁移中，您应使用-并行迁移路径。</span><span class="sxs-lookup"><span data-stu-id="28c0f-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="28c0f-109">在-并行迁移中，您将一起运行的是以前版本的相应服务器业务服务器 2019年部署具有 Skype 的新服务器，然后转接到新服务器的操作。</span><span class="sxs-lookup"><span data-stu-id="28c0f-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="28c0f-110">如果需要回滚到以前的版本，您只需要只要将操作切换回原始服务器。</span><span class="sxs-lookup"><span data-stu-id="28c0f-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="28c0f-111">请注意，在此情况下安排与已升级的客户端的任何新会议将不起作用，以及客户端还需要降级。</span><span class="sxs-lookup"><span data-stu-id="28c0f-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="28c0f-112">共存测试</span><span class="sxs-lookup"><span data-stu-id="28c0f-112">Coexistence Testing</span></span>

<span data-ttu-id="28c0f-113">部署 Skype 的业务服务器 2019年与早期版本的并行后，部署代表测试业务服务器 2019年和以前版本的 Skype 状态共存。</span><span class="sxs-lookup"><span data-stu-id="28c0f-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="28c0f-114">在此状态下，务必测试，并确保启动服务，可以管理每个网站，并且客户端可以与当前和旧用户通信。</span><span class="sxs-lookup"><span data-stu-id="28c0f-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="28c0f-115">之前的所有用户的迁移，它是非常重要，您了解每个部署的状态，并确保每个部署为功能且正常工作正常。</span><span class="sxs-lookup"><span data-stu-id="28c0f-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="28c0f-116">通常情况下，测试阶段的共存情况存在整个 Skype 试点测试的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="28c0f-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="28c0f-117">旧用户移至 Skype 的业务服务器 2019年的一段时间以确保该应用程序兼容性以及特性和功能正常运行。</span><span class="sxs-lookup"><span data-stu-id="28c0f-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="28c0f-118">试点测试之后，用户和应用程序移动到的业务服务器 2019 Skype 和旧池的产品版本和以前版本的应用程序停用。</span><span class="sxs-lookup"><span data-stu-id="28c0f-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
