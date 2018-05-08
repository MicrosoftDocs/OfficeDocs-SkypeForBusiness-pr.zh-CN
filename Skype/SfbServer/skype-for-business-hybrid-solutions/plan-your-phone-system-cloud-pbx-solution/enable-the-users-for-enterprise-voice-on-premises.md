---
title: 为用户启用本地的企业语音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 用于在 Office 365 (云 PBX) 电话系统的用户，首先必须启用企业语音并将其分配电话号码。 执行此操作时用户仍驻留在本地部署中使用您的本地部署。
ms.openlocfilehash: 1099aa825d76017df3afe64cf6d7b3c39391a883
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="ee35c-104">为用户启用本地的企业语音</span><span class="sxs-lookup"><span data-stu-id="ee35c-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="ee35c-105">用于在 Office 365 (云 PBX) 电话系统的用户，首先必须启用企业语音并将其分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="ee35c-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="ee35c-106">执行此操作时用户仍驻留在本地部署中使用您的本地部署。</span><span class="sxs-lookup"><span data-stu-id="ee35c-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="ee35c-107">若要为用户启用企业语音本地和分配电话号码</span><span class="sxs-lookup"><span data-stu-id="ee35c-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="ee35c-108">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ee35c-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ee35c-109">使用“开始”菜单或桌面快捷方式打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ee35c-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="ee35c-110">也可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ee35c-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ee35c-111">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="ee35c-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ee35c-112">在“**搜索用户**”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“**查找**”。</span><span class="sxs-lookup"><span data-stu-id="ee35c-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="ee35c-113">在表中，单击业务联机您想要启用企业语音的用户帐户 Skype。</span><span class="sxs-lookup"><span data-stu-id="ee35c-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="ee35c-114">在“**编辑**”菜单上，单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="ee35c-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="ee35c-115">在“**电话**”下，单击“**企业语音**”。</span><span class="sxs-lookup"><span data-stu-id="ee35c-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="ee35c-p103">单击“**线路 URI**”，输入唯一的规范化电话号码（例如，tel:+14255550200）。然后单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="ee35c-p103">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="ee35c-118">为用户启用本地的企业语音时的特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="ee35c-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="ee35c-119">在某些情况下，可能需要修改为用户启用企业语音的方式来确保他们可以成功地发出和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="ee35c-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="ee35c-120">如果必须满足以下条件的用户部署中，执行包含用户启用企业语音的步骤。</span><span class="sxs-lookup"><span data-stu-id="ee35c-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="ee35c-121">如果您的内部部署中创建用户 AD 和 Skype 与同步业务 online 不被启用 Skype 业务或企业语音的情况下，并且没有 LineURI 设置，运行以下 cmdlet 为每个受影响的用户，替换中的值 <c0 > <b1></b1>替换为您环境的实际值：</span><span class="sxs-lookup"><span data-stu-id="ee35c-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="ee35c-122">如果用户已启用 Skype for Business 在本地，但未启用企业语音或业务 online 被移动到 Skype 之前分配 LineURI，运行以下 cmdlet 为每个用户：</span><span class="sxs-lookup"><span data-stu-id="ee35c-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="ee35c-123">如果用户是在本地的业务的 Skype 中已启用，但未启用企业语音，即使已分配 LineURI，运行以下 cmdlet 为每个受影响的用户：</span><span class="sxs-lookup"><span data-stu-id="ee35c-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


