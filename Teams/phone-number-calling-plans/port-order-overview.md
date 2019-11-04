---
title: 什么是端口订单？
ms.author: v-lanac
author: lanachin
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
f1keywords: ms.teamsadmincenter.voice.phonenumbers.porting.overview
ms.custom:
- Calling Plans
description: 大致了解哪些端口订单，以及如何将电话号码从服务提供商转移到团队。
ms.openlocfilehash: 4edaac3722e8fc37ca856b240171f923a0a99f66
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925623"
---
# <a name="whats-a-port-order"></a>什么是端口订单？

如果您当前有电话服务提供商或运营商，并且您的用户或服务已有电话号码，则需要创建 "*端口顺序*" 以将这些电话号码转移到 Microsoft 团队。 当号码被移植时，您可以将这些电话号码分配给您的用户和服务，例如音频会议（适用于会议桥）、自动助理和通话队列。
  
将您的电话号码移植到团队后，Microsoft 将成为您的服务提供商，您可以将您的服务与您的旧服务提供商或运营商断开连接。

查看本文中的信息，了解数字移植。 之后，你应该准备好创建一个端口订单并转移你的电话号码。 有关分步说明，请参阅[将电话号码转移到团队](transfer-phone-numbers-to-teams.md)。
  
## <a name="what-countries-or-regions-support-number-porting"></a>哪些国家或地区支持号码移植？

您可以将电话号码移植或转移到所有受支持的国家或地区，但如何提交端口订单请求取决于电话号码来自的国家或地区。 有关支持号码移植的国家和地区的列表，请参阅[管理您的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。
  
## <a name="what-numbers-can-be-transferred"></a>哪些号码可以转移？

 **您可以转移**
  
通常，你可以转移来自受支持的提供商的任何电话号码，包括：
  
- 座机电话号码。

- 移动设备的电话号码，例如用于移动电话和平板电脑的电话号码。

    > [!NOTE]
    > 转移手机号码仅适用于美国和波多黎各。
  
- 收费电话号码。

- 免费电话号码。

    > [!NOTE]
    > 通用国际 Freephone 号码（UIFN）无法转让给我们。 
  
- 服务电话号码，例如，用于会议网桥、自动助理等的电话号码。

- 传真电话号码，但是它们不能用于传真。 必须将它们分配给用户。

- 来自电话提供商（如 Vonage 或 RingCentral）的电话号码。

- Skype for Business 混合电话号码。 如果您想要转移这些号码，请通过电子<ptn@microsoft.com>邮件发送给我们。

  **您无法转移：**
  
    > [!NOTE]
    > 此时，您无法从受支持的国家或地区（包括来自 VoIP 电话提供商的电话号码）传输任何电话号码或号码。 有关受支持的国家/地区的列表，请参阅[音频会议和通话计划的国家和地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- 用于 DSL 线路或宽带 Internet 连接等数据连接的电话号码。

- 专用于收发传真的电话号码。

    如果您有用于传真的现有专用电话号码，您*可以*将这些号码转移到团队，但您的传真服务不会继续按预期工作。 传真服务对团队客户不可用，即使你拥有电话系统、国内呼叫计划或国际呼叫计划的许可证也是如此。

    如果你将电话号码移植到团队，则可以将此电话号码分配给组织中的用户，而不是使用它进行传真。

    > [!NOTE]
    > 目前，我们目前不支持转移 UK 非地理号码，包括区号0843、0844、0845、0870、0871、0872的共享成本号码。
  
## <a name="what-information-do-i-need-to-provide"></a>我需要提供哪些信息？

您需要拥有当前运营商的所有帐户信息。 您在 "端口订单" 中输入的信息通常位于当前服务提供商的最新帐单或发票上。 您还需要知道其姓名在帐户上以及您想要移植的号码。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>什么是完整转网和部分转网？

当您将电话号码移植到团队时，您可以选择转移所有号码或其中的一些号码。
  
- **完整端口**这是将当前服务提供商的所有号码转移到团队的时候。 当系统要求您提供要转移的电话号码时，您必须在您的帐户上*包含*帐单电话号码（BTN）以及其他所有电话号码。

    例如，假设您的 BTN 是 *+ 1 425-555-1234* ，并且您想要将您的所有25个电话号码（*+ 1 425-555-1235 至 1259*）移植到一起。 按照下面的说明转网号码时，你应该输入： **+14255551234 - +14255551259** 。

- **部分端口**这是仅将当前服务提供商的一些电话号码转移到团队的时候。 如果您想要将某些电话号码移植到同一 BTN，您的 * **不得包含** * BTN 以及您的帐户上的其他所有电话号码。

    例如，假设您的 BTN 是 *+ 1 425-555-1234* ，并且您只想移植25个电话号码的5个（*+ 1 425-555-1235 至 1259*）。 按照以下说明转移您的号码时，您可以输入： **+ 1 425 555 1235-+ 1 425 555 1239**。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>我是否可以一次性针对我的所有号码提交一个携号转网请求？
<a name="bkmk_type_1"> </a>

需要为每个运营商和每种转网号码类型提交唯一的请求。
  
例如，你需要为下列每种号码类型提交唯一的携号转网请求：
  
- 本地收费号码，也称为订户号码或地理号码

- 带区号的免费号码，如：800、844、855、866、877 和 888

- 移动电话号码

- 可用于 Office 365 中音频会议的服务号码。

下面是有关如何为每种类型的号码提交号码移植请求的详细信息：
  
- 不同运营商提供的**电话号码**需要对每个运营商的号码进行唯一的移植请求。

- 带有区号的免费**电话号码**，如：800、844、855、866、877和888不能包含在具有其他类型的号码的数字移植请求中。 若要移植这些免费号码，您必须[手动提交一个端口订单](manually-submit-port-order.md)。 您无法将这些号码移植到 Microsoft 团队管理中心。 有关详细信息，请参阅[为你的组织管理电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

    对于要移植的国家和电话号码的类型，请务必使用正确的授权书（LOA）。 你可以在[此处下载所需的 LOA](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- **移动电话号码** 需使用 PIN 码来授权转移操作。 因此，它们需要单独的携号转网请求。

- **服务号码** 转网请求需单独提交。 它们不能与其他类型的号码一起提交。

## <a name="how-long-does-it-take-to-port-numbers"></a>转网号码需要多长时间？
<a name="bkmk_type_1"> </a>

完成了端口订单请求后，将在7-14 天内处理。 但是，根据你的服务提供商，可能需要花费长达 30 天时间。 拨打电话号码后，您将收到一封电子邮件，让您可以使用。
  
若要检查您的端口顺序的状态，请在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **电话号码**"，然后单击 "**订单历史记录**"。 每个端口订单状态都在 "**状态**" 列中列出。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>用户（订阅者）电话号码是否可以转换为服务号码？
<a name="bkmk_type_1"> </a>

可以。 你只需要提交一个服务请求，在请求中提供你组织的租户 GUID 和你要转换的电话号码。 若要执行此操作，请参阅[管理你的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="common-mistakes-to-watch-out-for"></a>需要注意的常见错误
<a name="bkmk_type_1"> </a>

携号转网很简单。 您的订单可能会 messed，但是如果电话服务提供商出现问题，订单不完整且缺少信息，或者存在拼写错误。
  
以下是我们发现客户在转网号码时最常见的错误。你无需致电客户支持，只需认真查看这些错误。
  
- 确保你提供的帐户信息与你的电话运营商记录的信息完全匹配。不匹配的信息是最常见的出错原因，并会导致你的转网订单延迟。请确认满足以下条件：

  - 授权对帐户进行更改的名称或人员是正确的。

  - 地址正确。

  - 帐户数量不正确。

  - BTN 是正确的。

- 请确保没有高级呼叫控制功能，例如，在这些电话号码上启用了呼叫查寻、区别性铃声。

- 确保你尚未提交任何新服务订单或者与你的当前服务提供商断开连接。

- 请确保所有号码来自同一个运营商和同一帐户。

- 确保你的服务处于活动状态。 冻结帐户将导致运营商无法更改帐户。 授权对帐户进行更改的人员必须向当前运营商提交订单才能删除冻结。 此过程可能需要一至三周的时间，具体取决于运营商。

## <a name="related-topics"></a>相关主题

- [您的端口订单的状态是什么？](port-order-status.md)
- [用于通话套餐的不同类型的电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)