---
title: 有关移植的详细信息
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1keyword: ms.teamsadmincenter.voice.phonenumbers.porting.moreinfo
description: 获得将电话号码移植到 Microsoft 团队所需的指南。
ms.openlocfilehash: 2fe77c4efb8728a10e433866ddf10309f51934a3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925193"
---
# <a name="more-information-about-porting"></a>有关移植的详细信息

在这里，你可以找到有关将电话号码移植到 Microsoft 团队的详细信息。

有关完整的分步说明，请参阅[将电话号码转移给团队](transfer-phone-numbers-to-teams.md)。

如果需要帮助，或者如果需要获取更多电话号码，请联系[PSTN 服务台帮助](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

## <a name="port-order-account-information"></a>端口订单帐户信息

在迁移向导的 "**添加帐户信息**" 页面上，您将输入您在 LOA 中提供的几乎所有相同信息，包括：
  
- 服务提供商或运营商的帐号
    
- 付费电话号码 (BTN)
    
- PIN-如果你的当前服务提供商或运营商需要
    
- 组织名称
    
    > [!NOTE]
    > 这将仅接受25个字符（包括空格）。 如果组织名称超过25个字符，将提交名称的前25个字符，并且将仍然处理该端口顺序。
  
- 授权对帐户进行更改的人员的姓名
    
    > [!NOTE]
    > 这将仅接受15个字符（包括空格）。 如果授权人员的姓名超过 15 个字符，将提交姓名的前 15 个字符，仍将处理转网订单。 
  
- 服务地址
  
若要轻松地提交端口顺序并避免错误，请确保执行以下操作：
  
- 删除与您的号码相关联的任何功能（如查寻组）。 确保没有在这些电话号码上启用的高级呼叫控制功能，例如呼叫查寻或独特震铃。
    
- 确保你未下任何新服务订单或与当前服务提供商断开连接。
    
- 请确保所有号码来自同一个运营商和同一帐户。
    
- 确保你提供的帐户信息与你的电话运营商记录的信息完全匹配。 不匹配的信息是错误的最常见原因，并且可能会延迟您的端口顺序。
    
> [!CAUTION]
> 不要将您的服务与您的服务提供商或运营商断开连接。 您必须让以前的服务处于活动状态才能将您的电话号码移植到团队。 不要通过您的服务提供商或运营商冻结您的帐户。 冻结帐户将导致运营商无法更改帐户。 获得授权的用户需要向当前运营商提交订单来取消冻结。 此过程可能需要一至三周，具体取决于运营商。

## <a name="authorized-person-on-the-account"></a>帐户的授权人员

在 "移植向导" 中，您必须输入有权通过服务提供商或运营商对帐户进行更改的人员的姓名。 该名称不用于处理端口顺序，而是用于争议的情况，或者当号码已移植时出现错误。 此人负责为端口订单授权（LOA）。
  
> [!NOTE]
> 该框限制为15个字符（包括空格）。 在框中没有完整的名称不会延迟或取消该端口顺序。
  
## <a name="whats-my-billing-telephone-number"></a>我的付费电话号码是什么？

帐单电话号码（BTN）是您的帐单上包含的主要电话号码，由您的服务提供商或运营商支付。 如果您要从仅有一个电话号码的帐户转移电话号码，您需要输入此电话号码。 如果您要从具有多个帐户的帐户转移电话号码，您可以查看帐单或联系您的服务提供商或运营商以确定您的帐户的 BTN。

## <a name="what-should-i-put-in-for-the-account-number"></a>我应该将哪些内容放入帐户号码？

通常，您可以在您的服务提供商或运营商提供的任何帐单或发票上查找帐号，或者您可以登录到您的运营商的网站。 如果您仍然不知道帐户号码，您可以与您的服务提供商或运营商联系以获取它。
  
> [!CAUTION]
>  请务必在输入服务提供商或运营商帐号时不要使用空格、短划线或连字符。

## <a name="what-should-i-put-in-for-the-organization-name"></a>我应该为组织名称添加哪些内容？

这是您的组织的名称。 组织名称限制为25个字符（包括空格）。 公司名称不用于处理端口订单请求。 在争议的情况下使用它，或者在拨打电话号码时出现错误。 如果在框中无法容纳公司的整个名称，则不会延迟或取消该端口顺序。
  
## <a name="what-should-i-put-in-for-the-service-address"></a>我应该输入什么作为服务地址？

服务地址与您在电话服务提供商或运营商处注册的帐单或紧急地址不同。 如果您不知道此问题，请与您的服务提供商或运营商联系，了解您的帐户上列出的服务地址。

## <a name="how-should-i-enter-the-phone-numbers"></a>如何输入电话号码？
<a name="bkadding"> </a>

提交端口顺序时，必须使用格式正确的 CSV 文件来提交您的电话号码。 下面是 CSV 文件的要求：

 - 你可以为文件指定所需的任何名称。
 - 该文件必须仅有一列的标题名为电话号码。
 - 每个电话号码必须位于单独的一行。
 - 电话号码只能是数字或以164格式显示。
 - 电话号码格式必须与您选择的国家或地区相匹配。 例如，如果在移植向导中选择英国，请使用44（国家/地区代码），后跟具有正确位数的电话号码。 例如，4420812341234。

## <a name="how-do-i-see-the-status-of-my-port-order"></a>如何查看我的 "我的端口" 订单的状态？

查看[您的端口订单的状态是什么？](port-order-status.md)

## <a name="related-topics"></a>相关主题

- [什么是端口订单？](port-order-overview.md)
- [用于通话套餐的不同类型的电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
