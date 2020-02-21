---
title: 管理 Microsoft 团队中的业务线应用
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
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
description: 了解如何让自定义团队应用从开发到部署。
ms.openlocfilehash: 070b0ecbf0ccc9af798e1d3a3c689ce4d4ff4da2
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161798"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a>管理 Microsoft 团队中的业务线应用

本文提供了有关如何将团队应用从开发部署到部署的端到端指南。 本指南重点介绍应用的团队内容，面向 IT 专业人士。 有关开发团队应用的详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">此处</a>。

![从开发到部署概述应用](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>入门

若要创建和管理团队中的业务线（LOB）应用，需要两个租户：用于开发和生产租户的测试租户。

> [!NOTE]
> 如果你还没有测试租户，则可以使用 Office 365 开发人员程序快速创建一个测试租户并使用测试数据填充它。 <a href="https://developer.microsoft.com/office/dev-program" target="_blank">在此处了解详细信息</a>。

## <a name="step-1-develop-and-test"></a>步骤1：开发和测试

### <a name="create-test-users"></a>创建测试用户

请确保你的开发人员（无论是内部还是外部）在你的测试租户中具有帐户。 <a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">了解有关添加用户的详细信息</a>。

### <a name="allow-custom-apps-in-the-test-tenant"></a>允许在测试租户中自定义应用

若要向开发人员提供测试所需的访问权限，请允许测试租户中的所有用户上载自定义应用（也称为旁加载）。 这允许开发人员上载自定义应用程序，以供个人或跨测试租户使用，而无需将应用提交到团队应用商店。 上载自定义应用程序使开发人员可以在更广泛地分发应用之前对其进行测试。

若要允许用户上载自定义应用程序，请按照下列步骤操作：

1. 启用 "**允许与自定义应用交互**" 组织范围的应用设置。 要执行此操作：
    1. 在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **管理应用**"，然后单击 "**组织范围的应用设置**"。
    2. 在 "**自定义应用**" 下，打开 "**允许与自定义应用交互**"，然后单击 "**保存**"。

    !["允许与自定义应用交互" 组织范围内的应用设置的屏幕截图](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. 在全局应用设置策略中启用 "**上载自定义应用**" 设置。 要执行此操作：
    1. 在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **设置策略**"，然后单击 "**全局（组织范围默认）** " 策略。
    2. 打开 "**上载自定义应用**"，然后单击 "**保存**"。

    !["上载自定义应用" 应用设置策略设置的屏幕截图](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> 在团队级别还会有一个上载自定义应用设置。 默认情况下，此设置为 "打开"。 但是，如果开发人员无法将自定义应用上载到团队，请按照<a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">此处</a>的步骤检查设置。

### <a name="create-your-app"></a>创建你的应用

开发人员现在应拥有创建你的应用所需的内容。 请参阅<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">此处</a>了解相关指南。

## <a name="step-2-validate-in-production"></a>步骤2：在生产中验证

### <a name="get-the-app-package"></a>获取应用包

当应用准备好在生产中使用时，开发人员应该生成一个应用包。 他们可以使用适用于该<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">应用的应用 Studio</a> 。 他们将以 .zip 格式发送文件。

Microsoft 使用<a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">这些指南</a>确保应用符合全球团队应用商店的质量和安全标准。

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>允许受信任的用户在生产租户中上载自定义应用

若要验证应用是否在你的生产租户中正常工作，你需要允许你的组织中的自己和/或受信任的用户上载自定义应用。  非常类似于前面的<a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">步骤</a>，你可以使用应用设置策略执行此操作。

> [!NOTE]
> 如果你不满意将应用上载到生产租户进行验证，即使对于你自己或受信任的用户，你也可以跳过此步骤，然后按照步骤3和步骤4将 unvalidated 应用上载到租户应用商店。 然后，将对该应用的访问限制为仅限自己和你信任的用户。 然后，这些用户可以从租户应用商店获取该应用以执行验证。 验证应用后，使用相同的权限策略打开 access，并将应用滚出以供生产使用。

若要允许受信任用户上载自定义应用程序，请按照下列步骤操作：

1. 启用 "**允许与自定义应用交互**" 组织范围的应用设置。 要执行此操作：
    1. 在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **管理应用**"，然后单击 "**组织范围的应用设置**"。
    2. 在 "**自定义应用**" 下，打开 "**允许与自定义应用交互**"，然后单击 "**保存**"。
2. 关闭全局应用设置策略中的 "**上载自定义应用**" 设置。 要执行此操作：
    1. 在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **设置策略**"，然后单击 "**全局（组织范围默认）** " 策略。
    2. 关闭 "**上载自定义应用**"，然后单击 "**保存**"。
3. 创建一个新的应用设置策略，该策略允许上载自定义应用并将其分配给你的受信任的用户集。 要执行此操作：
    1. 在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **设置策略**"，然后单击 "**添加**"。 为新策略提供名称和说明，打开 "**上载自定义应用**"，然后单击 "**保存**"。
    2. 选择您创建的新策略，然后单击 "**管理用户**"。 搜索用户，单击 "**添加**"，然后单击 "**应用**"。 重复此步骤，将策略分配给所有受信任的用户。

        !["添加应用程序设置策略" 页面的屏幕截图](media/manage-your-lob-apps-new-app-setup-policy.png)

    这些用户现在可以上载应用清单，以验证应用是否在生产租户中正常工作。

## <a name="step-3-upload-to-the-tenant-app-catalog"></a>步骤3：上传到租户应用目录

若要让租户应用商店中的用户可以使用该应用，请上载该应用。 你可以<a href="https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams#go-to-the-tenant-apps-catalog" target="_blank">使用团队桌面客户端</a>或 Microsoft 团队管理中心的 "[管理应用](manage-apps.md)" 页面执行此操作。

下面是 "团队桌面客户端" 中的 "上载" 选项的屏幕截图。

!["应用" 页面的屏幕截图](media/manage-your-lob-apps-store.png)

下面是 Microsoft 团队管理中心的 "**管理应用**" 页面上的 "上载" 选项的屏幕截图。

![管理中心中 "管理应用" 页面的屏幕截图](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a>步骤4：配置和分配权限

### <a name="control-access-to-the-app"></a>控制对应用的访问

默认情况下，所有用户都可以在 "团队应用商店" 中访问此应用。 若要限制和控制谁有权使用该应用程序，你可以创建并分配新的应用权限策略。 请按照<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">此处</a>的步骤操作。

!["添加应用权限策略" 页面的屏幕截图](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>固定应用以供用户发现

默认情况下，为使用户能够找到此应用，他们将必须转到 "团队应用商店" 和 "浏览" 或 "搜索"。 若要使用户可以轻松访问应用，可以将应用固定到团队中的应用栏。 若要执行此操作，请创建新的应用设置策略并将其分配给用户。 请按照<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">此处</a>的步骤操作。

!["添加固定应用" 窗格的屏幕截图](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>步骤5：更新应用

![从开发到部署概述应用](media/manage-your-lob-apps-update.png)

若要更新应用，开发人员应继续执行[步骤 1](#step-1-develop-and-test)和[步骤 2](#step-2-validate-in-production)。

你可以通过租户应用目录更新应用。 若要执行此操作，请在团队桌面客户端中，转到为**租户&gt;名称生成&lt;的****应用** > ，然后单击 **...** 在应用的右上角，然后单击 "**更新**"。 执行此操作将替换租户应用程序目录中的现有应用，并且所有权限策略和设置策略都将对已更新的应用保持强制。 

![更新 "应用" 页面上的应用的屏幕截图](media/manage-your-lob-apps-update-app.png)