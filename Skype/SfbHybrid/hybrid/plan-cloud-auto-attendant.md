---
title: 规划云自动助理
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
description: 在 2019 年 10 月Skype for Business Server云自动助理概述
ms.openlocfilehash: 5d28618efc2b02240cdfe3e4c05945f9a6e4b575
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610169"
---
# <a name="plan-cloud-auto-attendants"></a>规划云自动助理

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

与 Exchange 2013 (Exchange Server 2016 Exchange Server 2016) 一起使用的自动助理在 Exchange Server 2019 或 Exchange Online 中不再可用。 如果 Skype for Business Server 2019 的实现与这些 Exchange 版本之一集成，则需要使用与 电话系统 关联的联机云语音功能。 有关[将 Exchange](plan-um-migration.md) server 2013 和 Exchange Server 上托管的 Exchange UM 服务移动到云的信息，请参阅 Plan for Skype for Business Server and Exchange Server migration。

这本质上意味着，如果您希望使用统一消息功能（如自动助理）Skype for Business Server 2019 的混合实现。 有关详细信息[，请参阅](configure-hybrid-connectivity.md)配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接。

自动助理是一种云服务，它接受客户呼叫并播放问候语，为用户提供菜单选项，并且使用语音或拨号盘与呼叫者交互，以将呼叫路由到正确的目标。 每个自动助理都分配有一个资源 *帐户 (请参阅* 在 [](configure-onprem-ra.md)Skype for Business Server 2019 系统上配置资源帐户) ，这些帐户将直接链接到 Microsoft Teams 管理中心中的自动助理。 有关 [什么是自动](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 助理以及自动助理存在哪些选项和功能的详细信息，请参阅什么是云自动助理？

> [!NOTE]
> 可以将多个 Microsoft 服务号码、直接路由号码或混合号码分配给自动助理。

对云自动助理的传入呼叫可以采用以下几种路径之一，如下所示：

![自动助理关系图](../../SfBServer2019/media/AA-plan-concept.png)

1. 通过 Skype for Business Server 2019
2. 通过会话[边界控制器和](/MicrosoftTeams/direct-routing-border-controllers.md)[直接路由](/MicrosoftTeams/direct-routing-plan.md)
3. 通过联机Microsoft 365或Office 365。

另请参阅：

- [设置云自动助理](/microsoftteams/create-a-phone-system-auto-attendant)
- [自动接听和路由传入呼叫](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>要求

以下要求假定你已在Skype for Business Server拓扑中部署了 2019。  你的要求取决于你的方案：

- 如果已在联机或本地使用 Exchange UM 并升级到 Skype for Business 2019，则需要捕获自动助理的结构，然后使用云自动助理在云中重新创建它们。 有关详细信息，请参阅 Moving [an Exchange UM auto attendant or call queue to 电话系统](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。

- 有关云自动助理的新配置，请按照配置资源帐户  [中概述的步骤操作](configure-onprem-ra.md)。

除了上述要求之外，还必须将以下要求配置为连接到 Microsoft 云自动助理服务：

- 混合连接。 如果已Skype for Business Server云自动助理，并且希望为本地用户启用云自动助理，则必须确保在本地环境和联机环境之间设置了混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅 Plan [hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md)和 Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or [Office 365](configure-hybrid-connectivity.md)。

- 如果要将电话号码分配给自动助理，则需要一个Office 365 企业版[E5](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)许可证。
- 为每个自动[助理创建](/MicrosoftTeams/manage-resource-accounts.md)联机资源帐户或本地[](configure-onprem-ra.md)资源帐户，并分配电话号码和许可证。 

## <a name="migration-and-interoperability"></a>迁移和互操作性

如果计划部署 Skype for Business Server 2019 和/或 Exchange Server 2019，则必须仔细规划迁移以确保对自动助理的持续支持。 请注意以下几点：

- Exchange Server 2019 不再提供Exchange UM 功能
- Exchange统一消息进入停用模式
- Skype for Business Server 2019 不再与 UM Exchange Online集成

云自动助理可以使用 2019 Skype for Business Server 2015 和 2013 进行配置。

Microsoft 推荐以下迁移路径：

- 如果要升级到 Skype for Business Server 2019，可以在 Exchange Server 2013 或 2016 中使用 Exchange UM，但如果使用的是 Exchange Server 2019，则必须升级到云自动助理。

- 如果要升级到 Exchange Server 2019，并且对 Skype for Business Server 语音邮件使用早期版本的 Exchange Server UM，Microsoft 建议您在邮箱升级之前升级到 Skype for Business Server 2019。  否则，语音邮件功能将丢失。

有关规划迁移的信息，请参阅规划迁移[Skype for Business Server Exchange Server迁移。](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>迁移以前实现Exchange UM 自动助理系统

目前，我们不支持自动迁移到在 Exchange 2013 或 2016 中创建的 UM 自动助理系统的云。 若要手动重新创建自动助理系统，需要：

1. 使用 Exchange管理员 PowerShell 命令查看旧自动助理系统的结构，包括任何嵌套的自动助理和呼叫队列。  
2. 创建与每个 UM 自动助理节点关联的文本到语音脚本或录制的邮件的副本。
3. 为每个自动助理节点创建本地终结点，包括为对象分配测试电话号码和许可证。 请注意，你现在能够分配联机服务（如 电话系统）使用本地电话号码电话系统。
4. 使用新的云自动助理服务实现Microsoft Teams电话系统。 有关 [实现的详细信息，请参阅配置](configure-onprem-ra.md) 资源帐户。 在此操作时，上载与每个 UM 自动助理节点关联的文本到语音脚本或录制的邮件。
5. 测试云自动助理的功能。
6. 将分配给旧 UM 自动助理Exchange电话号码重新分配给新建的主云自动助理。

有关[这些步骤的详细信息，Exchange UM 自动助理或呼叫队列电话系统](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)移动 UM 自动助理或呼叫队列。

当你拥有满足你需求的稳固结构和一个可有效地指导客户的脚本时，请继续执行配置 [资源帐户](configure-onprem-ra.md)。

> [!CAUTION]
> 如[KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)所述，Exchange服务器 2015 中创建的 UM 自动助理移动到运行 Server 2019 的服务器。 目前，您必须在以共存模式运行的 Skype for Business Server 2015 池上保留它们。

## <a name="see-also"></a>另请参阅

[Skype for Business Server 和 Exchange Server 迁移规划](plan-um-migration.md)

[配置资源帐户](configure-onprem-ra.md)

[允许使用电话用户界面录制自定义提示语](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什么是云自动助理？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[设置云自动助理](/microsoftteams/create-a-phone-system-auto-attendant)

ExchangeUM：[自动应答和路由传入呼叫](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[规划 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](plan-hybrid-connectivity.md)

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](configure-hybrid-connectivity.md)

[KB4480742：将联系人对象移动到 Skype for Business Server 2019 后，订阅者访问或自动助理的呼叫失败，出现快速忙碌和"500 服务器内部"错误](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)