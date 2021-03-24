---
title: 为本地用户规划云语音邮件服务|PBX Skype for Business Server 2019
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
description: 本文介绍了实施 Microsoft 云语音邮件服务的好处、规划注意事项和要求。 有关配置云语音邮件的信息，请参阅配置云语音邮件。
ms.openlocfilehash: 4ae274f33d2b7d52c486cd9031d01bc3a532a6b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110278"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>为本地用户规划云语音邮件服务

## <a name="overview"></a>概述

本文介绍了为本地用户实施 Microsoft 云语音邮件服务的好处、规划注意事项和要求。 有关配置云语音邮件的信息，请参阅配置 [云语音邮件服务](configure-cloud-voicemail.md)。

云语音邮件将采用 Exchange 统一消息 (UM) ，为在 Exchange Server 2019 或 Exchange Online 上拥有邮箱的 Skype for Business 2019 语音用户提供语音邮件功能。 云语音邮件为本地用户和联机用户提供以下好处：

- 语音信箱应答和存放功能与增强的语音转录功能

- 使用 Skype for Business Online 或 Outlook 客户端访问用户 Exchange 邮箱中的语音邮件

- 能够使用 Microsoft 365 管理中心管理语音邮件选项

- 支持本地或云中的 Exchange 邮箱

- 利用 Exchange Online 统一消息中的现有用户问候语

> [!Important]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，此后用户将无法再通过 Skype for Business Online 客户端访问其 Exchange 邮箱中的语音邮件。

有关功能比较详细信息，请参阅 [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md)。

Skype for Business Server 2019 继续为邮箱使用早期版本的 Exchange Server (2013，2016) 。  了解将基于 Exchange Server 和 Skype for Business Server 版本使用哪个语音邮件解决方案是规划迁移到 Skype for Business Server 2019 或 Exchange Server 2019 的重要部分。 有关迁移和互操作性详细信息，请参阅 Plan [for Skype for Business Server and Exchange Server migration](plan-um-migration.md)。

借助云语音邮件，管理任务大大简化，因为：

- 无需配置 Exchange UM 角色。
- 云语音邮件的设置任务更简单。
- 语音邮件功能更新直接在云中提供，因此你的用户始终可以访问最新功能和更新，对累积更新和 CPU (的依赖) 。
- 对于内部部署和联机 Exchange 邮箱，您具有相同的一组控件。 有关这些控件详细信息，请参阅 [设置电话系统语音邮件](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)。

下图显示了混合部署中的云语音邮件：

![SfB 云语音邮件](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

未接听的呼叫的处理方式如下：  

1. 对于本地 Skype for Business 2019 中托管的用户，未接听的呼叫由本地 Skype for Business Server 发送到联机云语音邮件服务。
2. 该服务处理语音邮件，包括转录。
3. 然后，该服务将语音邮件放在用户的 Exchange 邮箱中，无论邮箱是本地邮箱还是联机邮箱。  
4. 用户可以从 Skype for Business 或 Outlook 客户端访问其语音邮件。

## <a name="requirements"></a>要求

以下要求假定你已在支持的拓扑中部署了 Skype for Business Server。  你的要求取决于你的方案：

- 如果已在联机使用 Exchange UM 并升级到 Skype for Business 2019，则需要修改托管语音邮件策略并验证托管提供商是否正确设置。 有关详细信息，请参阅配置 [云语音邮件服务](configure-cloud-voicemail.md)。

- 如果使用的是本地 Exchange UM，或者混合使用 Exchange UM 联机和内部部署，则需要同时修改托管语音邮件策略和托管提供商。  有关详细信息，请参阅配置 [云语音邮件服务](configure-cloud-voicemail.md)。

- 有关云语音邮件的新配置，请按照配置云语音邮件 [服务中概述的步骤操作](configure-cloud-voicemail.md)。

除了上述要求之外，还必须将以下要求配置为连接到 Microsoft 云语音邮件服务：

- 混合连接。 如果你已部署 Skype for Business Server，并且希望为本地用户启用云语音邮件，则必须确保在本地环境和联机环境之间设置了混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅规划 Skype for Business Server 与 [Microsoft 365 或 Office 365](plan-hybrid-connectivity.md) 之间的混合连接和配置 Skype for Business Server 和 [Office 365](configure-hybrid-connectivity.md)之间的混合连接。

- 必须为本地用户启用 企业语音 和 Skype for Business Server 中的托管语音邮件。

- 必须设置外部 Exchange Web (EWS) 自动发现，否则将限制某些云语音邮件功能。

- 如果你有本地 Exchange 服务器，则使用为邮箱用户设置云语音邮件中的步骤Exchange Server [云语音邮件](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)。

## <a name="migration-and-interoperability"></a>迁移和互操作性

如果计划部署 Skype for Business Server 2019 和/或 Exchange Server 2019，则必须仔细规划迁移以确保语音邮件服务持续有效。 请注意下列事项：

- Exchange Server 2019 不再提供 Exchange UM 功能
- Skype for Business Server 2019 不再与 Exchange Online UM 集成

下表列出了云语音邮件的版本互操作性和支持的拓扑，该表将用户可能托管的 Skype for Business Server 版本与提供其 Exchange 邮箱的可能版本进行比较。 如果你想要将 Skype for Business 2019 与 Exchange Online 或 Exchange Server 2019 一起使用，则需要使用云语音邮件。

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | 云语音邮件 | 云语音邮件 |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | 不支持 | 云语音邮件 |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | 不支持 | 云语音邮件 |

Microsoft 推荐以下迁移路径：

- 如果要升级到 Skype for Business Server 2019，可以在 Exchange Server 2013 或 2016 中使用 Exchange UM，但如果使用的是 Exchange Server 2019，则必须升级到云语音邮件。
- 如果要升级到 Exchange Server 2019，并且使用的是早期版本的 Exchange Server UM for Skype for Business Server 语音邮件，Microsoft 建议在邮箱升级之前升级到 Skype for Business Server 2019。  否则，语音邮件功能将丢失。
- 如果你要升级到 Skype for Business Server 2019，并且为具有 Exchange Online UM 的语音邮件配置了 Skype for Business Server 2015，则当用户的帐户移至 Skype for Business Server 2019 时，用户的语音邮件将自动从 Exchange Online UM 迁移到云语音邮件。 

有关规划迁移的信息，请参阅 Plan [for Skype for Business Server and Exchange Server migration](plan-um-migration.md)。