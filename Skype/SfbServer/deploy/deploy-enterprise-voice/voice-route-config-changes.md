---
title: 发布挂起的 Skype for Business 中的语音路由配置更改
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 摘要： 了解如何查看、 发布或取消语音路由配置更改中 Skype 业务服务器使用 Skype 业务 Server Control Panel。
ms.openlocfilehash: 9878e719234a5d7eff2e7321fa71e30c094d489a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222455"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="6107e-103">发布挂起的 Skype for Business 中的语音路由配置更改</span><span class="sxs-lookup"><span data-stu-id="6107e-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="6107e-104">**摘要：** 了解如何查看、 发布或取消语音路由配置更改中 Skype 业务服务器使用 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="6107e-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="6107e-105">在“语音路由”\*\*\*\* 组的页面中对任何配置设置做出更改后，执行此过程以查看、发布或取消待处理的更改。</span><span class="sxs-lookup"><span data-stu-id="6107e-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6107e-106">确保每次只有一个用户修改语音路由配置设置。</span><span class="sxs-lookup"><span data-stu-id="6107e-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6107e-p101">必须通过运行“全部提交”\*\*\*\* 命令，同时发布所有待处理的更改。不能选择性地发布待处理的更改。发布待处理的更改前，运行“查看未提交的更改”\*\*\*\* 命令并取消任何不希望发布的配置更改。</span><span class="sxs-lookup"><span data-stu-id="6107e-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6107e-110">如果在提交待处理更改前离开“语音路由”\*\*\*\* 组中的页面，所有待处理更改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="6107e-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="6107e-111">但是，可以将当前配置（包括所有待处理的更改）导出至语音配置文件，然后导入并发布已更新的配置。</span><span class="sxs-lookup"><span data-stu-id="6107e-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="6107e-112">有关详细信息，请参阅[导出或导入语音路由配置文件中的业务的 Skype](voice-route-configuration-import-export.md)。</span><span class="sxs-lookup"><span data-stu-id="6107e-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="6107e-113">查看、发布或取消语音路由配置更改</span><span class="sxs-lookup"><span data-stu-id="6107e-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="6107e-114">以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="6107e-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="6107e-115">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="6107e-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6107e-116">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6107e-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="6107e-117">在“语音路由”\*\*\*\* 组的每个页面中，对设置做出所需的配置更改。</span><span class="sxs-lookup"><span data-stu-id="6107e-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="6107e-118">要在不发布更改的情况下查看待处理的更改，请从“提交”\*\*\*\* 菜单中选择“查看未提交的更改”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6107e-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="6107e-119">如果要取消任何待处理的更改，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="6107e-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="6107e-120">从“提交”\*\*\*\* 菜单中选择“取消所有未提交的更改”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6107e-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="6107e-121">导航到包含要取消的待处理更改的“语音路由”\*\*\*\* 页的选项卡，选择包含待处理更改的项目，单击“提交”\*\*\*\*，然后单击“取消选择的更改”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6107e-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="6107e-122">查看所有待处理的更改并取消其中不希望发布的更改后，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6107e-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="6107e-123">在“未提交的语音配置设置”\*\*\*\* 对话框（其中显示所有待处理更改的列表）中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6107e-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="6107e-124">Skype 的业务 Server Control Panel 提交更改，出现**成功发布语音路由配置**邮件。</span><span class="sxs-lookup"><span data-stu-id="6107e-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

