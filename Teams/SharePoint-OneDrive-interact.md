---
title: "SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: "了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互，例如，如何存储私人聊天文件，以及团队、频道和文档库之间的关系。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0207cb87d6d340e4904e1ff8526165bf43a3f99e
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互
=============================================================================

Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。 对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。

私人聊天文件存储在**发送方的** OneDrive for Business 文件夹中，在文件共享过程中，系统会自动向所有参与者授予权限。

如果你的租户中未启用 SharePoint Online，那么 Microsoft Teams 用户不能在团队中共享文件。 此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。

下面是团队、频道和文档库之间的关系示例。

对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹*共享文档*。 包括每个团队的默认频道**“常规”**频道在内的每个频道在*共享文档*文件夹下都有一个文件夹。

![某个团队的 SharePoint Online 中的“共享文档”文件夹及其在 Microsoft Teams 中的频道示意图。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

对于每个用户，OneDrive 文件夹 *Microsoft Teams 聊天文件*用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。

![用于每个用户聊天的 OneDrive 文件夹（名为 Microsoft Teams Chat Files）示意图。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
