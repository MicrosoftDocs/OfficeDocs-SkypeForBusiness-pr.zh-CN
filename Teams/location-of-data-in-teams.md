---
title: Microsoft Teams 中的数据位置
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 在本文中，你将了解这些数据在 Microsoft Teams 中的地理位置。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121682"
---
# <a name="location-of-data-in-microsoft-teams"></a>Microsoft Teams 中的数据位置

Teams 中的数据位于与 Microsoft 365 或 Office 365 组织关联的地理区域中。 目前，Teams 支持澳大利亚、加拿大、法国、德国、印度、日本、南非、韩国、瑞士（包括列支敦士登）、阿拉伯联合酋长国、英国、美洲、亚太地区和欧洲、中东和非洲地区。 

> [!IMPORTANT]
> Teams 目前只为新租户提供澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、韩国、南非和瑞士（包括列支敦士登）的数据驻留。
> 新的租户被定义为任何未从租户中的单个用户登录 Teams 的租户。 来自澳大利亚、印度、日本和韩国的现有租户将继续将其 Teams 数据存储在亚太地区。 加拿大的现有租户将继续将其数据存储在美国。 法国、德国、列支敦士登、阿拉伯联合酋长国、英国、南非和瑞士的现有租户的数据将存储在欧洲、中东和非洲 (EMEA) 地区。

## <a name="where-your-teams-data-is-stored"></a>你的 Teams 数据的存储位置

要查看哪些区域托管你的租户数据，请转到 [Microsoft 365 管理中心](https://portal.office.com/adminportal/home) > “**设置**” > “**组织配置文件**”。 向下滚动到**数据位置**。

![包含管理中心中的 Teams 的数据位置表的屏幕截图](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Teams 静态数据的位置

Teams 数据的存储方式将有所不同，具体取决于内容类型。 

![显示 Teams 内容类型及其静态存储位置的图表](media/location-of-data-storage-at-rest.png)

查看有关 [Microsoft Teams 体系结构的 Ignite 分组讨论](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)，以进行深入讨论。

### <a name="core-teams-customer-data"></a>核心 Teams 客户数据

如果您的租户位于澳大利亚、加拿大、欧盟、法国、德国、印度、日本、南非、韩国、瑞士（包括列支敦士登）、阿拉伯联合酋长国、英国或美国，则 Microsoft 仅在该位置存储以下客户数据：

- Teams 聊天、团队和频道对话、图像、语音邮件和联系人
- SharePoint Online 网站内容和存储在该网站中的文件
- 上传到 OneDrive for Business 的文件

#### <a name="chat-channel-messages-team-structure"></a>聊天，频道消息，团队结构

Teams 中的每个团队都由 Microsoft 365 组及其 SharePoint 站点和 Exchange 邮箱支持。 私密聊天（包括群组聊天）、在频道中作为会话一部分发送的消息以及团队和频道的结构都存储在运行于 Azure 的聊天服务中。 数据还存储在用户和组邮箱中的隐藏文件夹中，以启用信息保护功能。

#### <a name="voicemail-and-contacts"></a>语音邮件和联系人

语音邮件存储在 Exchange 中。 联系人存储在基于 Exchange 的云数据存储中。 Exchange 和基于 Exchange 的云存储已在全球每个数据中心地理位置提供数据驻留。 对于所有团队，语音信箱和联系人存储在澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、南非、韩国、瑞士（包括列支敦士登）和美国的国家/地区。 对于所有其他国家/地区，基于租户相关性，文件存储在美国、欧洲或亚太地区。

#### <a name="images-and-media"></a>图像和媒体

聊天中使用的媒体（Giphy GIF 除外，它没有被存储，但是指向原始 Giphy 服务 URL 的引用链接，Giphy 是非 Microsoft 服务）存储在基于 Azure 的媒体服务中，该服务部署到与聊天服务相同的位置。

#### <a name="files"></a>文件

频道中共享的文件（包括 OneNote 和 Wiki ）存储在团队的 SharePoint 站点中。 在私密聊天、会议或通话期间的聊天中共享的文件将上载并存储在 OneDrive 中，供共享该文件的用户的业务帐户使用。 Exchange、SharePoint 和 OneDrive 已经在全球每个数据中心地理位置提供数据驻留。 因此，对于现有客户，作为 Teams 体验一部分的所有文件、OneNote 笔记本、Team wiki 内容和邮箱都已根据您的租户相关性存储在该位置。 文件存储在澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、南非、韩国和瑞士（包括列支敦士登）的国家/地区。 对于所有其他国家/地区，基于租户相关性，文件存储在美国、欧洲或亚太地区。

### <a name="datacenter-locations"></a>数据中心位置

本节中描述的 Teams 服务将静态数据存储在以下位置：

|国家或地区  |数据中心位置 |
|---------|---------|
|澳大利亚   |新南威尔士州和维多利亚         |
|加拿大    |魁北克市和多伦多         |
|法国    |马赛和巴黎         |
|德国    |柏林和法兰克福      |
|印度   |金奈和普纳        |
|日本    |东京（埼玉）和大阪         |
|列支敦士登   |日内瓦和苏黎世       |
|南非     |约翰内斯堡和开普敦         |
|韩国     |首尔和釜山         |
|瑞士    |日内瓦和苏黎世       |
|阿拉伯联合酋长国     |阿布扎比和迪拜         |
|英国     | 加的夫和伦敦        |
|美洲 - 北美洲和南美洲 (AMER) |加州湾和弗吉尼亚州博伊顿       |
|亚太地区 (APAC)  |新加坡和香港特别行政区        |
|欧洲、中东和亚洲 (EMEA)   |都柏林和阿姆斯特丹        |

> [!NOTE]
> 对列支敦士登来说，数据存储在日内瓦和苏黎世的瑞士数据中心。

### <a name="data-stored-with-a-third-party-storage-provider"></a>使用第三方存储提供商存储的数据

因此，对于那些依赖于第三方存储位置的服务的用户来说，应该允许他们将这些数据存储在第三方的位置上。

- **选项卡**：选项卡允许用户将应用程序和服务中的信息固定到频道。 因此，它因存储数据的选项卡类型而异。 该选项卡本身不存储任何数据。 例如，SharePoint 选项卡将根据 SharePoint 网站集的预配位置存储数据。 包含合作伙伴信息的选项卡将直接将数据存储在合作伙伴使用的系统中，并且只显示其视图。
- **其他合作伙伴应用**：对于您可能在 Teams 体验中使用的合作伙伴的应用程序和服务，Microsoft 不提供任何数据驻留支持。 直接查看这些解决方案中的信息，以了解其数据的存储位置。

## <a name="see-also"></a>另请参阅

- [Microsoft Teams 推出阿联酋数据驻留](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams 推出韩国数据驻留](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams 推出南非数据驻留](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams 推出法国数据驻留](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams 推出印度数据驻留，即将推出其他地点](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams 推出澳大利亚和日本数据驻留](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams 推出加拿大的数据驻留、澳大利亚和日本即将推出](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
