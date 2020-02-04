---
title: Microsoft Teams 中的数据位置
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 了解在 Microsoft 团队中存储数据的位置。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24432b0854ac0c4256f5d097bacfca5f1a392d72
ms.sourcegitcommit: 2cb46af39a0d116e8fd020aa04bd2ecbd6998a5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41679037"
---
# <a name="location-of-data-in-microsoft-teams"></a>Microsoft Teams 中的数据位置

Teams 中的数据位于与你的 Office 365 租户关联的地理区域。 目前，团队支持澳大利亚、加拿大、法国、德国、印度、日本、南非、韩国、瑞士（包括列支敦士登）、阿拉伯联合酋长国、英国、美洲、APAC 和 EMEA 地区。 

> [!IMPORTANT]
> 团队目前在澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、韩国、南非和瑞士（包括列支敦士登）中提供了新租户的数据常驻。
> 新租户的定义是，该租户中没有任何一个用户登录过 Teams。 澳大利亚、印度、日本和韩国的现有租户将继续在 APAC 区域中存储其团队数据。 加拿大的现有租户将继续将其数据存储在美洲。 在法国、德国、列支敦士登、阿拉伯联合酋长国、英国、南非和瑞士的现有租户的数据将存储在 EMEA 地区。

## <a name="where-your-teams-data-is-stored"></a>存储团队数据的位置

若要查看哪个区域驻留你的租户的数据，请转到[Microsoft 365 管理中心](https://portal.office.com/adminportal/home) > **设置** > **组织配置文件**。 向下滚动到“**数据位置**”。

![数据位置表的屏幕截图，其中包括管理中心中的团队](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>工作组数据的存放位置

团队数据的存储方式会有所不同，具体取决于内容类型。 

![显示团队内容类型及其在其他位置存储的位置的图表](media/location-of-data-storage-at-rest.png)

查看[Microsoft 团队体系结构上的 Ignite 专题讨论](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)可进行深入讨论。

### <a name="core-teams-customer-data"></a>核心团队客户数据

如果你的租户是在澳大利亚、加拿大、欧洲同盟、法国、德国、印度、日本、南非、韩国、瑞士（包括列支敦士登）、阿拉伯联合酋长国、英国或美国，Microsoft 商店以下客户数据仅位于该位置内：

- 团队聊天、团队和频道对话、图像、语音邮件和联系人
- SharePoint Online 网站内容和该网站中存储的文件
- 已上载到 OneDrive for business 的文件

#### <a name="chat-channel-messages-team-structure"></a>聊天、频道消息、团队结构

团队中的每个团队均受 Office 365 组及其 SharePoint 网站和 Exchange 邮箱的支持。 私人聊天（包括群组聊天）、在频道中作为对话的一部分发送的邮件以及团队和频道的结构存储在在 Azure 中运行的聊天服务中。 数据还存储在用户和组邮箱的隐藏文件夹中，以启用信息保护功能。

#### <a name="voicemail-and-contacts"></a>语音邮件和联系人

语音邮件存储在 Exchange 中。 联系人存储在基于 Exchange 的云数据存储中。 Exchange 和基于 Exchange 的云应用商店已在每个全球数据中心 geos 提供了数据派驻服务。 对于所有团队，语音邮件和联系人均存储在国内、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、南非、韩国、瑞士、瑞士（包括列支敦士登）和美国。 对于所有其他国家/地区，文件基于租户相关性存储在美国、欧洲或亚太地区位置。

#### <a name="images-and-media"></a>图像和媒体

聊天中使用的媒体（除不存储的 Giphy Gif 和指向原始 Giphy 服务 URL 的引用链接，Giphy 是非 Microsoft 服务）存储在与聊天服务部署到同一位置的基于 Azure 的媒体服务中。

#### <a name="files"></a>文件

在频道中共享的文件（包括 OneNote 和 Wiki）存储在团队的 SharePoint 网站中。 在会议或通话期间，在私人聊天或聊天中共享的文件将上载并存储在共享该文件的用户的商业帐户中。 Exchange、SharePoint 和 OneDrive 已在每个全球数据中心 geos 提供了数据派驻服务。 因此，对于现有客户，所有文件、OneNote 笔记本、团队 wiki 内容和属于团队体验的邮箱已存储在基于你的租户相关性的位置。 文件存储在适用于澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、南非、韩国和瑞士（包括列支敦士登）的国家/地区。 对于所有其他国家/地区，文件基于租户相关性存储在美国、欧洲或亚太地区位置。

### <a name="datacenter-locations"></a>数据中心位置

本部分中所述的团队服务将数据存储在以下位置中的其他位置：

|国家或地区  |数据中心位置 |
|---------|---------|
|澳大利亚   |新的南威尔士和维多利亚         |
|加拿大    |魁北克城市和多伦多         |
|法国    |Marseille 和巴黎         |
|德国    |柏林和法兰克福      |
|印度   |金奈和 Pune        |
|日本    |东京（Saitama）和大阪         |
|列支敦士登   |日内瓦和苏黎世       |
|南非     |约翰内斯堡和佛得角         |
|韩国     |首尔和 Busan         |
|瑞士    |日内瓦和苏黎世       |
|阿拉伯联合酋长国     |Abu Dhabi 和迪拜         |
|英国     | 加和伦敦        |
|美洲–北部和南（AMER） |Bay、CA 和 Boydton、VA       |
|亚太地区（APAC）  |新加坡和香港特别行政区        |
|欧洲、中东和亚洲（EMEA）   |都柏林和阿姆斯特丹        |

> [!NOTE]
> 对于列支敦士登，数据存储在日内瓦和苏黎世的瑞士数据中心中的其他位置。

### <a name="data-stored-with-a-third-party-storage-provider"></a>与第三方存储提供商存储的数据

允许用户使用第三方存储提供程序存储文件的组织依赖于这些服务的存储位置，因此应单独查看这些服务的剩余数据位置。

- **选项卡**：选项卡允许用户将应用和服务中的信息固定到频道。 因此，它会因存储数据的选项卡的类型而异。 选项卡本身不存储任何数据。 例如，SharePoint 选项卡将根据 SharePoint 网站集的预配位置存储数据。 包括来自合作伙伴的信息的选项卡将直接存储在合作伙伴使用的系统中的数据，并仅显示该数据的视图。
- **其他合作伙伴应用**： Microsoft 不会为你可能在团队体验中使用的合作伙伴提供对应用和服务的任何数据派驻支持。 直接查看这些解决方案中的信息，了解存储其数据的位置。

## <a name="see-also"></a>另请参阅

- [Microsoft 团队启动阿拉伯联合酋长国数据派驻服务](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft 团队启动南亚韩文数据派驻服务](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft 团队启动南非数据派驻服务](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft 团队启动法国数据派驻服务](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft 团队启动印度数据派驻服务，即将推出其他 geos](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft 团队启动澳大利亚和日本数据派驻服务](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft 团队启动加拿大数据派驻、澳大利亚和日本即将推出](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
