---
title: SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: 了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互，例如，如何存储私人聊天文件，以及团队、频道和文档库之间的关系。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af1d12eda58dc481ba28bf96ff4ecbfeab8ed5f0
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37567117"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互

> [!Tip]
> 观看以下会话，了解团队如何与 Azure Active Directory （AAD）、Office 365 组、Exchange、SharePoint 和 OneDrive for business 进行交互： [Microsoft 团队基础](https://aka.ms/teams-foundations)

Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。 对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。

私人聊天文件存储在发送方的 OneDrive for Business 文件夹中，在文件共享过程中，系统会自动向所有参与者授予权限。

如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Office 365 中没有 OneDrive for Business 存储空间。 文件共享将继续在频道中工作，但用户无法在 Office 365 中共享没有 OneDrive for business 存储的聊天文件。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。 

> [!NOTE]
> 目前不支持 Microsoft 团队与本地 SharePoint 的集成。

下面是团队、频道和文档库之间的关系示例。

对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹**共享文档**。 包括每个团队的默认频道“**常规**”频道在内的每个频道在“**共享文档**”下都有一个文件夹。

![SharePoint Online 中的 "共享文档" 文件夹的图表。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 当前无法替代默认 SharePoint 站点和文档库。 我们已经知道你的需求，我们正在考虑。 查看 [Teams 路线图](https://aka.ms/teamsroadmap)或 [Teams UserVoice](https://aka.ms/TeamsUserVoice)，以随时了解即将推出的功能。

> [!TIP]
> 若要向团队添加链接到现有 SharePoint 网站页面或现有 SharePoint 文档库的选项卡，请执行以下操作：
> 1. 选择选项卡旁边的加号。
> 2. 为现有文档库的现有 SharePoint 网站页面或**文档库**选择任一**SharePoint** 。
> 3. 选择相应的页面或文档库。

对于每个用户，OneDrive 文件夹 **Microsoft Teams 聊天文件**用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。

![名为 Microsoft 团队聊天文件的 OneDrive 文件夹的图表](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>频道文件选项卡

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

团队中的 "**文件**" 选项卡紧密类似于 SharePoint 文档视图。 在 "**文件**" 选项卡上，用户可以：

- 在 "**新建**文件" 菜单中查看其他选项。
- 将文件同步到其本地驱动器。
- 在 "**所有文档**" 菜单上，从**列表**视图切换到**压缩列表**到 "**磁贴**" 视图。
- 确定需要关注或有恶意软件的文件。
- 立即查看文件是否为只读或已签出。
- 签出和签入文件。
- 固定、取消固定和更改文件的排序顺序。
- 确定需要元数据的文件
- 从更多筛选选项中进行选择。
- 基于列标题对文件进行分组。
- 修改栏设置（向左或向右移动、隐藏）和列宽。

## <a name="default-link-type-setting"></a>默认链接类型设置

SharePoint 和 OneDrive 具有管理员设置，用于指定为文件创建的链接的默认链接类型。 团队通过重复使用管理员为 SharePoint 和 OneDrive 设置的设置来采用相同的方法。 有关此方法的更多详细信息，[请参阅更改用户获取共享链接时的默认链接类型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。 

## <a name="more-information"></a>更多信息

有关 SharePoint 如何与团队协同工作的详细信息，请参阅[sharepoint 和团队：更好地协作](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。

若要了解有关团队中的来宾体验的详细信息，请阅读[来宾体验](guest-experience.md)。

