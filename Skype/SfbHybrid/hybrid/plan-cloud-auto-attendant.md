---
title: 规划云自动助理
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 将云自动助理与 Skype for Business Server 2019 结合使用的概述
ms.openlocfilehash: f7a3799df083d1404a2d635ee38403cc2653b9ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037814"
---
# <a name="plan-cloud-auto-attendants"></a>规划云自动助理

Exchange 统一消息（Exchange Server 2013 或 Exchange Server 2016）使用的自动助理已不再在 Exchange Server 2019 或 Exchange Online 中可用。 如果实施 Skype for Business Server 2019 与上述任一 Exchange 版本集成，则需要使用与电话系统相关联的联机云语音功能。 请参阅[Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)，了解有关将 exchange UM 服务托管在 exchange server 2013 和2016上的信息移动到云。

这本身就意味着，如果您希望使用统一消息功能（如自动助理），您将拥有 Skype for business Server 2019 的混合实施。 有关详细信息，请参阅[配置 Skype For Business Server 和 Office 365 之间的混合连接](configure-hybrid-connectivity.md)。

自动助理是一种云服务，可接受客户呼叫和播放问候语、为他们提供菜单选项以及使用语音或 dialpad 与呼叫者进行交互，以将呼叫路由到正确的目标。 在 Skype for Business Server 2019 系统上为每个自动助理分配一个**资源帐户**（请参阅[配置资源帐户](configure-onprem-ra.md)），该帐户将直接链接到 Microsoft 团队管理中心中的自动助理。 请参阅[什么是云自动助理？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md)有关自动助理的详细信息以及自动助理存在哪些选项和功能的详细信息，请参阅什么是云自动助理。

> [!NOTE]
> 您可以将多个 Microsoft 服务号码或混合号码分配给自动助理。

对云自动助理的传入呼叫可以采用多个路径之一，如下所示：

![自动助理的关系图](../../SfBServer2019/media/AA-plan-concept.png)

1. 通过 Skype for Business Server 2019
2. 通过[会话边界控制器](/MicrosoftTeams/direct-routing-border-controllers.md)和[直接路由](/MicrosoftTeams/direct-routing-plan.md)
3. 通过在 Office 365 中托管的号码联机。

另请参阅：

- [设置云自动助理](/microsoftteams/create-a-phone-system-auto-attendant)
- [自动接听和路由传入呼叫](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requirements

以下要求假定您已在受支持的拓扑中部署了 Skype for Business Server 2019。  您的要求取决于您的方案：

- 如果你已在使用 Exchange UM online 或本地，并且升级到 Skype for Business 2019，你将需要捕获自动助理的结构，并使用云自动助理在云中重新创建它们。 有关详细信息，请参阅[将 EXCHANGE UM 自动助理或呼叫队列移动到电话系统](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。

- 对于云自动助理的新配置，请按照[Configure resource accounts](configure-onprem-ra.md)中所述的步骤操作。

除了上述要求之外，还必须将以下要求配置为连接到 Microsoft 云自动助理服务：

- 混合连接性。 如果已部署 Skype for Business Server，并且要为本地用户启用云自动助理，则必须确保在本地和联机环境之间设置混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅[规划 skype For Business server 和 office 365 之间的混合连接](plan-hybrid-connectivity.md)和[配置 Skype for Business server 和 office 365 之间的混合连接](configure-hybrid-connectivity.md)。

- 如果你要向自动助理分配电话号码，你将需要[Office 365 企业版 E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)许可证。
- 为每个自动助理创建一个联机[资源帐户](/MicrosoftTeams/manage-resource-accounts.md)或本地[资源帐户](configure-onprem-ra.md)，并分配电话号码和许可证。 

## <a name="migration-and-interoperability"></a>迁移和互操作性

如果您计划部署 Skype for Business Server 2019 和/或 Exchange Server 2019，则必须仔细规划迁移，以确保自动助理的持续支持。 请注意下列事项：

- Exchange Server 2019 不再提供 Exchange UM 功能
- Exchange 统一消息处于退休模式
- Skype for Business Server 2019 不再与 Exchange Online UM 集成

可以使用 Skype for Business Server 2019、2015和2013配置云自动助理。

Microsoft 建议采用以下迁移途径：

- 如果要升级到 Skype for business Server 2019，可以在 Exchange Server 2013 或2016中使用 Exchange UM，但如果您使用的是 Exchange Server 2019，则必须升级到云自动助理。

- 如果要升级到 Exchange Server 2019，并且使用的是以前版本的 Exchange Server UM for Skype for business Server voice 消息，Microsoft 建议您先升级到 Skype for business Server 2019，然后再升级邮箱。  否则，语音邮件功能将丢失。

有关规划迁移的详细信息，请参阅[Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)。

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>迁移以前实施的 Exchange UM 自动助理系统

目前，我们不支持自动迁移到在 Exchange 2013 或2016中创建的 UM 自动助理系统的云。 若要手动重新创建自动助理系统，需要执行以下操作：

1. 使用 Exchange 管理 powershell 命令查看旧自动助理系统（包括任何嵌套的自动助理和呼叫队列）的结构。  
2. 创建与每个 UM 自动助理节点关联的文本到语音的脚本或记录的邮件的副本。
3. 为每个自动助理节点创建本地终结点，包括为对象分配测试电话号码和许可证。 请注意，您现在可以分配联机服务（如电话系统）使用的内部部署电话号码许可证。
4. 使用 Skype for Business Online 和电话系统实现新的云自动助理服务。 有关实现的详细信息，请参阅[配置资源帐户](configure-onprem-ra.md)。 在执行此操作时，请上载与每个 UM 自动助理节点关联的文本到语音的脚本或记录的邮件。
5. 测试云自动助理的功能。
6. 将分配给旧 Exchange UM 自动助理的电话号码重新分配给新创建的主云自动助理。

有关这些步骤的详细信息，请参阅[将 EXCHANGE UM 自动助理或呼叫队列移动到电话系统](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。

## <a name="additional-planning-resources"></a>其他规划资源

标题为 "[小型企业" 的教程示例-设置自动助理](/microsoftteams/tutorial-org-aa)，以收集有关用户需求的信息、规划自动助理和用户的结构（以及可能的呼叫队列）、编写菜单提示以及在团队管理中心实施计划的过程。 查看教程并使用此处的练习来创建您的计划。

如果您具有满足需求的实体结构和指导客户有效的脚本，请继续[配置资源帐户](configure-onprem-ra.md)。

> [!CAUTION]
> 如[KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)中所述，不鼓励将在服务器2015中创建的 Exchange UM 自动助理移动到运行服务器2019的服务器。 在这种情况下，您必须将其保留在共存模式下运行的 Skype for Business Server 2015 池上。

## <a name="see-also"></a>另请参阅

[规划 Skype for Business Server 和 Exchange Server 迁移](plan-um-migration.md)

[配置资源帐户](configure-onprem-ra.md)

[允许使用电话用户界面录制自定义提示语](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什么是云自动助理？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[设置云自动助理](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM：[自动应答和路由传入呼叫](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[规划 Skype for Business Server 和 Office 365 之间的混合连接](plan-hybrid-connectivity.md)

[配置 Skype for Business Server 和 Office 365 之间的混合连接](configure-hybrid-connectivity.md)

[KB4480742：将联系人对象移至 Skype for business Server 2019 后，对订阅者访问或自动助理的呼叫失败，并出现 "500 服务器内部" 错误](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
