---
title: 为用户分配或更改紧急位置
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
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
description: '了解如何更改您的用户的紧急位置。使用任意数量的位置，您可以更改紧急位置，员工移动楼层或建筑。 '
ms.openlocfilehash: 49410b0ba98e6d193749b558e479d98de1f4ef29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303831"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a>为用户分配或更改紧急位置

为用户分配电话号码时, 每个活动电话号码都必须具有相关联的紧急地址。 (当您在 Office 365 中获取电话号码或转移电话号码时, 您可以关联该地址。)将号码与紧急地址相关联后, 您还可以添加紧急位置以在物理位置内提供更准确的位置。 紧急位置可以是用户所在的楼层、侧楼或办公室编号。 给定的紧急地址可以具有任意的数量的位置，并且如果用户转到其他办公室或建筑，您可以更改紧急位置 — 例如，如果用户从 34 楼转到 35 楼。
  
若要了解如何获取 Office 365 中的通话套餐以及它们的价格，请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
  
## <a name="assign-or-change-the-emergency-location"></a>分配或更改紧急位置

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 团队管理中心** > **旧版门户**。
    
3. 在左侧导航中, 转到 "**语音** > **语音用户**"。
    
    > [!IMPORTANT]
    > 要在 Skype for Business 管理中心的左侧导航中看到 "**语音**" 选项, 您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。
    
4. 在 "**语音用户**" 页面上, 找到并选择要更改其紧急位置的用户。
    
5. 在操作窗格中，在" **紧急位置**"下，单击" **更改**"。
    
6. 在" **分配号码**"页面上，单击" **更改位置**"。 
    
7. 在 "**将紧急地址更改为**" 下, 在框中输入城市的名称, 然后单击 "**搜索**"。

8. 从下拉列表中选择 "**按位置搜索**", 输入位置的部分名称 (例如, "输入**楼层**"), 然后单击 "**搜索**"。 
    
8. 从列表中选择紧急位置, 然后单击 "**保存**"。
    
    如果要添加列表中显示的新紧急位置, 请参阅[添加、更改或删除您的组织的紧急位置](add-change-or-remove-an-emergency-location-for-your-organization.md)。
    
## <a name="related-topics"></a>相关主题

[通过 powershell 分配紧急响应位置](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsOnlineVoiceUser.md)

[为你的组织添加或删除紧急地址](add-or-remove-an-emergency-address-for-your-organization.md)

[添加、 更改或删除您的组织紧急地点](add-change-or-remove-an-emergency-location-for-your-organization.md)

[什么是地址验证？](what-is-address-validation.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[CsOnlineVoiceUser cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

  
 
