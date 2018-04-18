---
title: 调用计划的已知的问题
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: c4e3834960439fb09c58ece2bf9e39e2756419e7
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="calling-plans-known-issues"></a>调用计划的已知的问题

Office 365 中的通话方案是找到在 Skype 的在线业务的新增功能。 以下是当前的问题正在跟踪，主动调查。 他们将有可能解决该功能在 Office 365 和 Skype 的未来版本中更新在线业务时。
  
## <a name="calling-plans-known-issues"></a>调用计划的已知的问题

|**已知问题**|**注释**|
|:-----|:-----|
|从技术预览过渡到调用计划生产许可证的许可证不自动更新许可证。  <br/> |请首先购买新的许可证，以便准备好将它们分配给你的用户。 删除用户，促销 （技术预览） 许可证，然后**立即**将新的**国内调用计划**和 （或）**国内和国际调用规划**许可证分配给用户。 <br/> 如果要为多个用户删除和添加许可证，则应使用 Windows PowerShell 删除所有用户的许可证，然后再使用 Windows PowerShell **立即** 为所有用户分配许可证，这一点非常重要。 这样可确保在处理大量的用户许可证分配没有服务不会中断。 PowerShell 的示例脚本，请参阅[分配的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。  <br/> **注意：**如果使用混合用户的内部的 PSTN 连接，您*只*需要分派**电话系统**许可证。 **不**应指定调用计划语音。 但是，如果启用 Office 365 中调用计划为 Office 365 中的用户，您需要**调用计划国内** **，并调用计划国际**许可证的用户仍将分配。 请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

> [!NOTE]
> 如果您需要得到比这更多的电话号码，请[联系支持业务产品的管理帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](transferring-phone-numbers-common-questions.md)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 