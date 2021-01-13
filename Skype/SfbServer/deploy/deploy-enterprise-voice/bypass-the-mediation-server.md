---
title: 在 Skype for Business Server 中配置媒体旁路以始终绕过中介服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 启用媒体旁路功能，以始终绕过 Skype for Business Server 企业语音。
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804212"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="b95fd-103">在 Skype for Business Server 中配置媒体旁路以始终绕过中介服务器</span><span class="sxs-lookup"><span data-stu-id="b95fd-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="b95fd-104">启用媒体旁路功能，以始终绕过 Skype for Business Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="b95fd-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="b95fd-105">如果使用本主题中的步骤为媒体旁路配置全局设置，则假定前提是 Skype for Business 终结点与在中继连接上配置了媒体旁路的任何对等方之间的连接良好。</span><span class="sxs-lookup"><span data-stu-id="b95fd-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="b95fd-106">如果 Skype for Business 终结点与中介服务器的所有对等方之间没有良好的连接，且中介服务器各自的中继连接已启用媒体旁路，则必须配置全局媒体旁路设置，以在使用媒体旁路时使用站点和地区信息。</span><span class="sxs-lookup"><span data-stu-id="b95fd-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="b95fd-107">这可以在媒体绕过中介服务器时，提供更为细化的控制。</span><span class="sxs-lookup"><span data-stu-id="b95fd-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="b95fd-108">为此，请使用 Skype for [Business Server](use-site-and-region-information.md) 中的"配置媒体旁路全局设置"中的步骤使用站点和地区信息，并改为将子网与 [网络站点](deploy-network.md#BKMK_AssociateSubnets) 关联。</span><span class="sxs-lookup"><span data-stu-id="b95fd-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="b95fd-109">在全局范围启用媒体旁路以始终绕过中介服务器</span><span class="sxs-lookup"><span data-stu-id="b95fd-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="b95fd-110">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="b95fd-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b95fd-111">在左侧导航栏中，单击“网络配置”。</span><span class="sxs-lookup"><span data-stu-id="b95fd-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="b95fd-112">双击列表中的“全局”配置。</span><span class="sxs-lookup"><span data-stu-id="b95fd-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="b95fd-113">在“编辑全局设置”页上，选中“启用媒体旁路”复选框。</span><span class="sxs-lookup"><span data-stu-id="b95fd-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="b95fd-114">单击“始终绕过”。</span><span class="sxs-lookup"><span data-stu-id="b95fd-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="b95fd-115">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="b95fd-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b95fd-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b95fd-116">See also</span></span>

[<span data-ttu-id="b95fd-117">在 Skype for Business 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b95fd-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="b95fd-118">在 Skype for Business Server 中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b95fd-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

