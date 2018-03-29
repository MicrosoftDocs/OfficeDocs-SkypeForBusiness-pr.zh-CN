---
title: 在 Skype 的业务服务器 2015 始终绕过中介服务器中配置媒体回避
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 启用媒体旁路来总是跳过业务服务器企业语音在 Skype 的中介服务器。
ms.openlocfilehash: 5a7ca70b6f060c9d6a5399934fb784c9247e95fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a><span data-ttu-id="3b67b-103">在 Skype 的业务服务器 2015 始终绕过中介服务器中配置媒体回避</span><span class="sxs-lookup"><span data-stu-id="3b67b-103">Configure media bypass in Skype for Business Server 2015 to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="3b67b-104">启用媒体旁路来总是跳过业务服务器企业语音在 Skype 的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="3b67b-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="3b67b-105">如果您使用绕过媒体的全局设置配置本主题中的步骤，前提是您具有很好互连性 Skype 业务终结点和任何您配置媒体回避干线连接的对等。</span><span class="sxs-lookup"><span data-stu-id="3b67b-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="3b67b-106">如果您没有良好 Skype 业务终结点并对其各自的主干连接已启用媒体跳过中介服务器的所有对等点之间的连接性，必须配置全球媒体回避设置使用网站和区域信息当绕过使用媒体。</span><span class="sxs-lookup"><span data-stu-id="3b67b-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="3b67b-107">这样可以确定介质时绕过中介服务器的更多控制。</span><span class="sxs-lookup"><span data-stu-id="3b67b-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="3b67b-108">要执行此操作，使用[配置媒体跳过 Skype 的业务服务器 2015 使用网站和区域信息中的全局设置](use-site-and-region-information.md)和[与网络站点建立子网关联](deploy-network.md#BKMK_AssociateSubnets)的步骤。</span><span class="sxs-lookup"><span data-stu-id="3b67b-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server 2015 to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="3b67b-109">在全局范围启用媒体旁路以始终绕过中介服务器</span><span class="sxs-lookup"><span data-stu-id="3b67b-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="3b67b-110">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="3b67b-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="3b67b-111">在左侧导航栏中，单击“网络配置”****。</span><span class="sxs-lookup"><span data-stu-id="3b67b-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="3b67b-112">双击列表中的“全局”****配置。</span><span class="sxs-lookup"><span data-stu-id="3b67b-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="3b67b-113">在“编辑全局设置”****页上，选中“启用媒体旁路”****复选框。</span><span class="sxs-lookup"><span data-stu-id="3b67b-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="3b67b-114">单击“始终绕过”****。</span><span class="sxs-lookup"><span data-stu-id="3b67b-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="3b67b-115">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="3b67b-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3b67b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b67b-116">See also</span></span>

#### 

[<span data-ttu-id="3b67b-117">在业务 2015年的 Skype 的媒体跳过计划</span><span class="sxs-lookup"><span data-stu-id="3b67b-117">Plan for media bypass in Skype for Business 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="3b67b-118">为业务服务器 2015年部署 Skype 在媒体回避</span><span class="sxs-lookup"><span data-stu-id="3b67b-118">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)

