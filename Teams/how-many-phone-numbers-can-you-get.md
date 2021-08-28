---
title: 可以获得多少个电话号码？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.quantity
- seo-marvel-mar2020
description: 根据号码的类型和许可证数量Microsoft Teams可以获取多少个电话号码。
ms.openlocfilehash: 8ee72f7af039fae5fc5f0a9b4983cc7d7691b2ce
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598526"
---
# <a name="how-many-phone-numbers-can-you-get"></a>可以获得多少个电话号码？

在查找并获取组织的电话号码时，获取的电话号码会比已分配许可证的电话号码多。 但这取决于你已购买并分配的电话号码类型和许可证类型。 可以单击["呼叫计划](different-kinds-of-phone-numbers-used-for-calling-plans.md)"使用的不同类型的电话号码，了解呼叫计划中使用的不同Microsoft Teams。
  
可以在 Microsoft Teams 管理中心的"获取电话号码"页面上查看可以获取的电话号码数，也可以运行[Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/Get-CsOnlineTelephoneNumberAvailableCount) cmdlet。
  
> [!IMPORTANT]
> [!重要信息] 以下限制不包括你已经转网或转移到 Microsoft 的电话号码。 
  
## <a name="how-many-phone-numbers-you-can-get"></a>你可以获取多少个电话号码？

||||
|:-----|:-----|:-----|
|**下面是电话号码类型** <br/> |**如何获取电话号码总数？** <br/> |**下面是一个示例** <br/> |
|用户（订阅者）号码  <br/> |电话号码数等于国内呼叫计划和/或国内和国际呼叫计划许可证总数乘以 1.1 + 10 个其他电话号码。  <br/> |如果我总共有 50 个用户具有国内呼叫计划和/或国内和国际呼叫计划，你可以获取 **65** 个电话号码 **(50 x 1.1 + 10**) 。 <br/> |
|收费服务号码  <br/> | 电话号码数等于音频会议许可证 **电话系统****总数**，并执行以下操作： <br/>  如果有 **1-25 个许可证** ，则给定 **5** 个电话号码。 <br/>  如果有 **26-49 个许可证** ，则给定 **10** 个电话号码。 <br/>  如果有 **50-99 个许可证** ， **则给定 20** 个电话号码。 <br/>  如果有 **100-149 个许可证** ，则给定 **30** 个电话号码。 <br/>  如果有 **150-199 个许可证** ，则给定 **40** 个电话号码。 <br/>  如果有 **200-499 个许可证** ，则给定 **65** 个电话号码。 <br/>  如果有 **500-749 个许可证** ，则给定 **90** 个电话号码。 <br/>  如果有 **750-999 个许可证** ，则给定 **110** 个电话号码。 <br/>  如果有 **1,000-1,249 个许可证** ，则给定 **125** 个电话号码。 <br/>  如果有 **1，250-1，499** 个许可证， **则给定 135** 个电话号码。 <br/>  如果有 **1,500-1,999 个许可证** ，则给定 **160** 个电话号码。 <br/>  如果有 **2,000-2,999 个许可证** ，则给定 **210** 个电话号码。 <br/>  如果有 **3,000-6,999 个许可证** ，则给定 **420** 个电话号码。 <br/>  如果有 **7,000-9,999 个许可证** ，则给定 **500** 个电话号码。 <br/>  如果有 **10,000-14,999 个许可证** ，则给定 **600** 个电话号码。 <br/>  如果有 **15,000-19,999 个许可证** ，则给定 **700** 个电话号码。 <br/>  如果有 **20,000-49,999 个许可证** ，则给定 **1000** 个电话号码。 <br/>  如果有 **50,000 个以上许可证** ，则给定 **1500** 个电话号码。 <br/> |如果你总共有 **51** 个 **电话系统音频会议****许可证，** 你可以获取 **20 个** 收费服务号码。 <br/> |
|免费服务号码  <br/> | 电话号码数等于音频会议许可证 **电话系统****总数**，并执行以下操作： <br/>  如果有 **1-25 个许可证** ，则给定 **5** 个电话号码。 <br/>  如果有 **26-49 个许可证** ，则给定 **10** 个电话号码。 <br/>  如果有 **50-99 个许可证** ， **则给定 20** 个电话号码。 <br/>  如果有 **100-149 个许可证** ，则给定 **30** 个电话号码。 <br/>  如果有 **150-199 个许可证** ，则给定 **40** 个电话号码。 <br/>  如果有 **200-499 个许可证** ，则给定 **65** 个电话号码。 <br/>  如果有 **500-749 个许可证** ，则给定 **90** 个电话号码。 <br/>  如果有 **750-999 个许可证** ，则给定 **110** 个电话号码。 <br/>  如果有 **1,000-1,249 个许可证** ，则给定 **125** 个电话号码。 <br/>  如果有 **1，250-1，499** 个许可证， **则给定 135** 个电话号码。 <br/>  如果有 **1,500-1,999 个许可证** ，则给定 **160** 个电话号码。 <br/>  如果有 **2,000-2,999 个许可证** ，则给定 **210** 个电话号码。 <br/>  如果有 **3,000-6,999 个许可证** ，则给定 **420** 个电话号码。 <br/>  如果有 **7,000-9,999 个许可证** ，则给定 **500** 个电话号码。 <br/>  如果有 **10,000-14,999 个许可证** ，则给定 **600** 个电话号码。 <br/>  如果有 **15,000-19,999 个许可证** ，则给定 **700** 个电话号码。 <br/>  如果有 **20,000-49,999 个许可证** ，则给定 **1000** 个电话号码。 <br/>  如果有 **50,000 个以上许可证** ，则给定 **1500** 个电话号码。 <br/> |如果你总共有 **1001** 个 **电话系统音频会议** 许可证，你可以获取 **125** 个免费服务号码。 <br/> <br/> **重要提示**[：需要支付](set-up-communications-credits-for-your-organization.md)通信信用额度才能保留和使用免费电话号码。          |
   
> [!NOTE]
> 如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
