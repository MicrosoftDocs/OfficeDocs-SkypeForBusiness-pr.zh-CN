---
title: 在 Skype for Business 服务器中配置 "绕过媒体" 服务器以始终绕过中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 在 Skype for Business Server Enterprise Voice 中启用 "绕过媒体" 以始终绕过中介服务器。
ms.openlocfilehash: 0e45f8ede38411974f9433c17ccd0a0946b427ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275876"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="ebf81-103">在 Skype for Business 服务器中配置 "绕过媒体" 服务器以始终绕过中介服务器</span><span class="sxs-lookup"><span data-stu-id="ebf81-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="ebf81-104">在 Skype for Business Server Enterprise Voice 中启用 "绕过媒体" 以始终绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ebf81-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="ebf81-105">如果你使用本主题中的步骤来配置媒体绕过的全局设置, 则假设你在 Skype for Business 终结点和任何对等客户之间具有良好的连接, 你可以在中继连接上配置了媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="ebf81-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="ebf81-106">如果您在 Skype for Business 终结点和所有对等的外部服务器之间没有良好的连接, 并且其各自的干线连接已启用媒体旁路, 则必须将全局媒体绕过设置配置为使用网站和区域信息采用媒体旁路时。</span><span class="sxs-lookup"><span data-stu-id="ebf81-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="ebf81-107">这允许在确定媒体绕过中介服务器时提供更多控制。</span><span class="sxs-lookup"><span data-stu-id="ebf81-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="ebf81-108">若要执行此操作, 请使用 "在[Skype For Business 服务器中配置媒体绕过全局设置" 中的步骤使用网站和区域信息](use-site-and-region-information.md), 而[将子网与网络网站相关联](deploy-network.md#BKMK_AssociateSubnets)。</span><span class="sxs-lookup"><span data-stu-id="ebf81-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="ebf81-109">在全局范围启用媒体旁路以始终绕过中介服务器</span><span class="sxs-lookup"><span data-stu-id="ebf81-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="ebf81-110">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ebf81-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ebf81-111">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebf81-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="ebf81-112">双击列表中的“全局”\*\*\*\* 配置。</span><span class="sxs-lookup"><span data-stu-id="ebf81-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="ebf81-113">在“编辑全局设置”\*\*\*\* 页上，选中“启用媒体旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="ebf81-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="ebf81-114">单击“始终绕过”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebf81-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="ebf81-115">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="ebf81-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ebf81-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebf81-116">See also</span></span>

[<span data-ttu-id="ebf81-117">在 Skype for Business 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="ebf81-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="ebf81-118">在 Skype for Business 服务器中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="ebf81-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

