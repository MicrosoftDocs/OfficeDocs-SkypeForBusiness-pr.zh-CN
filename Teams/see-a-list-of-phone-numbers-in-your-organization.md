---
title: 查看组织中的电话号码列表
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 了解如何使用 Microsoft Teams 管理中心查看组织中所有电话号码以及分配给用户或未分配的所有号码的列表。
ms.openlocfilehash: a0c5bf59d4ebf2d760ae6c8b4abb6c70e3e3ebb7
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551846"
---
# <a name="see-a-list-of-telephone-numbers"></a>查看电话号码列表 

有不同类型的电话号码，你可以分配给用户或语音应用程序，如 [音频会议](deploy-audio-conferencing-teams-landing-page.md) 或 [呼叫队列](plan-auto-attendant-call-queue.md)。 有关详细信息，请参阅 [管理组织的电话号码](/microsoftteams/manage-phone-numbers-landing-page)。

本文适用于通话套餐、运营商连接和 Teams Phone Mobile。 有关直接路由的信息，请参阅 [配置电话号码并启用企业语音](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)。
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>查看组织中的所有电话号码

若要查看组织中所有电话号码的列表，

1. 转到 **Microsoft Teams 管理中心**。

2. 在左侧导航栏中，转到 **语音** > **电话号码**。

3. 若要查看分配的电话号码，请参阅 **“分配状态”** 列，该列还显示该号码分配给的服务类型。

4. 若要筛选视图，请单击筛选器图标。 在 **“筛选器”** 窗格中，可以使用下拉列表按以下方法筛选视图：

   - 设置 **的数字范围**。 可以按最小数字或最高数进行搜索。

   - 以指定的数字开头的数字。

   - 数字 **激活状态**。

   - 数字 **类型**。

   - 电话号码 **状态**。

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>查看分配给用户的所有电话号码

设置用户时，你可能只想查看已分配给用户的电话号码列表，以及哪些电话号码可供分配给用户。

1. 转到 **Microsoft Teams 管理中心**。

2. 在左侧导航栏中，转到 **语音** > **电话号码**。

    > [!IMPORTANT]
    > 若要在 Microsoft Teams 管理中心左侧导航中看到 **“语音** ”选项，必须先购买至少一个 **企业 E5 许可证**、一个 **电话系统** 加载项许可证或一个 **音频会议** 加载项许可证。

3. 若要快速对数字进行排序，以便能够查看分配的数字，请单击“ **分配状态”** 列标题。 或者，可以单击筛选器图标，然后筛选视图，查看已分配给用户的电话号码或可分配给用户的未分配号码。 你可以按以下内容筛选：

   - **分配给用户**
   - **分配给会议网桥** 
   - **分配给语音应用 (自动助理/呼叫队列)**
   - **未分配**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>查看分配给语音用户的所有电话号码

在组织中设置用户以拨打和接听电话时，必须先获取电话号码，然后将其分配给用户。 获取电话号码后，可能需要查看号码分配的激活状态。
  
1. 转到 **Microsoft Teams 管理中心**。

2. 在左侧导航栏中，转到 **语音** > **电话号码**。

3. 单击筛选器图标，按 **激活状态** 筛选视图。 你可以按以下内容筛选：

   - **激活**
   - **挂起的分配**
   - **分配失败**
   - **更新挂起**
   - **更新失败**

## <a name="using-the-teams-powershell-module"></a>使用 Teams PowerShell 模块

可以使用 Teams PowerShell 模块从前面的部分获取相同的信息，但需要版本 1.1.6 或更高版本，其中包括 Skype for Business Online 连接器的集成。 有关模块的详细信息，请参阅 [Microsoft Teams PowerShell 概述](teams-powershell-overview.md)。

若要查看组织的所有电话号码列表，请使用 [Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment) cmdlet。 例如，若要查看每个电话号码、其类型及其状态，请运行以下命令：

```PowerShell
Get-CsPhoneNumberAssignment | ft TelephoneNumber,ActivationState,NumberType
```

若要查看分配给用户的所有电话号码，请使用 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) cmdlet。 例如，若要查看分配有电话号码的所有用户，请运行以下命令：

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>相关主题

[管理组织的电话号码](manage-phone-numbers-landing-page.md)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)
