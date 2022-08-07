---
title: 什么是转网订单？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: 大致了解什么是端口订单，以及如何将电话号码从服务提供商传输到 Teams。
ms.collection:
- M365-voice
- m365initiative-voice
ms.openlocfilehash: e9f267bfdb56558245fecefe240f2c09c07d4783
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270867"
---
# <a name="whats-a-port-order"></a>什么是转网订单？

如果当前拥有电话服务提供商或运营商，并且已经为用户或服务提供电话号码，则需要创建一个“*端口订单*”，将这些电话号码传输到 Microsoft Teams。 移植号码后，可以将这些电话号码分配给用户和服务，例如会议桥) 、自动助理和呼叫队列的音频会议 (。
  
将电话号码移植到 Teams 后，Microsoft 将成为你的服务提供商，你可以与旧的服务提供商或运营商断开服务连接。

查看本文中的信息以熟悉数字移植。 之后，应准备好创建端口订单并传输电话号码。 有关分步说明，请参阅 [将电话号码传输到 Teams](transfer-phone-numbers-to-teams.md) 。
  
## <a name="what-countries-or-regions-support-number-porting"></a>哪些国家或地区支持数字移植？

可以在所有受支持的国家或地区中移植或传输电话号码，但如何提交端口订单请求取决于电话号码来源的国家或地区。 有关支持号码移植的国家和地区的列表，请参阅 [管理组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。  

目前，Microsoft Teams 管理中心的[移植向导](transfer-phone-numbers-to-teams.md)支持获取英国、美国和加拿大的电话号码。 若要获取其他国家和地区的电话号码，可以 [手动提交端口订单](manually-submit-port-order.md)。
  
## <a name="what-numbers-can-be-transferred"></a>哪些号码可以转移？

 **可以转移**
  
一般情况下，可以从受支持的提供商传输任何电话号码，包括：
  
- 座机电话号码。

- 移动设备电话号码，例如用于手机和平板电脑的电话号码。

    > [!NOTE]
    > 传输移动号码仅在美国和波多黎各可用。
  
- 收费电话号码。

- 免费电话号码。

    > [!NOTE]
    > 无法将通用国际免费电话号码 (UIFN) 转移到我们。
    > 免费电话号码的移植可用性可能因国家/地区而异。 若要查找我们的详细信息，请参阅您的国家或地区特定文档，以查看对移植服务的可用支持。 
  
- 服务电话号码，例如，用于会议网桥、自动助理等的电话号码。

- 传真电话号码，但是它们不能用于传真。 必须将它们分配给用户。

- 来自电话提供商（如 Vonage 或 RingCentral）的电话号码。

- 如果要将混合电话号码移植 (从直接路由或运营商连接迁移到呼叫计划) 请联系 [电话号码服务团队](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)，请确保包含说明这些是混合电话号码的便笺。

**无法传输：**
  
> [!NOTE]
> 目前，无法传输任何不来自受支持国家或地区的电话号码，包括来自 VoIP 电话提供商的电话号码。 有关受支持的国家/地区列表，请参阅 [音频会议和通话套餐的国家/地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- 用于 DSL 线路或宽带 Internet 连接等数据连接的电话号码。

- 专用于收发传真的电话号码。

    如果你有用于传真的现有专用电话号码，  *可以将*  这些号码转移到 Teams，但传真服务不会继续按预期工作。 即使你拥有电话系统、国内呼叫计划或国际通话套餐的许可证，Teams 客户也无法使用传真服务。

    如果将电话号码移植到 Teams，则可以将此电话号码分配给组织中的用户，而不是将其用于传真。

> [!NOTE]
> 目前，在英国，我们目前不支持转移英国非地理号码，包括区号 0843、0844、0845、0870、0871、0872 的共享成本号。
  
## <a name="what-information-do-i-need-to-provide"></a>我需要提供哪些信息？

需要拥有当前运营商的所有帐户信息。 在端口订单中输入的信息大多位于当前服务提供商的最新帐单或发票上。 还需要知道帐户上的名称以及要移植的数字。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>什么是完整转网和部分转网？

将电话号码移植到 Teams 时，可以选择转移所有号码或部分电话号码。
  
- **全端口** 此时会将所有号码从当前服务提供商传输到 Teams。 当系统询问要转接的电话号码时， *必须包括* (BTN) 的计费电话号码以及帐户上所有其他电话号码。

    例如，假设 BTN  *是 +1 425-555-1234*  ，你想要移植所有 25 个电话号码 (*+1 425-555-1235 到 1259*) 。 按照下面的说明转网号码时，你应该输入： **+14255551234 - +14255551259** 。

- **部分端口** 此时，仅将部分电话号码从当前服务提供商传输到 Teams。 如果要移植绑定到同一 BTN 的一些电话号码，则不得 *包含* BTN 以及帐户上所有其他电话号码。

    例如，假设 BTN  *是 +1 425-555-1234*  ，你只想移植 25 个电话号码中的 5 个， (*+1 425-555-1235 到 1259*) 。 按照以下说明传输号码时，将输入： **+1 425 555 1235 - +1 425 555 1239**。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>我是否可以一次性针对我的所有号码提交一个携号转网请求？
<a name="bkmk_type_1"> </a>

需要为每个运营商和每种转网号码类型提交唯一的请求。
  
例如，你需要为下列每种号码类型提交唯一的携号转网请求：
  
- 本地通行费号码，也称为订阅者号码或地理号码

- 带区号的免费号码，如：800、844、855、866、877 和 888

- 移动电话号码

- 可在 Microsoft 365 或 Office 365 中用于音频会议的服务编号。

下面是有关如何为每种类型的数字提交数字移植请求的详细信息：
  
- 不同运营商提供的 **电话号码** 需要为每个运营商提供号码的唯一移植请求。

- 包含区域代码（例如：800、844、855、866、877 和 888）的 **免费号码** 不能包含在包含其他类型的号码的号码移植请求中。 若要移植这些免费号码，必须 [手动提交端口订单](manually-submit-port-order.md)。 无法在 Microsoft Teams 管理中心中移植这些数字。 有关详细信息，请参阅[为你的组织管理电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

    对于要移植的国家/地区和电话号码类型，请务必使用正确的授权书 (LOA) 。 可以 [在此处下载所需的 LOA](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- **移动电话号码** 需使用 PIN 码来授权转移操作。 因此，它们需要单独的携号转网请求。

- **服务号码** 转网请求需单独提交。 不能使用其他类型的数字提交它们。

## <a name="how-long-does-it-take-to-port-numbers"></a>转网号码需要多长时间？
<a name="bkmk_type_1"> </a>

完成端口订单请求后，需要 7 到 14 天的处理时间。 但是，根据你的服务提供商，可能需要花费长达 30 天时间。 转网电话号码后，你将收到一封来自我们的电子邮件，让你知道你最好转到。
  
若要检查端口订单的状态，请在 Microsoft Teams 管理中心的左侧导航中转到 **“语音** > **电话号码**”，然后单击 **“订单历史记录**”。 状态 **列中** 列出了每个端口订单状态。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>用户（订阅者）电话号码是否可以转换为服务号码？
<a name="bkmk_type_1"> </a>

可以。 你只需要提交一个服务请求，在请求中提供你组织的租户 GUID 和你要转换的电话号码。 若要执行此操作，请参阅 [管理组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>是否可以将我的号码从 Teams 移植到其他电话服务提供商或运营商？

若要将号码从 Teams 移植到其他运营商，必须使用新运营商提交请求。 还需要在 Microsoft Teams 管理中心设置移植 PIN。

若要定义移植 PIN，请在 Microsoft Teams 管理中心的左侧导航中转到 **语音** > **电话号码**，在页面右上角选择 **“管理移植 PIN**”，然后输入 10 位 PIN。

当你的新运营商与我们联系移植请求时，我们将要求他们提供你定义的 PIN。

如果需要进一步设置 PIN，请联系 [电话号码服务团队](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

## <a name="common-mistakes-to-watch-out-for"></a>需要注意的常见错误
<a name="bkmk_type_1"> </a>

携号转网很简单。 但是，如果电话服务提供商出现问题、订单不完整且缺少信息或有拼写错误，订单可能会混乱。
  
以下是我们发现客户在转网号码时最常见的错误。你无需致电客户支持，只需认真查看这些错误。
  
- 确保你提供的帐户信息与你的电话运营商记录的信息完全匹配。不匹配的信息是最常见的出错原因，并会导致你的转网订单延迟。请确认满足以下条件：

  - 有权对帐户进行更改的姓名或人员是正确的。

  - 地址正确。

  - 帐户数量不正确。

  - BTN 正确。

- 请确保没有在这些电话号码上启用的高级呼叫控制功能，例如呼叫搜寻、独特环。

- 确保你尚未提交任何新服务订单或者与你的当前服务提供商断开连接。

- 请确保所有号码来自同一个运营商和同一帐户。

- 确保你的服务处于活动状态。 冻结帐户将导致运营商无法更改帐户。 有权对帐户进行更改的人员必须向当前承运商提交订单以删除冻结。 此过程可能需要一到三周的时间，具体取决于承运商。

## <a name="related-topics"></a>相关主题

- [你的转网订单的状态是什么？](port-order-status.md)
- [用于通话套餐的不同类型的电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
