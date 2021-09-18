---
title: 查看组织中电话号码的列表
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
description: 了解如何使用 Microsoft Teams管理中心查看组织中所有电话号码以及分配给用户或未分配的所有号码的列表。
ms.openlocfilehash: 1473a87a190a671d537a958b34e839d53a668f3a
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432484"
---
# <a name="see-a-list-of-telephone-numbers"></a>查看电话号码列表 

你可以向用户或语音应用程序（如音频会议或呼叫队列）分配不同类型的[电话号码](plan-auto-attendant-call-queue.md)。 [](deploy-audio-conferencing-teams-landing-page.md) 有关详细信息，请参阅 [管理组织的电话号码](/microsoftteams/manage-phone-numbers-landing-page)。

本文适用于呼叫计划和运营商连接。 有关直接路由的信息，请参阅 [配置电话号码并启用企业语音和语音邮件](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)。
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>查看组织的所有电话号码

查看组织中所有电话号码的列表：

1. 转到 **"Microsoft Teams管理中心"。**

2. 在左侧导航栏中，转到"**语音**  >  **"电话数字"**。

3. 若要查看已分配的电话号码，请参阅"工作分配状态"列，其中还显示该号码分配到的服务类型。

4. 若要筛选视图，请单击筛选器图标。 在 **"筛选器** "窗格中，可以使用下拉列表按以下方法筛选视图：

   - **设置** 的数量范围。 可以按最小数字或最高数字进行搜索。

   - 以指定的数字开始的数字。

   - 数字 **激活状态**。

   - 数字 **类型**。

   - 电话状态 **。**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>查看分配给用户的所有电话号码

设置用户时，可能只想查看已分配给用户的电话号码列表，以及可为其分配的电话号码。

1. 转到 **"Microsoft Teams管理中心"。**

2. 在左侧导航栏中，转到"**语音**  >  **"电话数字"**。

    > [!IMPORTANT]
    > 若要在 Microsoft Teams管理中心的左侧导航栏中查看"语音"选项，必须先购买至少一个 **Enterprise E5** 许可证、一个 **电话系统** 附加许可证或一个音频会议附加许可证。 

3. 若要快速对数字进行排序，以便查看已分配的数字，请单击"工作 **分配状态"** 列标题。 或者，您可以单击筛选器图标，然后筛选视图以查看已分配给用户的电话号码或您可以分配给用户的未分配号码。 你可以按以下内容筛选：

   - **分配给用户**
   - **分配到会议网桥** 
   - **分配到语音应用 (自动助理/呼叫队列)**
   - **未分配**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>查看分配给语音用户的所有电话号码

当您在组织中设置用户以拨打和接听电话呼叫时，您必须先获取电话号码，然后再将其分配给您的用户。 获得电话号码后，可能需要查看号码分配的激活状态。
  
1. 转到 **"Microsoft Teams管理中心"。**

2. 在左侧导航栏中，转到"**语音**  >  **"电话数字"**。

3. 单击筛选器图标，按"激活状态 **"筛选视图**。 你可以按以下内容筛选：

   - **已激活**
   - **待处理分配**
   - **分配失败**
   - **更新挂起**
   - **更新失败**

## <a name="using-the-teams-powershell-module"></a>使用 Teams PowerShell 模块

可以使用 Teams PowerShell 模块从前面部分获取相同的信息，但需要版本 1.1.6 或更高版本，其中包括 Skype for Business Online 连接器的集成。 有关模块详细信息，请参阅[PowerShell Microsoft Teams概述](teams-powershell-overview.md)。

若要查看组织拥有的所有电话号码的列表，请使用 [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber) cmdlet。 例如，若要查看每个电话号码及其状态，请运行以下命令：

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

若要查看分配给用户的所有电话号码，请使用 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) cmdlet。 例如，若要查看分配有电话号码的所有用户，请运行以下命令：

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>相关主题

[管理组织的电话号码](manage-phone-numbers-landing-page.md)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)