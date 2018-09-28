---
title: 设置 PIN 以将号码转移到新服务提供商
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 如需将电话号码从 Skype for Business Online 转移或转出到另一个电话服务提供商或运营商，将需要手动 PIN。 设置 PIN 后，在请求将电话号码转出时将需要将其包括在内。
ms.openlocfilehash: 3a3744a4b1272bab987add10039c89c6e3983927
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347088"
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="9cbf7-104">设置 PIN 以将号码转移到新服务提供商</span><span class="sxs-lookup"><span data-stu-id="9cbf7-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="9cbf7-105">将电话号码从 Skype for Business Online 传输或*转出*到另一个电话服务提供商或运营商，将需要手动设置 PIN。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-105">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN.</span></span> <span data-ttu-id="9cbf7-106">设置 PIN 后，在请求将电话号码转出时将需要将其包括在内。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-106">After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9cbf7-107">PIN 转网 PIN 仅适用于美国国内的组织。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="9cbf7-108">有关转移和转入/转出电话号码的详细信息，请参阅[将电话号码转移到 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-108">See [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="9cbf7-109">这里是有关此 PIN 所应了解一些具体信息：</span><span class="sxs-lookup"><span data-stu-id="9cbf7-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="9cbf7-110">如果未设置 PIN，将无法从Skype for Business Online 转移或转出电话号码。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="9cbf7-111">它可以包含 6-10 位（数字）。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="9cbf7-112">它不能包含字母或特殊字符。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="9cbf7-113">默认 PIN 为空，但如果在其中输入，就无法删除或将其重新设置为空白。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="9cbf7-114">在输入 PIN 后，可以对其进行更新或更改。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="9cbf7-115">设置 PIN</span><span class="sxs-lookup"><span data-stu-id="9cbf7-115">Set up your PIN</span></span>

<span data-ttu-id="9cbf7-116">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="9cbf7-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="9cbf7-117">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9cbf7-118">转到**Microsoft 团队和业务管理中心的 Skype** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-118">Go to the **Microsoft Teams and Skype for Business Admin Center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="9cbf7-119">在左侧导航窗格中，选择**语音** > **端口订单**。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-119">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="9cbf7-120">单击**设置和管理 PIN**，此功能用于将号码转移或转出到另一个服务运营商。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-120">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="9cbf7-121">在**设置或更改转出 PIN **面板，输入 PIN，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="9cbf7-121">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="9cbf7-122">如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="9cbf7-122">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="9cbf7-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="9cbf7-123">Related topics</span></span>
[<span data-ttu-id="9cbf7-124">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="9cbf7-124">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="9cbf7-125">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="9cbf7-125">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="9cbf7-126">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="9cbf7-126">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="9cbf7-127">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="9cbf7-127">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="9cbf7-128">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="9cbf7-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
  

