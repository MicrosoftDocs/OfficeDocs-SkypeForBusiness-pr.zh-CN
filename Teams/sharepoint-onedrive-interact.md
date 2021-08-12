---
title: 如何SharePoint OneDrive交互Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive与 Teams 交互;私人聊天文件存储&团队、标准频道和文档库&交互。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e550acd5d47c0199318c820f595253eb8f2477421f62d90e3a7d16ced2336d05
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308483"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>如何SharePoint OneDrive交互Microsoft Teams

> [!Tip]
> 观看以下会话，了解 Teams 如何与 Azure Active Directory (AAD) 、Microsoft 365 组、Exchange、SharePoint 和 OneDrive 交互：Microsoft Teams [](https://aka.ms/teams-foundations)

每个团队Microsoft Teams都有一个团队网站SharePoint，团队中的每个标准频道在默认团队网站文档库中都有一个文件夹。 每个[专用频道](private-channels.md)都有自己的独立SharePoint站点。 若要了解有关这些团队网站和频道网站的信息，请参阅[管理Teams网站和频道网站](/sharepoint/teams-connected-sites)。

对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。 若要了解更改网站地址对SharePoint的影响，请阅读[更改网站地址](/sharepoint/change-site-address)。

私人聊天文件存储在发件人的 OneDrive 文件夹中，权限会在文件共享过程中自动授予所有参与者。

如果未为用户分配SharePoint许可证，则他们OneDrive存储Microsoft 365。 文件共享在标准通道中正常工作，但如果没有在聊天中存储OneDrive用户Microsoft 365。

通过将文件存储在文档SharePoint库OneDrive，将遵循在组织级别配置的所有符合性规则。 

> [!NOTE]
> 不支持SharePoint服务器集成Teams。

下面是团队、标准频道和文档库之间的关系示例。

对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹 **共享文档**。 每个标准频道（包括 **"** 常规" (每个团队的默认频道) 共享 **文档"中都有一个文件夹**。

!["共享文档"文件夹在SharePoint。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

不能SharePoint网站和文档库的默认文档。

对于每个用户，OneDrive 文件夹 **Microsoft Teams 聊天文件** 用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。

![名为 OneDrive 聊天文件Microsoft Teams文件夹的图示](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

请注意，对于公共团队，SharePoint网站预配了"除外部用户以外的所有人"访问权限。 对于不是该团队Teams，公共团队不会显示在"公共团队"中。 但是，他们可以使用团队SharePoint网站的 URL 访问SharePoint网站上的内容。 

## <a name="channel-files-tab"></a>"频道文件"选项卡

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

当用户共享文件时，默认显示的共享链接类型在SharePoint设置。 有关 [信息，请参阅在用户获取用于共享的链接时更改](/sharepoint/change-default-sharing-link) 默认链接类型。

## <a name="related-topics"></a>相关主题

[SharePoint和Teams：更好地在一起](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。

[来宾体验介绍](guest-experience.md)