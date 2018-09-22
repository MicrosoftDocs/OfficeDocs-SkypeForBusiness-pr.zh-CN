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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 01a49749f472b6a3e591295cff7184dc26fd564a
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958408"
---
# <a name="calling-plans-known-issues"></a>通话套餐已知问题

Office 365 中的呼叫计划是业务 online Skype 中找到的新增功能。 以下是当前问题正在跟踪，主动调查。 它们将可能解析功能在 Office 365 和 Skype 中的将来版本中更新业务 online 时。
  
## <a name="calling-plans-known-issues"></a>通话套餐已知问题

|**已知问题**|**注释**|
|:-----|:-----|
|从技术预览版转换到调用计划生产许可证的许可证不自动更新许可证。  <br/> |请首先购买新的许可证，以便准备好将它们分配给你的用户。 升级 （技术预览） 许可证删除用户，然后**立即**将新的**国内调用规划**和/或**国内和国际呼叫规划**许可证分配给用户。 <br/> 如果要为多个用户删除和添加许可证，则应使用 Windows PowerShell 删除所有用户的许可证，然后再使用 Windows PowerShell **立即** 为所有用户分配许可证，这一点非常重要。 此操作将确保有服务不会中断时处理大量用户许可证分配。 示例 PowerShell 脚本，请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。  <br/> **注意：** 如果您的混合用户使用内部部署 PSTN 连接，您*只*需将**电话系统**许可证分配。 **不**应还分配调用规划语音。 但是，如果要为 Office 365 中的用户启用调用计划在 Office 365 中，您需要仍分配**国内调用规划**或**国内和国际呼叫规划**许可证，这些用户。 请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

> [!NOTE]
> 如果您需要获取比这的多个电话号码，请[与业务产品的管理员技术支持部门联系](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 