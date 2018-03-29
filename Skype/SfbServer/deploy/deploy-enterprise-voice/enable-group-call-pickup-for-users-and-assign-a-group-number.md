---
title: 在 Skype for Business 2015 中为用户启用组内呼叫应答并分配组号码
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 允许用户使用在 Skype 的组调用取货业务服务器企业语音，并指定一组数。
ms.openlocfilehash: aaacf080f9e7f7ae7f9bad3f8b13201972d7a72f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a><span data-ttu-id="e87af-103">在 Skype for Business 2015 中为用户启用组内呼叫应答并分配组号码</span><span class="sxs-lookup"><span data-stu-id="e87af-103">Enable Group Call Pickup for users and assign a group number in Skype for Business 2015</span></span>
 
<span data-ttu-id="e87af-104">允许用户使用在 Skype 的组调用取货业务服务器企业语音，并指定一组数。</span><span class="sxs-lookup"><span data-stu-id="e87af-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>
  
<span data-ttu-id="e87af-105">呼叫分拣组电话号码添加到调用公园轨道表后，您使用 SEFAUtil 工具向用户分配组数字并为其启用组调用装货。</span><span class="sxs-lookup"><span data-stu-id="e87af-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e87af-106">在混合部署中，不要给在线托管的用户分配组调用拾取组。</span><span class="sxs-lookup"><span data-stu-id="e87af-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="e87af-107">联机托管的用户无法参与组调用装货。</span><span class="sxs-lookup"><span data-stu-id="e87af-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="e87af-108">也就是说，他们的呼叫无法由其他用户应答，他们也无法应答对其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e87af-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span> 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="e87af-109">指定组号，为用户启用组调用装货</span><span class="sxs-lookup"><span data-stu-id="e87af-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="e87af-110">使用管理员权限登录安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="e87af-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>
    
2. <span data-ttu-id="e87af-111">在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="e87af-111">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="e87af-112">例如，将组号码 199 分配给用户：</span><span class="sxs-lookup"><span data-stu-id="e87af-112">For example, to assign group number 199 to a user:</span></span>
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a><span data-ttu-id="e87af-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e87af-113">See also</span></span>

#### 

[<span data-ttu-id="e87af-114">用户的禁用组装货</span><span class="sxs-lookup"><span data-stu-id="e87af-114">Disable Group Pickup for Users</span></span>](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

