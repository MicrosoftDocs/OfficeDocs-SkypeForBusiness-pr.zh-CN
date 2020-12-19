---
title: 在 Microsoft Teams 中共享文件
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: 了解 Microsoft Teams 中的文件共享体验。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138324"
---
# <a name="sharing-files-in-microsoft-teams"></a>在 Microsoft Teams 中共享文件

在 Microsoft Teams 中，用户可以与组织内外的其他 Teams 用户共享内容。 Teams 中的共享基于在 SharePoint 和 OneDrive 中配置的设置，因此你为 SharePoint 和 OneDrive 设置的任何内容也将控制 Teams 中的共享。

## <a name="overview"></a>概述

用户可以从 OneDrive、他们有权访问的团队和网站以及他们的计算机共享文件。 若要共享文件，用户可以执行下列操作：

- 在频道中，单击“**附加**”（曲别针图标），选择“**最近**”、“**浏览团队和频道**”、“**OneDrive**”或“**从我的计算机上传**”，然后选择要共享的文件。 <br> 
    ![显示从频道共享文件的屏幕截图](media/share-files-channel.png)
- 在聊天中，单击“**附加**”（曲别针图标），选择  或者“**OneDrive**”或“**从我的计算机上传**”，然后选择要共享的文件。 <br>
    ![显示从聊天共享文件的屏幕截图](media/share-files-chat.png)
- 复制并在撰写框中粘贴共享链接。<br>
    ![在撰写框中显示文件预览的屏幕截图](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>有关文件共享体验的须知

### <a name="permissions-of-shared-files-and-sharing-links"></a>共享文件和共享链接的权限

当用户通过在 OneDrive 或团队和频道中浏览到某个文件来共享该文件时，所有收件人都获得访问权限以及[在组织级别设置的默认权限](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。

当用户复制并粘贴共享链接时，将保留在该共享链接上设置的权限，并且 SharePoint URL 将缩短为文件名。 换言之，Teams 仅使用文件名链接到文件。

当用户在 Teams 中共享文件时，他们可以设置谁可以访问该文件，就像在 Microsoft 365 中所做的那样。 他们可以向任何人、你组织中的人员、具有现有访问权限的人员或特定人员授予访问权限（可以将人员包括在一对一聊天、群组聊天或频道中）。  共享文件时，消息中将显示文件预览，同时还可执行所有文件操作，如“**在线打开**”、“**下载**”和“**复制链接**”。 默认情况下，该文件在 Teams 中打开。 有时，在用户发送消息时，共享链接可能尚未转换为文件预览。 文件预览将由系统生成，但在这种情况下，共享链接不会缩短为仅文件名。

当用户在聊天或频道中共享文件时，系统会通知他们是否有部分或全部收件人没有查看文件的权限。 他们可以单击消息中现在显示的文件预览旁边的箭头，在共享文件之前更改文件的权限。

![收件人没有权限时的通知屏幕截图](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>复制 Teams 中的共享链接

用户可以复制 SharePoint 共享链接并更改共享权限，就像在 Microsoft 365 中所做的那样。 他们可以向任何人、你组织中的人员、具有现有访问权限的人员或特定人员授予访问权限。 链接的默认权限与在组织级别设置的默认权限相同，除非 SharePoint 网站级别权限覆盖它。

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>配置 OneDrive 和 SharePoint 中的共享

有关在 OneDrive 和 SharePoint 中共享文件的详细信息，包括如何配置共享以及如何打开和关闭共享，请参阅：

- [外部共享概述](https://docs.microsoft.com/sharepoint/external-sharing-overview) - 介绍用户共享时的情况，具体取决于他们共享的内容以及与谁共享。

- [管理共享设置](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - 介绍全局管理员和 SharePoint 管理员如何更改 SharePoint 和 OneDrive 的组织级别共享设置。

- [打开或关闭网站的外部共享](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – 介绍全局管理员和 SharePoint 管理员如何打开或关闭网站的外部共享。

- [更改网站的默认链接类型](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - 介绍如何设置默认链接类型以便更严格地限制。

## <a name="more-information"></a>更多信息

- [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)

- [SharePoint 和 Teams：更好地协同工作](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [共享 OneDrive 文件和文件夹](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [共享 SharePoint 文件或文件夹](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
