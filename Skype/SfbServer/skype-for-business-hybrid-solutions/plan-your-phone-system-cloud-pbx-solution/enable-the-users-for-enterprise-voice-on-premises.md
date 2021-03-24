---
title: 为用户启用企业语音内部部署
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 对于使用电话系统 (云 PBX) ，必须先为其启用企业语音并为其分配电话号码。 在用户仍位于本地部署中时，可以使用本地部署完成此操作。
ms.openlocfilehash: b26e51ba316c63e0f992b843a7763586d7e9b575
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098588"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="2cf54-104">为用户启用企业语音内部部署</span><span class="sxs-lookup"><span data-stu-id="2cf54-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="2cf54-105">对于使用电话系统 (云 PBX) ，必须先为其启用企业语音并为其分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="2cf54-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="2cf54-106">在用户仍位于本地部署中时，可以使用本地部署完成此操作。</span><span class="sxs-lookup"><span data-stu-id="2cf54-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="2cf54-107">Skype for Business Online 将于 2021 年 7 月 31 日停用，此后服务将不再可用。</span><span class="sxs-lookup"><span data-stu-id="2cf54-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="2cf54-108">此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="2cf54-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="2cf54-109">了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="2cf54-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="2cf54-110">为用户启用本地企业语音并分配电话号码</span><span class="sxs-lookup"><span data-stu-id="2cf54-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="2cf54-111">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2cf54-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2cf54-112">使用"开始"菜单或桌面快捷方式打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2cf54-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="2cf54-113">还可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2cf54-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2cf54-114">在左侧导航栏中，单击“用户”。</span><span class="sxs-lookup"><span data-stu-id="2cf54-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="2cf54-115">在“搜索用户”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="2cf54-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="2cf54-116">在表中，单击要为此帐户启用的 Skype for Business Online 企业语音。</span><span class="sxs-lookup"><span data-stu-id="2cf54-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="2cf54-117">在"编辑 **"菜单** 上，单击"**显示详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="2cf54-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="2cf54-118">在 **"电话"下**，单击 **"企业语音"。**</span><span class="sxs-lookup"><span data-stu-id="2cf54-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="2cf54-119">单击 **"线路 URI"，** 然后键入唯一的规范化电话号码 (例如 tel：+14255550200) 。</span><span class="sxs-lookup"><span data-stu-id="2cf54-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="2cf54-120">然后单击"**提交"。**</span><span class="sxs-lookup"><span data-stu-id="2cf54-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="2cf54-121">为用户启用本地部署企业语音注意事项</span><span class="sxs-lookup"><span data-stu-id="2cf54-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="2cf54-122">在某些情况下，您可能需要修改为用户启用企业语音以确保他们可以成功拨打和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="2cf54-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="2cf54-123">如果您的部署中具有满足以下条件的用户，请执行包含的步骤以启用用户企业语音。</span><span class="sxs-lookup"><span data-stu-id="2cf54-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="2cf54-124">如果在内部部署 AD 中创建用户，然后在未启用 Skype for Business 或 企业语音 的情况下与 Skype for Business Online 同步，并且没有设置 LineURI，请针对每个受影响的用户运行以下 cmdlet，将 中的值替换为您的环境的实际 \< \> 值：</span><span class="sxs-lookup"><span data-stu-id="2cf54-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="2cf54-125">如果用户已启用本地 Skype for Business，但在移至 Skype for Business Online 之前未为 企业语音 启用或分配了 LineURI，请为每个用户运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2cf54-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="2cf54-126">如果用户已在本地 Skype for Business 中启用，但没有为 企业语音 启用，即使已分配 LineURI，请为每个受影响的用户运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2cf54-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```