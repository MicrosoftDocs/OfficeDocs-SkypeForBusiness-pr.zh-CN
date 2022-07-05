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
ms.localizationpriority: medium
ms.collection: ''
description: 将云自动助理与 Skype for Business Server 2019 配合使用的概述。
ms.openlocfilehash: df8013a4abc2029d585032b3d0bce810175e04f4
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615418"
---
# <a name="plan-cloud-call-queues"></a>规划云呼叫队列

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

云呼叫队列是一项服务，可接受客户呼叫、播放问候消息，然后在搜索预配置的代理列表以接听这些呼叫时将这些呼叫置于等待队列中。 可以在启用邮件的通讯组列表或安全组中定义代理集。 你的组织可以有一个或多个呼叫队列。 呼叫队列通常与自动助理结合使用。

此外，云呼叫队列可以提供：

- 呼叫者等待等待等待时的音乐
- 调用队列最大大小、超时和呼叫处理选项的自定义设置

为每个呼叫队列分配一个 **资源帐户** (请参阅在 Skype for Business Server 2019 系统上) [配置资源帐户](configure-onprem-ra.md)，这些帐户将直接链接到 Microsoft Teams 管理中心的呼叫队列。 有关呼叫队列是什么以及呼叫队列的选项和功能的更多详细信息，请参阅 [“创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue) ”。

> [!NOTE]
> 可以将多个电话号码分配给呼叫队列，但必须是 Microsoft 服务号码、直接路由号码或混合号码。

## <a name="requirements"></a>要求

以下要求假定你已Skype for Business Server 2019 部署在受支持的拓扑中。  你的要求取决于你的方案：

- 对于云呼叫队列的新配置，请按照配置 [资源帐户](configure-onprem-ra.md)中所述的步骤操作。 需要联机或在 2019 Skype for Business Server创建资源帐户，并且可能需要将电话号码与呼叫队列相关联。

除上述要求外，还必须将以下要求配置为连接到 Microsoft 云呼叫队列服务：

- 混合连接。 如果已部署Skype for Business Server，并且希望为本地用户启用云呼叫队列，则必须确保在本地环境和联机环境之间设置了混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅[规划 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](plan-hybrid-connectivity.md)，[并配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](configure-hybrid-connectivity.md)。

- 如果要将电话号码分配给资源帐户，现在可以使用免费 **Microsoft Teams 电话资源帐户** 许可证。 这为组织级别的电话号码提供电话系统功能，并允许你创建自动助理和呼叫队列功能。

- 为每个呼叫队列创建一个本地 [资源帐户](configure-onprem-ra.md) ，并根据需要分配许可证和电话号码。  

当你有一个符合需求的坚实结构和一个可有效引导客户的脚本时，请继续  [配置资源帐户](configure-onprem-ra.md)。

## <a name="see-also"></a>另请参阅

[配置资源帐户](configure-onprem-ra.md)

[允许使用电话用户界面录制自定义提示语](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什么是云自动助理？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[规划 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](plan-hybrid-connectivity.md)

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](configure-hybrid-connectivity.md)

[在 Microsoft Teams 中管理资源帐户](/MicrosoftTeams/manage-resource-accounts)