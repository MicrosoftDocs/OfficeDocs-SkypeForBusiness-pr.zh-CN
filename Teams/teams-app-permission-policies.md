---
title: 在 Microsoft Teams 中管理应用权限策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解有关 Microsoft 团队和如何使用它们来控制对组织中用户可用的应用程序中的应用程序权限策略。
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: 49200d597811d87ce27d94d9bb19577def6355c1
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "31520221"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理应用权限策略

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon.md)]

作为一名管理员，您可以使用应用程序的权限策略来控制应用程序可供您的组织中的 Microsoft 团队用户。 您可以允许或阻止所有应用程序或由 Microsoft 已发布的特定应用程序第三方和您的组织。 当您阻止应用程序时，用户将无法从团队应用程序商店安装它。

管理 Microsoft 团队管理中心中的应用程序权限策略。 可以应用设置组织范围、 使用 （组织范围内默认值） 全局策略，并创建和自定义策略分配给单个用户或组中的用户。  

![应用程序权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> 您的组织中的用户将自动授予全局策略，除非您创建和分配自定义策略。 组织范围应用程序设置将覆盖全局策略和创建并向用户分配的任何自定义策略。

例如，假设您想要阻止所有第三方应用程序并允许来自 Microsoft 的特定应用程序，您的组织中的 HR 小组。 您可以创建名为 HR 应用程序权限策略的自定义策略，将其设置为阻止或允许应用程序所需，然后将其分配给人事部门的用户。

## <a name="manage-org-wide-app-settings"></a>管理组织范围应用程序设置

使用的应用程序可在整个组织的控制组织范围应用程序设置。 组织范围应用程序设置控制的所有用户的行为和替代的任何其他应用程序权限策略分配给用户。 组织范围应用程序设置会立即生效，并可用于控制恶意或有问题的应用程序。

1. 在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **权限策略**。
2. 选择**组织范围的设置**。 然后，您可以面板中配置所需的设置。 
![组织范围应用程序设置的屏幕截图](media/app-permission-policies-org-wide-settings.png)
3. 在**第三方应用程序**，下关闭或打开来控制对第三方应用程序访问这些设置：

    - **允许在工作组中的第三方应用程序**： 此选项控制用户是否可以使用第三方应用程序。
    - **允许任何新的第三方应用程序发布到默认情况下存储**： 是否将新的第三方应用程序发布到团队应用程序的存储成为团队中自动提供此控件。 如果允许第三方应用程序，仅可设置此选项。

4. 在**自定义应用程序**，下关闭或打开**与自定义应用程序允许进行交互**。 此设置控制用户是否可以与自定义 (sideloaded) 应用程序进行交互。 请记住，这一点不同于允许用户*上载*自定义应用程序。
5. 在**已阻止应用程序**，下搜索并添加您想要阻止在整个组织的应用程序。 您可以选择从租户的应用程序目录或团队应用程序商店的应用程序。
6. 单击**另存**为组织范围应用程序设置才会生效。

## <a name="create-a-custom-app-permission-policy"></a>创建自定义应用程序权限策略

如果您想要控制可用于不同的组织中的用户组的应用程序，创建并分配一个或多个自定义应用程序权限策略。 您可以创建和分配单独基于是否由 Microsoft 发布应用程序的自定义策略第三方或您的组织。 务必要了解创建自定义策略后，您不能更改其是否组织范围的设置中禁用第三方应用程序。 

1. 在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **权限策略**。
2. 选择**新策略**。
    ![新的应用程序权限策略的屏幕截图](media/app-permission-policies-new-policy.png)
3. 输入策略的描述性名称。
4. 在**Microsoft 应用程序**、**第三方应用程序**，和**租户的应用程序**，选择下列选项之一：

    - **允许所有应用程序**
    - **允许特定应用程序和阻止所有其他人**
    - **阻止特定应用程序，并允许所有其他人**
    - **阻止所有应用程序**

5. 如果您选择**允许特定应用程序和阻止其他人**，添加您希望允许的应用程序：

    1. 选择**允许应用程序**。
    1. 要允许，然后单击**添加**的应用程序的搜索。 搜索结果进行筛选到应用程序发布者 （**Microsoft 应用程序**，**第三方应用程序**或**租户的应用程序**）。
    1. 当您选择的应用程序列表时，请单击**允许**。

6. 同样，如果选择了**阻止特定应用程序，并允许所有其他人**，搜索并添加您想要阻止的应用程序。
7. 单击“**保存**”。

## <a name="edit-an-app-permission-policy"></a>编辑应用程序权限策略

您可以使用的 Microsoft 团队管理中心编辑策略，包括全局 （组织范围内默认值） 策略和您创建的自定义策略。 

1. 在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **权限策略**。
2. 选择您想要编辑的策略。
3. 从此处，进行所需的更改。 您可以管理基于应用程序发布者设置和添加和删除基于允许/阻止设置的应用程序。
4. 单击“**保存**”。

## <a name="assign-a-custom-app-permission-policy-to-users"></a>将自定义应用程序权限策略分配给用户

您可以使用的 Microsoft 团队管理中心分配给各个用户的自定义策略或 Skype for Business PowerShell 模块，将自定义策略分配给多个用户，例如安全组或通讯组中的所有用户。

> [!IMPORTANT]
> 建议仅使用 PowerShell 将策略分配给用户。 使用 Microsoft 团队管理中心创建、 编辑和管理策略。

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a>将自定义应用程序权限策略分配给单个用户

1. 在 Microsoft 团队管理中心的左侧导航窗格中，转到**用户**，，然后单击用户。
2. 旁边**分配策略**，选择**编辑**。
3. 在**应用程序权限策略**中，选择要分配的应用程序权限策略，然后选择**保存**。

    ![应用程序的安装程序的权限-分配-policy.png](media/app-permission-policies-assign-policy.png)

按如下方式向一个或多个用户还可以分配的应用程序权限策略：

1. 转到**Microsoft 团队管理中心** > **团队 apps** > **权限策略**。
2. 通过单击左侧的策略名称选择的策略。
3. 选择**管理用户**。
4. 在**管理用户**窗格中，搜索用户按显示名称或用户名称，选择名称，然后选择**添加**。 要添加的每个用户重复此步骤。
5. 添加完用户后，选择**保存**。
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>将自定义应用程序权限策略分配给组中的用户

您可能想要将自定义应用程序权限策略分配给已识别的多个用户。 例如，您可能要将策略分配给安全组中的所有用户。 您可以通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块 Skype 来执行此操作。 有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell Overview](teams-powershell-overview.md)。

本示例中，我们将分配到 Contoso 药品 HR 项目组中的所有用户称为人力资源应用程序权限策略的自定义应用程序权限策略。  

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
组中的所有用户都分配特定的应用程序权限策略。 本示例中，它是 HR 应用程序权限策略。
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
根据组中成员的数目，此命令可能需要几分钟才能执行。

## <a name="faq"></a>常见问题解答

### <a name="working-with-app-permission-policies"></a>使用应用程序权限策略

#### <a name="can-i-control-line-of-business-lob-apps"></a>可以控制行业 (LOB) 应用程序？

是，可以使用应用程序的权限策略来控制推出和通讯组的自定义 (LOB) 应用程序。

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>应用程序的权限策略如何固定的应用程序和应用程序设置策略相关联？

您可以使用与应用程序的权限策略的应用程序设置策略。 从一组的用户启用应用程序中选择预固定的应用程序。 此外，如果用户具有阻止应用程序在其应用程序安装策略中的应用程序权限策略，该应用程序不会出现在工作组中。

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a>可以使用应用程序的权限策略来限制上载自定义应用程序 (也称为 sideloading)？

若要了解有关如何限制上载自定义应用程序的详细信息，请参阅[团队中管理自定义应用程序策略和设置](teams-custom-app-policies-and-settings.md)。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>如何长时间才会生效的策略更改？

编辑全局策略，或为用户分配策略后，可以最多 24 小时才能使更改生效。 组织范围应用程序设置会立即生效。

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>阻止应用程序适用于团队移动客户端？

是时阻止应用程序，该应用程序阻止所有团队客户端。  

### <a name="user-experience"></a>用户体验

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>什么用户体验时阻止应用程序？

用户不能与阻止应用程序或其功能、 此类机器人、 制表符和消息扩展进行交互。 在共享上下文中，团队或组聊天中，如自动程序仍然可以向所有参与者的上下文的发送消息。 阻止应用程序时，向用户指明团队。 

例如，当阻止应用程序时，用户不能执行以下任一操作：

- 将应用程序添加个人或聊天或团队
- 将邮件发送到应用程序的自动程序
- 执行将信息发送回应用程序，例如，可操作的消息的按钮操作  
- 查看应用程序的选项卡
- 设置连接器以接收通知
- 使用应用程序的消息扩展

 ## <a name="related-topics"></a>相关主题
- [Teams 中适用于应用的管理设置](admin-settings.md)
- [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
- [在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)
