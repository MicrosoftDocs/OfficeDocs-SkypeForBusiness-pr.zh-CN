---
title: "调用计划的已知的问题"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a>调用计划的已知的问题

Office 365 中的通话方案是找到在 Skype 的在线业务的新增功能。 以下是当前的问题正在跟踪，主动调查。 他们将有可能解决该功能在 Office 365 和 Skype 的未来版本中更新在线业务时。
  
## <a name="calling-plans-known-issues"></a>调用计划的已知的问题

|**已知问题**|**注释**|
|:-----|:-----|
|从技术预览过渡到调用计划生产许可证的许可证不自动更新许可证。  <br/> |第一次购买新的许可证，这样他们就可以分配给您的用户。 删除用户，促销 （技术预览） 许可证，然后**立即**将新的**国内调用计划**和 （或）**国内和国际调用规划**许可证分配给用户。 <br/> 如果您删除并添加多个用户的许可证，则极其重要，从所有使用 Windows PowerShell 的用户删除许可证，然后**立即**指派的所有用户同时在使用 Windows PowerShell 的许可证。 这样可确保在处理大量的用户许可证分配没有服务不会中断。 PowerShell 的示例脚本，请参阅[分配的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。  <br/> **注意：**如果使用混合用户的内部的 PSTN 连接，您*只*需要分派**电话系统**许可证。 **不**应指定调用计划语音。 但是，如果启用 Office 365 中调用计划为 Office 365 中的用户，您需要**调用计划国内** **，并调用计划国际**许可证的用户仍将分配。 请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

> [!NOTE]
> 如果您需要得到比这更多的电话号码，请[联系支持业务产品的管理帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>相关主题
[传送电话号码的常见问题](transferring-phone-numbers-common-questions.md)

[不同种类的用于调用计划的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责标签](https://go.microsoft.com/fwlink/?LinkID=692099)
