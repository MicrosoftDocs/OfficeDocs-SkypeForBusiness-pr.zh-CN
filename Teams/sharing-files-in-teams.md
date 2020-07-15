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
description: 了解 Microsoft 团队中的文件共享体验。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138324"
---
# <a name="sharing-files-in-microsoft-teams"></a>在 Microsoft Teams 中共享文件

在 Microsoft 团队中，用户可以与组织内部和外部的其他团队用户共享内容。 团队中的共享基于 SharePoint 和 OneDrive 中配置的设置，因此你为 SharePoint 和 OneDrive 设置的任何内容也将控制团队中的共享。

## <a name="overview"></a>概述

用户可以从 OneDrive、他们有权访问的团队和网站以及他们的计算机共享文件。 若要共享文件，用户可以执行以下操作：

- 在通道中，单击 "**附加**" （曲别针图标），选择 "**最近**"、"**浏览团队和频道**"、" **OneDrive**" 或 **"从我的计算机上传**"，然后选择要共享的文件。 <br> 
    ![显示从频道共享文件的屏幕截图](media/share-files-channel.png)
- 在聊天中，单击 "**附加**" （曲别针图标），选择或 " **OneDrive** " 或 **"从我的计算机上传**"，然后选择要共享的文件。 <br>
    ![显示从聊天共享文件的屏幕截图](media/share-files-chat.png)
- 将共享链接复制并粘贴在撰写框中。<br>
    ![显示 "撰写" 框中的文件预览的屏幕截图](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>您需要了解的有关文件共享体验的哪些信息

### <a name="permissions-of-shared-files-and-sharing-links"></a>共享文件和共享链接的权限

当用户通过在 OneDrive 或团队和频道中浏览来共享文件时，将向所有收件人授予访问权限以及[在组织级别设置的默认权限](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。

当用户复制和粘贴共享链接时，将接受在该共享链接上设置的权限，并将 SharePoint URL 缩短为文件名。 换言之，团队只使用文件名链接到文件。

当用户从团队内部共享文件时，他们可以设置可以访问该文件的人员，就像在 Microsoft 365 中访问该文件一样。 他们可以向组织中的人员、拥有现有访问权限的人员或特定用户（可在1:1 聊天、群组聊天或频道中包括人员）授予访问权限。  共享文件时，文件预览在邮件中可用，以及所有文件操作，如 "**打开联机**"、"**下载**" 和 "**复制链接**"。 默认情况下，将在 "团队" 中打开该文件。 有时，共享链接可能在用户发送邮件时未转换为文件预览。 文件预览将由系统生成，但在这种情况下，不会将共享链接缩短为唯一的文件名。

当用户在聊天或频道中共享文件时，系统会通知某些收件人是否有查看该文件的权限。 他们可以在共享文件之前更改文件的权限，方法是单击 "文件预览" 旁边的箭头（现在出现在邮件中）。

![收件人没有权限时通知的屏幕截图](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>复制团队中的共享链接

用户可以复制 SharePoint 共享链接，并更改共享权限，就像他们在 Microsoft 365 中所做的那样。 他们可以向您的组织中的人员、拥有现有访问权限的人员或特定人员授予访问权限。 链接的默认权限与组织级别的默认权限集相同，除非 SharePoint 网站级别权限覆盖它。

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>在 OneDrive 和 SharePoint 中配置共享

有关在 OneDrive 和 SharePoint 中共享文件的详细信息，包括如何配置共享以及如何打开和关闭共享，请参阅：

- [外部共享概述](https://docs.microsoft.com/sharepoint/external-sharing-overview)-介绍用户共享时所发生的情况，具体取决于他们共享的内容和用户。

- [管理共享设置](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)-介绍全局管理员和 sharepoint 管理员如何更改其组织级别的 SharePoint 和 OneDrive 共享设置。

- [为网站启用或禁用外部共享](https://docs.microsoft.com/sharepoint/change-external-sharing-site)-介绍全局管理员和 SharePoint 管理员如何为网站打开或关闭外部共享。

- [更改网站的默认链接类型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)-介绍如何设置默认链接类型，以使其更具限制性。

## <a name="more-information"></a>更多信息

- [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)

- [SharePoint 和团队：更好地协作](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [共享 OneDrive 文件和文件夹](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [共享 SharePoint 文件或文件夹](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
