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
description: 了解 PSTN 呼叫的呼叫计划的已知问题，以及您可以如何解决这些问题。
ms.openlocfilehash: 239a0c83a12ae7d5d7b0be2fcbf81bf8825dd85d8a0dcb7a880bc53ad8b8e477
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306105"
---
# <a name="calling-plans-known-issues"></a>通话套餐已知问题

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

呼叫计划是联机通话中的Skype for Business功能。 以下是当前正在跟踪并积极调查的问题。 在将来的生成中更新功能时，它们可能会得到解决。
  
## <a name="calling-plans-known-issues"></a>通话套餐已知问题

|**已知问题**|**注释**|
|:-----|:-----|
|从技术预览版许可证过渡到调用计划的生产许可证不会自动更新许可证。  <br/> |请首先购买新的许可证，以便准备好将它们分配给你的用户。 从用户中删除 (技术预览版) 许可证，然后立即向该用户分配新的国内呼叫计划和/或国内和国际呼叫计划许可证。  <br/> 如果要为多个用户删除和添加许可证，则应使用 Windows PowerShell 删除所有用户的许可证，然后再使用 Windows PowerShell **立即** 为所有用户分配许可证，这一点非常重要。 这样做可确保在处理大量用户许可证分配时，服务不会中断。 有关示例 PowerShell 脚本，请参阅[分配Skype for Business和Microsoft Teams许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。  <br/> **注意：** 如果为混合用户使用本地 PSTN *连接，则* 只需 **分配一个** 电话系统许可证。 你 **不应分配** 语音呼叫计划。 但是，如果在 Microsoft 365 或 Office 365 中为 Microsoft 365 或 Office 365 中的用户启用呼叫计划，你仍然需要为这些用户分配国内呼叫计划或国内和国际呼叫计划许可证。  请参阅[分配Skype for Business许可证Microsoft Teams许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

> [!NOTE]
> 如果需要获取的电话号码超过此数目，请联系商业产品支持 [人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
