---
title: 为企业内部部署的用户启用企业语音
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 若要让用户在 Office 365 （云 PBX）中使用电话系统，必须首先启用企业语音，并为其分配电话号码。 你可以使用本地部署执行此操作，同时用户仍托管在本地部署中。
ms.openlocfilehash: 8bf8720896aa8115cb24d3b632b4ae576f466bcc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003472"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="260d5-104">为企业内部部署的用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="260d5-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="260d5-105">若要让用户在 Office 365 （云 PBX）中使用电话系统，必须首先启用企业语音，并为其分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="260d5-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="260d5-106">你可以使用本地部署执行此操作，同时用户仍托管在本地部署中。</span><span class="sxs-lookup"><span data-stu-id="260d5-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="260d5-107">允许用户在内部部署企业语音并分配电话号码</span><span class="sxs-lookup"><span data-stu-id="260d5-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="260d5-108">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="260d5-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="260d5-109">使用“开始”菜单或桌面快捷方式打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="260d5-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="260d5-110">也可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="260d5-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="260d5-111">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="260d5-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="260d5-112">在“搜索用户”\*\*\*\* 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="260d5-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="260d5-113">在表中，单击要为企业语音启用的 Skype for Business Online 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="260d5-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="260d5-114">在“**编辑**”菜单上，单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="260d5-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="260d5-115">在“**电话**”下，单击“**企业语音**”。</span><span class="sxs-lookup"><span data-stu-id="260d5-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="260d5-p103">单击“**线路 URI**”，输入唯一的规范化电话号码（例如，tel:+14255550200）。然后单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="260d5-p103">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="260d5-118">为企业内部部署的用户启用的特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="260d5-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="260d5-119">在某些情况下，可能需要修改为用户启用企业语音的方式来确保他们可以成功地发出和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="260d5-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="260d5-120">如果你的部署中有满足以下条件的用户，请执行所包含的步骤以启用企业语音用户。</span><span class="sxs-lookup"><span data-stu-id="260d5-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="260d5-121">如果用户在本地广告中创建，然后与 skype for business Online 同步，而不启用 skype for business 或企业语音，并且没有 LineURI 集，请为每个受影响的用户运行以下 cmdlet， \< \>并用你的环境的实际值替换其中的值：</span><span class="sxs-lookup"><span data-stu-id="260d5-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="260d5-122">如果用户已针对本地 Skype for business 启用，但未启用企业语音或在移动到 Skype for business Online 之前分配了 LineURI，请为每个用户运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="260d5-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="260d5-123">如果用户已在本地 Skype for Business 中启用，但未启用企业语音，即使已分配了 LineURI，也为每个受影响的用户运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="260d5-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


