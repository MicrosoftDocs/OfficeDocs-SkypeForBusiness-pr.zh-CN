---
title: 为用户启用企业语音（本地）
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
description: 若要让用户使用电话系统（云 PBX），必须首先为企业语音启用它们并为其分配一个电话号码。 您可以使用本地部署执行此操作，同时用户仍驻留在本地部署中。
ms.openlocfilehash: f02638f618b32190fafcded66550b5c3dcc52f2d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221696"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="491bb-104">为用户启用企业语音（本地）</span><span class="sxs-lookup"><span data-stu-id="491bb-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="491bb-105">若要让用户使用电话系统（云 PBX），必须首先为企业语音启用它们并为其分配一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="491bb-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="491bb-106">您可以使用本地部署执行此操作，同时用户仍驻留在本地部署中。</span><span class="sxs-lookup"><span data-stu-id="491bb-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="491bb-107">为用户启用企业内部语音和分配电话号码</span><span class="sxs-lookup"><span data-stu-id="491bb-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="491bb-108">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="491bb-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="491bb-109">使用 "开始" 菜单或桌面快捷方式打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="491bb-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="491bb-110">您还可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="491bb-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="491bb-111">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="491bb-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="491bb-112">在“搜索用户”\*\*\*\* 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="491bb-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="491bb-113">在表中，单击要为企业语音启用的 Skype for Business Online 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="491bb-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="491bb-114">在 "**编辑**" 菜单上，单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="491bb-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="491bb-115">在 "**电话**" 下，单击 "**企业语音**"。</span><span class="sxs-lookup"><span data-stu-id="491bb-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="491bb-116">单击 "**线路 URI**"，然后键入唯一的规范化电话号码（例如，电话： + 14255550200）。</span><span class="sxs-lookup"><span data-stu-id="491bb-116">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="491bb-117">然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="491bb-117">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="491bb-118">为用户启用企业内部语音时的特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="491bb-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="491bb-119">在某些情况下，您可能需要修改为用户启用企业语音的方式，以确保他们可以成功发出和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="491bb-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="491bb-120">如果您的部署中有满足以下条件的用户，请执行所包含的步骤以使用户能够使用企业语音。</span><span class="sxs-lookup"><span data-stu-id="491bb-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="491bb-121">如果用户在本地 AD 中创建，然后与 Skype for business Online 同步，而无需为 Skype for Business 或 Enterprise Voice 启用，并且没有 LineURI 集，请为每个受影响的用户运行以下 cmdlet，并将值替换为 \< \> 您的环境的实际值：</span><span class="sxs-lookup"><span data-stu-id="491bb-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="491bb-122">如果用户已在本地启用 Skype for Business，但未启用企业语音或在移动到 Skype for business Online 之前分配了 LineURI，请为每个用户运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="491bb-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="491bb-123">如果用户已在本地 Skype for Business 中启用，但未启用企业语音（即使已分配了 LineURI），请为每个受影响的用户运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="491bb-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


