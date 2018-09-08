---
title: Skype 业务服务器以始终绕过中介服务器中配置媒体绕过
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 启用媒体绕过以始终绕过中介服务器中 Skype，业务 Server 企业语音。
ms.openlocfilehash: 2671a4df1b7c068e650cba35be6409f97b8682f8
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881852"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="470ee-103">Skype 业务服务器以始终绕过中介服务器中配置媒体绕过</span><span class="sxs-lookup"><span data-stu-id="470ee-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="470ee-104">启用媒体绕过以始终绕过中介服务器中 Skype，业务 Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="470ee-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="470ee-105">如果您使用本主题可配置为媒体的全局设置中的步骤绕过，假设您有良好 Skype 业务终结点和任何在中继连接为其配置媒体绕过的对等方之间的连接性。</span><span class="sxs-lookup"><span data-stu-id="470ee-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="470ee-106">如果您没有为业务终结点的 Skype 和到其各自的中继连接已启用媒体绕过中介服务器的所有对等方之间的良好连接，则必须配置全局媒体绕过设置以使用站点和区域信息当采用媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="470ee-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="470ee-107">这样，确定当媒体绕过中介服务器中的多个控件。</span><span class="sxs-lookup"><span data-stu-id="470ee-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="470ee-108">若要执行此操作，而是使用[配置媒体绕过全局设置中的 Business Server 以使用站点和区域信息的 Skype](use-site-and-region-information.md)和[关联子网与网络站点](deploy-network.md#BKMK_AssociateSubnets)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="470ee-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="470ee-109">在全局范围启用媒体旁路以始终绕过中介服务器</span><span class="sxs-lookup"><span data-stu-id="470ee-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="470ee-110">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="470ee-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="470ee-111">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="470ee-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="470ee-112">双击列表中的“全局”\*\*\*\* 配置。</span><span class="sxs-lookup"><span data-stu-id="470ee-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="470ee-113">在“编辑全局设置”\*\*\*\* 页上，选中“启用媒体旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="470ee-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="470ee-114">单击“始终绕过”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="470ee-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="470ee-115">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="470ee-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="470ee-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="470ee-116">See also</span></span>

[<span data-ttu-id="470ee-117">规划媒体绕过 Skype for Business 中</span><span class="sxs-lookup"><span data-stu-id="470ee-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="470ee-118">为业务服务器部署中 Skype 的媒体绕过</span><span class="sxs-lookup"><span data-stu-id="470ee-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

