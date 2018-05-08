---
title: 在 Skype for Business 2015 中配置语音策略、PSTN 用法记录和语音路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 摘要： 了解如何为业务服务器 2015 Skype 中配置语音策略、 PSTN 用法记录和语音路由。
ms.openlocfilehash: b0d5d9edaf94cb0c8041ef5ef679ad81b9c54edd
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business-2015"></a><span data-ttu-id="952bd-103">在 Skype for Business 2015 中配置语音策略、PSTN 用法记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="952bd-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>
 
<span data-ttu-id="952bd-104">**摘要：**了解如何为业务服务器 2015 Skype 中配置语音策略、 PSTN 用法记录和语音路由。</span><span class="sxs-lookup"><span data-stu-id="952bd-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="952bd-p101">语音策略、PSTN 用法记录和语音路由是一个有机整体。可以通过选择一组呼叫功能，然后为策略分配一组 PSTN 用法记录来配置语音策略，这些记录指定为分配了语音策略的用户或组授予哪些权限。系统还向语音路由分配 PSTN 用法记录，这些记录用于将路由与有权使用它们的用户进行匹配。也就是说，用户只能发出使用用户对于其有匹配的 PSTN 用法记录的路由的呼叫。</span><span class="sxs-lookup"><span data-stu-id="952bd-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="952bd-109">通过配置包含相应的 PSTN 用法记录的语音策略来启动新企业语音部署的建议工作流，然后将相应的路由关联到每个 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="952bd-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="952bd-110">您还可以具有*用户*作用域创建语音策略，并将其分配给单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="952bd-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="952bd-111">有关执行上述各项任务的详细步骤，请参阅本节中的过程。</span><span class="sxs-lookup"><span data-stu-id="952bd-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="952bd-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="952bd-112">In this section</span></span>

- [<span data-ttu-id="952bd-113">创建或修改语音策略和配置 PSTN 用法记录中的业务 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="952bd-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="952bd-114">配置中的业务 2015 Skype 的语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="952bd-114">Configure voice mail escape in Skype for Business 2015</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="952bd-115">查看 PSTN 用法记录中的业务 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="952bd-115">View PSTN usage records in Skype for Business 2015</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="952bd-116">创建或修改语音路由中的业务 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="952bd-116">Create or modify a voice route in Skype for Business 2015</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="952bd-117">导出或导入业务 2015 Skype 中的语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="952bd-117">Export or import a voice route configuration file in Skype for Business 2015</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="952bd-118">挂起更改语音路由配置中的业务 2015 Skype 的发布</span><span class="sxs-lookup"><span data-stu-id="952bd-118">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)
    

