---
title: 有关移植的信息
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tonysmit,jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.phonenumbers.porting.moreinfo
description: 获取将电话号码移植到 Microsoft Teams。
ms.openlocfilehash: 5ed15432517ae6ba5709e699c89c341dc86f30f2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598386"
---
# <a name="more-information-about-porting"></a>有关移植的信息

可在此处找到有关将电话号码移植到Microsoft Teams。

有关完整的分步说明，请参阅[将电话号码转移到 Teams。](transfer-phone-numbers-to-teams.md)

如果你需要帮助或需要获取更多电话号码，请联系 [PSTN 服务台帮助](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

## <a name="port-order-account-information"></a>移植订单帐户信息

在移植向导的"添加帐户信息"页上提交移植订单时，你几乎会输入在 LOA 中提供的所有相同信息，包括：
  
- 服务提供商或运营商的帐户编号
    
- 付费电话号码 (BTN)
    
- PIN - 如果当前服务提供商或运营商需要
    
- 组织名称
    
    > [!NOTE]
    > 这仅接受 25 个字符，包括空格。 如果组织名称超过 25 个字符，将提交名称的前 25 个字符，并且仍将处理移植订单。
  
- 有权对帐户进行更改的人员的姓名
    
    > [!NOTE]
    > 这仅接受 15 个字符，包括空格。 如果授权人员的姓名超过 15 个字符，将提交姓名的前 15 个字符，仍将处理转网订单。 
  
- 服务地址
  
若要轻松提交移植订单并避免错误，请确保执行以下操作：
  
- 删除与 (相关联的任何功能，) "寻道组"。 确保这些电话号码上未启用高级呼叫控制功能，例如"呼叫寻线"或"独特圈"。
    
- 确保尚未下任何新的服务订单或与当前服务提供商断开连接。
    
- 请确保所有号码来自同一个运营商和同一帐户。
    
- 确保你提供的帐户信息与你的电话运营商记录的信息完全匹配。 不匹配的信息是最常见的错误原因，可能会延迟你的移植订单。
    
> [!CAUTION]
> 不要断开服务与服务提供商或运营商的连接。 必须保持以前的服务处于活动状态，才能将电话号码移植到Teams。 不要冻结你的服务提供商或运营商的帐户。 冻结帐户将导致运营商无法更改帐户。 获得授权的用户需要向当前运营商提交订单来取消冻结。 此过程可能需要一到三周的时间，具体取决于运营商。

## <a name="authorized-person-on-the-account"></a>帐户的授权人员

在移植向导中，必须输入有权对服务提供商或运营商的帐户进行更改的人员的姓名。 该名称不用于处理移植订单，但用于争议，或者当号码移植时存在错误的情况。 此人负责处理转 (LOA) 授权书。
  
> [!NOTE]
> 此框限制为 15 个字符， (空格) 。 框中没有完整名称不会延迟或取消移植订单。
  
## <a name="whats-my-billing-telephone-number"></a>我的付费电话号码是什么？

BTN (收费电话号码) 包含在帐单上且由服务提供商或运营商计费的主电话号码。 如果要从只有一个电话号码的帐户转移电话号码，则需要输入此电话号码。 如果要从具有多个帐户转移电话号码，可以查看帐单或联系服务提供商或运营商，确定您的帐户的 BTN 是什么。

## <a name="what-should-i-put-in-for-the-account-number"></a>我应该为帐号放入什么？

通常，可以在服务提供商或运营商提供的任何帐单或发票上找到帐号，也可以登录到运营商的网站。 如果仍然不知道帐号，可以联系服务提供商或运营商获取。
  
> [!CAUTION]
>  请务必确保在输入服务提供商或运营商帐号时不使用空格、短划线或连字符。

## <a name="what-should-i-put-in-for-the-organization-name"></a>我应该输入什么作为组织名称？

这是组织的名称。 组织名称限制为 25 个字符，其中包括空格。 公司名称不用于处理移植订单请求。 它在存在争议时或当电话号码被移植时出错时使用。 如果框中不能容纳公司全名，它不会延迟或取消移植订单。
  
## <a name="what-should-i-put-in-for-the-service-address"></a>我应该输入什么作为服务地址？

服务地址不同于向电话服务提供商或运营商注册的帐单或紧急地址。 如果不知道此地址，请联系服务提供商或运营商，了解帐户上列出的服务地址。

## <a name="how-should-i-enter-the-phone-numbers"></a>如何输入电话号码？
<a name="bkadding"> </a>

提交移植订单时，必须使用格式正确的 CSV 文件来提交电话号码。 下面是 CSV 文件的要求：

 - 你可以为文件指定任何需要的名称。
 - 该文件必须只有一列，其标头名为 PhoneNumber。
 - 每个电话号码必须位于单独的行中。
 - 电话数字只能是数字，也可以采用 E.164 格式。
 - 电话号码格式必须与所选国家/地区匹配。 例如，如果在移植向导中选择"英国"，请使用 44，即国家/地区代码，后跟具有正确位数的电话号码。 例如，4420812341234。

## <a name="how-do-i-see-the-status-of-my-port-order"></a>如何查看我的移植订单的状态？

[请参阅你的移植订单的状态是什么？](port-order-status.md)

## <a name="related-topics"></a>相关主题

- [什么是转网订单？](port-order-overview.md)
- [用于通话套餐的不同类型的电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
