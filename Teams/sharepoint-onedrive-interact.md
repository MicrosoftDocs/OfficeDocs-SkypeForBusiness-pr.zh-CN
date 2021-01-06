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
description: SharePoint Online & OneDrive for Business 与 Teams 交互;私人聊天文件存储&团队、标准频道和文档&交互。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ff18a0645f81d1892e246ee7432d58a1c728f3ad
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757777"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互

> [!Tip]
> 观看以下会话，以了解 Teams 如何与 Azure Active Directory (AAD)、Microsoft 365 组、Exchange、SharePoint 和 OneDrive for Business 进行交互：[Microsoft Teams 基础知识](https://aka.ms/teams-foundations)

Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队的每个标准频道获取默认团队网站文档库中的文件夹。 对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。 若要了解在 SharePoint 中更改网站地址的影响，请阅读"[更改网站地址"。](https://docs.microsoft.com/sharepoint/change-site-address)

> [!NOTE]
> 本文仅适用于标准通道。 专用通道的体系结构不同于标准通道。 每个专用频道都有自己的 SharePoint 网站集，与父团队网站分开。 若要了解有关详细信息，请参阅 [Microsoft Teams 中的专用频道](private-channels.md)。

私人聊天文件存储在发件人的 OneDrive for Business 文件夹中，权限作为文件共享过程的一部分自动授予给所有参与者。

如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Microsoft 365 或 Office 365 中没有 OneDrive for Business 存储空间。 文件共享将继续在标准频道中工作，但如果没有 Microsoft 365 或 Office 365 中的 OneDrive for Business 存储，用户将无法在聊天中共享文件。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。 

> [!NOTE]
> Microsoft Teams 目前不支持与本地 SharePoint 集成。

下面是团队、标准频道和文档库之间的关系示例。

对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹 **共享文档**。 每个标准频道（包括常规频道 (每个团队的默认频道) 共享文档中 **有一个文件夹**。

![SharePoint Online 中共享文档文件夹的图表。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 当前无法替代默认 SharePoint 站点和文档库。 我们已经知道你的需求，我们正在考虑。 查看 [Teams 路线图](https://aka.ms/teamsroadmap)或 [Teams UserVoice](https://aka.ms/TeamsUserVoice)，以随时了解即将推出的功能。

> [!TIP]
> 若要向团队添加链接到现有 SharePoint 网站页面或现有 SharePoint 文档库的选项卡，请进行以下操作：
> 1. 选择选项卡旁边的加号。
> 2. 为现有 SharePoint 网站页面选择 **SharePoint，** 或 **文档库现有文档** 库的 SharePoint。
> 3. 选择相应的页面或文档库。

对于每个用户，OneDrive 文件夹 **Microsoft Teams 聊天文件** 用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。

![名为 Microsoft Teams 聊天文件的 OneDrive 文件夹图示](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

请注意，对于公共团队，SharePoint 团队网站预配了"除外部用户以外的所有人"访问权限。 对于不是该团队成员的人，公共团队不会显示在 Teams 中。 但是，他们可以使用 SharePoint 团队网站的 URL 访问 SharePoint 团队网站上的内容。 

## <a name="channel-files-tab"></a>"频道文件"选项卡

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

Teams **中的** "文件"选项卡与 SharePoint 文档视图非常类似。 在" **文件"** 选项卡上，用户可以：

- 在"新建文件" **菜单中查看其他** 选项。
- 将文件同步到其本地驱动器。
- 在"**所有文档"** 菜单上，从 **"列表"** 视图切换到"**压缩"列表，切换到****"图块"** 视图。
- 识别需要关注或具有恶意软件的文件。
- 立即查看文件是只读还是签出。
- 签出并签入文件。
- 固定、取消固定和更改文件的排序顺序。
- 确定哪些文件需要元数据
- 从更多筛选器选项中进行选择。
- 基于列标题对文件进行分组。
- 修改列设置 (向左或向右移动，隐藏) 和列宽。

## <a name="default-link-type-setting"></a>默认链接类型设置

SharePoint 和 OneDrive 具有管理员设置，用于指定为文件创建的链接的默认链接类型。 Teams 正在采用相同的方法，方法是重新使用管理员为 SharePoint 和 OneDrive 设置的设置。 有关此方法的更多详细信息，请参阅"当用户获取用于共享的链接时更改[默认链接类型"。](https://docs.microsoft.com/sharepoint/change-default-sharing-link) 

## <a name="more-information"></a>更多信息

有关 SharePoint 如何与 Teams 协同工作的信息，请参阅 SharePoint 和 [Teams：更好地协同工作](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。

若要详细了解 Teams 中的来宾体验，请阅读[来宾体验。](guest-experience.md)

