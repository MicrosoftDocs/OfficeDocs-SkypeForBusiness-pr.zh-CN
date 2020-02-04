---
title: 通话套餐已知问题
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 3441969133c8f67b63b620aff25545b89085858f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692307"
---
# <a name="calling-plans-known-issues"></a>通话套餐已知问题

Office 365 中的通话计划是在 Skype for Business Online 中找到的一项新功能。以下是当前正在跟踪和主动调查的问题。如果在 Office 365 和 Skype for business Online 中的未来版本中更新该功能，则可能会解决这些功能。
  
## <a name="calling-plans-known-issues"></a>通话套餐已知问题

|**已知问题**|**注释**|
|:-----|:-----|
|从技术预览许可证转换到用于通话计划的生产许可证不会自动更新许可证。  <br/> |请首先购买新的许可证，以便准备好将它们分配给你的用户。 删除用户的促销（技术预览版）许可证，然后**立即**将新的**国内呼叫计划**和/或**国内和国际呼叫计划**许可证分配给用户。 <br/> 如果要为多个用户删除和添加许可证，则应使用 Windows PowerShell 删除所有用户的许可证，然后再使用 Windows PowerShell **立即** 为所有用户分配许可证，这一点非常重要。 这样做可确保在处理大量用户许可证分配时，服务不会中断。 有关 PowerShell 脚本示例，请参阅[分配 Skype For business 和 Microsoft 团队许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。  <br/> **注意：** 如果您使用的是混合用户的本地 PSTN 连接，则*只*需分配**电话系统**许可证。 您还**不**应分配语音呼叫计划。 但是，如果在 Office 365 中为 Office 365 中的用户启用呼叫计划，则仍需为这些用户分配**国内呼叫计划**或**国内和国际呼叫计划**许可证。 请参阅[分配 Skype For business 和 Microsoft 团队许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

> [!NOTE]
> 如果您需要获得比这更多的电话号码，请[联系客户支持部门-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 