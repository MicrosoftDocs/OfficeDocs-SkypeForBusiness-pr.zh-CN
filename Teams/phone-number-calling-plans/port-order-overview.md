---
title: 什么是转网订单？
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: 大致了解什么是转口订单以及如何将电话号码从服务提供商转移到 Teams。
ms.openlocfilehash: d7ca4769dcd1f320a7d0b8a8ed18fdba5b06abbd
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615048"
---
# <a name="whats-a-port-order"></a>什么是转网订单？

如果当前拥有电话服务提供商或运营商，并且已有用户或服务的电话号码，则需要创建"转网订单"以将这些电话号码转移到Microsoft Teams。 当号码被移植时，你可以为用户和服务分配这些电话号码，例如音频会议 (会议网桥) 、自动助理和呼叫队列。
  
将电话号码移植到 Teams 后，Microsoft 将成为服务提供商，你可以断开服务与旧服务提供商或运营商之间的连接。

查看本文中的信息，熟悉号码移植。 之后，应已准备好创建转口订单并转移电话号码。 有关 [分步说明](transfer-phone-numbers-to-teams.md) ，请参阅"将电话号码转移到 Teams"。
  
## <a name="what-countries-or-regions-support-number-porting"></a>哪些国家/地区支持号码移植？

您可以在所有受支持的国家/地区转转或转移电话号码，但如何提交转口订单请求取决于电话号码来自的国家和地区。 有关支持号码移植的国家和地区的列表，请参阅"[管理组织的电话号码"。](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

目前 [，Microsoft](transfer-phone-numbers-to-teams.md) Teams 管理中心中的移植向导支持获取英国、美国和加拿大的电话号码。 若要获取其他国家/地区的电话号码，可以 [手动提交移植订单](manually-submit-port-order.md)。
  
## <a name="what-numbers-can-be-transferred"></a>哪些号码可以转移？

 **你可以转移**
  
通常，你可以转移来自受支持提供商的任何电话号码，包括：
  
- 座机电话号码。

- 移动设备电话号码，例如用于手机和平板电脑的电话号码。

    > [!NOTE]
    > 转移移动电话号码仅适用于美国和波多黎各。
  
- 收费电话号码。

- 免费电话号码。

    > [!NOTE]
    > 无法将通用国际免费 (UIFN) 转接给我们。 
  
- 服务电话号码，例如，用于会议网桥、自动助理等的电话号码。

- 传真电话号码，但是它们不能用于传真。 必须将其分配给用户。

- 来自电话提供商（如 Vonage 或 RingCentral）的电话号码。

- Skype for Business 混合电话号码。 如果要转移这些号码，请通过以下地址向我们发送电子邮件 <ptn@microsoft.com> ：

  **无法传输：**
  
    > [!NOTE]
    > 目前，你无法转移任何来自受支持国家/地区的电话号码，包括 VoIP 电话提供商提供的电话号码。 有关支持的国家/地区列表，请参阅音频会议和呼叫计划的国家和地区 [可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- 用于 DSL 线路或宽带 Internet 连接等数据连接的电话号码。

- 专用于收发传真的电话号码。

    如果有用于传真的现有专用电话号码，可以将这些号码转移到 Teams，但传真服务无法继续正常工作。 即使你拥有电话系统、国内呼叫计划或国际呼叫计划的许可证，Teams 客户也不可用传真服务。

    如果将电话号码移植到 Teams，可以将此电话号码分配给贵组织的用户，而不是将其用于传真。

    > [!NOTE]
    > 目前，在英国，我们不支持转移英国非地理号码，包括区号 0843、0844、0845、0870、0871、0872 的共享成本编号。
  
## <a name="what-information-do-i-need-to-provide"></a>我需要提供哪些信息？

你需要拥有当前运营商的所有帐户信息。 在移植订单中输入的信息大多位于当前服务提供商的最新帐单或发票上。 此外，还需要知道帐户上的姓名以及要移植的号码。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>什么是完整转网和部分转网？

将电话号码移植到 Teams 时，可以选择转移所有号码或部分号码。
  
- **完整端口** 此时，你将所有号码从当前服务提供商转移到 Teams。 当系统要求您提供要转移的电话号码时，您必须包括计费电话号码 ( BTN) 以及您的帐户上的所有其他电话号码。

    例如，假设 BTN  *为 +1 425-555-1234，*  并且想要将 25 个电话号码全部 (*+1 425-555-1235 到 1259*) 。 按照下面的说明转网号码时，你应该输入： **+14255551234 - +14255551259** 。

- **Partial-port** 此时，你仅将某些电话号码从当前服务提供商转移到 Teams。 当您想要移植与同一 BTN 绑定的一些电话号码时，不得包括** BTN 以及帐户上所有其他电话号码。

    例如，假设 BTN  *为 +1 425-555-1234，*  而您希望仅移植 25 个电话号码中的 5 个 (*+1 425-555-1235 到 1259*) 。 按照以下说明转移号码时，请输入 **：+1 425 555 1235 - +1 425 555 1239。**
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>我是否可以一次性针对我的所有号码提交一个携号转网请求？
<a name="bkmk_type_1"> </a>

需要为每个运营商和每种转网号码类型提交唯一的请求。
  
例如，你需要为下列每种号码类型提交唯一的携号转网请求：
  
- 本地收费电话号码，也称为订户号码或地理号码

- 带区号的免费号码，如：800、844、855、866、877 和 888

- 移动电话号码

- 可用于 Microsoft 365 或 Office 365 音频会议的服务号码。

下面详细了解如何为每种号码类型提交号码移植请求：
  
- **不同运营商** 提供的电话号码需要针对每个运营商提供的唯一号码移植请求。

- **带** 区号（如：800、844、855、866、877 和 888）的免费电话号码不能包含在包含其他类型的号码的号码移植请求中。 若要移植这些免费电话号码，必须 [手动提交移植订单](manually-submit-port-order.md)。 你无法将这些数字移植到 Microsoft Teams 管理中心。 有关详细信息，请参阅[为你的组织管理电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

    对于要转网的电话号码的国家/ (类型) LOA 地址，使用正确的授权书非常重要。 可以[在此处下载所需的 LOA。](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- **移动电话号码** 需使用 PIN 码来授权转移操作。 因此，它们需要单独的携号转网请求。

- **服务号码** 转网请求需单独提交。 它们不能与其他类型的数字一起提交。

## <a name="how-long-does-it-take-to-port-numbers"></a>转网号码需要多长时间？
<a name="bkmk_type_1"> </a>

完成移植订单请求后，需要 7-14 天进行处理。 但是，根据你的服务提供商，可能需要花费长达 30 天时间。 将电话号码移植到后，你向我们发送一封电子邮件，告知你已做好了准备。
  
若要检查转单状态，请在 Microsoft Teams 管理中心的左侧导航栏中转到语音电话号码，然后单击"订单  >  **历史记录"。** 每个端口订单状态都列在"状态 **"** 列中。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>用户（订阅者）电话号码是否可以转换为服务号码？
<a name="bkmk_type_1"> </a>

可以。 你只需要提交一个服务请求，在请求中提供你组织的租户 GUID 和你要转换的电话号码。 为此，请参阅["管理组织的电话号码"。](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>能否将我的号码从 Teams 移植到其他电话服务提供商或运营商？

若要将你的号码从 Teams 移植到其他运营商，你必须向新运营商提交请求。 还需要在 Microsoft Teams 管理中心设置移植 PIN。

若要定义移植 PIN，请在 Microsoft Teams 管理中心的左侧导航栏中转到"语音电话号码"，在页面右上角选择"管理移植 PIN"，然后输入  >  10 位数的 PIN。 

当你的新运营商联系我们提出移植请求时，我们将要求他们提供你定义的 PIN。

## <a name="common-mistakes-to-watch-out-for"></a>需要注意的常见错误
<a name="bkmk_type_1"> </a>

携号转网很简单。 但是，如果电话服务提供商出现问题、订单不完整、缺少信息或存在拼写错误，订单可能会混乱。
  
以下是我们发现客户在转网号码时最常见的错误。你无需致电客户支持，只需认真查看这些错误。
  
- 确保你提供的帐户信息与你的电话运营商记录的信息完全匹配。不匹配的信息是最常见的出错原因，并会导致你的转网订单延迟。请确认满足以下条件：

  - 有权更改帐户的姓名或人员是正确的。

  - 地址正确。

  - 帐户数量不正确。

  - BTN 是正确的。

- 请确保没有在这些电话号码上启用的高级呼叫控制功能，例如呼叫寻线、独特铃声。

- 确保你尚未提交任何新服务订单或者与你的当前服务提供商断开连接。

- 请确保所有号码来自同一个运营商和同一帐户。

- 确保你的服务处于活动状态。 冻结帐户将导致运营商无法更改帐户。 有权更改帐户的人员必须向当前运营商提交订单以取消冻结。 此过程可能需要一到三周的时间，具体取决于运营商。

## <a name="related-topics"></a>相关主题

- [你的转网订单的状态是什么？](port-order-status.md)
- [用于通话套餐的不同类型的电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
