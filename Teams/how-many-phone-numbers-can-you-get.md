---
title: 你可以获取多少个电话号码？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: 在查找并获取组织的电话号码时，获取的电话号码会比已分配许可证的电话号码多。 但这取决于你已购买并分配的电话号码类型和许可证类型。 您可以单击不同种类的用于调用计划以找出有关业务 online Skype 中使用不同的电话号码的电话号码。
ms.openlocfilehash: a0d4e1273a49ac4f9e82cb98c8baddf22772f9d4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856304"
---
# <a name="how-many-phone-numbers-can-you-get"></a>你可以获取多少个电话号码？

在查找并获取组织的电话号码时，获取的电话号码会比已分配许可证的电话号码多。 但这取决于你已购买并分配的电话号码类型和许可证类型。 您可以单击[不同种类的电话号码用于调用计划](different-kinds-of-phone-numbers-used-for-calling-plans.md)以找出有关业务 online Skype 中使用不同的电话号码。
  
您可以看到您可以获取业务管理中心中，为 Skype**电话号码**页的电话号码的号码，或者您可以运行[Get CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/library/mt634605.aspx) cmdlet。
  
> [!IMPORTANT]
> [!重要信息] 以下限制不包括你已经转网或转移到 Microsoft 的电话号码。 
  
## <a name="how-many-phone-numbers-you-can-get"></a>您可以获取多少个电话号码？

||||
|:-----|:-----|:-----|
|**下面是电话号码类型** <br/> |**如何获取电话号码总数？** <br/> |**下面是一个示例** <br/> |
|用户（订阅者）号码  <br/> |等于**国内调用规划**和/或**国内和国际呼叫规划**许可证乘以 1.1 总数 + 10 其他电话号码的电话号码数。 <br/> |如果我有 50 个总与任一国内调用规划和/或国内和国际呼叫规划中的用户，您可以获取**65**电话号码 **(50 x 1.1 + 10)**。 <br/> |
|收费服务号码  <br/> | 电话号码数等于总**电话系统**和**音频会议**的许可证数量，并使用以下： <br/>  如果有 **1-25 个许可证** ，则给定 **5** 个电话号码。 <br/>  如果有 **26-49 个许可证** ，则给定 **10** 个电话号码。 <br/>  如果有**50-99 许可证**是给定**20**电话号码。 <br/>  如果有 **100-149 个许可证** ，则给定 **30** 个电话号码。 <br/>  如果有 **150-199 个许可证** ，则给定 **40** 个电话号码。 <br/>  如果有 **200-499 个许可证** ，则给定 **65** 个电话号码。 <br/>  如果有 **500-749 个许可证** ，则给定 **90** 个电话号码。 <br/>  如果有 **750-999 个许可证** ，则给定 **110** 个电话号码。 <br/>  如果有 **1,000-1,249 个许可证** ，则给定 **125** 个电话号码。 <br/>  如果有**1250 1,499 许可证**是给定**135**电话号码。 <br/>  如果有 **1,500-1,999 个许可证** ，则给定 **160** 个电话号码。 <br/>  如果有 **2,000-2,999 个许可证** ，则给定 **210** 个电话号码。 <br/>  如果有 **3,000-6,999 个许可证** ，则给定 **420** 个电话号码。 <br/>  如果有 **7,000-9,999 个许可证** ，则给定 **500** 个电话号码。 <br/>  如果有 **10,000-14,999 个许可证** ，则给定 **600** 个电话号码。 <br/>  如果有 **15,000-19,999 个许可证** ，则给定 **700** 个电话号码。 <br/>  如果有 **20,000-49,999 个许可证** ，则给定 **1000** 个电话号码。 <br/>  如果有 **50,000 个以上许可证** ，则给定 **1500** 个电话号码。 <br/> |如果您有总共**51** **电话系统**和**音频会议**许可证，您可以获取**20**收费电话服务号码。 <br/> |
|免费服务号码  <br/> | 电话号码数等于总**电话系统**和**音频会议**的许可证数量，并使用以下： <br/>  如果有 **1-25 个许可证** ，则给定 **5** 个电话号码。 <br/>  如果有 **26-49 个许可证** ，则给定 **10** 个电话号码。 <br/>  如果有**50-99 许可证**是给定**20**电话号码。 <br/>  如果有 **100-149 个许可证** ，则给定 **30** 个电话号码。 <br/>  如果有 **150-199 个许可证** ，则给定 **40** 个电话号码。 <br/>  如果有 **200-499 个许可证** ，则给定 **65** 个电话号码。 <br/>  如果有 **500-749 个许可证** ，则给定 **90** 个电话号码。 <br/>  如果有 **750-999 个许可证** ，则给定 **110** 个电话号码。 <br/>  如果有 **1,000-1,249 个许可证** ，则给定 **125** 个电话号码。 <br/>  如果有**1250 1,499 许可证**是给定**135**电话号码。 <br/>  如果有 **1,500-1,999 个许可证** ，则给定 **160** 个电话号码。 <br/>  如果有 **2,000-2,999 个许可证** ，则给定 **210** 个电话号码。 <br/>  如果有 **3,000-6,999 个许可证** ，则给定 **420** 个电话号码。 <br/>  如果有 **7,000-9,999 个许可证** ，则给定 **500** 个电话号码。 <br/>  如果有 **10,000-14,999 个许可证** ，则给定 **600** 个电话号码。 <br/>  如果有 **15,000-19,999 个许可证** ，则给定 **700** 个电话号码。 <br/>  如果有 **20,000-49,999 个许可证** ，则给定 **1000** 个电话号码。 <br/>  如果有 **50,000 个以上许可证** ，则给定 **1500** 个电话号码。 <br/> |如果您有总共**1001年****电话系统**和**音频会议**许可证，您可以获取**125**免费电话服务号码。 <br/> <br/> **重要：**[Communications 字幕式帐单](set-up-communications-credits-for-your-organization.md)需要保留和使用免费电话号码。          |
   
> [!NOTE]
> 如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](transferring-phone-numbers-common-questions.md)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 