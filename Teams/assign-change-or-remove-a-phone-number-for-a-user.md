---
title: 为用户分配、更改或删除电话号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 了解如何为你的团队或 Skype for business 用户分配、更改或删除工作电话号码, 以便外部企业和客户可以呼叫。
ms.openlocfilehash: ea2135a095a60d6da37ce4db0fb443f2e9a74154
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493895"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>为用户分配、更改或删除电话号码

在 Office 365 中设置呼叫计划时, 您可以为用户分配电话号码。 

在 Microsoft Teams 客户端，当用户单击**呼叫**时，就会列出你分配的电话号码。

![显示在 Microsoft Teams 中的用户电话号码。](media/teams-phone-number.png)

在 Skype for Business 客户端中, 您分配的电话号码将在 "**工作电话**" 框中列出, 并且不能由用户更改。
  
![Work Phone Number is Greyed Out.](media/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> 如果用户想要[更改其 skype for business 的电话号码](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e), 并且 Skype for business 应用中的电话号码不能更改或灰显, 这意味着管理员已为其设置了它, 并且无法更改。
  


当您设置用户以使其可以拨打和接听电话时, 您必须首先使用 Skype for Business 管理中心并分配电话号码, 但您可以根据需要更改或删除电话号码。
  
若要了解如何获取 Office 365 中的通话套餐以及它们的价格，请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。
  
> [!NOTE]
> One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center. 
  
 ## <a name="assign-a-phone-number-to-a-user"></a>为用户分配电话号码
 
![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标
 
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 " **Microsoft 团队管理中心** > **旧版门户**"。
    
3. 在左侧导航中, 单击 "**语音** > **语音用户**"。
   > [!NOTE]
   > 要在 Skype for Business 管理中心的左侧导航中看到 "**语音**" 选项, 您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。
 
   
    
4. 在" **语音用户**"页面上，查找并选择要为其分配电话号码的一个或多个用户。
    
5. 在"操作"窗格中，单击" **分配号码**"。
    
6. 在 "**分配**号码" 页面上的 "**选择要分配的号码**" 列表中, 选择用户的电话号码。
    
    > [!TIP]
    > 如果您未看到列出的任何电话号码, 您需要首先[为您的用户获取电话号码](/microsoftteams/getting-phone-numbers-for-your-users)。 或者，如果使用 **Skype for Business 管理中心** > **语音** > **电话号码**页面，可单击**添加**，然后单击**新用户号码**。 
  
7. 若要分配或更改关联的紧急地址, 请在 "**选择已验证的紧急位置**" 下, 从列表中选择位置, 或者, 如果定义了多个位置, 请在搜索框中输入城市的名称, 然后单击 "**搜索**"。
    
8. 在选择电话号码和紧急位置之后，请单击" **保存**"。
    
    > [!NOTE]
    > Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help! 
  


 ## <a name="change-a-phone-number-for-a-user"></a>更改用户的电话号码
 
![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标
 
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 " **Microsoft 团队管理中心** > **旧版门户**"。
    
3. 在左侧导航中, 单击 "**语音** > **语音用户**"。
    
4. 在" **语音用户**"页面上，查找并选择要更改其电话号码的一个或多个用户。
    
5. 在操作窗格中的 "**分配的号码**" 下, 单击 "**更改**"。 
    
6. 在" **分配号码**"页面上，单击" **更改号码**"。
    
7. 在" **分配号码**"页面上的" **选择要分配的号码**"下，使用列表选择新的电话号码。 
    
8. 若要更改关联的紧急地址, 请单击 "**更改位置**", 然后在 "**将紧急地址更改为**" 下, 从列表中选择位置, 或者, 如果定义了多个位置, 请在搜索框中输入城市的名称, 然后单击**搜索**。
    
9. 单击“**保存**”。
    


 ## <a name="remove-a-phone-number-from-a-user"></a>删除用户的电话号码
 
![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标
 
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 " **Microsoft 团队管理中心** > **旧版门户**"。
    
3. 在左侧导航中, 单击 "**语音** > **语音用户**"。
    
4. 在" **语音用户**"页面上，查找并选择要删除其电话号码的一个或多个用户。
    
5. 在操作窗格中的 "**分配的号码**" 下, 单击 "**删除**"。 
    
6. 在" **要删除选定的已分配号码吗?**" 页面上，单击" **是**"。
    

## <a name="related-topics"></a>相关主题
[什么是地址验证？](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 