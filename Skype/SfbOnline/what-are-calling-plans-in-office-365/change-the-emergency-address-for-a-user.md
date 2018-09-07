---
title: 更改用户的紧急地址
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 5412636c-ad0e-48a5-b199-5925156abee4
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: '请参阅有关如何更改用户的美国和欧洲的公共公用电话交换网 (PSTN) 紧急地址的步骤。 '
ms.openlocfilehash: 5f08e7503e95028e5045404dc4a0ba294addd481
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860546"
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="f4f17-103">更改用户的紧急地址</span><span class="sxs-lookup"><span data-stu-id="f4f17-103">Change the emergency address for a user</span></span>

<span data-ttu-id="f4f17-104">当设置 Office 365 的通话套餐时，需要将紧急地址分配给每个电话号码或用户。</span><span class="sxs-lookup"><span data-stu-id="f4f17-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="f4f17-105">在欧洲国家/地区，当从 Office 365 获取或将电话号码转到 Office 365 时，紧急地址将与电话号码关联。</span><span class="sxs-lookup"><span data-stu-id="f4f17-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="f4f17-106">在美国，紧急地址在被分配给用户时与电话号码关联。</span><span class="sxs-lookup"><span data-stu-id="f4f17-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="f4f17-107">如果分配给的用户移至新的位置，可以更改紧急地址。</span><span class="sxs-lookup"><span data-stu-id="f4f17-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="f4f17-108">有关紧急地址和位置的详细信息，请参阅 [什么是紧急位置、地址和呼叫路由？](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="f4f17-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for details.</span></span>
  
<span data-ttu-id="f4f17-109">若要了解如何获取 Office 365 中的通话套餐以及它们的价格，请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="f4f17-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="f4f17-110">更改用户的紧急地址</span><span class="sxs-lookup"><span data-stu-id="f4f17-110">Change the emergency address for a user</span></span>

<span data-ttu-id="f4f17-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="f4f17-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="f4f17-112">使用工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f4f17-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f4f17-113">转到 **Office 365 管理中心** > **Skype for Business** 。</span><span class="sxs-lookup"><span data-stu-id="f4f17-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f4f17-114">在左侧导航中，转到 **语音** > **语音用户** 。</span><span class="sxs-lookup"><span data-stu-id="f4f17-114">In the Skype for Business admin center, in the left navigation, go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f4f17-115">若要在 Skype for Business 管理中心的左侧导航中查看 **语音** 选项，必须先购买至少一个 **Enterprise E5 许可证** 、一个 **电话系统** 加载项许可证，或一个 **音频会议** 加载项许可证。</span><span class="sxs-lookup"><span data-stu-id="f4f17-115">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="f4f17-116">在" **语音用户**"页面上，查找并选择要更改其紧急地址的用户。</span><span class="sxs-lookup"><span data-stu-id="f4f17-116">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="f4f17-117">在操作窗格中，在" **紧急位置**"下，单击" **更改**"。</span><span class="sxs-lookup"><span data-stu-id="f4f17-117">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="f4f17-118">在 **分配号码** 页面上，单击 **更改位置** 。</span><span class="sxs-lookup"><span data-stu-id="f4f17-118">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="f4f17-119">在 **将紧急地址更改为** 下方，在框中输入城市的名称，然后单击 **搜索** 。</span><span class="sxs-lookup"><span data-stu-id="f4f17-119">Under **Change emergency address to** put the name of the city in the Find City box and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f4f17-120">只能更改已验证的紧急地址。</span><span class="sxs-lookup"><span data-stu-id="f4f17-120">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="f4f17-121">若要更改尚未验证的地址，请将其删除并创建另一个紧急地址。</span><span class="sxs-lookup"><span data-stu-id="f4f17-121">To change an emergency address that hasn't been validated, delete it and recreate another emergency address.</span></span> 
  
8. <span data-ttu-id="f4f17-122">从列表中，选择一个新的紧急地址，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="f4f17-122">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="f4f17-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="f4f17-123">Related topics</span></span>
[<span data-ttu-id="f4f17-124">为组织添加或删除紧急地址</span><span class="sxs-lookup"><span data-stu-id="f4f17-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="f4f17-125">添加、更改或删除组织的紧急地点</span><span class="sxs-lookup"><span data-stu-id="f4f17-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="f4f17-126">什么是地址验证？</span><span class="sxs-lookup"><span data-stu-id="f4f17-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="f4f17-127">管理组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="f4f17-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="f4f17-128">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="f4f17-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="f4f17-129">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="f4f17-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 