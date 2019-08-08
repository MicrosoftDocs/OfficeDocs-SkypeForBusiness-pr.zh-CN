---
title: 规划 Skype for Business Server 和 Exchange Server 迁移
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: 本主题介绍在决定将现有的 Skype for Business 服务器或 Exchange Server 部署迁移到最新版本或 Skype for Business Online 或 Exchange Online 时需要考虑的事项。
ms.openlocfilehash: 864a777c1fcb483df7f3779e9b105c1af551748e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237467"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>规划 Skype for Business Server 和 Exchange Server 迁移

本主题介绍在决定将现有的 Skype for Business 服务器或 Exchange Server 部署迁移到最新版本或 Skype for Business Online 或 Exchange Online 时需要考虑的事项。 您可以迁移的内容和时间, 具体取决于您在组织中已设置的内容。 某些功能 (如组织自动助理) 在正式发行版 (GA) 中不可用, 但以后将在2018中推出。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和 Skype for Business Server 2019 中的功能更改

在 Exchange 2019 和 Skype for business Server 2019 中, 我们将对支持的功能进行一些更改。

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019 中的统一消息支持

统一消息 (UM) 在 Exchange 2019 中已被弃用。 这意味着 Exchange 2019 不再提供以下功能:

- Voicemail
- 自动助理

如果您已在 exchange 2013 或 Exchange 2016 中的 UM 服务中部署 UM 角色, 并且您希望升级到 Exchange 2019, 则需要将语音邮件迁移到 Office 365 中的 Microsoft 云语音邮件服务。 如果要将语音邮件迁移到云语音邮件, 请查看下面的[exchange 2013/exchange 2016 和 skype for business 2015 To exchange 2019 和 skype for business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)部分。
> [!IMPORTANT]
> 如果 Exchange 2013 或 Exchange 2016 服务器上的用户具有已启用 UM 的邮箱, 请不要在将 Skype for business 服务器升级到 Skype for Business Server 2019 之前将它们移动到 Exchange 2019 中, 并将用户移动到这些服务器以避免语音邮件中断。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和 Skype for Business Server 2019 中的 PBX 支持

云语音邮件不会向专用交换机 (Pbx) 提供语音邮件功能。 如果您使用 Exchange Server 统一消息进行 Pbx 并希望升级到 Exchange Server 2019, 则需要采用博客文章新日期中列出的三个选项之一, 以[终止 Exchange 中对会话边界控制器的支持](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) [Exchange 团队博客](https://blogs.technet.microsoft.com/exchange/)上的在线统一消息。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 中的 Exchange Online UM 支持

在 Skype for Business Server 2019 中, 我们将从 Exchange Online UM 移动到云语音邮件。 将用户移动到 Skype for Business 2019 服务器时, 会在为托管语音邮件配置时自动开始使用云语音邮件。 如果你当前使用的是 Exchange Online UM, 则无需执行任何其他操作, 除了将用户迁移到 Skype for business Server 2019 以开始使用云语音邮件。 但是, 您需要注意一些对功能的更改:

- 组织自动助理 (Exchange Online UM 中的自动助理替代) 在 GA 上市后不可用, 但将在2018以后提供。
- Web 上的 Outlook 中的用户语音邮件设置不适用于云语音邮件。

## <a name="on-premises-um-migration-scenarios"></a>本地 UM 迁移方案

我们支持以下方案, 使你能够将用户同时迁移到 Exchange 2019 和云语音邮件。 在后面的2018中, 我们将支持其他方案, 让你能够从其他版本的 Exchange 和 Skype for Business server 进行迁移。 我们还将提供其他功能, 例如组织自动助理。

- Exchange 2013/Exchange 2016 和 Skype for Business Server 2015 至 Exchange 2019 和 Skype for business Server 2019
- Skype for business Server 2015 至 Skype for business Server 2019 with Exchange 2013/Exchange 2016

以下方案要求在当前部署中不存在任何 PBX 或 SBC 配置, 并假设您在本地 Exchange 服务器上配置了 UM。 这些解决方案中的每一项都假设您已决定在本地 Skype for Business 服务器和 Office 365 之间配置混合部署。 有关 Skype for business 混合部署的详细信息, 请参阅[规划混合连接](plan-hybrid-connectivity.md)。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 和 Skype for Business 2015 至 Exchange 2019 和 Skype for business 2019

在这种情况下, 您需要将现有的 Exchange 2013、Exchange 2016 和 Skype for Business 2015 服务器迁移到 Exchange 2019 和 Skype for business 2019。

如本主题前面所述, Exchange 2019 不再包含 UM 服务。 这意味着, 对于要移动到 Exchange 2019 的任何邮箱, 都需要使用云语音邮件替换 UM 服务提供的功能。 当您设置 Skype for business Server 2019 以及 it 与 Office 365 之间的混合部署时, 云语音邮件将替换这些 Exchange UM 语音邮件服务。

将用户移动到 Exchange 2019 和 Skype for Business Server 2019 的顺序对于确保所有用户仍然可以使用语音邮件功能至关重要。 处理语音邮件的位置也由 Exchange 和 Skype for Business 邮箱和用户所在的位置决定。 查看下表以查看支持哪些 Exchange 和 Skype for business Server 组合以及处理语音邮件的位置。

| 邮箱位于:            | 位于 Skype for Business Server 2015 的用户 | 位于 Skype for Business Server 2019 的用户  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 不支持                           | 云语音邮件                          |

在开始迁移到 Skype for business Server 2019 和 Exchange 2019 之前, 请记住以下几点:

- 云语音邮件在公开发布时不支持组织自动助理。 如果您希望将邮箱移动到云语音邮件以继续通过自动助理使用, 则需要至少有一个 Exchange 2013 或 Exchange 2016 服务器运行 UM 角色或服务。
- 您需要设置至少一个 Skype for Business 2019 服务器 **, 并**将用户移到该服务器, 然后再将其邮箱移动到 Exchange 2019。 如果不这样做, 则会导致这些邮箱无法接收语音邮件。
- 发送给语音邮件的呼叫将被转移到云语音邮件, 并在其中记录这些呼叫。 呼叫结束后, 语音邮件将发送到本地 Exchange 2019 服务器上的收件人邮箱。 在确定您的 Internet 连接是否足以支持云语音邮件时, 您需要考虑语音流量。

下面是完成此迁移的高级步骤。

1. 在新服务器上安装和配置 Skype for business Server 2019。
2. 更新您的混合部署配置, 以包括新的 Skype for Business 2019 服务器。
3. 在新服务器上安装和配置 Exchange Server 2019。
4. 将用户从 Skype for business 2015 服务器移动到 Skype for Business 2019 服务器。
5. 将每个已移动到 Skype for business Server 2019 的用户的托管语音邮件策略设置为使用云语音邮件。
6. 将邮箱从 Exchange 2013 或 Exchange 2016 服务器移动到 Exchange 2019 服务器。
7. 将最后一个用户移出后, 请停用 Skype for business 2015 服务器。
8. 将最后一个邮箱移出后, 请停止 Exchange 2013 或 Exchange 2016 服务器。

    > [!IMPORTANT]
    > 如果你依赖自动助理, 请至少保留一个 Exchange 2013 或 Exchange 2016 运行并可用。

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for business Server 2015 至 Skype for business Server 2019 with Exchange 2013/Exchange 2016

在这种情况下, 您需要将现有的 Skype for Business 2015 服务器迁移到 Skype for Business Server 2019, 但仍保留在 Exchange 2013 或 Exchange 2016 中。

当 Skype for business Server 2015 和 Skype for Business Server 2019 在同一组织中共存时, 它们将与 Exchange UM 和云语音邮件无缝协作, 以确保正确地将语音邮件传递到 Exchange 邮箱。 Exchange UM 或云语音邮件是否处理语音邮件取决于用户是否位于 Skype for business Server 2015 或 Skype for business Server 2019:

- 如果用户位于 Skype for Business Server 2015, Exchange UM 将处理语音邮件。
- 如果用户位于 Skype for Business Server 2019, 云语音邮件将处理语音邮件。

无论 Exchange UM 或云语音邮件是否处理语音邮件, 邮件都将存储在用户的 Exchange 邮箱中。

在开始迁移到 Skype for business Server 2019 之前, 请记住以下几点:

- 云语音邮件在公开发布时不支持组织自动助理。 如果您希望将邮箱移动到云语音邮件以继续通过自动助理使用, 则需要至少有一个 Exchange 2013 或 Exchange 2016 服务器运行 UM 角色或服务。
- 发送给语音邮件的呼叫将被转移到云语音邮件, 并在其中记录这些呼叫。 呼叫结束后, 语音邮件将发送到内部部署 Exchange 服务器上的收件人邮箱。 在确定您的 Internet 连接是否足以支持云语音邮件时, 您需要考虑语音流量。

下面是完成此迁移的高级步骤。

1. 在新服务器上安装和配置 Skype for business Server 2019。
2. 更新您的混合部署配置, 以包括新的 Skype for Business 2019 服务器。
3. 将用户从 Skype for business 2015 服务器移动到 Skype for Business 2019 服务器。
4. 将每个已移动到 Skype for business Server 2019 的用户的托管语音邮件策略设置为使用云语音邮件。
5. 将最后一个用户移出后, 请停用 Skype for business 2015 服务器。

    > [!IMPORTANT]
    > 如果你依赖自动助理, 请至少保留一个 Exchange 2013 或 Exchange 2016 运行并可用。
