---
title: 规划云呼叫队列
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 将云自动助理与 Skype for Business Server 2019 一同使用概述。
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918738"
---
# <a name="plan-cloud-call-queues"></a>规划云呼叫队列

云呼叫队列是一项服务，该服务接受客户呼叫、播放问候消息，然后在搜索预先配置的代理列表以应答这些呼叫时，将这些呼叫发送到等待队列中。 可以在启用邮件的通讯组列表或安全组中定义代理集。 您的组织可以有一个或多个呼叫队列。 呼叫队列通常与自动助理结合使用。

此外，云呼叫队列可以提供：

- 音乐呼叫者等待等待时显示
- 呼叫队列最大大小、超时和呼叫处理选项的自定义设置

每个呼叫队列分配有一个资源 **帐户 (请参阅** 在 Skype for Business Server 2019 系统上配置资源帐户 [) ，](configure-onprem-ra.md) 这些帐户将直接链接到 Microsoft Teams 管理中心中的呼叫队列。 请参阅 ["创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue) "，了解有关什么是呼叫队列以及呼叫队列存在哪些选项和功能的详细信息。

> [!NOTE]
> 可以将多个电话号码分配给呼叫队列，但它们必须是 Microsoft 服务号码、直接路由号码或混合号码。

## <a name="requirements"></a>要求

以下要求假定你已在支持的拓扑中部署了 Skype for Business Server 2019。  你的要求取决于你的方案：

- 有关云呼叫队列的新配置，请按照配置资源帐户中 [概述的步骤操作](configure-onprem-ra.md)。 你将需要联机或在 Skype for Business Server 2019 中创建资源帐户，并且可能还需要将电话号码与呼叫队列关联。

除了上述要求之外，还必须将以下要求配置为连接到 Microsoft 云呼叫队列服务：

- 混合连接。 如果你已部署 Skype for Business Server，并且希望为本地用户启用云呼叫队列，则必须确保在本地环境和联机环境之间设置了混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅[Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365.](configure-hybrid-connectivity.md)

- 如果你将电话号码分配给资源帐户，你现在可以使用免费电话系统虚拟用户许可证。 这将为组织级别的电话号码提供电话系统功能，并允许创建自动助理和呼叫队列功能。

- 为每个呼叫队列 [创建](configure-onprem-ra.md) 本地资源帐户，并分配许可证和电话号码（如果需要）。  

当你拥有一个满足你需求的稳固结构和一个可有效地指导客户的脚本时，请继续  [配置资源帐户](configure-onprem-ra.md)。

## <a name="see-also"></a>另请参阅

[配置资源帐户](configure-onprem-ra.md)

[允许使用电话用户界面录制自定义提示语](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什么是云自动助理？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[规划 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](plan-hybrid-connectivity.md)

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](configure-hybrid-connectivity.md)

[在 Microsoft Teams 中管理资源帐户](/MicrosoftTeams/manage-resource-accounts)
