---
title: 在 Skype for Business 2015 中配置语音策略、PSTN 用法记录和语音路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 摘要： 了解如何配置语音策略、 PSTN 使用记录和语音路由在 Skype 业务服务器 2015年。
ms.openlocfilehash: d238703b98ebe532b2370456212760620c30ebf4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business-2015"></a><span data-ttu-id="b8d67-103">在 Skype for Business 2015 中配置语音策略、PSTN 用法记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="b8d67-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>
 
<span data-ttu-id="b8d67-104">**摘要：**了解如何为业务服务器 2015年配置在 Skype 语音策略、 PSTN 使用记录和语音路由。</span><span class="sxs-lookup"><span data-stu-id="b8d67-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b8d67-p101">语音策略、PSTN 用法记录和语音路由是一个有机整体。可以通过选择一组呼叫功能，然后为策略分配一组 PSTN 用法记录来配置语音策略，这些记录指定为分配了语音策略的用户或组授予哪些权限。系统还向语音路由分配 PSTN 用法记录，这些记录用于将路由与有权使用它们的用户进行匹配。也就是说，用户只能发出使用用户对于其有匹配的 PSTN 用法记录的路由的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b8d67-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="b8d67-109">通过配置包含相应的 PSTN 用法记录的语音策略来启动新企业语音部署的建议工作流，然后将相应的路由关联到每个 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="b8d67-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b8d67-110">此外可以使用*用户*范围创建语音策略并将它们分配给单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="b8d67-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="b8d67-111">有关执行上述各项任务的详细步骤，请参阅本节中的过程。</span><span class="sxs-lookup"><span data-stu-id="b8d67-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b8d67-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="b8d67-112">In this section</span></span>

- [<span data-ttu-id="b8d67-113">创建或修改语音策略和业务 2015年的 Skype 在配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="b8d67-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="b8d67-114">在业务 2015年的 Skype 配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="b8d67-114">Configure voice mail escape in Skype for Business 2015</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="b8d67-115">查看业务 2015年的 Skype 在 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="b8d67-115">View PSTN usage records in Skype for Business 2015</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="b8d67-116">创建或修改在企业 2015年的 Skype 语音路由</span><span class="sxs-lookup"><span data-stu-id="b8d67-116">Create or modify a voice route in Skype for Business 2015</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="b8d67-117">导出或导入业务 2015年在 Skype 的语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="b8d67-117">Export or import a voice route configuration file in Skype for Business 2015</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="b8d67-118">挂起更改的业务 2015年的 Skype 语音路由配置发布</span><span class="sxs-lookup"><span data-stu-id="b8d67-118">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)
    

