---
title: 查看组织中的电话号码列表
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 了解如何使用 Microsoft Teams 管理中心查看组织中所有电话号码以及分配给用户或未分配的所有号码的列表。
ms.openlocfilehash: 41eceb3618fae61308b90a88165ce1935ad6b30b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117230"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>查看组织中的电话号码列表

您可以向用户或其他服务分配不同类型的电话号码 (服务号码) ，例如 Microsoft 365 或 Office 365 中的音频会议。
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>查看贵组织拥有的所有电话号码的列表

![使用 Microsoft Teams 管理中心 ](media/teams-logo-30x30.png) **显示 Teams 徽标的图标**

1. 转到 **Microsoft Teams 管理中心**。

2. 在左侧导航栏中，转到"**语音**  >  **电话号码"。**

    > [!IMPORTANT]
    > 若要在 Skype for Business 管理中心的左侧导航栏中查看"语音"选项，必须先购买至少一个企业 **版 E5** 许可证、一个电话系统附加许可证或一个音频会议附加许可证。 

3. 若要查看分配的电话号码，请参阅"状态 **"** 列。

4. 若要筛选视图，请单击筛选器图标。 在 **"筛选器** "窗格中，可以使用下拉列表按以下方法筛选视图：

   - **设置** 的数量范围。 可以按最小数字或最高数字进行搜索。

   - 以指定的数字开始的数字。

   - 数字 **激活状态**。

   - 数字 **类型**。

   - 电话号码 **状态**。

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>查看分配给用户的所有电话号码

设置用户时，可能只想查看已分配给用户的电话号码列表，以及可为其分配的电话号码。
  
![使用 Microsoft Teams 管理中心 ](media/teams-logo-30x30.png) **显示 Teams 徽标的图标**

1. 转到 **Microsoft Teams 管理中心**。

2. 在左侧导航栏中，转到"**语音**  >  **电话号码"。**

    > [!IMPORTANT]
    > 若要在 Microsoft  Teams 管理中心的左侧导航栏中查看"语音"选项，必须先购买至少一个企业 **版 E5** 许可证、一个电话系统附加许可证或一个音频会议附加许可证。

3. 若要快速对数字进行排序，以便查看已分配的数字，请单击"状态 **"** 列标题。 或者，可以单击筛选器图标，然后筛选视图以查看已分配给用户的电话号码或可以分配给用户的未分配号码。 你可以按以下内容筛选：

   - **分配给用户**

   - **分配到会议网桥** 

   - **未分配**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>查看分配给语音用户的电话号码

当你在组织中设置用户以便拨打和接听电话呼叫时，必须首先获得电话号码，然后将其分配给用户。 获得电话号码后，你可能只想查看号码分配的激活状态。

![使用 Microsoft Teams 管理 ](media/teams-logo-30x30.png) **中心显示 Teams 徽标的图标** ！
  
1. 转到 **Microsoft Teams 管理中心**。

2. 在左侧导航栏中，转到"**语音**  >  **电话号码"。**

    > [!IMPORTANT]
    > 若要在 Microsoft  Teams 管理中心的左侧导航栏中查看"语音"选项，必须先购买至少一个企业 **版 E5** 许可证、一个电话系统附加许可证或一个音频会议附加许可证。

3. 单击筛选器图标，按"激活状态"筛选 **视图可以按** 以下条件进行筛选：

   - **已激活**

   - **待处理分配**

   - **分配失败**

   - **更新挂起**

   - **更新失败**

## <a name="using-the-teams-powershell-module"></a>使用 Teams PowerShell 模块

可以使用 Teams PowerShell 模块从前面的部分获取相同的信息，但需要版本 1.1.6 或更高版本，其中包括 Skype for Business Online 连接器的集成。 有关模块详细信息，请参阅 Microsoft [Teams PowerShell 概述](teams-powershell-overview.md)。

可以使用 [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber) cmdlet 查看组织拥有的所有电话号码的列表。 例如，可以运行以下命令来查看每个电话号码及其状态：

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

可以使用 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) cmdlet 查看分配给用户的所有电话号码。 例如，可以运行以下命令来查看分配有电话号码的所有用户：

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)