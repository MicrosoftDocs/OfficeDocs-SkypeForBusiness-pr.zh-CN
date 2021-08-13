---
title: 为云语音邮件用户规划服务|PBX Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 本文介绍实施服务的好处、规划注意事项和Microsoft 云语音邮件要求。 有关配置配置云语音邮件的信息，请参阅配置云语音邮件。
ms.openlocfilehash: f12bd29c51b2ce08c0b4d29a6bce56e3dc22dddca7188cb046e59daaba7cf329
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323674"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>规划云语音邮件本地用户的部署服务

## <a name="overview"></a>概述

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文介绍为本地用户实施 Microsoft 云语音邮件 服务的好处、规划注意事项和要求。 有关配置服务云语音邮件，请参阅配置[云语音邮件 服务](configure-cloud-voicemail.md)。

云语音邮件 Exchange 统一消息 (UM) ，为在 Exchange Server 2019 或 Exchange Online 上拥有邮箱的 Skype for Business 2019 语音用户提供语音邮件功能。 云语音邮件为本地用户和联机用户提供以下好处：

- 语音信箱应答和存放功能与增强的语音转录功能

- 使用 Skype for Business Online 或 Exchange Outlook 客户端访问用户邮箱中的语音邮件

- 能够使用 Microsoft 365 管理中心管理语音邮件选项

- 支持Exchange或云中的邮箱

- 利用统一消息中的现有Exchange Online问候语

> [!Important]
> Skype for BusinessOnline 将于 2021 年 7 月 31 日停用，此后用户将无法再通过 Exchange Online 客户端访问 Skype for Business 邮箱中的语音邮件。

有关功能比较详细信息，请参阅 Plan [for Skype for Business Server and Exchange Server migration](plan-um-migration.md)。

Skype for Business Server 2019 Exchange 2016 年 12 月 16 日版邮箱位于早期版本的 Exchange Server (的用户继续使用) 。  了解基于 Exchange Server 和 Skype for Business Server 版本的语音邮件解决方案是规划迁移到 Skype for Business Server 2019 或 Exchange Server 2019 的重要部分。 有关迁移和互操作性详细信息，请参阅 Plan [for Skype for Business Server and Exchange Server migration](plan-um-migration.md)。

使用云语音邮件，管理任务将大大简化，因为：

- 无需配置 UM Exchange UM 角色。
- 此参数的云语音邮件更简单。
- 语音邮件功能更新直接在云中提供，因此你的用户始终可以访问最新功能和更新，对累积更新和 CPU (的依赖) 。
- 对于内部部署邮箱和联机邮箱，您Exchange组。 有关这些控件详细信息，请参阅设置电话系统[语音邮件](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)。

下图显示了云语音邮件部署中的位置：

![SfB 云语音邮件](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

未接听的呼叫的处理方式如下：  

1. 对于本地 Skype for Business 2019 中的用户，未接听的呼叫由本地Skype for Business Server发送到联机 云语音邮件 服务。
2. 该服务处理语音邮件，包括转录。
3. 然后，该服务将语音邮件Exchange邮箱中，无论邮箱是本地邮箱还是联机邮箱。  
4. 用户可以从自己的客户端或 Skype for Business访问Outlook语音邮件。

## <a name="requirements"></a>要求

以下要求假定你已Skype for Business Server拓扑中部署。  你的要求取决于你的方案：

- 如果您已经联机使用 Exchange UM 并升级到 Skype for Business 2019，则需要修改托管语音邮件策略并验证您的托管提供商是否正确设置。 有关详细信息，请参阅配置 云语音邮件[服务](configure-cloud-voicemail.md)。

- 如果要在本地Exchange UM，或者混合使用 Exchange UM 联机和本地用户，则需要同时修改托管语音邮件策略和托管提供商。  有关详细信息，请参阅配置 云语音邮件[服务](configure-cloud-voicemail.md)。

- 有关新配置云语音邮件，请按照配置 云语音邮件[service 中概述的步骤操作](configure-cloud-voicemail.md)。

除了上述要求之外，还必须将以下要求配置为连接到 Microsoft 云语音邮件 服务：

- 混合连接。 如果已Skype for Business Server，并且希望为本地用户启用 云语音邮件，则必须确保在本地环境和联机环境之间设置了混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅 Plan [hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md)和 Configure hybrid connectivity between Skype for Business Server and [Office 365](configure-hybrid-connectivity.md)。

- 必须为本地用户启用 企业语音 和 Skype for Business Server。

- 必须Exchange外部 (EWS) URL 和自动发现，否则某些 云语音邮件功能将受到限制。

- 如果你有本地邮箱Exchange，云语音邮件为邮箱用户设置云语音邮件[设置Exchange Server邮箱。](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)

## <a name="migration-and-interoperability"></a>迁移和互操作性

如果您计划部署 Skype for Business Server 2019 和/或 Exchange Server 2019，则必须仔细规划迁移以确保语音邮件服务持续有效。 请注意下列事项：

- Exchange Server 2019 不再提供Exchange UM 功能
- Skype for Business Server 2019 不再与 UM Exchange Online集成

下表列出了 云语音邮件 版本互操作性和支持的拓扑，该表将用户可能位于的 Skype for Business Server 版本与提供其 Exchange Mailbox 的可能版本进行比较。 如果要将 云语音邮件 2019 与 Skype for Business 2019 或 Exchange Online 2019 Exchange Server使用。

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange ServerUM | Exchange ServerUM | 云语音邮件 | 云语音邮件 |
| Skype for Business Server 2015 | Exchange ServerUM | Exchange ServerUM | 不支持 | 云语音邮件 |
| Lync Server 2013 <br>  | Exchange ServerUM | Exchange ServerUM | 不支持 | 云语音邮件 |

Microsoft 推荐以下迁移路径：

- 如果要升级到 Skype for Business Server 2019，可以在 Exchange Server 2013 或 2016 中使用 Exchange UM，但如果使用的是 Exchange Server 2019，则必须升级到 云语音邮件。
- 如果要升级到 Exchange Server 2019，并且对 Skype for Business Server 语音邮件使用早期版本的 Exchange Server UM，Microsoft 建议您在邮箱升级之前升级到 Skype for Business Server 2019。  否则，语音邮件功能将丢失。
- 如果要升级到 Skype for Business Server 2019，并且为 Exchange Online UM 的语音邮件配置了 Skype for Business Server 2015，则当用户的帐户移至 Skype for Business Server 2019 时，用户的语音邮件将自动从 Exchange Online UM 迁移到 云语音邮件。 

有关规划迁移的信息，请参阅规划迁移[Skype for Business Server Exchange Server迁移。](plan-um-migration.md)