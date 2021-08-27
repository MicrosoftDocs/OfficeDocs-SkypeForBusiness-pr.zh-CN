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
description: 本主题介绍决定将现有 Skype for Business Server 或 Exchange Server 部署迁移到最新版本或 Skype for Business Online 或 Exchange Online 时需要考虑的内容。
ms.openlocfilehash: edc6256bc9e366b4ee75a637c41141ec3d435da2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596116"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>规划 Skype for Business Server 和 Exchange Server 迁移

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主题介绍决定将现有部署或部署迁移到 Skype for Business Server Exchange Server时需要考虑Exchange Online。 可以迁移哪些内容以及迁移时间主要取决于已在组织中设置哪些内容。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>2019 Exchange 2019 和 Skype for Business Server 中的功能更改

在 Exchange 2019 和 Skype for Business Server 2019 中，我们将对所支持的功能进行一些更改。

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019 中的统一消息支持

2019 年 (统一消息) 统一消息Exchange已弃用。 这意味着 2019 Exchange不再提供以下功能：

- 语音邮件
- 自动助理

如果已部署 Exchange 2013 中的 UM 角色或 Exchange 2016 中的 UM 服务，并且要升级到 Exchange 2019，则需要将语音邮件迁移到 Microsoft 365 或 Office 365 中的 Microsoft 云语音邮件 服务。 如果您想将语音邮件迁移到 云语音邮件，请看下面的[Exchange 2013/Exchange 2016 和 Skype for Business 2015 到 Exchange 2019 和 Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)部分。
> [!IMPORTANT]
> 如果 Exchange 2013 或 Exchange 2016 服务器上用户具有启用 UM 的邮箱，请不要在将 Skype for Business 服务器升级到 Skype for Business Server 2019 之前将其移动到 Exchange 2019，并且将用户移至这些服务器以避免语音邮件中断。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>2019 Exchange 2019 和 2019 Skype for Business Server PBX 支持

云语音邮件为专用交换机和 PBX 交换机交换机 (语音邮件) 。 如果对 PBX 使用 Exchange Server 统一消息，并且要升级到 Exchange Server 2019，则需要采用[Exchange](https://blogs.technet.microsoft.com/exchange/)团队博客上博客上有关不再支持[Exchange Online](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/)统一消息中的会话边界控制器的新日期中列出的三个选项之一。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange OnlineSkype for Business Server 2019 中的 UM 支持

在 Skype for Business Server 2019 中，我们将从 um Exchange Online 移动到 云语音邮件。 将用户移动到 Skype for Business 2019 服务器时，他们将自动开始使用 云语音邮件 托管语音邮件。 如果您当前使用的是 Exchange Online UM，则无需执行任何其他操作，只需将用户移至 Skype for Business Server 2019，云语音邮件。 但是，您需要注意对功能进行一些更改：

- 组织自动助理 UM 中的自动助理Exchange Online替代。
- Web Outlook中的用户语音邮件设置不适用于云语音邮件。

## <a name="on-premises-um-migration-scenarios"></a>本地 UM 迁移方案

我们支持以下方案，使您能够将用户迁移到 Exchange 2019 和 云语音邮件。

- Exchange 2013/Exchange 2016 和 Skype for Business Server 2015 Exchange 2019 和 Skype for Business Server 2019
- Skype for Business Server 2015 Skype for Business Server 2019 与 2013/Exchange 2016 Exchange 2019

以下方案要求当前部署中不存在 PBX 或 SBC 配置，并假定已在内部部署服务器上配置了 UM Exchange配置。 其中每个解决方案还假定你已决定在本地部署服务器和本地服务器Skype for Business或 Microsoft 365 或 Office 365。 有关混合部署Skype for Business，请参阅规划[混合连接](plan-hybrid-connectivity.md)。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 和 Skype for Business 2015 Exchange 2019 和 2019 Skype for Business 2019

在此方案中，您希望将现有 Exchange 2013、Exchange 2016 和 Skype for Business 2015 服务器迁移到 Exchange 2019 和 Skype for Business 2019。

如本主题前面所述，Exchange 2019 不再包括 UM 服务。 这意味着，对于要移动到 Exchange 2019 的任何邮箱，您需要使用 云语音邮件 来替换 UM 服务提供的功能。 当您设置 Skype for Business Server 2019 及其与 Microsoft 365 或 Office 365 之间的混合部署时，云语音邮件将Exchange UM 语音邮件服务。

将用户移至 2019 Exchange 2019 和 Skype for Business Server 2019 的顺序对于确保语音邮件功能对所有用户保持可用至关重要。 语音邮件的处理位置也由邮箱和Exchange Skype for Business和用户所在的位置决定。 查看下表，了解支持哪些Exchange和Skype for Business Server以及在何处处理语音邮件。

| 邮箱位于：            | 位于 2015 Skype for Business Server的用户 | 用户位于 Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 不支持                           | 云语音邮件                          |

在开始迁移到 2019 Skype for Business Server 2019 和 Exchange 2019 之前，请牢记以下事项：

- 云语音邮件不支持 GA 上的自动助理组织功能。 如果希望将邮箱移动到 云语音邮件 以继续通过自动助理使用，则需要至少保留一台运行 UM 角色或服务的 Exchange 2013 或 Exchange 2016 服务器。
- 在将用户的邮箱移动到 2019 年 10月之前，至少需要设置一个 Skype for Business 2019 服务器，Exchange该服务器。 如果不这样做，将导致这些邮箱无法接收语音邮件。
- 发送到语音邮件的呼叫将转接到云语音邮件将记录这些呼叫。 呼叫结束后，语音邮件将发送到内部部署 Exchange 2019 服务器上收件人的邮箱。 在确定 Internet 连接是否足以支持语音连接时，您需要考虑云语音邮件。

以下是完成此迁移的高级别步骤。

1. 在一台Skype for Business Server安装和配置 2019。
2. 更新混合部署配置以包含新的 Skype for Business 2019 服务器。
3. 在一台Exchange Server安装和配置 2019。
4. 将用户从 Skype for Business 2015 服务器移动到 Skype for Business 2019 服务器。
5. 为移动到 2019 Skype for Business Server每个用户设置托管语音邮件策略，以使用云语音邮件。
6. 将邮箱从 Exchange 2013 或 Exchange 2016 服务器移动到 Exchange 2019 服务器。
7. 在上Skype for Business个用户离开 2015 服务器后停用您的 2015 服务器。
8. 在将最后Exchange个邮箱从 2013 Exchange 2016 服务器中停用。

    > [!IMPORTANT]
    > 如果依赖自动助理，请至少保留一个 Exchange 2013 或 Exchange 2016 运行且可用。

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 Skype for Business Server 2019 与 2013/Exchange 2016 Exchange 2019

在此方案中，您希望将现有 Skype for Business 2015 服务器迁移到 Skype for Business Server 2019，但保留于 Exchange 2013 或 Exchange 2016。

当 Skype for Business Server 2015 和 Skype for Business Server 2019 共存于同一组织中时，它们可与 Exchange UM 和 云语音邮件 无缝协作，以确保语音邮件正确传递到 Exchange 邮箱。 UM Exchange um 还是 云语音邮件 处理语音邮件取决于用户是位于 Skype for Business Server 2015 还是 Skype for Business Server 2019：

- 如果用户位于 2015 Skype for Business Server，um Exchange UM 将处理语音邮件。
- 如果用户位于 2019 Skype for Business Server，云语音邮件将处理语音邮件。

无论 um Exchange还是 云语音邮件处理语音邮件，邮件都将存储在用户的邮箱Exchange邮箱中。

在开始迁移到 Skype for Business Server 2019 之前，请牢记以下事项：

- 云语音邮件不支持 GA 上的自动助理组织功能。 如果希望将邮箱移动到 云语音邮件 以继续通过自动助理使用，则需要至少保留一台运行 UM 角色或服务的 Exchange 2013 或 Exchange 2016 服务器。
- 发送到语音邮件的呼叫将转接到云语音邮件将记录这些呼叫。 呼叫结束后，语音邮件将发送到内部部署服务器上收件人Exchange邮箱。 在确定 Internet 连接是否足以支持语音连接时，您需要考虑云语音邮件。

以下是完成此迁移的高级别步骤。

1. 在一台Skype for Business Server安装和配置 2019。
2. 更新混合部署配置以包含新的 Skype for Business 2019 服务器。
3. 将用户从 Skype for Business 2015 服务器移动到 Skype for Business 2019 服务器。
4. 为移动到 2019 Skype for Business Server每个用户设置托管语音邮件策略，以使用云语音邮件。
5. 在上Skype for Business个用户离开 2015 服务器后停用您的 2015 服务器。

    > [!IMPORTANT]
    > 如果依赖自动助理，请至少保留一个 Exchange 2013 或 Exchange 2016 运行且可用。
