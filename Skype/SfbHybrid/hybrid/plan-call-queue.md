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
description: 使用与 Skype for business Server 2019 的云自动助理的概述。
ms.openlocfilehash: 2186909b3ec905d6ec6d387bcea172d8fb80287c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221302"
---
# <a name="plan-cloud-call-queues"></a>规划云呼叫队列

云呼叫队列是一项服务，它可以接受客户呼叫、播放问候语邮件，然后将这些呼叫放在等待队列中，同时搜索预先配置的代理列表以应答这些呼叫。 您可以在启用邮件的通讯组列表或安全组中定义一组代理。 您的组织可以有一个或多个呼叫队列。 呼叫队列通常与自动助理结合使用。

此外，云呼叫队列可以提供：

- 呼叫者等待保留时的音乐
- 呼叫队列的自定义设置最大大小、超时和呼叫处理选项

将在 Skype for Business Server 2019 系统上为每个呼叫队列分配一个**资源帐户**（请参阅[配置资源帐户](configure-onprem-ra.md)），该帐户将直接链接到 Microsoft 团队管理中心中的呼叫队列。 请参阅[创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)，了解有关呼叫队列的内容以及呼叫队列中存在哪些选项和功能的详细信息。

> [!NOTE]
> 可以将多个电话号码分配给呼叫队列，但这些号码必须是 Microsoft 服务号码、直接路由号码或混合号码。

## <a name="requirements"></a>Requirements

以下要求假定您已在受支持的拓扑中部署了 Skype for Business Server 2019。  您的要求取决于您的方案：

- 对于云呼叫队列的新配置，请执行[配置资源帐户](configure-onprem-ra.md)中所述的步骤。 你将需要联机或在 Skype for Business Server 2019 中创建资源帐户，并且你可能还需要将电话号码与呼叫队列相关联。

除了上述要求之外，还必须配置以下要求以连接到 Microsoft 云呼叫队列服务：

- 混合连接性。 如果已部署 Skype for Business Server，并且要为本地用户启用云呼叫队列，则必须确保在本地和联机环境之间设置混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅[规划 skype for Business server 与 microsoft 365 或 office 365 之间的混合连接](plan-hybrid-connectivity.md)和[配置 Skype for Business server 与 Microsoft 365 或 office 365 之间的混合连接](configure-hybrid-connectivity.md)。

- 如果要将电话号码分配给资源帐户，现在可以使用免费电话系统虚拟用户许可证。 这样可以在组织级别为电话号码提供电话系统功能，并允许您创建自动助理和呼叫队列功能。

- 为每个呼叫队列创建本地[资源帐户](configure-onprem-ra.md)，并根据需要分配许可证和电话号码。  

## <a name="additional-planning-resources"></a>其他规划资源

标题为 "[小型企业" 的教程示例-设置自动助理](/microsoftteams/tutorial-org-aa)，以收集有关用户需求的信息、规划自动助理和用户（以及可能的呼叫队列）的结构、编写菜单提示以及在联机管理中心实施计划的过程。 查看教程并使用练习。 t 创建计划。

如果您具有满足需求的实体结构和指导客户有效的脚本，请继续[配置资源帐户](configure-onprem-ra.md)。

## <a name="see-also"></a>另请参阅

[配置资源帐户](configure-onprem-ra.md)

[允许使用电话用户界面录制自定义提示语](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什么是云自动助理？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[规划 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](plan-hybrid-connectivity.md)

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](configure-hybrid-connectivity.md)

[在 Microsoft Teams 中管理资源帐户](/MicrosoftTeams/manage-resource-accounts)
