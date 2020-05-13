---
title: 为本地用户规划云语音邮件服务 |PBX Skype for Business Server 2019
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
ms.openlocfilehash: 30a4983c79f4a7cddd274c272b5a094c17653bbb
ms.sourcegitcommit: 7c08d88dcaa85e34e93131bb9a5a64597c6d8155
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210628"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>为本地用户规划云语音邮件服务

## <a name="overview"></a>概述

本文介绍了为您的本地用户实施 Microsoft 云语音邮件服务的好处、规划注意事项和要求。 有关配置云语音邮件的信息，请参阅[配置云语音邮件服务](configure-cloud-voicemail.md)。

云语音邮件取代 Exchange 统一消息（UM），用于在 Exchange Server 2019 或 Exchange Online 上为邮箱提供适用于 Skype for Business 2019 语音用户的语音邮件功能。 云语音邮件为您的内部部署用户和联机用户提供以下好处：

- 通过增强的语音方式应答和放入功能的语音邮件

- 使用 Skype for Business Online 或 Outlook 客户端访问用户的 Exchange 邮箱中的语音邮件

- 使用基于 web 的 Office 365 门户管理语音邮件选项的能力

- 在本地或在云中支持 Exchange 邮箱

- 从 Exchange Online 统一消息中利用现有用户问候语

有关功能比较的详细信息，请参阅[Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)。

Skype for Business Server 2019 继续为其邮箱位于早期版本的 Exchange Server （2013，2016）的用户使用 Exchange UM。  了解将根据 Exchange Server 和 Skype for Business Server 版本使用哪种语音邮件解决方案是规划迁移到 Skype for business Server 2019 或 Exchange Server 2019 的重要部分。 有关迁移和互操作性的详细信息，请参阅[Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)。

使用云语音邮件，您的管理任务大大简化，因为：

- 无需配置 Exchange UM 角色。
- 云语音邮件的设置任务更简单。
- 对语音邮件功能的更新是直接在云中传递的，因此，您的用户始终可以访问最新的功能和更新，而不依赖于累积更新（Cu）。
- 对于内部部署和联机 Exchange 邮箱，都具有相同的控件集。 有关这些控件的详细信息，请参阅[设置电话系统语音邮件](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)。

下图显示了混合部署中的云语音邮件：

![SfB 云语音邮件](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

将按如下方式处理未应答的呼叫：  

1. 对于驻留在本地 Skype for business 2019 中的用户，本地 Skype for Business Server 会将未应答的呼叫发送到联机云语音邮件服务。
2. 该服务处理语音邮件，包括进行工作。
3. 然后，该服务将语音邮件存款到用户的 Exchange 邮箱中，无论邮箱是位于本地还是联机。  
4. 用户可以从其 Skype for Business 或 Outlook 客户端访问其语音邮件。

## <a name="requirements"></a>Requirements

以下要求假定您已在受支持的拓扑中部署了 Skype for Business 服务器。  您的要求取决于您的方案：

- 如果你已在使用 Exchange UM online，并且升级到 Skype for Business 2019，则需要修改托管的语音邮件策略，并验证托管提供程序的设置是否正确。 有关详细信息，请参阅[配置云语音邮件服务](configure-cloud-voicemail.md)。

- 如果您在本地使用 Exchange UM，或者使用 Exchange UM online 和内部部署的用户混合，则需要修改托管的语音邮件策略和托管提供程序。  有关详细信息，请参阅[配置云语音邮件服务](configure-cloud-voicemail.md)。

- 对于云语音邮件的新配置，请按照[配置云语音邮件服务](configure-cloud-voicemail.md)中所述的步骤操作。

除了上述要求之外，还必须配置以下要求以连接到 Microsoft 云语音邮件服务：

- 混合连接性。 如果已部署 Skype for Business Server，并且要为本地用户启用云语音邮件，则必须确保在本地和联机环境之间设置混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅[规划 skype For Business server 和 office 365 之间的混合连接](plan-hybrid-connectivity.md)和[配置 Skype for Business server 和 office 365 之间的混合连接](configure-hybrid-connectivity.md)。

- 必须在 Skype for Business Server 中为企业语音和托管语音邮件启用本地用户。

- 外部 Exchange Web 服务（EWS） URL 和自动发现必须设置，否则一些云语音邮件功能将受到限制。

- 如果您具有仅限本地部署&#x2014;也就是说，仅 Exchange 和 Skype for business 内部部署服务器&#x2014;但您希望充分利用云语音邮件，则需要电话系统许可证。

## <a name="migration-and-interoperability"></a>迁移和互操作性

如果您计划部署 Skype for Business Server 2019 和/或 Exchange Server 2019，则必须仔细规划迁移以确保语音邮件的持续服务。 请注意以下几点：

- Exchange Server 2019 不再提供 Exchange UM 功能
- Skype for Business Server 2019 不再与 Exchange Online UM 集成

下表列出了云语音邮件的版本互操作性和受支持的拓扑，它们将比较用户可能驻留的 Skype for Business Server 版本，并提供其 Exchange 邮箱的可能版本。 如果要将 Skype for Business 2019 与 Exchange Online 或 Exchange Server 2019 一起使用，则需要使用云语音邮件。

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | 云语音邮件 | 云语音邮件 |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | 云语音邮件 | 云语音邮件 |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | 不支持 | 云语音邮件 |

Microsoft 建议采用以下迁移途径：

- 如果要升级到 Skype for business Server 2019，可以在 Exchange Server 2013 或2016中使用 Exchange UM，但如果使用的是 Exchange Server 2019，则必须升级到云语音邮件。
- 如果要升级到 Exchange Server 2019，并且使用的是以前版本的 Exchange Server UM for Skype for business Server voice 消息，Microsoft 建议您先升级到 Skype for business Server 2019，然后再升级邮箱。  否则，语音邮件功能将丢失。
- 如果要升级到 Skype for business Server 2019，并且已为使用 Exchange Online UM 的语音邮件配置了 Skype for Business Server 2015，则用户的语音邮件将在其帐户移动到 Skype for business Server 2019 时自动从 Exchange Online UM 迁移到云语音邮件。 

有关规划迁移的详细信息，请参阅[Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)。
