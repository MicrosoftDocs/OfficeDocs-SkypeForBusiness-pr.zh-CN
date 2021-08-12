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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 可以使用名为 CallingLineIdentity 的策略控制 电话系统 用户的入站和出站呼叫的来电显示。
ms.openlocfilehash: ddd01d899597a96b5085c92ac9e20681b0a5c92b18ca342008b499e44892743a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54293819"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在你的组织中使用来电显示

调用方 ID 由两个面向用户的可识别信息片段组成：

- 电话号码 (称为 CLID 或呼叫线路 ID) 。 这是 PSTN 公用 (号码) 表示为呼叫者的标识。

- 呼叫方名称 (称为 CNAM) 。 
  
无论 PSTN 连接选项如何，电话系统呼叫者 ID 功能都可用：

- Microsoft 通话套餐 

- 电话系统直接路由 
  
可以使用名为 CallingLineIdentity 的策略控制入站和出站呼叫的来电显示。 有关详细信息，请参阅 [有关呼叫线路 ID 和呼叫方名称的更多信息](more-about-calling-line-id-and-calling-party-name.md)。

  
## <a name="outbound-pstn-caller-id"></a>出站 PSTN 呼叫者 ID

对于出站 PSTN 呼叫者 ID，可以使用以下选项。 
  
- 分配给用户的电话号码，这是默认设置。

- 匿名，通过删除用户的 PSTN 号码的表示形式提供。 

- 替代电话号码，可以是：

  - 在"呼叫计划"电话号码清单中分类为服务和免费电话号码的电话号码。 它通常分配给一个Teams 自动助理或呼叫队列。

  - 本地电话号码，通过直接路由分配给呼叫队列或呼叫Teams 自动助理资源帐户。 

- 在出站 PSTN 呼叫上设置的呼叫方名称或 CNAM。  
    
有关详细信息，请参阅 [为用户设置来电显示](./set-the-caller-id-for-a-user.md)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>出站来电显示最终用户控制

用户可以通过设置 EnableUserOverride **属性，** 将呼叫者 ID 设置更改为匿名。 

如果出站呼叫者 ID 设置为 Anonymous，EnableUserOverride 将不起作用，并且调用方 ID 始终设置为 Anonymous。 EnableUserOverride 的默认值是 False。

最终用户可以通过以下方法将其来电显示设置为匿名：设置 >呼叫"，然后在"呼叫者 **ID"** 下，选择"隐藏我的电话号码和所有呼叫 **的个人资料信息"。**

### <a name="notes"></a>注释

注意以下几项：

- 不能为出站来电显示分配以下类型的电话号码：

  - 在"呼叫计划"电话号码清单中分类为用户的任何电话号码。

  - 通过直接路由分配给用户的任何本地电话号码。

  - Skype for Business Server本地电话号码。

- 使用资源帐户电话号码替换仅适用于Teams用户。 服务电话号码的替换适用于 Skype for Business Online Teams用户。

- 呼叫方名称仅在呼叫方 ID 替换为 LineUri、服务或资源帐户电话号码以及呼叫方是用户时Teams发送。

- 呼叫方名称最多可包含 200 个字符，但下游系统可能支持较少的字符。

- 对于直接路由，电话号码替换和呼叫方名称在 FROM SIP 标头中发送。 如果相应的 OnlinePstnGateway 配置为 ForwardPai = True，则 P-ASSERTED-IDENTITY SIP 标头将包含真正的呼叫用户。

- 除非替换设置为 Anonymous，否则 EnableUserOverride 优先于策略中的其他设置。 例如，假设策略实例具有使用资源帐户的替换项，并且 EnableUserOverride 由用户设置和启用。 在这种情况下，将阻止出站来电显示，使用匿名。 如果策略实例的替换设置为 Anonymous 且 EnableUserOverride 已设置，则出站调用方 ID 将始终为 Anonymous，而不考虑最终用户设置。

   
## <a name="inbound-caller-id"></a>入站来电显示

电话系统来电显示作为来电显示的外部电话号码。 如果号码与 Azure AD 中的用户或联系人或个人联系人相关联，Skype for Business客户端Teams基于该信息显示呼叫者 ID。 如果电话号码不在 Azure AD 或个人联系人中，则会显示由显示名称提供的电话号码（如果可用）。

BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。 可以设置此属性，但它在用户设置页上对最终用户不可用。 启用此设置后，传入 PSTN 呼叫者将显示为来自匿名。
  
若要阻止入站来电显示，请参阅 [为用户设置来电显示](./set-the-caller-id-for-a-user.md)。
  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
