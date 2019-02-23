---
title: 在 Microsoft Teams 中管理应用设置策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 2/11/2019
ms.reviewer: larryjin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解 Microsoft 团队以及如何使用它们 pin 应用程序自定义您的组织中的用户的工作组中的应用程序设置策略。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e6ad41dac9021079bffa80284809733c39f3cc9
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205760"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理应用设置策略

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

作为一名管理员，您可以使用应用程序设置策略自定义 Microsoft 团队以突出显示您的用户的最重要的应用程序。 选择锁定并设置它们出现的顺序的应用程序。 应用程序安装策略允许您展示您的组织中的用户需要包括由第三方或由组织中的开发人员构建的应用程序。 您还可以使用应用程序安装策略管理如何内置功能显示。

应用程序被固定到应用程序栏。 这是一小组桌面客户端侧和底部的团队移动客户端 （iOS 和 Android） 的栏。 

|团队桌面客户端  |团队移动客户端 |
|---------|---------|
|![app-setup-policies-desktop-app-bar.png](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![app-setup-policies-mobile-app-bar.png](media/app-setup-policies-mobile-app-bar.png)      |

管理 Microsoft 团队管理中心中的应用程序设置策略。 您可以使用全局 （组织范围内默认值） 策略或创建自定义策略，并将其分配给用户。 您的组织中的用户将自动授予全局策略，除非您创建和分配自定义策略。

您可以编辑该全局策略中的设置，以包含所需的应用程序。 如果您想要自定义为不同的组织中用户组的团队，创建并分配一个或多个自定义策略。

![应用程序的安装程序 policies.png](media/app-setup-policies.png)

> [!NOTE]
> 如果用户已分配的自定义策略，该策略应用于用户。 如果用户未分配的自定义策略，全局策略应用于用户。

## <a name="create-a-custom-app-setup-policy"></a>创建自定义应用程序安装程序策略

您可以使用的 Microsoft 团队管理中心或 Windows PowerShell 创建自定义策略。

1. 在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **应用程序设置策略**。
2. 选择**新策略**。
3. 输入策略的描述性名称，然后单击**添加应用程序**。
4. 在**添加固定应用程序**窗格中，搜索要添加，然后单击**添加**的应用程序。  若要查看所有应用程序的列表，请选中**团队应用程序存储**。 您已选择您的应用程序的列表，单击**添加**。

     ![应用程序的安装程序的策略-添加-apps.png](media/app-setup-policies-add-apps.png)

5. 排列您所愿团队中显示，然后单击**保存**的顺序应用程序。

    ![app-setup-policies-new-policy-setup.png](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>编辑应用程序安装程序策略

您可以使用的 Microsoft 团队管理中心或 Windows PowerShell 编辑策略，包括全局 （组织范围内默认值） 策略和您创建的自定义策略。 

1. 在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **应用程序设置策略**。
2. 选择您想要编辑的策略。 
3. 从此处，进行所需的更改。 您可以添加、 删除和更改的应用程序的顺序。
4. 单击“**保存**”。 

## <a name="assign-a-custom-app-setup-policy-to-users"></a>将自定义应用程序安装策略分配给用户

您可以使用 Microsoft 团队管理中心自定义策略分配给单个用户或 Windows PowerShell，可以分配给用户，例如安全组的组或通讯组的自定义策略。

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a>自定义应用程序安装策略分配给单个用户

1. 在 Microsoft 团队管理中心的左侧导航窗格中，转到**用户**，，然后单击用户。
2. 旁边**分配策略**，选择**编辑**。
3. **团队应用程序设置策略**，下选择要分配的应用程序设置策略，然后选择**保存**。

    ![应用程序的安装程序的策略-分配-policy.png](media/app-setup-policies-assign-policy.png)

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>自定义应用程序安装策略分配给组中的用户

您可能想要为已识别的多个用户分配自定义应用程序设置策略。 例如，您可能要将策略分配给安全组中的所有用户。 您可以通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块 Skype 来执行此操作。 有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell Overview](teams-powershell-overview.md)。

本示例中，我们自定义应用程序安装程序将策略分配到 Contoso 药品 HR 项目组中的所有用户称为人力资源应用程序设置策略。  

> [!NOTE]
> 请确保您首次[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块的 Skype。

获取特定的组的 GroupObjectId。
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
获取指定组的成员。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
组中的所有用户都分配特定的应用程序设置策略。 本示例中，它是 HR 应用程序设置策略。
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
根据组中成员的数目，此命令可能需要几分钟才能执行。

## <a name="faq"></a>常见问题

### <a name="working-with-app-setup-policies"></a>使用应用程序设置策略

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>内置应用程序安装程序将哪些策略都包含在 Microsoft 团队管理中心？

- **全局 （组织范围内默认值）**： 此默认策略应用于组织中的所有用户，除非您将其他策略分配。 编辑您的用户的最重要的 pin 应用程序的全局策略。
- **FirstLineWorker**： 此策略为 firstline 工作者。 您可以将其组织中分配给 firstline 工作者。 务必要了解，如您所创建的自定义策略，您必须将策略分配给用户处于活动状态的设置。 详细信息，请转到本文的[分配给用户的自定义应用程序设置策略](#assign-a-custom-app-setup-policy-to-users)一节。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>为什么我无法在添加固定的应用程序窗格中查找应用程序

通过应用程序设置策略，可以向工作组固定并非所有应用程序。 某些应用程序可能不支持此功能。 若要查找可以固定的应用程序，请搜索**添加固定应用程序**窗格中的应用程序。 具有个人范围 （静态选项卡） 和自动程序的选项卡可以固定到团队桌面客户端，这些应用程序也可在**添加固定应用程序**窗格中。

请记住，团队应用程序商店将列出所有团队应用程序，而**固定添加应用程序**窗格包括仅可以通过策略固定到团队的应用程序。 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>我是团队教育管理员。我需要了解在面向教育机构的团队中的应用程序设置策略的哪些内容？

面向教育机构的团队中调用应用程序不可用。 创建新的自定义应用程序安装策略时，调用应用程序的应用程序列表中显示。 但是，应用程序不固定到团队客户端和团队的培训用户看团队中的呼叫应用程序。 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a>可以向策略添加多少应用程序？

至少两个应用程序必须固定的团队移动客户端 （iOS 和 Android）。 如果策略具有少于两个应用程序，移动客户端不会反映的策略设置和改为将继续使用现有的配置。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>如何长时间才会生效的策略更改？

编辑全局策略或分配策略后，可以最多 24 小时才能使更改生效。

### <a name="user-experience"></a>用户体验

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>用户如何查看团队中的其固定应用程序？

若要查看固定的用户的所有应用程序，用户可能需要执行以下操作具体取决于已安装的应用程序的数目和其团队客户端窗口的大小。

|团队桌面客户端 |团队移动客户端 |
|---------|---------|
|在工作组的一侧的应用程序栏中，单击 **...更多应用程序**。| 在工作组底部附近的应用程序栏中，向上轻扫。|
|![app-setup-policies-desktop-more-apps.png](media/app-setup-policies-desktop-more-apps.png)<br>   |![app-setup-policies-mobile-more-apps.png](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>了解团队移动体验时需要什么操作？

团队移动客户端 （iOS 和 Android） 当前不支持静态选项卡与个人应用程序。 在策略中设置的应用程序，根据固定到团队桌面客户端应用程序可能不出现在工作组移动客户端。 个人 bot 仍显示在聊天移动客户端上。

团队移动客户端，用户会看到如活动、 聊天和团队的核心团队应用程序，您可以锁定某些 microsoft，如班次的第一方应用程序。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>用户可以更改的固定通过策略的应用程序的顺序？

目前，用户可以更改其固定的应用程序团队移动客户端上但团队桌面或 web 客户端的顺序。 

### <a name="custom-teams-apps"></a>自定义团队应用程序

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-through-appsource-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>我的组织构建自定义的团队应用程序并将其发布到 AppSource 但预期时应用程序固定到应用程序栏团队中不显示的应用程序图标。 如何解决它？ 

请确保您遵循徽标准则之前提交应用程序。 若要了解详细信息，请参阅[卖方仪表板提交的清单](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist)。 

 ## <a name="related-topics"></a>相关主题
- [从工作组客户端租户的应用程序目录发布应用程序](tenant-apps-catalog-teams.md)
