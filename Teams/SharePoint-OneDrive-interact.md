---
title: SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: 了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互，例如，如何存储私人聊天文件，以及团队、频道和文档库之间的关系。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c7cddeb2ee125fa54cc7db353c83157bec90d76
ms.sourcegitcommit: 6d30cfdd8c8b8908d4e4f278c39fd22062f4a888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890545"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互
=============================================================================

> [!Tip]
> 观看下面的会话，若要了解与 Azure Active Directory (AAD)、 Office 365 组、 Exchange、 SharePoint 和 OneDrive for Business 团队交互的方式：[基础的 Microsoft 团队](https://aka.ms/teams-foundations)

Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。 对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。

私人聊天文件存储在发送方的 OneDrive for Business 文件夹中，在文件共享过程中，系统会自动向所有参与者授予权限。

如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Office 365 中没有 OneDrive for Business 存储空间。 文件共享将继续以在通道，但用户无法共享 Office 365 中的业务存储中没有 OneDrive 聊天文件。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。 

> [!NOTE]
> 与 Sharepoint 内部部署集成不支持的 Microsoft 团队这一次。

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
