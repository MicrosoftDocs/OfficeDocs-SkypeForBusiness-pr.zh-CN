---
title: 有关移植的详细信息
author: CarolynRowe
ms.author: crowe
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
description: 获取将电话号码移植到 Microsoft Teams 所需的指导。
ms.openlocfilehash: 6edb3f617a890659d6aeedb817b38fba4a2c1da1
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790357"
---
# <a name="more-information-about-porting"></a>有关移植的详细信息

在这里，你将找到有关将电话号码移植到 Microsoft Teams 的详细信息。

有关完整的分步说明，请参阅 [将电话号码传输到 Teams](transfer-phone-numbers-to-teams.md)。

如果需要帮助或需要获取更多电话号码，请联系 [TNS 服务台帮助](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)。

## <a name="port-order-account-information"></a>端口订单帐户信息

当你在移植向导的 **“添加帐户信息** ”页上提交端口订单时，你将输入在 LOA 中提供的几乎所有相同的信息，包括：
  
- 服务提供商或运营商的帐号
    
- 付费电话号码 (BTN)
    
- PIN - 如果当前服务提供商或运营商需要
    
- 组织名称
    
    > [!NOTE]
    > 这仅接受 25 个字符，包括空格。 如果组织名称超过 25 个字符，则将提交名称的前 25 个字符，并且仍将处理端口顺序。
  
- 有权对帐户进行更改的人员的姓名
    
    > [!NOTE]
    > 这仅接受 15 个字符，包括空格。 如果授权人员的姓名超过 15 个字符，将提交姓名的前 15 个字符，仍将处理转网订单。 
  
- 服务地址
  
若要简化提交端口订单并避免错误，请确保执行以下操作：
  
- 删除任何 (功能，例如与数字关联) 搜寻组。 请确保这些电话号码上未启用高级呼叫控制功能，例如呼叫搜寻或独特环。
    
- 确保未下任何新的服务订单或与当前服务提供商断开连接。
    
- 请确保所有号码来自同一个运营商和同一帐户。
    
- 确保你提供的帐户信息与你的电话运营商记录的信息完全匹配。 信息不匹配是导致错误的最常见原因，可能会延迟端口顺序。
    
> [!CAUTION]
> 请勿断开服务提供商或运营商的连接。 必须保持以前的服务处于活动状态，才能将电话号码移植到 Teams。 请勿冻结服务提供商或运营商的帐户。 冻结帐户将导致运营商无法更改帐户。 获得授权的用户需要向当前运营商提交订单来取消冻结。 此过程可能需要一到三周的时间，具体取决于承运商。

## <a name="authorized-person-on-the-account"></a>帐户上的授权人员

在移植向导中，必须输入有权使用服务提供商或运营商更改帐户的人员的姓名。 该名称不用于处理端口顺序，但在发生争议时使用，或者在移植数字时出现错误时使用。 此人负责端口订单的授权书 (LOA) 。
  
> [!NOTE]
> 该框限制为 15 个字符 (包括空格) 。 框中没有完整名称不会延迟或取消端口订单。
  
## <a name="whats-my-billing-telephone-number"></a>我的计费电话号码是什么？

 (BTN) 的计费电话号码是账单上包含的主要电话号码，由服务提供商或运营商计费。 如果要从只有一个电话号码的帐户传输电话号码，则需要输入此电话号码。 如果要从拥有多个帐户的帐户传输电话号码，可以查看帐单或联系服务提供商或运营商以确定你的帐户的 BTN。

## <a name="what-should-i-put-in-for-the-account-number"></a>应该为帐号放什么？

通常，你可以从服务提供商或运营商处找到任何帐单或发票上的帐号，也可以登录到运营商的网站。 如果仍然不知道帐户号，可以联系服务提供商或运营商来获取它。
  
> [!CAUTION]
>  输入服务提供商或运营商帐户号时，请务必确保不使用空格、短划线或连字符。

## <a name="what-should-i-put-in-for-the-organization-name"></a>我应该为组织名称输入哪些内容？

这是组织的名称。 组织名称限制为 25 个字符，其中包括空格。 公司名称不用于处理端口订单请求。 在发生争执时或在转网电话号码时出现错误时，将使用它。 如果无法将公司的整个名称装在框中，则不会延迟或取消端口订单。
  
## <a name="what-should-i-put-in-for-the-service-address"></a>应为服务地址放入哪些内容？

服务地址不同于已向电话服务提供商或运营商注册的计费或紧急地址。 如果不知道这一点，请联系服务提供商或运营商，了解帐户上列出的服务地址。

## <a name="how-should-i-enter-the-phone-numbers"></a>应如何输入电话号码？
<a name="bkadding"> </a>

提交端口订单时，必须使用格式正确的 CSV 文件提交电话号码。 以下是 CSV 文件的要求：

 - 可以为文件提供所需的任何名称。
 - 该文件只能有一个标题为 PhoneNumber 的列。
 - 每个电话号码必须位于单独的行上。
 - 电话号码只能是数字或 E.164 格式。
 - 电话号码格式必须与所选国家/地区匹配。 例如，如果在移植向导中选择英国，请使用 44，即国家/地区代码，后跟电话号码和正确的数字。 例如，4420812341234。

## <a name="how-do-i-see-the-status-of-my-port-order"></a>如何实现查看我的端口订单的状态？

查看 [端口订单的状态如何？](port-order-status.md)

## <a name="related-topics"></a>相关主题

- [什么是转网订单？](port-order-overview.md)
- [用于通话套餐的不同类型的电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
