---
title: SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint联机& OneDrive for Business与 Teams 交互;私人聊天文件存储&团队、标准频道和文档库&交互。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d063cae8b87ffcacd63676da17fc000384c432c
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948619"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互

> [!Tip]
> 观看以下会话，以了解 Teams 如何与 Azure Active Directory (AAD)、Microsoft 365 组、Exchange、SharePoint 和 OneDrive for Business 进行交互：[Microsoft Teams 基础知识](https://aka.ms/teams-foundations)

每个团队Microsoft Teams在 SharePoint Online 中都有一个团队网站，而团队的每个标准频道在默认团队网站文档库中都有一个文件夹。 对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。 若要了解更改网站地址对SharePoint的影响，请阅读[更改网站地址](/sharepoint/change-site-address)。

> [!NOTE]
> 本文仅适用于标准通道。 专用通道的体系结构不同于标准通道。 每个专用频道都有自己的SharePoint网站集，与父团队网站分开。 若要了解有关详细信息，请参阅中的专用[Microsoft Teams。](private-channels.md)

私人聊天文件存储在发件人的 OneDrive for Business 文件夹中，权限会在文件共享过程中自动授予所有参与者。

如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Microsoft 365 或 Office 365 中没有 OneDrive for Business 存储空间。 文件共享将继续在标准频道中工作，但如果不将文件存储OneDrive for Business或Microsoft 365，用户Office 365。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。 

> [!NOTE]
> 目前SharePoint本地部署Microsoft Teams集成。

下面是团队、标准频道和文档库之间的关系示例。

对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹 **共享文档**。 每个标准频道（包括 **"** 常规" (每个团队的默认频道) 共享 **文档"中都有一个文件夹**。

![联机共享文档文件夹的SharePoint图。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 当前无法替代默认 SharePoint 站点和文档库。 我们已经知道你的需求，我们正在考虑。 查看 [Teams 路线图](https://aka.ms/teamsroadmap)或 [Teams UserVoice](https://aka.ms/TeamsUserVoice)，以随时了解即将推出的功能。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

> [!TIP]
> 若要向团队添加一个链接到现有网站SharePoint或现有文档库的选项卡，SharePoint文档库：
> 1. 选择选项卡旁边的加号。
> 2. 为 **SharePoint** 网站页面选择SharePoint，或 **文档库现有文档** 库的页。
> 3. 选择相应的页面或文档库。

对于每个用户，OneDrive 文件夹 **Microsoft Teams 聊天文件** 用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。

![名为 OneDrive 聊天文件Microsoft Teams文件夹的图示](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

请注意，对于公共团队，SharePoint网站预配了"除外部用户以外的所有人"访问权限。 对于不是该团队Teams，公共团队不会显示在"公共团队"中。 但是，他们可以使用团队SharePoint网站的 URL 访问SharePoint网站上的内容。 

## <a name="channel-files-tab"></a>"频道文件"选项卡

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

"**文件"** 选项卡Teams文档视图SharePoint视图。 在" **文件"** 选项卡上，用户可以：

- 在"新建文件" **菜单中查看其他** 选项。
- 将文件同步到本地驱动器。
- 在"**所有文档"** 菜单上，从"列表 **"** 视图切换到 **"压缩列表"，切换到****"平铺"** 视图。
- 识别需要关注或具有恶意软件的文件。
- 立即查看文件是只读还是签出。
- 签出并签入文件。
- 固定、取消固定和更改文件的排序顺序。
- 确定哪些文件需要元数据
- 从更多筛选器选项中进行选择。
- 基于列标题对文件进行分组。
- 修改列设置 (向左或向右移动，) 和列宽。

## <a name="default-link-type-setting"></a>默认链接类型设置

SharePoint和OneDrive具有管理员设置，用于指定为文件创建的链接的默认链接类型。 Teams管理员为用户和管理员设置的设置，SharePoint采用OneDrive。 有关此方法的更多详细信息，请参阅在用户获取用于共享的链接时更改 [默认链接类型](/sharepoint/change-default-sharing-link)。 

## <a name="more-information"></a>更多信息

有关如何与 SharePoint 协同工作Teams，请参阅SharePoint[和Teams：更好地协同工作](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。

若要详细了解来宾体验Teams，请阅读[来宾体验是什么](guest-experience.md)。