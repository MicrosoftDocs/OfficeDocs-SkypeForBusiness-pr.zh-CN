---
title: 规划 Skype for Business Server 和 Exchange Server 迁移
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.localizationpriority: medium
ms.prod: skype-for-business-itpro
description: 本主题介绍在决定将现有Skype for Business Server或Exchange Server部署迁移到最新版本或Skype for Business联机或Exchange Online时需要考虑的事项。
ms.openlocfilehash: ace5151a9a1a910b12b7cba36340bd00f2e96874
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486987"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>规划 Skype for Business Server 和 Exchange Server 迁移

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主题介绍在决定将现有Skype for Business Server或Exchange Server部署迁移到Exchange Online时需要考虑的事项。 可以迁移的内容以及迁移时间在很大程度上取决于你已在组织中设置的内容。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和 2019 Skype for Business Server中的功能更改

使用 Exchange 2019 和 Skype for Business Server 2019，我们将对我们支持的功能进行一些更改。

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019 中的统一消息支持

Exchange 2019 中已弃用统一消息 (UM) 。 这意味着 Exchange 2019 不再提供以下功能：

- 语音邮件
- 自动助理

如果已在 Exchange 2013 中部署 UM 角色或 Exchange 2016 中的 UM 服务，并且想要升级到 Exchange 2019，则需要将语音邮件迁移到 Microsoft 365 或 Office 365 中的Microsoft 云语音邮件服务。 若要将语音邮件迁移到云语音邮件，请查看下面的 [Exchange 2013/Exchange 2016 和 Skype for Business 2015 到 Exchange 2019 和 Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) 部分。
> [!IMPORTANT]
> 如果 Exchange 2013 或 Exchange 2016 服务器上的用户已启用 UM 邮箱，请勿在将Skype for Business服务器升级到 2019 Skype for Business Server之前将其移动到 Exchange 2019，并将用户移动到它们以避免语音消息中断。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和 2019 Skype for Business Server中的 PBX 支持

云语音邮件不向专用分支交换 (PBX) 提供语音消息传送功能。 如果使用的是 PBX 的Exchange Server统一消息传送，并且要升级到 2019 Exchange Server，则需要采用博客文章“新建日期”中列出的三个选项之一，以便停止在 [Exchange 团队博客](https://blogs.technet.microsoft.com/exchange/)上[Exchange Online统一消息传送中对会话边界控制器的支持](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/)。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>2019 Skype for Business Server Exchange Online UM 支持

随着 2019 Skype for Business Server，我们将从 Exchange Online UM 迁移到云语音邮件。 当用户移动到 Skype for Business 2019 服务器时，在为托管语音邮件配置时，他们将自动开始使用云语音邮件。 如果当前使用的是 Exchange Online UM，则除了将用户移动到 Skype for Business Server 2019 以开始使用云语音邮件之外，无需执行任何其他操作。 但是，需要注意的功能有一些更改：

- 组织自动助理是 Exchange Online UM 中自动助理的替代项。
- Outlook 网页版中的用户语音邮件设置不适用于云语音邮件。

## <a name="on-premises-um-migration-scenarios"></a>本地 UM 迁移方案

我们支持以下方案，使你能够将用户迁移到 Exchange 2019 和云语音邮件。

- Exchange 2013/Exchange 2016 和 Skype for Business Server 2015 到 Exchange 2019 和 Skype for Business Server 2019
- Skype for Business Server 2015 到 2019 Skype for Business Server Exchange 2013/Exchange 2016

以下方案要求当前部署中不存在任何 PBX 或 SBC 配置，并假定你已在本地 Exchange 服务器上配置了 UM。 其中每个解决方案还假定你已决定在本地Skype for Business服务器与 Microsoft 365 或 Office 365 之间配置混合部署。 有关Skype for Business混合部署的详细信息，请参阅[计划混合连接](plan-hybrid-connectivity.md)。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 和 Skype for Business 2015 到 Exchange 2019 和 Skype for Business 2019

在此方案中，需要将现有的 Exchange 2013、Exchange 2016 和 Skype for Business 2015 服务器迁移到 Exchange 2019 和 Skype for Business 2019。

如本主题前面所述，Exchange 2019 不再包含 UM 服务。 这意味着，对于要移动到 Exchange 2019 的任何邮箱，需要使用云语音邮件来替换 UM 服务提供的功能。 当你设置 Skype for Business Server 2019 以及它与 Microsoft 365 或 Office 365 之间的混合部署时，云语音邮件替换这些 Exchange UM 语音邮件服务。

将用户移动到 Exchange 2019 和 Skype for Business Server 2019 的顺序对于确保语音邮件功能仍可供所有用户使用至关重要。 处理语音邮件的位置也由 Exchange 和Skype for Business邮箱和用户所在的位置决定。 查看下表，了解支持哪些 Exchange 和Skype for Business Server组合以及处理语音邮件的位置。

| 位于以下位置的邮箱：            | 位于 Skype for Business Server 2015 上的用户 | 位于 Skype for Business Server 2019 上的用户  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 不支持                           | 云语音邮件                          |

在开始迁移到 Skype for Business Server 2019 和 Exchange 2019 之前，请记住以下事项：

- 在将用户的邮箱移动到 Exchange 2019 之前，需要设置至少一个 Skype for Business 2019 **服务器并将** 用户移动到该服务器。 否则将导致这些邮箱无法接收语音邮件。
- 发送到语音邮件的呼叫将传输到云语音邮件将记录这些呼叫。 呼叫结束后，语音邮件将发送到本地 Exchange 2019 服务器上的收件人邮箱。 在确定 Internet 连接是否足以支持云语音邮件时，需要考虑此语音流量。

下面是完成此迁移的高级步骤。

1. 在新服务器上安装和配置 Skype for Business Server 2019。
2. 更新混合部署配置以包括新的 Skype for Business 2019 服务器。
3. 在新服务器上安装和配置 Exchange Server 2019。
4. 将用户从Skype for Business 2015 服务器移动到 Skype for Business 2019 服务器。
5. 为移动到 2019 Skype for Business Server的每个用户设置托管语音邮件策略以使用云语音邮件。
6. 将邮箱从 Exchange 2013 或 Exchange 2016 服务器移动到 Exchange 2019 服务器。
7. 在将最后一个用户移出后，请停用Skype for Business 2015 服务器。
8. 在最后一个邮箱被移出后，解除 Exchange 2013 或 Exchange 2016 服务器的授权。


### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 到 2019 Skype for Business Server Exchange 2013/Exchange 2016

在此方案中，你希望将现有的 Skype for Business 2015 服务器迁移到 2019 Skype for Business Server，但仍保留在 Exchange 2013 或 Exchange 2016 上。

当Skype for Business Server 2015 和 Skype for Business Server 2019 在同一组织中共存时，它们与 Exchange UM 和云语音邮件无缝协作，以确保语音邮件正确传递到 Exchange 邮箱。 Exchange UM 还是云语音邮件处理语音邮件取决于用户是位于 2015 Skype for Business Server还是 2019 Skype for Business Server：

- 如果用户位于 Skype for Business Server 2015，Exchange UM 将处理语音邮件。
- 如果用户位于 2019 Skype for Business Server，云语音邮件将处理语音邮件。

无论 Exchange UM 还是云语音邮件处理语音邮件，邮件都将存储在用户的 Exchange 邮箱中。

在开始迁移到 Skype for Business Server 2019 之前，请记住以下事项：

- 发送到语音邮件的呼叫将传输到云语音邮件将记录这些呼叫。 呼叫结束后，语音邮件将发送到本地 Exchange 服务器上的收件人邮箱。 在确定 Internet 连接是否足以支持云语音邮件时，需要考虑此语音流量。

下面是完成此迁移的高级步骤。

1. 在新服务器上安装和配置 Skype for Business Server 2019。
2. 更新混合部署配置以包括新的 Skype for Business 2019 服务器。
3. 将用户从Skype for Business 2015 服务器移动到 Skype for Business 2019 服务器。
4. 为移动到 2019 Skype for Business Server的每个用户设置托管语音邮件策略以使用云语音邮件。
5. 在将最后一个用户移出后，请停用Skype for Business 2015 服务器。

