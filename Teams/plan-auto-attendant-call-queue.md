---
title: 规划 Teams 自动助理和呼叫队列
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 了解自动助理和呼叫队列，以及如何使用它们帮助呼叫者在菜单系统中移动以联系组织中的人员或部门。
ms.openlocfilehash: acaa4d3e4db56b1b64869f92d27f2dfd73c4afee
ms.sourcegitcommit: 0dfe48fde767d8d9ed7bfc93684af05534acad12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2022
ms.locfileid: "69166728"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>规划 Teams 自动助理和呼叫队列

使用自动助理可以设置菜单选项，以便根据呼叫方输入路由呼叫。 自动助理的菜单选项（如“对于销售人员，按 1-For Services 按 2”），让组织提供一系列选项，引导呼叫者快速到达目的地，而无需依赖人工操作员来处理传入呼叫。

呼叫队列是呼叫方的等待区域。 对于呼叫者需要联系具有特定专业（例如销售或服务）而不是特定人员的情况，可以使用呼叫队列将呼叫者连接到可以提供帮助的代理组。 调用方将处于保留状态，直到分配给队列的代理可以接听其呼叫。

结合使用自动助理和呼叫队列可以轻松地将呼叫者路由到组织中的相应人员或部门。

## <a name="auto-attendants"></a>自动助理

自动助理的主要用途是根据呼叫者对提供的菜单选项的输入，将呼叫者定向到相应的人员或部门。 呼叫者可以定向到组织内的特定人员、呼叫等待与下一个可用代理交谈的队列或语音邮件。 可以为营业时间、非工作时间和节假日指定不同的呼叫路由选项。

可以通过使用文本转语音 (系统生成的提示) 或通过上传录制的音频文件来创建菜单提示。 语音识别接受语音命令进行免提导航，但呼叫者也可以使用电话键盘导航菜单。

每个自动助理都有特定的语言和时区。 如果你使用多种语言或世界多个地区开展业务，则可以根据需要创建多个不同的自动助理来容纳呼叫者。

对于每个自动助理，可以配置操作员。 虽然可以将操作员呼叫配置为转到各种目标，但操作员功能旨在允许呼叫者与组织中可以帮助的特定人员交谈。

可以将自动助理配置为允许调用方按名称或分机号搜索组织的目录。 在自动助理中，可以通过选择要包含或排除的用户组来指定要用于目录搜索的人员。  (这称为 *拨号范围*。) 

呼叫者可以通过直接电话号码（如果已配置）或从其他自动助理或呼叫队列重定向来联系自动助理。

## <a name="call-queues"></a>呼叫队列

呼叫队列类似于物理大楼中的候诊室。 调用方在呼叫路由到队列中的代理时等待暂停。 调用队列通常用于销售和服务函数。 但是，呼叫队列可用于呼叫数超过内部容量的任何情况，例如繁忙设施中的接待员。

当队列中的调用方总数或等待时间超过指定的限制时，呼叫队列允许特定的呼叫路由。 呼叫可以路由到特定人员、语音邮件、其他呼叫队列或自动助理。

与自动助理一样，每个呼叫队列都有一个语言设置。 如果使用多种语言开展业务，则可以使用不同的呼叫队列。 如果代理是多语言的，则可以是多个队列的成员。

对于每个呼叫队列，可以指定队列中的代理是否可以选择不接听呼叫，以及是否应根据他们在 Teams 中的状态指示将呼叫路由到他们。

可以将电话号码分配给呼叫队列，但呼叫队列不会为非工作时间和节假日提供单独的呼叫路由。 除非呼叫队列全天候配备，否则我们建议将电话号码分配给在营业时间重定向到呼叫队列的自动助理。

## <a name="prerequisites"></a>先决条件

若要配置自动助理和呼叫队列，需要以下资源：

- 每个自动助理和每个呼叫队列 [的资源帐户](manage-resource-accounts.md) 。
- 每个[资源帐户的免费Microsoft Teams 电话资源帐户许可证](teams-add-on-licensing/virtual-user.md)，可从 Teams 用户或外部电话号码直接拨号。
- 对于要从外部电话号码直接拨号的每个资源帐户，至少有一个[Microsoft服务](getting-service-phone-numbers.md)号码、[操作员连接](operator-connect-plan.md)[号码、直接路由](direct-routing-plan.md)号码或混合号码。
  - 服务号码可以是收费号码或免费号码。

> [!NOTE]
> 资源帐户已禁用登录，并且必须保持登录状态。 聊天和状态不适用于这些帐户。

必须企业语音联机或本地用户启用从呼叫队列接收呼叫的代理。 此外，如果呼叫队列使用直接路由号码，则需要电话会议或转接呼叫的代理还需要：

- 如果呼叫队列使用传输模式，则分配 [的联机语音路由策略](manage-voice-routing-policies.md) 。
- 如果呼叫队列使用会议模式，则分配的 [音频会议许可证](set-up-audio-conferencing-in-teams.md) 或 [联机语音路由策略](manage-voice-routing-policies.md) 。

如果代理使用 Microsoft Teams 应用进行呼叫队列呼叫，则需要处于 TeamsOnly 模式。

在呼叫队列中使用资源帐户进行呼叫线路 ID 时，资源帐户必须具有 Teams 电话资源帐户许可证并分配了以下其中一项：

- [通话套餐](calling-plans-for-office-365.md)许可证和分配的电话号码。
- 分配的 [操作员连接](operator-connect-plan.md) 电话号码。
- [联机语音路由策略](manage-voice-routing-policies.md)。
  - 使用直接路由时，电话号码分配是可选的。

当自动助理或呼叫队列将呼叫转移到外部号码时，下面概述的特定资源帐户必须具有 Teams 电话资源帐户许可证，并且分配了以下其中一项：

- [通话套餐](calling-plans-for-office-365.md)许可证和分配的电话号码。
- 分配的 [操作员连接](operator-connect-plan.md) 电话号码。
- [联机语音路由策略](manage-voice-routing-policies.md)。
  - 使用直接路由时，电话号码分配是可选的。

要许可的资源帐户：

- 当自动助理转接到其他自动助理或从外部转移呼叫的呼叫队列时，为接收呼叫的第一个自动助理上的资源帐户授予许可。
- 在所有其他调用方案中，为执行外部传输的自动助理或呼叫队列的资源帐户授予许可。

> [!NOTE]
> 如果分配给资源帐户的通话套餐被禁用或删除，则通信 [点数](what-are-communications-credits.md)（如果在租户 (中可用，但未分配给资源帐户) ）将被使用。 如果没有通话套餐或通信额度，呼叫将失败。
>
> 仅Microsoft Teams 用户和呼叫代理支持自动助理和呼叫队列的直接路由服务号码。
> 
> 不支持在通话套餐、操作员连接和直接路由中继之间转移。
> 
> 在混合方案中，必须在本地创建资源帐户。 有关详细信息，请参阅 [规划云呼叫队列](/skypeforbusiness/hybrid/plan-call-queue)。

## <a name="business-decisions"></a>业务决策

在设置自动助理和呼叫队列之前，应就如何在业务中使用这些功能做出一些决定。 这些决策将确定在配置自动助理和呼叫队列时选择的设置。

记录这些问题的解答，并向执行配置的管理员提供信息。

- 需要哪些语言？ 这些语言需要在哪里 - 哪个部门或组？
- 是允许来自呼叫者的语音输入还是仅允许拨号输入？
- 下班或节假日是否需要单独的呼叫路由？ 什么是时间和节假日？
- 是否允许呼叫队列中的代理选择不接听呼叫？
- 你希望呼叫队列中的代理或操作员在拨出时具有特定的呼叫方 ID？
- 是否要在组织中启用 [呼叫停车和检索](call-park-and-retrieve.md) ，以帮助人员或部门之间的呼叫切换？
- 对于语音提示，是要录制自己的语音还是使用系统生成的语音？
  - 系统生成的语音易于更新。

## <a name="technical-decisions"></a>技术决策

使用自动助理和呼叫队列将呼叫者连接到组织中的人员时，在开始配置之前，需要做出一些技术决策。

可以通过以下方式将代理添加到调用队列：

- 单个用户
- 通讯组列表
- 安全组，包括启用邮件的安全组
- Microsoft 365 组或 Teams

如果需要，可以将这些选项组合用于每个队列。 具有电子邮件地址的组可用于语音邮件。 使用 Teams 提供了许多优势，包括共享文件存储和代理之间的聊天、可以接收语音邮件的通用邮箱，以及可以与业务线应用程序或 Power Apps 集成的可扩展平台。

建议在开始配置之前选择将呼叫代理添加到队列的策略。

如果你有现有的自动助理和呼叫队列基础结构，并且要迁移到 Teams，则需要计划将现有电话号码转移到新的自动助理和呼叫队列。 可能需要创建 [转网订单](phone-number-calling-plans/port-order-overview.md) 才能从其他提供商移动号码。 建议先暂时获取一个或多个新电话号码，并测试自动助理和呼叫队列流，然后再将它们切换为当前正在使用的号码。

**会议模式** 是呼叫队列中的一个选项，可显著减少将 Teams VOIP 呼叫和 PSTN 呼叫连接到代理所需的时间。 若要使会议模式正常工作，呼叫队列中的代理必须使用以下客户端之一：

- 最新版本的 Microsoft Teams 桌面客户端、Android 应用或 iOS 应用。
- Microsoft电话系统版本 1449/1.0.94.2020051601 或更高版本。
  
将代理的 Teams 帐户设置为仅限 Teams 模式。 不符合要求的代理不包括在呼叫路由列表中。

如果代理都使用兼容的客户端，我们建议为呼叫队列启用会议模式。

**呼叫路由流** 计划有助于确定呼叫组织的人员最有效的路由。 若要了解如何规划呼叫路由流，请参阅 [规划呼叫路由流](plan-your-call-routing-flow.md)。

## <a name="getting-started"></a>入门

完成本文中的规划任务后，请按照以下步骤设置自动助理和呼叫队列：

1. 获取要通过组织外部直接拨号访问的自动助理和呼叫队列所需的服务号码。 这可能包括 [从其他提供商转移号码](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [请求新的服务号码](getting-service-phone-numbers.md)。

2. 获取计划创建的每个资源 [帐户的 Teams 电话](teams-add-on-licensing/virtual-user.md) 资源帐户许可证。 这些许可证是免费的，因此，如果你决定将来对资源帐户进行更改，我们建议额外获取一些许可证。

3. 为每个要创建的自动助理和呼叫队列[创建资源帐户](manage-resource-accounts.md)。 将 Teams 电话资源帐户许可证分配给可直接调用的每个资源帐户，并选择性地分配服务号码。

4. [创建](set-up-holidays-in-teams.md) 要在自动助理中具有单独呼叫路由的假日。

5. （可选）设置 [呼叫停车和检索](call-park-and-retrieve.md) （如果想要使用此功能来帮助进行呼叫转接）。

6. 创建要用于包含呼叫队列的呼叫代理的组。

7. 如果计划允许按分机拨号，请确保已将用户的分机号码添加到其 Azure Active Directory (Azure AD) 配置文件。

完成上述步骤后，即可创建自动助理和呼叫队列。 由于自动助理和呼叫队列可以相互重定向呼叫，因此请参阅创建的工作流图来确定应首先创建哪个自动助理或呼叫队列。 在上图中的示例中，在创建 Contoso 主自动助理之前，需要先创建销售和支持呼叫队列，因为主自动助理需要将呼叫者定向到销售和支持呼叫队列。

有关如何创建自动助理和呼叫队列的信息，请参阅以下文章：

- [设置自动助理](create-a-phone-system-auto-attendant.md)
- [创建呼叫队列](create-a-phone-system-call-queue.md)

> [!IMPORTANT]
> 当用户配置为时，用户的 Azure AD GUID 令牌将存储为自动助理或呼叫队列配置的一部分：
>
>  - 自动助理或呼叫队列 **授权用户**。
>  - 自动助理 **操作员**。
>  - 组织转移点 **中的人员** 。
>  - 呼叫队列的单个成员。
> 
> 自动助理和呼叫队列配置不会与 Azure AD 生命周期事件同步。  当配置中包含的用户离开组织时，Teams 管理员需要手动更新自动助理和呼叫队列配置，以删除此个人数据。
>
> 这不适用于通过通讯组列表或频道配置的呼叫队列代理成员身份。 它还不适用于通过自动助理的“ **按名称拨号”** 或“ **按号码拨号”** 功能联系的用户。

如果需要更广泛的功能（例如与工作流、机器人和短信集成），请考虑[Azure Communication Services](/azure/communication-services/overview)。

## <a name="related-topics"></a>相关主题

[规划直接路由](direct-routing-plan.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
