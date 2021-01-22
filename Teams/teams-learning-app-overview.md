---
title: '安装、管理和分配 Teams Learning 应用的权限 (个人预览版) '
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: 使用 Microsoft Teams 学习应用创建一个中心，供员工在整个组织中共享、分配和学习内容库。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6d4cb45334edb9307663eb1ffcab5e7c1085b149
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923834"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>安装、管理和分配 Teams Learning 应用的权限 (个人预览版) 

*本文包含 Teams Learning 应用（个人预览版）的初步内容。*

Microsoft Teams Learning 应用 (个人预览版) 使组织中的团队和个人能够自然地学习。 该应用在 Teams 中创建了一个中心，员工可以在其中共享、分配内容以及从整个组织的内容库中学习。 管理员设置权限并允许学习应用的内容源。 学习内容可能包括 LinkedIn Learning、Microsoft Learn、Microsoft 365 培训、组织自己存储在 SharePoint Online 中的内容以及应用支持的第三方提供商。

若要将 Teams Learning 应用 (个人预览版) ，需要涉及：

-   Teams 管理中心管理员
-   Microsoft 365 管理中心管理员 (，即全局管理员) 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>在 Teams 管理中心 (Teams) 个人预览版

Teams 管理员从应用商店 (Teams 学习) 个人预览版，并通过 Teams 管理中心应用应用设置、管理和权限策略。

### <a name="manage-the-teams-learning-app-private-preview"></a>管理 Teams Learning 应用 (个人预览版) 

若要管理应用的设置，请执行以下步骤：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**

   ![Teams 管理中心中的左侧导航，显示 Teams 应用和"管理应用"部分](media/learning-app-teams-manage-apps-nav.png)

2. 在"**管理应用"** 页面的搜索框中，键入学习内容以搜索 Teams Learning 应用 (个人预览) 。

   ![Teams 管理中心中的"管理应用"页面，显示搜索框](media/learning-app-teams-manage-apps-page.png)

3. 在" **学习"** 页上：
   1. 在 **"状态**" **下，选择** "允许"以打开应用。
   2. 在" **设置"** 选项卡上的"应用 **设置** "部分中，转到 Microsoft 365 管理中心以配置学习内容源。

   ![Teams 管理中心中的学习页面，显示"状态"和"应用设置"部分](media/learning-app-teams-learning-page.png)

4. 管理 **应用设置** 后，转到"权限"和"设置"策略，向应有权访问应用（作为组织参与个人预览版一部分的员工）授予权限。

> [!NOTE]
>  如果你的组织作为 Teams TAP100 计划的一部分进入 4.0 圈，你可能需要执行以下操作，使 3.0 圈中的获批用户能够访问 Teams Learning 应用 (个人预览版) 。

作为个人预览的一部分，Teams Learning 应用 (个人预览版) 3.0 圈中发布。 如果你的组织在 4.0 圈中，你将在应用商店中看不到该应用。 若要测试应用，需要创建自定义应用权限策略，将其设置为"允许 **所有** 应用"，并将其分配给 3.0 批准用户。

   ![TAP-AppsPermission-Plcy 页面，显示"允许选择所有应用"](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心配置学习内容源

Microsoft 365 管理中心的管理员可以管理与 Teams Learning 应用相关的设置 (个人预览版) 并配置学习内容源。

管理员选择哪些学习内容源 (如 LinkedIn Learning 或 SharePoint) 可在应用中使用。 然后，管理员配置这些源，以确保内容可用于搜索和发现，并且可供使用应用的员工浏览。

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>为应用配置学习内容源的设置

这些步骤由 Microsoft 365 管理员执行。

1.  在 Microsoft 365 管理中心的左侧导航中，转到"**设置**  >  **组织设置"。**

2.  在"**设置"** 页上的"**服务&"** 选项卡上，选择 **"学习应用"。**

   ![Microsoft 365 管理中心中的"设置"页，其中列出了学习应用](media/learning-app-365-settings-page.png)

3.  在 **"学习"** 应用面板中，选择要为组织配置的学习内容源，然后选择"保存 **"。**

   ![Microsoft 365 管理中心中显示内容源选项的学习应用面板](media/learning-app-365-settings-learning-app-panel.png)

在存在的所有学习源中，一些默认已启用。 其中包括：

- LinkedIn Learning (免费内容) 
- Microsoft Learn
- Microsoft 365 培训

> [!NOTE]
> 如果您的组织具有 LinkedIn Learning Standard 或 Pro 订阅，将为您的组织中的员工解锁内容存储库。 只有具有权限的员工才能使用整个内容存储库。

其他源可能需要手动启用或配置。 非 Microsoft 的学习源在组织和第三方之间单独获得许可。 你需要验证你已注册供你和用户学习。

若要启用或禁用学习内容源，请选中源旁边的复选框。 如果启用了源，则显示一个选中标记。

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a>将 SharePoint 配置为学习内容源 (即将推出) 

在 Microsoft 365 管理中心中将 SharePoint 配置为 Teams 学习应用 (个人) 预览版源。

### <a name="overview"></a>概述

管理员提供一个网站 URL，学习服务可在其中以结构化 SharePoint 列表的形式创建空的集中学习内容存储库。 组织可以使用此列表来存储指向包含学习内容的跨公司 SharePoint 文件夹的链接。 管理员负责收集和管理文件夹的 URL 列表。 这些文件夹应仅包含可在 Teams Learning 应用或个人预览版 (提供) 。

### <a name="permissions"></a>权限

可以从组织的任何 SharePoint 网站收集文件夹 URL。 这些文件夹中的任何内容都可以搜索，但只能使用单个员工具有权限的内容。
 
### <a name="learning-service"></a>学习服务

学习服务使用提供的文件夹 URL 从存储在这些文件夹中的所有内容获取元数据。 在集中式存储库中提供文件夹 URL 的 24 小时内，员工可以在应用中搜索和使用公司的内容。 目前不支持从存储库删除内容。 只有在 Microsoft 365 管理中心中提供新的 SharePoint 网站 URL，才能删除意外显示的内容。

### <a name="configure-sharepoint-as-a-source"></a>将 SharePoint 配置为源

这些步骤由 Microsoft 365 管理员执行。

1.  在 Microsoft 365 管理中心的左侧导航中，转到"设置 **"。**
 
2.  在"**设置"** 页上的"**服务&"** 选项卡上，选择 **"学习应用"。**

   ![Microsoft 365 管理中心中的"设置"页，其中列出了学习应用](media/learning-app-365-settings-page.png)

3.  在 **"学习"** 应用面板上，提供 SharePoint 网站的网站 URL，以便应用程序创建集中式存储库。

   ![Microsoft 365 管理中心中的学习应用面板，其中显示已选中 SharePoint](media/learning-app-365-panel-sharepoint-selected.png)

4.  SharePoint 列表在提供的组织的 SharePoint 网站中自动创建。 在 SharePoint 网站的左侧导航栏中，选择 **"学习应用内容存储库"。** 

   ![SharePoint 中的左侧导航，显示"学习应用内容存储库"部分](media/learning-app-content-repository-nav.png)

 
5. 在" **学习应用内容存储库"** 页上，使用学习内容文件夹的 URL 填充 SharePoint 列表。

   1.   选择 **"新建** "以查看 **"新建项目"** 面板。 

   ![SharePoint 中显示"新建"选项的"学习应用内容存储库"页](media/learning-app-content-repository-new.png)
 
   2.   在 **"新建项** "面板的"标题 **"字段中，** 添加选择的目录名称。 在 **"文件夹 URL"** 字段中，将 URL 添加到学习内容文件夹。 选择 **"保存"。**

   ![SharePoint 中的"新建项目"面板，显示"标题"和"文件夹 URL"字段](media/learning-app-new-item-panel.png)

   3. 学习应用内容存储库页面使用新的学习内容进行更新。

   ![SharePoint 中的"学习应用内容存储库"页，显示更新的信息](media/learning-app-content-repository-populated.png)


 


