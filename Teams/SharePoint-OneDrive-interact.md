---
title: SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: 了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互，例如，如何存储私人聊天文件，以及团队、频道和文档库之间的关系。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f790a01050811ee46526fe37a4d6c14f107491b5
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827737"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互

> [!Tip]
> 观看下面的会话，若要了解与 Azure Active Directory (AAD)、 Office 365 组、 Exchange、 SharePoint 和 OneDrive for Business 团队交互的方式：[基础的 Microsoft 团队](https://aka.ms/teams-foundations)

Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。 对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。

私人聊天文件存储在发送方的 OneDrive for Business 文件夹中，在文件共享过程中，系统会自动向所有参与者授予权限。

如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Office 365 中没有 OneDrive for Business 存储空间。 文件共享将继续以在通道，但用户无法共享 Office 365 中的业务存储中没有 OneDrive 聊天文件。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。 

> [!NOTE]
> 与 SharePoint 内部部署集成不支持的 Microsoft 团队这一次。

下面是团队、频道和文档库之间的关系示例。

对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹**共享文档**。 包括每个团队的默认频道“**常规**”频道在内的每个频道在“**共享文档**”下都有一个文件夹。

![某个团队的 SharePoint Online 中的“共享文档”文件夹及其在 Microsoft Teams 中的频道示意图。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 当前无法替代默认 SharePoint 站点和文档库。 我们已经知道你的需求，我们正在考虑。 查看 [Teams 路线图](https://aka.ms/teamsroadmap)或 [Teams UserVoice](https://aka.ms/TeamsUserVoice)，以随时了解即将推出的功能。

> [!TIP]
> 向团队链接到现有 SharePoint 网站页或现有的 SharePoint 文档库中添加选项卡：
> 1. 选择选项卡旁边的加号。
> 2. 选择**SharePoint**的现有 SharePoint 网站页或**文档库**的现有文档库。
> 3. 选择相应的页或文档库。

对于每个用户，OneDrive 文件夹 **Microsoft Teams 聊天文件**用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。

![用于每个用户聊天的 OneDrive 文件夹（名为 Microsoft Teams Chat Files）示意图。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>通道文件选项卡

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

**文件**选项卡团队非常相似的 SharePoint 文档视图。 在**文件**选项卡，用户可以：

- 请参阅**新建**文件菜单中的其他选项。
- 文件与他们的本地驱动器同步。
- 在**所有文档**菜单上，从**列表**视图切换到**紧凑列表**到**平铺**视图。
- 确定需要注意或恶意软件的文件。
- 立即查看文件是只读的或已签出。
- 签出和签入文件。
- 固定、 取消固定，并将更改文件的排序顺序。
- 确定需要哪些文件的元数据
- 选择从更多的筛选器选项。
- 基于列标题的组文件。
- 修改列设置 （向左移动或向右，隐藏） 和列的宽度。

## <a name="default-link-type-setting"></a>设置的默认链接类型

SharePoint 和 OneDrive 具有管理设置用于指定链接的文件创建的默认链接类型。 团队采用方法的同一个通过重用管理员设置 SharePoint 和 OneDrive 的设置。 有关此方法的详细信息进行了描述[更改时用户获取共享链接的默认链接类型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。 

## <a name="more-information"></a>详细信息

有关与团队的 SharePoint 工作原理的详细信息，请参阅[SharePoint 和团队： 携手共赢](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。

若要了解团队中的来宾体验，请阅读[新增的来宾体验](guest-experience.md)。

