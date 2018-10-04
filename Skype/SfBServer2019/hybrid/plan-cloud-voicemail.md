---
title: 规划云语音邮件服务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 本文介绍优点、 规划注意事项以及用于实现 Microsoft 云语音邮件服务的要求。 有关配置云语音邮件的信息，请参阅配置云语音邮件。
ms.openlocfilehash: 8f7c2e394aa7d3f5a04961088202d1d9055eef9e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370632"
---
# <a name="plan-cloud-voicemail-service"></a>规划云语音邮件服务

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a>概述 

本文介绍优点、 规划注意事项以及用于实现 Microsoft 云语音邮件服务的要求。 有关配置云语音邮件的信息，请参阅[配置云语音邮件服务](configure-cloud-voicemail.md)。

云语音邮件将取代的 Exchange 统一消息 (UM) 中提供语音消息通讯功能的 Skype 的业务 2019年语音用户拥有在 Exchange Server 2019 或 Exchange Online 邮箱。 云语音邮件的本地和联机用户提供以下好处：

- 语音邮件应答和处理功能提供增强的语音转录

- 使用 Skype 业务联机或 Outlook 客户端的用户的 Exchange 邮箱中的语音邮件访问 

- 能够使用基于 web 的 Office 365 门户管理语音邮件选项

- 对 Exchange 邮箱在本地或云中的支持

- 利用从 Exchange Online 统一消息的现有用户问候语

有关功能比较的详细信息，请参阅[Plan for Business Server 和 Exchange Server 迁移的 Skype](plan-um-migration.md)。 

业务服务器 2019年的 Skype 继续使用 Exchange UM 用户为邮箱位于早期版本的 Exchange Server 2013 (2016年）。  了解基于 Exchange Server 和 Skype 业务服务器将使用语音邮件解决方案版本是规划迁移到任一 Skype 业务服务器 2019年或 Exchange Server 2019 的重要组成部分。 有关迁移和互操作性的详细信息，请参阅[Plan for Business Server 和 Exchange Server 迁移的 Skype](plan-um-migration.md)。 

与云语音邮件，因为是大大简化管理任务：

- 没有需要配置 Exchange UM 角色。
- 云语音邮件的安装任务更加简单。
- 直接在云中，了传递到语音邮件功能的更新，以便您的用户始终在累积更新 （累积） 有权访问的最新功能和更新较少的依赖关系。
- 您具有一组相同的内部部署和联机 Exchange 邮箱的控件。 有关这些控件的详细信息，请参阅[设置电话系统的语音邮件](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)。

下图显示了在混合部署中的云语音邮件：


![SfB 云语音邮件](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

未应答的呼叫处理，如下所示：  

1. 为用户驻留在 Skype 的本地业务 2019年，未应答的呼叫发送通过内部部署 Skype 业务服务器到 online 云语音邮件服务。 
2. 该服务处理语音邮件，包括转录。
3. 该服务然后放语音邮件的用户的 Exchange 邮箱中邮箱是否在本地或联机。  
4. 用户可以从以下任意业务或 Outlook 客户端其 Skype 访问他们的语音邮件。

## <a name="requirements"></a>要求

以下要求假定您已有 Skype 业务服务器部署中支持的拓扑。  您的要求取决于您的方案：

- 如果您已使用 Exchange UM online 您升级到业务 2019年的 Skype，您将需要修改托管语音邮件策略，请确认已正确设置宿主提供商。 有关详细信息，请参阅[配置云语音邮件服务](configure-cloud-voicemail.md)。

- 如果您在本地，Exchange UM 使用或具有联机和本地 Exchange UM 使用的用户的组合，您将需要修改您的托管语音邮件策略和宿主提供商。  有关详细信息，请参阅[配置云语音邮件服务](configure-cloud-voicemail.md)。

- 云语音邮件的新配置，请按照所述[配置语音邮件云服务](configure-cloud-voicemail.md)中的步骤。

除了上述，要求如下要求必须配置为连接到 Microsoft 云语音邮件服务：

- 混合连接性。 如果您已有 Skype 业务服务器部署，并且您希望为您的内部部署用户启用云语音邮件，您必须确保您有设置您的本地和联机环境之间的混合连接性。 此有时也称为拆分域配置。 

   有关详细信息，请参阅[规划之间 Skype Business Server 和 Office 365 的混合连接性](plan-hybrid-connectivity.md)和[Skype Business Server 和 Office 365 之间配置混合连接性](configure-hybrid-connectivity.md)。

- 内部部署业务服务器，必须为用户启用了企业语音和 Skype 中承载语音邮件。

- 外部 Exchange Web Services (EWS) URL 和自动发现，必须先设置或某些云语音邮件功能将受到限制。

-  如果您具有内部部署仅部署-的只有 Exchange 和 Skype for Business 的本地服务器-但要充分利用云语音邮件，则需要 ON PREM 许可证。 

## <a name="migration-and-interoperability"></a>迁移和互操作性

如果您打算部署的 Business Server 2019 和/或 Exchange Server 2019 Skype，您必须规划迁移仔细以确保能够持续的语音消息传递服务。 注意以下几项：

- Exchange Server 2019 不再提供的 Exchange UM 功能
- Skype 的业务服务器 2019年不再与 Exchange Online UM 集成

下表中列出版本互操作性和受支持的拓扑云语音邮件。 对于预览版本，云语音邮件只适用于 Skype Business Server 和 Exchange Server 2019 或 Exchange Online。


|                               | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---------------------------    |:---------------------|:---------------------|:------------------|:---------------------- |
| Skype 业务服务器 2019 | Exchange Server 统一消息 | Exchange Server 统一消息 | 云语音邮件 | 云语音邮件
Skype for Business Server 2015 | Exchange Server 统一消息 | Exchange Server 统一消息 |  | 云语音邮件 <br> Exchange Online UM * |
Lync Server 2013 <br>  | Exchange Server 统一消息 | Exchange Server 统一消息 | | 云语音邮件 <br> Exchange Online UM * |

\*直到弃用。

Microsoft 建议的以下的迁移路径：

-  如果您要升级到 Skype 的业务服务器 2019年，您可以使用 Exchange UM 中 Exchange Server 2013 或 2016，但如果使用 Exchange Server 2019 必须升级到云语音邮件。

- 如果您要升级到 Exchange Server 2019，并且您使用早期版本的 Exchange Server UM 的 Skype 进行业务服务器语音消息传递，Microsoft 建议您升级到 Skype 的业务服务器 2019年邮箱升级之前。  否则，语音消息功能都将丢失。 


有关规划迁移的详细信息，请参阅[Plan for Business Server 和 Exchange Server 迁移的 Skype](plan-um-migration.md)。
