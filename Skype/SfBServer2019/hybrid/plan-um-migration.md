---
title: 规划 Skype for Business Server 和 Exchange Server 迁移
author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skypeforbusiness-server-itpro
description: 本主题介绍了您需要考虑时您决定为业务 Online 或 Exchange Online 迁移您现有的 Skype 业务服务器或 Exchange Server 部署到最新版本或 Skype。
ms.openlocfilehash: 3678b7531d60324bd557acdd762f428b048d99fc
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696217"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>规划 Skype for Business Server 和 Exchange Server 迁移

本主题介绍了您需要考虑时您决定为业务 Online 或 Exchange Online 迁移您现有的 Skype 业务服务器或 Exchange Server 部署到最新版本或 Skype。 您的可以迁移，以及应在何时，主要取决于什么您已得到设置您的组织中。 在预览，我们开始关注支持几个特定方案，与其他方案成为可在常规可用性 (GA)。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>为业务服务器 2019年功能 Exchange 2019 和 Skype 中的更改

使用 Exchange 2019 和 Skype 的业务服务器 2019年，我们您对我们支持的功能的一些更改。

### <a name="unified-messaging-support-in-exchange-2019"></a>在 Exchange 统一消息支持，则会 2019

Exchange 2019 中已弃用统一消息 (UM)。 这意味着 Exchange 2019 不再提供以下功能：

- 语音邮件
- 自动助理

如果您已经部署了 Exchange 2013 或 UM 服务中的统一消息角色在 Exchange 2016，并且想要升级到 Exchange 2019，您需要将您的语音邮件迁移到 Office 365 中的 Microsoft 云语音邮件服务。 如果您想要迁移到云语音邮件的语音邮件，看看下面的[Exchange 2013/Exchange 2016 和 Skype 的 Exchange 2019 和 Skype 的业务 2019年业务 2015年](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)部分。
> [!IMPORTANT]
> 如果您的 Exchange 2013 或 Exchange 2016 服务器上的用户启用 UM 的邮箱，不要将它们移动到 Exchange 2019 升级您的业务服务器 Skype 到 Skype 的业务服务器 2019年和将用户移至它们以避免语音消息传递中断之前。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和 Skype 中的业务服务器 2019年的 PBX 支持

云语音邮件不提供语音消息传递到专用交换机 (Pbx) 的功能。 如果您使用 Exchange Server 统一消息 Pbx，并且想要升级到 Exchange Server 2019，您需要采用中列出的博客张贴内容[终止的会话边界控制器的支持的新日期在 Exchange 中的三个选项之一联机统一消息](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) [Exchange 团队博客](https://blogs.technet.microsoft.com/exchange/)上。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online UM for 中支持 Skype 业务服务器 2019

与业务服务器 2019年的 Skype，我们移动从 Exchange Online UM 到云语音邮件。 当用户移至 Skype 业务 2019年服务器时，就会自动开始使用云语音邮件配置为托管语音邮件时。 如果您当前使用的 Exchange Online UM，您无需执行任何操作之外移动 Skype 业务服务器 2019 开始使用云语音邮件的用户。 但是，有一些您需要注意的功能的更改：

- 预览，组织自动助理 （在 Exchange Online UM 自动助理的替代） 不可用。 可在 ga 修改的组织的自动助理
- 在 Web 上的 Outlook 中的用户的语音邮件设置不适用于云语音邮件。

## <a name="on-premises-um-migration-scenarios"></a>在本地统一消息迁移方案

在预览，我们便在支持以下方案，您可以将用户迁移到 Exchange 2019 兼到云语音邮件。 在 GA 我们将支持将允许您从其他版本的 Exchange 和 Skype 业务服务器身份验证迁移的其他方案。 我们还将提供组织的自动助理等其他功能。

- Exchange 2013/exchange 2016年和 Skype 业务服务器到 Exchange 2019 2015年业务服务器 2019 Skype
- Exchange 2013/exchange 2016年具有业务服务器 2019 Skype 业务服务器 2015年的 Skype

以下方案需要无 PBX 或 SBC 配置存在当前部署的一部分，并假定您具有内部部署 Exchange 服务器上配置 UM。 每种解决方案还假定您已确定配置之间的业务服务器您的本地 Skype 和 Office 365 的混合部署。 业务混合部署的 Skype 的详细信息，请参阅[业务混合解决方案的 Skype](hybrid-solutions.md)。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/exchange 2016年和 Skype 的业务 2015 到 Exchange 2019 和 Skype 的业务 2019

在此方案中，您想要迁移现有的 Exchange 2013、 Exchange 2016 和 Skype 业务 2015年服务器到 Exchange 2019 和 Skype 的业务 2019年。

本主题前面所述，如 Exchange 2019 不再包括了 UM 服务。 这意味着，您想要将移动到 Exchange 2019，您需要使用云语音邮件以替换功能 UM 服务所提供的任何邮箱。 当您设置 Skype 业务服务器 2019年和之间其和 Office 365 的混合部署时，云语音邮件将替换这些 Exchange UM 语音邮件服务。

在其中您将用户移至 Exchange 2019 和 Skype 的业务服务器 2019年的顺序至关重要确保保持可供所有用户的语音邮件功能。 处理语音邮件，还取决于 Exchange 和业务邮箱和用户的 Skype 位于。 请看一下下表，请参阅支持的 Exchange 和 Skype 业务服务器的组合和处理语音邮件所在的位置。

| 邮箱位于：            | 为业务服务器 2015年位于 Skype 的用户 | 为业务服务器 2019年位于 Skype 的用户  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/exchange 2016    | Exchange UM                             | 云语音邮件                          |
| Exchange 2019                  | 不支持                           | 云语音邮件                          |

在开始迁移到 Skype 业务服务器 2019年和 Exchange 2019 之前，请牢记以下事项：

- 云语音邮件不支持在预览组织的自动助理。 如果您希望邮箱移动到云语音邮件，以继续，可通过自动助理，您将需要保留至少一个运行的 UM 角色或服务提供的 Exchange 2013 或 Exchange 2016 服务器。
- 您需要设置的业务 2019年服务器**并**将用户移动到该服务器的至少一个 Skype 之前将其邮箱移动到 Exchange 2019。 如果不这样做，将导致出现这些邮箱无法接收语音邮件消息。
- 发送到语音邮件的呼叫将转接到云记录其中的语音邮件。 在呼叫结束后，语音邮件消息将发送到内部部署 Exchange 2019 服务器上的收件人的邮箱。 您需要确定 Internet 连接是否足以支持云语音邮件时考虑此语音通信。

下面是完成此迁移的简要步骤。

1. 安装和配置新服务器上 Skype 业务服务器 2019年。
2. 更新您的混合部署配置，以包含新 Skype 业务 2019年服务器。
3. 安装和配置新服务器上的 Exchange Server 2019。
4. 将用户从您的业务 2015年服务器 Skype 移至您 Skype 业务 2019年服务器。
5. 为每个用户移至业务服务器 2019 使用云语音邮件的 Skype 的托管语音邮件策略。
6. 将邮箱从 Exchange 2013 或 Exchange 2016 服务器移动到 Exchange 2019 服务器。
7. 停用业务 2015年服务器您 Skype 最后一个用户移动移开它们之后。
8. 最后一个邮箱已移动移开它们后，停用 Exchange 2013 或 Exchange 2016 服务器。

    > [!IMPORTANT]
    > 如果依靠自动助理时，保留至少一个 Exchange 2013 或 Exchange 2016 运行且可用。

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Exchange 2013/exchange 2016年具有业务服务器 2019 Skype 业务服务器 2015年的 Skype

在此方案中，您想要迁移到 Skype 业务服务器 2019年您现有的 Skype 业务 2015年服务器，但仍保留在 Exchange 2013 或 Exchange 2016 上。

当业务服务器 2015年的 Skype 和 Skype 的业务服务器 2019年共存在同一组织时，他们无缝地工作与 Exchange UM 和云语音邮件，以确保该语音邮件正确传递到 Exchange 邮箱。 Exchange UM 或云语音邮件处理语音邮件取决于是否用户所在的业务服务器 2015 Skype 或业务服务器 2019年的 Skype 上：

- 如果用户所在的业务服务器 2015 Skype，Exchange UM 将处理的语音邮件消息。
- 如果用户所在的业务服务器 2019 Skype，云语音邮件将处理的语音邮件消息。

无论是否 Exchange UM 或云语音邮件处理的语音邮件消息，该消息将存储在用户的 Exchange 邮箱。

在开始迁移到 Skype 的业务服务器 2019年之前，请牢记以下事项：

- 云语音邮件不支持在预览组织的自动助理。 如果您希望邮箱移动到云语音邮件，以继续，可通过自动助理，您将需要保留至少一个运行的 UM 角色或服务提供的 Exchange 2013 或 Exchange 2016 服务器。
- 发送到语音邮件的呼叫将转接到云记录其中的语音邮件。 在呼叫结束后，语音邮件消息将发送到内部部署 Exchange 服务器上的收件人的邮箱。 您需要确定 Internet 连接是否足以支持云语音邮件时考虑此语音通信。

下面是完成此迁移的简要步骤。

1. 安装和配置新服务器上 Skype 业务服务器 2019年。
2. 更新您的混合部署配置，以包含新 Skype 业务 2019年服务器。
3. 将用户从您的业务 2015年服务器 Skype 移至您 Skype 业务 2019年服务器。
4. 为每个用户移至业务服务器 2019 使用云语音邮件的 Skype 的托管语音邮件策略。
5. 停用业务 2015年服务器您 Skype 最后一个用户移动移开它们之后。

    > [!IMPORTANT]
    > 如果依靠自动助理时，保留至少一个 Exchange 2013 或 Exchange 2016 运行且可用。