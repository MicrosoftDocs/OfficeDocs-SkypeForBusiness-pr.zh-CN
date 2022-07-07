---
title: 如何在你的组织中使用来电显示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 可以使用名为 CallLineIdentity 的策略控制电话系统用户的入站和出站呼叫的呼叫者 ID。
ms.openlocfilehash: 250f8a1a516aec4c9941b0c6396e6d44771b4f53
ms.sourcegitcommit: f608811288c82a6348a6af1671246a93ed06e578
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2022
ms.locfileid: "66660958"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在你的组织中使用来电显示

调用方 ID 由两个面向用户的信息部分组成：

- 电话号码 (称为 CLID 或呼叫行 ID) 。 这是作为呼叫者标识的公共交换电话网络 (PSTN) 号码。

- 呼叫方名称 (通常称为 CNAM) 。 
  
无论 [PSTN 连接选项](pstn-connectivity.md)如何：Microsoft 呼叫计划、操作员连接或直接路由，呼叫者 ID 功能都可供所有电话系统用户使用。 
  
可以使用名为 CallLineIdentity 的策略控制入站和出站调用的调用方 ID。 有关详细信息，请参阅 [有关呼叫行 ID 和呼叫方名称的详细](more-about-calling-line-id-and-calling-party-name.md)信息。

  
## <a name="outbound-pstn-caller-id"></a>出站 PSTN 调用方 ID

对于出站 PSTN 调用方 ID，可使用以下选项。 
  
- 分配给用户的电话号码，这是默认值。

- 匿名，可通过删除用户的 PSTN 号码的演示文稿提供。 

- 替换电话号码，可以是：

  - 一个电话号码，在通话套餐电话号码清单中分类为服务号码和免费电话号码。 它分配给 Teams 自动助理或呼叫队列。

  - 通过直接路由分配给 Teams 自动助理或呼叫队列使用的资源帐户的本地电话号码。 

- 在出站 PSTN 调用上设置的呼叫方名称或 CNAM。  
    
有关详细信息，请参阅 [设置用户的调用方 ID](./set-the-caller-id-for-a-user.md)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>出站调用方 ID 的最终用户控制

用户可以通过设置 EnableUserOverride 属性将其调用方 ID 设置更改为 **匿名** 。 

如果出站调用方 ID 设置为“匿名”，则 EnableUserOverride 不起作用，并且调用方 ID 始终设置为“匿名”。 EnableUserOverride 的默认值是 False。

最终用户可以通过转到 **“设置”>呼叫** 将呼叫者 ID 设置为“匿名”，然后在 **“呼叫者 ID**”下，选择 **“隐藏所有呼叫的电话号码和个人资料信息**”。 此设置更改需要几分钟时间来反映新调用。 

### <a name="notes"></a>注释

注意以下几项：

- 无法为出站呼叫者 ID 分配以下类型的电话号码：

  - 在通话套餐电话号码清单中归类为用户的任何电话号码。

  - 通过分配给用户的直接路由的任何本地电话号码。

  - 本地电话号码Skype for Business Server。

- 使用资源帐户电话号码替换适用于 Teams 用户。 服务电话号码的替换适用于 Teams 用户。

- 呼叫方名称是在调用方 ID 替换为 LineUri、服务或资源帐户电话号码以及调用方是 Teams 用户的呼叫时发送的。

- 调用方名称最多可以有 200 个字符，但下游系统可能支持较少的字符。

- 对于直接路由，电话号码替换和呼叫方名称会在 FROM SIP 标头中发送。 如果使用 ForwardPai = True 配置了相应的 OnlinePstnGateway，则 P-ASSERTED-IDENTITY SIP 标头将包含真正的调用用户。

- EnableUserOverride 优先于策略中的其他设置，除非将替换设置为匿名。 例如，假定策略实例使用资源帐户进行替换，用户设置并启用 EnableUserOverride。 在这种情况下，将阻止出站调用方 ID，并使用匿名。 如果策略实例已将替换设置为“匿名”，并且已设置 EnableUserOverride，则出站调用方 ID 将始终为匿名，而不考虑最终用户设置。

   
## <a name="inbound-caller-id"></a>入站调用方 ID

电话系统将传入的外部电话号码显示为呼叫者 ID。 如果该号码与 Azure AD 中的用户或联系人或个人联系人关联，则Skype for Business和 Teams 客户端将根据该信息显示调用方 ID。 如果电话号码不在 Azure AD 或个人联系人中，则电信提供的显示名称将显示（如果可用）。

BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。 可以设置此属性，但用户设置页面上的最终用户无法使用此属性。 启用此设置后，传入的 PSTN 调用方将显示为来自匿名。
  
若要阻止入站调用方 ID，请参阅 [设置用户的调用方 ID](./set-the-caller-id-for-a-user.md)。
  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
