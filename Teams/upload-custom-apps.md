---
title: 在 Microsoft Teams 管理中心上传自定义应用
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心将自定义应用上传到组织的应用商店。
ms.openlocfilehash: f1b5267fe1003d69c0d91349f5b6bc425df2b038
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831162"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>通过上传应用包发布自定义应用

> [!NOTE]
> 发布自定义 Teams 应用时，该应用可供组织应用商店中的用户使用。 有两种方法可以发布自定义应用，使用方式取决于获取应用的方式。 **本文重点介绍如何发布自定义** 应用，将应用包 (.zip 格式) 开发人员发送给你的应用包。 当开发人员通过 Teams 应用提交 API 将应用直接提交到"管理应用"<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a>页面时，会使用另一种方法（即批准自定义应用）。 若要详细了解该方法，请参阅"发布通过 Teams 应用提交 API 提交的自定义<a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">应用"。</a>

本文提供有关如何将 Teams 应用从开发到部署到发现的端到端指南。 本指南重点介绍应用的 Teams 方面，面向管理员和 IT 专业人员。 有关开发 Teams 应用的信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams 开发人员文档</a>。

![从开发到部署的应用的概述](media/upload-custom-apps.png)

## <a name="develop"></a>开发

### <a name="create-your-app"></a>创建应用

使用 Microsoft Teams 开发人员平台，开发人员可以轻松集成自己的应用和服务，以提高工作效率、更快地做出决策，以及围绕现有内容和工作流创建协作。 基于 Teams 平台构建的应用是 Teams 客户端与服务和工作流之间的桥梁，可将它们直接引入协作平台的上下文中。 有关详细信息，请转到 Teams 开发人员 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">文档</a>。

## <a name="validate"></a>验证

### <a name="get-the-app-package"></a>获取应用包

当应用准备好在生产环境中使用时，开发人员应生成应用包。 他们可以使用<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio。</a> 他们将以 .zip 格式发送给你文件。

Microsoft <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">使用这些指南</a> 来确保应用符合全球 Teams 应用存储的质量和安全标准。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>允许受信任的用户上传自定义应用

若要验证应用在生产租户中是否正常工作，需要允许你自己和/或受信任的用户上传生产租户中的自定义应用。 可以使用 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">应用设置策略</a> 来这样做。

> [!NOTE]
> 如果将应用上传到生产租户进行验证（即使是为自己或受信任的用户）感到不便，可以跳过此步骤，按照"上传和设置和管理"部分中的步骤将未经验证的应用发布到组织的应用商店[](#upload)。 [](#set-up-and-manage) 然后，仅你自己和信任的用户可以访问该应用。 然后，这些用户可以从组织的应用商店获取应用以执行验证。 验证应用后，使用相同的权限策略打开访问权限，并推出应用供生产使用。

若要允许受信任的用户上传自定义应用，请执行以下步骤：

1. 打开" **允许与自定义应用组织** 范围内的应用交互"设置。 要执行此操作：
    1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用** 管理应用"，然后单击"  >  **组织范围的应用设置"。**
    2. 在 **"自定义应用**"下，打开 **"允许与自定义应用交互**"，然后单击"保存 **"。**
2. 关闭全局 **应用设置策略中的** "上传自定义应用"设置。 要执行此操作：
    1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams** 应用设置策略，然后单击"全局 (组织范围内的默认)  >  策略。 
    2. 关闭"**上传自定义应用"，** 然后单击"保存 **"。**
3. 创建允许上传自定义应用并将其分配给受信任用户集的新应用设置策略。 要执行此操作：
    1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams 应用** 设置策略，然后单击"添加  >  **"。** 为新策略指定名称和说明，打开"上传 **自定义** 应用"，然后单击"保存 **"。**
    2. 选择创建的新策略，并单击"**管理用户"。** 搜索用户，单击"添加 **"，** 然后单击"应用 **"。** 重复此步骤，将策略分配给所有受信任的用户。

        !["添加应用设置策略"页的屏幕截图](media/manage-your-lob-apps-new-app-setup-policy.png)

    这些用户现在可以上传应用清单，以验证应用在生产租户中是否正常工作。

## <a name="upload"></a>上传

若要使应用可供组织应用商店中的用户使用，请上传该应用。 可以在 Microsoft Teams 管理 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">中心的"管理应用</a> "页面上执行此操作。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**
2. 单击 **"** 上传"， **单击"选择文件**"，然后选择从开发人员收到的应用包。

   ![在管理中心上传应用的屏幕截图](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>设置和管理

### <a name="control-access-to-the-app"></a>控制对应用的访问

默认情况下，组织中的所有用户都可以访问组织应用商店中的应用。 若要限制和控制谁有权使用应用，可以创建并分配应用权限策略。 若要了解有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">"在 Teams 中管理应用权限策略"。</a>

### <a name="pin-and-install-the-app-for-users-to-discover"></a>固定并安装应用供用户发现

默认情况下，用户若要查找应用，必须转到组织的应用商店并浏览或搜索该应用。 为了方便用户访问该应用，你可以将应用固定到 Teams 中的应用栏。 为此，请创建应用设置策略并将其分配给用户。 若要了解有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">"在 Teams 中管理应用设置策略"。</a>

### <a name="search-the-audit-log-for-teams-app-events"></a>在审核日志搜索 Teams 应用事件

可以搜索应用审核日志查看组织中 Teams 应用活动。 若要详细了解如何搜索 审核日志并查看记录在 审核日志 中的 Teams 活动列表，请参阅"在 审核日志 中搜索 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">活动</a>。

在搜索安全中心审核日志，首先必须打开安全中心& <a href="https://protection.office.com" target="_blank">审核</a>。 若要了解有关详细信息，请参阅 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">审核日志打开或关闭搜索</a>。 请记住，只有启用审核时，审核数据才可用。

## <a name="discover-and-adopt"></a>发现和采用

对应用具有权限的用户可以在组织的应用商店中查找它。 转到 **"应用 *"页上*** 的"为组织名称构建"，查找组织的自定义应用。

![显示已发布应用的应用页面的屏幕截图 ](media/custom-app-lifecycle-discovery.png)

如果创建并分配了应用设置策略，该应用将固定到 Teams 中的应用栏，以便分配有该策略的用户轻松访问。

## <a name="update"></a>更新

若要更新应用，开发人员应继续按照"开发和验证"部分中[的步骤](#validate)操作[](#develop)。

可以在 Microsoft Teams 管理中心的"管理应用"页面上更新应用。 为此，在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。** 单击应用名称，然后单击"更新 **"。** 执行此操作会替换现有应用，并且所有应用权限策略和应用设置策略仍对更新的应用强制实施。

### <a name="end-user-update-experience"></a>最终用户更新体验

在大多数情况下，完成应用更新后，最终用户会自动显示新版本。 但是，Microsoft <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Teams</a> 清单的一些更新需要用户验收才能完成：

* 添加或删除了机器人
* 现有机器人的"botId"属性已更改
* 现有机器人的"isNotificationOnly"属性已更改
* 机器人的"supportsFiles"属性已更改
* 已添加或删除消息传送扩展
* 添加了一个新连接器
* 添加了新的静态选项卡
* 添加了新的"可配置"选项卡
* "webApplicationInfo"中的属性已更改

![应用列表的屏幕截图，其中显示了提供新版本的应用](media/manage-your-custom-apps-update1.png)

![应用的升级选项屏幕截图](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>相关主题

- [发布通过 Teams 应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)
- [在 Microsoft Teams 管理中心管理应用](manage-apps.md)
- [在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
- [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
