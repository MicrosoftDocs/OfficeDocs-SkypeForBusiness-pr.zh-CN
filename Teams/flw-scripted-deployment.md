---
title: 为一线工作人员大规模预配 Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: 关于使用脚本为一线工作人员部署或预配 Microsoft Teams 的指南。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bb1250fd3cc02599fafa37ab6ac694403e33df9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106829"
---
# <a name="how-to-provisions-teams-at-scale-for-firstline-workers"></a>如何为一线工作人员预配 Teams

是否需要快速将大量用户加入到 Microsoft Teams 并为他们配置精简体验？ 可按以下说明操作，快速预配标识、预配团队，并分配所有相关策略来控制最终用户体验。

在本演练中，你将学习如何：

- 创建大量用户。
- 创建大量团队并设置适当的频道。
- 大规模分配许可。
- 创建相应的 Teams 消息传递策略、应用设置策略和应用权限策略。
- 将这些策略大规模应用至用户。
- 向指定团队分配大量用户。

## <a name="prerequisites"></a>先决条件

从[此位置](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)下载资产。

> [!IMPORTANT]
> 上面提供的链接中的脚本是由 Microsoft 按原样提供的，必须根据你的个人需求进行修改。

## <a name="technical-requirements"></a>技术要求

- 租户必须具有相应数量的可用许可证，包括 Microsoft Teams。 如果你还没有此类许可证，请按照此处的说明激活 [ Office 365 E1 免费试用版](e1-trial-license.md)。
- 执行这些步骤的用户必须在 Azure AD 中具有全局管理员或用户管理员角色。
- 用户必须具有在其本地计算机上安装和配置软件的权限。

## <a name="step-by-step-process-overview"></a>分步流程概述

1. **设置环境**
    1. 下载包含示例 PowerShell 脚本和文档的 ZIP 文件
    1. 设置凭据
    1. 配置本地环境
    1. 配置 PowerShell 模块和环境变量
    1. 创建应用注册
1. **创建和设置团队**
    1. 创建团队
    1. 为团队创建频道
1. **创建 Teams 策略**
    1. 创建 Teams 消息传递策略。
    1. 创建 Teams 应用设置策略。
    1. 创建 Teams 应用权限策略。
1. **创建和设置用户**
    1. 创建用户和安全组
    1. 通过基于组的许可向用户分配许可
1. **分配用户和策略**
    1. 向团队分配用户
    1. 向用户和组分配策略
1. **测试和验证**
    1. 检查错误
    1. 以测试用户身份登录 Teams

## <a name="set-up-your-environment"></a>设置环境

可以通过以下步骤设置环境：

### <a name="download-zip-file-containing-sample-powershell-scripts"></a>下载包含示例 PowerShell 脚本的 .zip 文件

在继续操作前，你需要在[此位置](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)下载脚本。

### <a name="setup-credentials"></a>设置凭据

在本文档和示例脚本中，我们选择创建一个包含凭据的引用文件以简化操作。 这种技术使你无需在将凭据保留在本地存储的同时对所有不同的服务终结点进行身份验证。 为了运行后续脚本，你需要使用你和你的环境特有的凭据更新该引用文件。 在随后的每个脚本中，使用我们在 **GetCreds** 中调用的 helper 函数读取相应的凭据，这些凭据用于连接到各种服务。

不同服务要求不同凭据的情况并不常见。 例如，你可能对 MicrosoftTeams、AzureAD 和 MSonline 使用不同的凭据，在这种情况下，你可以运行 SetCred，使用有意义的名称保存每个凭据文件。

例如：SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml

> [!NOTE]
> 用于凭据的帐户不能要求提供 MFA。

以下是说明各种脚本如何使用保存的凭据进行身份验证的示例：

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = GetCreds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

要设置你的凭据，请完成以下操作：

1. 在 .zip 文件资产中查找 **SetCreds.ps1**。
1. 在 PowerShell 中运行 **SetCreds.ps1** 脚本以保存你的凭据。
    1. 系统将提示你“正在执行操作‘Export-Clixml’...”，你需要输入“Y”以批准。

### <a name="configure-the-local-environment"></a>配置本地环境

1. 在.zip 文件资产中查找 **SetConfig.ps1**。
1. 在 PowerShell 中运行以下命令，将带括号的条目替换为你的特定信息。
    1. **SetConfig.ps1** -tenantName [你的租户名称] -rootPath“[git 存储库根目录的完整路径]”

例如：`.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`

### <a name="configure-powershell-modules-and-environmental-variables"></a>配置 PowerShell 模块和环境变量

在继续之前，你需要安装并连接若干个 PowerShell 模块，包括 Azure AD、MSAL、MSCloudUtils 和 MicrosoftTeams。

1. 在 .zip 文件资产中查找 **ConfigurePowerShellModules.ps1**。
1. 编辑并使用你的变量替换以下环境变量：
1. 在 PowerShell 中运行 **ConfigurePowerShellModules.ps1** 脚本。

## <a name="create-and-set-up-teams"></a>创建和设置团队

为了与一线工作人员进行沟通和协作，首先需要建立一系列团队，并向这些团队添加标准频道，我们将在接下来介绍这些内容。

### <a name="create-teams"></a>创建团队

团队是组织内人员、内容和工具的集合。 对于大多数以一线工作人为中心的组织，最佳做法是将团队固定在一个物理位置周围。 例如，对以下每个位置设立团队：

- 商店
- 通讯组列表
- 制造工厂
- 医院
- 杂货店

*最佳实践讨论*：设计团队时，务必牢记[团队限制和规范](limits-specifications-teams.md)。 对于小型组织，可使用组织范围的团队来简化通信并对物理位置结构进行补充。 对于其他组织，结构化物理位置团队命名约定有助于企业轻松地同时向多个团队交叉发布通信。 例如，可以搜索名称中带有 US 的所有团队并向其交叉发布通信，以定位所有 US 位置。 有关交叉发布的详细信息，请参阅[此处](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)。

#### <a name="steps-to-create-teams"></a>创建团队的步骤

1. 在资产中查找 **Teams Information.csv** 文件。
1. 使用组织的特定信息来更新 **Teams Information.csv** 文件中的信息。 请牢记我们上面的最佳做法。
1. 查找 **CreateTeams. ps1** 脚本。
1. 在 PowerShell 中运行 **CreateTeams.ps1** 脚本。

### <a name="create-channels-for-teams"></a>为团队创建频道

频道是团队中专门的分区，用于按特定主题、项目、学科等整理对话。 每个团队都将自动获得一个常规频道，但在那里，你可以根据业务需求自定义你的结构。 例如，你的附加频道结构可能包括：

- **制造** - 安全、第 1 行、第 2 行、企业沟通、培训
- **杂货** - 面包店、农产品、肉类、企业沟通、培训
- **医疗保健** - 护士、医生、危症监护病房 1、危症监护病房 2
- **宾馆** - 前台、维修、客房服务、代客泊车和行李运送、企业沟通、培训
- **零售** - 商店前门、商店后门、企业沟通、培训

> [!NOTE]
> 不应将频道视为安全边界。 它们是组织工作人员进行协作的一种手段。

*最佳实践讨论*：在设计频道结构时，请务必保持简单，尤其是在你希望许多用户加入的情况下。 为了最大程度地降低培训需求，请抑制住为每种情况、角色或主题创建频道的冲动。 最多选择 3-5 个频道开始体验。 可在需要时轻松创建其他频道。 实际上，目前仅使用常规频道即可！

#### <a name="steps-to-create-channels-for-teams"></a>为 Teams 创建频道的步骤

1. 在 .zip 文件资产中查找 **TeamsChannels.csv** 文件。
1. 使用组织的特定信息来更新 **TeamsChannels.csv** 文件。 请牢记我们上面的最佳做法。
1. 在 .zip 文件资产中查找 **CreateTeamsChannels.ps1** 脚本。
1. 在 PowerShell 中运行 **TeamsChannels.ps1** 脚本。

## <a name="create-teams-policies"></a>创建 Teams 策略

作为管理员，你可以使用 Microsoft Teams 中的团队策略来控制组织中的用户能够看到的内容。 例如，可以控制将哪些应用程序固定到桌面或 Web 浏览器上的左边栏，或移动设备上的底部栏，以便在大量用户加入时简化最终用户体验。 这些策略中的一部分可使用 PowerShell 创建，另一些则必须在 Teams 管理控制台中手动创建。

*最佳实践讨论*：对于下面的每个策略，我们将选择实际创建两个策略：一个用于一线工作人员，一个用于一线管理人员。 可以根据需要导入任意数目的联系人。 对于大多数客户来说，最好从两个联系人开始，即使你最初为每个组进行了相同的设置也不例外。 随着 Teams 体验的发展，你可以选择进一步区分自己的体验，创建两个单独的策略可简化这项工作。

### <a name="create-teams-message-policies"></a>创建 Teams 消息策略

消息传递策略用于控制为 Microsoft Teams 中的用户提供哪些聊天和频道消息功能。

*最佳实践讨论*：尽管可使用自动创建的默认全局策略，但我们选择了按照以下步骤创建自定义策略，为一线管理人员和一线工作人员提供更加锁定、简单和差异化的体验。

#### <a name="steps-to-create-teams-message-policies"></a>创建 Teams 消息策略的步骤

1. 在 .zip 文件资产中查找 **TeamsMessagingPolicies.csv** 文件。
1. 使用组织的特定信息来更新 **TeamsMessagingPolicies.csv** 文件。 有关各选项的详细信息，请参阅[此处](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)。
1. 在资产中查找 **CreateTeamsMessagePolicies.ps1** 脚本。
1. 在 PowerShell 中运行 **TeamsMessagePolicies.ps1** 脚本。

### <a name="create-teams-app-setup-policies"></a>创建 Teams 应用设置策略

作为管理员，你可以使用应用设置策略执行以下操作：

- 自定义 Teams 以突出显示对用户最为重要的应用。 选择要固定的应用并设置其显示顺序。 通过固定应用，可展示组织中的用户所需的应用，包括由第三方或组织中的开发人员构建的应用。
- 控制用户是否可以将应用固定到 Teams。

将应用程序固定到应用栏。 这是 Teams 桌面客户端的侧边栏和 Teams 移动客户端（iOS 和 Android）的底边栏。

|Teams 桌面客户端  |         |Teams 移动客户端  |
|---------|---------|---------|
|![Teams 桌面客户端的屏幕截图，其中应用已固定到 *应用* 栏。](media/FLW-Teams-Desktop-Client.png)         |         |![Teams 桌面客户端的屏幕截图，其中应用已固定到 *底部* 栏。](media/FLW-Teams-Mobile-Client.png) |

*最佳实践讨论*：在 Microsoft Teams 管理中心管理应用设置策略。 无法使用 PowerShell 创建它们。 可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。 除非你创建并分配了自定义策略，否则你组织中的用户将自动分配到全局策略。 出于我们的目的，我们将为一线工作人员和一线管理人员创建两个新策略，以便为他们提供更简单、更精简的体验，从而轻松地同时加入大量用户。 你可以选择根据业务需求自定义体验。

#### <a name="create-the-firstline-manager-app-setup-policy"></a>创建一线管理人员应用设置策略

可以自定义以下设置以满足你的业务需求。 我们已根据最佳实践选择了一些推荐的选项，并提高了大规模加入新用户的轻松度。 有关详细信息，请单击[此处](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **设置策略**”。
2. 单击“ **添加**”。  
3. 输入策略的名称和说明。 例如，**一线管理人员应用设置策略**。
![一线管理人员应用设置策略图像。](media/FLW-FLM-App-Setup-Policy.png)

4. 关闭“**上载自定义应用**”。
5. 关闭“**允许用户固定**”。
![允许用户固定切换图像。](media/FLW-Allow-User-Pinning.png)

6. 如果尚未列出**班次**应用，请添加。 有关**班次**的更多信息，请单击[此处](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。
![“添加固定的应用”屏幕，显示班次应用（列在“添加”按钮旁边）。](media/FLW-Add-Pinned-Apps.png)

7. 删除显示的呼叫 注意：删除此功能不会针对用户禁用它，但会阻止它出现在应用栏，从而简化最终用户体验。
8. 按以下顺序排列应用以指定其在 Teams 应用栏中的顺序，然后单击“ **保存**”。
    1. 活动
    1. 聊天
    1. 团队
    1. 日历
    1. 班次 ![按顺序显示的管理人员应用程序列表的屏幕截图](media/FLW-Manager-Pinned-Apps.png)

#### <a name="create-the-firstline-worker-app-setup-policy"></a>创建一线工作人员应用设置策略

可以自定义以下设置以满足你的业务需求。 我们已根据最佳实践选择了一些推荐的选项，并提高了大规模加入新用户的轻松度。 有关详细信息，请单击[此处](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **设置策略**”。
2. 单击“ **添加**”。
3. 输入策略的名称和说明。 例如：**一线工作人员应用设置策略**。
![一线工作人员应用设置策略图像。](media/FLW-FLW-App-Setup-Policy.png)

4. 关闭“**上载自定义应用**”。
5. 关闭“**允许用户固定**”。
![允许用户固定切换图像。](media/FLW-Allow-User-Pinning.png)

6. 如果尚未列出**班次**应用，请添加。 有关**班次**的详细信息，请单击此处。
![“添加固定的应用”屏幕，显示班次应用（列在“添加”按钮旁边）。](media/FLW-Add-Pinned-Apps.png)

7. 删除显示的会议和呼叫 注意：删除这些功能不会针对用户禁用它们，但会阻止它们出现在应用栏，从而简化最终用户体验。
8. 按以下顺序排列应用以指定其在 Teams 应用栏中的顺序，然后单击“ **保存**”。
    1. 活动
    1. 聊天
    1. Teams
    1. 班次 ![按顺序显示的工作人员应用的屏幕截图。](media/FLW-Worker-Pinned-Apps.png)

### <a name="create-app-permission-policies"></a>创建应用权限策略

作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。 你可以允许或阻止 Microsoft、第三方和你的组织发布的所有应用或特定应用。 阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

*最佳实践讨论*：在 Microsoft Teams 管理中心管理应用设置策略。 无法使用 PowerShell 创建它们。 可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。 除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。 出于我们的目的，我们将为一线工作人员和一线管理人员创建了两个新策略，以便为他们提供更安全、更精简的体验，从而轻松地同时加入大量用户。 当然，你也可以选择根据业务需求自定义体验。

#### <a name="create-the-firstline-manager-app-permission-policy"></a>创建一线管理人员应用权限策略

可以自定义以下设置以满足你的业务需求。 这些是基于最佳实践的一些推荐选项，可以提高新用户大规模登录的便利性。 有关详细信息，请单击[此处](teams-app-permission-policies.md)。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **权限策略**”。
2. 单击“ **添加**”。
![显示添加应用权限策略页面，包含针对 Microsoft、第三方和租户应用的部分。](media/FLW-add-app-permission-policy.png)

3. 输入策略的名称和说明。 例如，一线管理人员应用权限策略。
4. 在 Microsoft 应用下，选择“**允许所有应用**”。
5. 在第三方应用下，选择“**允许所有应用**”。
6. 在租户应用下，选择“**允许所有应用**”。
7. 单击“ **保存**”。

#### <a name="create-the-firstline-worker-app-permission-policy"></a>创建一线员工应用权限策略

可以自定义以下设置以满足你的业务需求。 这些是基于最佳实践的一些推荐选项，可以提高新用户大规模登录的便利性。 有关详细信息，请单击[此处](teams-app-permission-policies.md)。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **权限策略**”。
2. 单击“ **添加**”。
![显示添加应用权限策略页面，包含针对 Microsoft、第三方和租户应用的部分。](media/FLW-add-app-permission-policy.png)

3. 输入策略的名称和说明。 例如，一线员工应用权限策略。
4. 在 Microsoft 应用下，选择“**允许所有应用**”。
5. 在第三方应用下，选择“**阻止所有应用**”。
6. 在租户应用下，选择“**允许所有应用**”。
7. 单击“ **保存**”。

## <a name="create-and-set-up-users"></a>创建和设置用户

### <a name="create-user-and-security-groups"></a>创建用户和安全组

要在 Teams 中处理大量用户，你首先需要在 Azure AD 中创建用户。 有很多方法可以预配大量用户，但我们要强调以下几点：

- 如果这些用户已存在于下面其中一个 HR 系统只中，请使用以下链接设置用户预配：
  - SAP Success Factors - [教程：配置 Active Directory 用户预配的 SAP SuccessFactors](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial)。
  - Workday - [教程：针对自动用户预配配置 Workday](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial)。
- 如果你的用户信息存在于其他系统中，请继续执行以下步骤。

为了更高效地管理这些用户，你需要为一线工作人员和一线管理人员创建两个安全组，并按照以下步骤直接将这些用户预配到安全组：

1. 在 .zip 文件资产中查找 **SecurityGroups.csv** 文件。
1. 使用组织的特定信息来更新 **SecurityGroups.csv** 文件。
    1. 务必更新 **MessagePolicy**、**AppPermissionPolicy** 和 **AppSetupPolicy** 的字段，以映射到先前创建的相应策略。
    1. 务必更新 **LicensePlan** 字段，以反映你打算为每个用户提供的许可证。 有关产品名称和服务计划标识符的详细信息，请参阅[此处](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)的文档。
1. 在 .zip 文件资产中查找 **Users.csv** 文件。
1. 使用组织的特定信息来更新 **Users.csv** 文件。
    1. 默认情况下，我们提供的脚本将创建一个用户，其中临时密码必须在首次登录时更改。 如果你不想使用默认密码，请编辑 **CreateUsers.ps1** 脚本以满足你的需求。
    1. 请确保更新“SecurityGroup”字段以反映先前创建的相应名称。
1. 在 PowerShell 中，运行资产中的 **CreateUsers.ps1**。

### <a name="assign-licensing-to-users-by-group-based-licensing"></a>通过基于组的许可向用户分配许可

Microsoft 付费的云服务（如 Office 365、企业移动性 + 安全性、Dynamics 365 和其他类似产品）需要许可证。 这些许可证将分配给需要访问这些服务的每个用户。 为管理许可证，管理员将使用其中一个管理门户（Office 或 Azure）和 PowerShell cmdlet。 Azure Active Directory (Azure AD) 是支持所有 Microsoft 云服务标识管理的基础结构。 Azure AD 存储有关用户许可证分配状态的信息。

为了大规模启用许可，Azure AD 现在包含基于组的许可，因此我们在本文前面创建了安全组。 可向组分配一个或多个产品许可证。 Azure AD 可确保许可证分配给组的所有成员。 任何加入该组的新成员都获得了相应的许可证。 离开组的成员的许可证将被删除。 此许可管理无需通过 PowerShell 自动执行许可证管理，以根据用户的具体情况反映组织中的变化和部门结构。

## <a name="assign-users-and-policies"></a>分配用户和策略

### <a name="assigning-users-to-teams"></a>向团队分配用户

现在你已创建用户并创建团队，可将所有用户放在适当的团队中。

1. 在 .zip 文件资产中查找 **Users.csv** 文件，并确保你能准确映射到此文件中的团队。
1. 在 PowerShell 中运行 .zip 文件资产中的 **AssignUserstoTeams.ps1** 文件。

### <a name="assign-teams-policies-to-users"></a>向用户分配 Teams 策略

你已创建用户和策略来修改 Teams 中的体验，现在可以将这些策略分配给合适的用户了。

1. 在 .zip 文件资产中查找 **SecurityGroups.csv** 文件，并确保你能将策略准确映射到组。
1. 从 PowerShell 中运行 .zip 资产中的 **AssignPoliciestoUsers.ps1**。

## <a name="test-and-validate"></a>测试和验证

### <a name="check-for-errors"></a>检查错误

运行早期版本的脚本时，将向位于 .zip 文件资产的日志文件夹中的 .csv 文件写入错误或异常。 此文件可用于调查可能发生的任何问题。

异常的一个示例是，你试图创建一个租户中已经存在的团队。

1. 查找“**日志**”文件夹，并审查它可能包含的任何 .csv 文件。 如果没有异常，则不会在这里找到异常文件。

### <a name="login-to-teams-with-a-test-user"></a>以测试用户身份登录 Teams

你已经完成所有步骤，现在可以验证已完成的工作了。

1. 从先前的列表中选择一个用户，并使用该用户的凭据登录到 Teams。
1. 验证 Teams 的外观和风格是否符合你的预期。 如果不符合，请查看**创建 Teams 策略**和**向用户分配 Teams 策略**部分。
1. 验证用户是否在正确的团队中。 如果不在，请查看**创建和设置用户**和**向团队分配用户**部分。
