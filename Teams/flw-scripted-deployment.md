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
ms.openlocfilehash: ed657590e024104e773b7a96b785b3b3db0ccbfc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120743"
---
# <a name="how-to-provision-teams-at-scale-for-frontline-workers"></a>如何为一线工作人员大规模预配 Teams

是否需要快速将大量用户加入到 Microsoft Teams 并为他们配置精简体验？ 可按以下说明操作，快速预配标识、预配团队，并分配所有相关策略来控制最终用户体验。

在本演练中，你将学习如何：

- 创建大量用户。
- 创建大量团队并设置适当的频道。
- 大规模分配许可。
- 创建相应的 Teams 消息传递策略、应用设置策略和应用权限策略。
- 将这些策略大规模应用至用户。
- 向指定团队分配大量用户。

> [!NOTE]
> 如果查看了这些信息，并认为需要帮助或存在疑问，可以 [**单击此处**](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMDv-1voW9MqL7zkQ11DzBUREZaU1E0WEk5T0NYS0NDSkFMSDROUUdYMC4u)与 White Glove支持联系。

## <a name="prerequisites"></a>先决条件

从[此位置](https://aka.ms/flwteamsscale)下载资产。

> [!IMPORTANT]
> 上面提供的链接中的脚本是由 Microsoft 按原样提供的，必须根据你的个人需求进行修改。

## <a name="technical-requirements"></a>技术要求

- 租户必须具有相应数量的可用许可证，包括 Microsoft Teams。 如果尚无这些许可证，请查看 [Teams 探索](teams-exploratory.md)，获取免费的试用订阅。
- 执行这些步骤的用户必须在 Azure AD 中分配以下角色：全局管理员、用户管理员和 Teams 服务管理员。
- 用户必须具有在其本地计算机上安装和配置软件的权限。

## <a name="step-by-step-process-overview"></a>分步流程概述

1. **设置环境**
    1. 从包含示例 PowerShell 脚本和文档的 GitHub 存储库下载
    1. 配置本地环境
    1. 设置凭据
    1. 配置 PowerShell 模块和环境变量
1. **创建和设置团队**
    1. 创建团队
    1. 创建团队的步骤
    1. 为团队创建频道
1. **创建 Teams 策略**
    1. 创建 Teams 消息策略
    1. 创建 Teams 应用设置策略
    1. 创建 Teams 应用权限策略
1. **用户和安全组**
    1. 创建用户和安全组
    1. 通过基于组的许可向用户分配许可
1. **分配用户和策略**
    1. 向团队分配用户
    1. 向用户分配 Teams 策略
    1. 可选：转换组成员身份类型
1. **测试和验证**
    1. 以测试用户身份登录 Teams
    1. 检查错误
    1. 错误处理
1. **延伸阅读**

## <a name="set-up-your-environment"></a>设置环境

可以通过以下步骤设置环境：

### <a name="download-from-the-github-repository-containing-sample-powershell-scripts-and-documentation"></a>从包含示例 PowerShell 脚本和文档的 GitHub 存储库下载

在继续操作前，你需要在[此位置](https://aka.ms/flwteamsscale)下载脚本。

### <a name="configure-the-local-environment"></a>配置本地环境

通过设置本地环境变量，此处引用的脚本可使用相对路径运行。 rootPath 是克隆此存储库的位置的根路径，tenantName 的格式为 **yourTenant.onmicrosoft.com**（不应包括 https）。

1. 打开 PowerShell 会话并导航到克隆的 git 存储库内的脚本文件夹。
1. 运行脚本 .\SetConfig.ps1 -tenantName [你的租户名称] -rootPath“git 存储库的完整根路径”。

例如：.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"

### <a name="setup-credentials"></a>设置凭据

> [!IMPORTANT]
> 这些脚本中的凭据管理方式可能不适合你使用，而且它们可轻松更改以满足你的要求。 始终遵循公司的标准和做法来保护服务帐户和托管身份。

这些脚本使用以 XML 文件形式存储在 $ENV:LOCALAPPDATA\keys（即 AppData\Local 文件夹）中的凭据。 需要调用模块 **BulkAddFunctions.psm1** 中的 helper 函数 **Set-Creds** 来设置用于运行这些脚本的凭据。 此技术消除了在维护本地存储中的凭据时对各种服务终结点进行身份验证的需要。 在每个脚本中，将使用 helper 函数 **Get-Creds** 读取相应的凭据，这些凭据用于连接到各种服务。

当你调用 **Set-Creds** 时，系统将提示你提供要写入到 $ENV:LOCALAPPDATA\keys 的 XML 文件名称。 你可能需要为不同的服务使用不同的凭据。 例如，你可能对 MicrosoftTeams、AzureAD 和 MSonline 使用不同的凭据，在这种情况下，你可以多次运行 **Set-Creds**，使用有意义的名称保存每个凭据文件。

例如：Set-Creds msol-cred.xml Set-Creds azuread-cred.xml Set-Creds teams-cred.xml

运行脚本 **SetCreds.ps1** 以保存你的凭据。 系统将提示你“正在执行操作‘Export-Clixml’...”，输入“Y”以批准。

> [!NOTE]
> 用于凭据的帐户不能要求多重身份验证 (MFA)。

以下是说明各种脚本如何使用保存的凭据进行身份验证的示例：

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = Get-Creds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

### <a name="configure-powershell-modules-and-environmental-variables"></a>配置 PowerShell 模块和环境变量

你需要安装并连接若干个 PowerShell 模块，包括 Azure AD、MSAL、MSCloudUtils 和 MicrosoftTeams。

1. 在存储库的脚本文件夹中查找 **ConfigurePowerShellModules.ps1**。
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

*最佳实践讨论*：设计团队时，务必牢记 [团队限制和规范](limits-specifications-teams.md)。 对于小型组织，可使用组织范围的团队来简化通信并对物理位置结构进行补充。 对于其他组织，结构化物理位置团队命名约定有助于企业轻松地同时向多个团队交叉发布通信。 例如，可以搜索名称中带有 US 的所有团队并向其交叉发布通信，以定位所有 US 位置。 有关交叉发布的详细信息，请参阅[此处](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)。

#### <a name="steps-to-create-teams"></a>创建团队的步骤

1. 在存储库的数据文件夹中查找 **TeamsInformation.csv** 文件。
1. 使用组织的特定信息来更新 **TeamsInformation.csv** 文件中的信息。 请牢记我们上面的最佳做法。
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

1. 在存储库的脚本文件夹中查找 **TeamsChannels.csv** 文件。
1. 使用组织的特定信息来更新 **TeamsChannels.csv** 文件。 请牢记我们上面的最佳做法。
1. 在存储库的脚本文件夹中查找 **CreateTeamsChannels.ps1** 脚本。
1. 在 PowerShell 中运行 **CreateTeamsChannels.ps1** 脚本。

## <a name="create-teams-policies"></a>创建 Teams 策略

作为管理员，你可以使用 Microsoft Teams 中的团队策略来控制组织中的用户能够看到的内容。 例如，可以控制将哪些应用程序固定到桌面或 Web 浏览器上的左边栏，或移动设备上的底部栏，以便在大量用户加入时简化最终用户体验。 这些策略中的一部分可使用 PowerShell 创建，另一些则必须在 Teams 管理控制台中手动创建。

*最佳实践讨论*：对于下面的每个策略，我们将选择实际创建两个策略：一个用于一线工作人员，一个用于一线管理人员。 可以根据需要导入任意数目的联系人。 对于大多数客户来说，最好从两个联系人开始，即使你最初为每个组进行了相同的设置也不例外。 随着 Teams 体验的发展，你可以选择进一步区分自己的体验，创建两个单独的策略可简化这项工作。

### <a name="create-teams-message-policies"></a>创建 Teams 消息策略

消息传递策略用于控制为 Microsoft Teams 中的用户提供哪些聊天和频道消息功能。

*最佳实践讨论*：尽管可使用自动创建的默认全局策略，但我们选择了按照以下步骤创建自定义策略，为一线管理人员和一线工作人员提供更加锁定、简单和差异化的体验。

#### <a name="steps-to-create-teams-message-policies"></a>创建 Teams 消息策略的步骤

1. 在存储库的脚本文件夹中查找 **TeamsMessagingPolicies.csv** 文件。
1. 使用组织的特定信息来更新 **TeamsMessagingPolicies.csv** 文件。 有关各选项的详细信息，请参阅[此处](./messaging-policies-in-teams.md#messaging-policy-settings)。
1. 在存储库的脚本文件夹中查找 **CreateTeamsMessagePolicies.ps1** 脚本。
1. 在 PowerShell 中运行 **CreateTeamsMessagePolicies.ps1** 脚本。

### <a name="create-teams-app-setup-policies"></a>创建 Teams 应用设置策略

作为管理员，你可以使用应用设置策略执行以下操作：

- 自定义 Teams 以突出显示对用户最为重要的应用。 选择要固定的应用并设置其显示顺序。 通过固定应用，可展示组织中的用户所需的应用，包括由第三方或组织中的开发人员构建的应用。
- 控制用户是否可以将应用固定到 Teams。

将应用程序固定到应用栏。 这是 Teams 桌面客户端的侧边栏和 Teams 移动客户端（iOS 和 Android）的底边栏。

|Teams 桌面客户端  |         |Teams 移动客户端  |
|---------|---------|---------|
|![Teams 桌面客户端的屏幕截图，其中应用已固定到 *应用* 栏。](media/FLW-Teams-Desktop-Client.png)         |         |![Teams 桌面客户端的屏幕截图，其中应用已固定到 *底部* 栏。](media/FLW-Teams-Mobile-Client.png) |

*最佳实践讨论*：在 Microsoft Teams 管理中心管理应用设置策略。 无法使用 PowerShell 创建它们。 可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。 除非你创建并分配了自定义策略，否则你组织中的用户将自动分配到全局策略。 出于我们的目的，我们将为一线工作人员和一线管理人员创建两个新策略，以便为他们提供更简单、更精简的体验，从而轻松地同时加入大量用户。 你可以选择根据业务需求自定义体验。

#### <a name="create-the-frontline-manager-app-setup-policy"></a>创建一线管理人员应用设置策略

可以自定义以下设置以满足你的业务需求。 我们已根据最佳实践选择了一些推荐的选项，并提高了大规模加入新用户的轻松度。 有关详细信息，请单击[此处](./teams-app-setup-policies.md#create-a-custom-app-setup-policy)。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **设置策略**”。
2. 单击“ **添加**”。  
3. 输入策略的名称和说明。 例如，**一线管理人员应用设置策略**。
![一线管理人员应用设置策略图像。](media/FLW-FLM-App-Setup-Policy.png)

4. 关闭“**上载自定义应用**”。
5. 关闭“**允许用户固定**”。
![允许用户固定切换图像。](media/FLW-Allow-User-Pinning.png)

6. 如果尚未列出 **班次** 应用，请添加。 有关 **班次** 的更多信息，请单击 [此处](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。
![“添加固定的应用”屏幕，显示班次应用（列在“添加”按钮旁边）。](media/FLW-Add-Pinned-Apps.png)

7. 删除显示的呼叫 注意：删除此功能不会针对用户禁用它，但会阻止它出现在应用栏，从而简化最终用户体验。
8. 按以下顺序排列应用以指定其在 Teams 应用栏中的顺序，然后单击“ **保存**”。
    1. 活动
    1. 聊天
    1. 团队
    1. 日历
    1. 班次 ![按顺序显示的管理人员应用程序列表的屏幕截图](media/FLW-Manager-Pinned-Apps.png)

#### <a name="create-the-frontline-worker-app-setup-policy"></a>创建一线工作人员应用设置策略

可以自定义以下设置以满足你的业务需求。 我们已根据最佳实践选择了一些推荐的选项，并提高了大规模加入新用户的轻松度。 有关详细信息，请单击[此处](./teams-app-setup-policies.md#create-a-custom-app-setup-policy)。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **设置策略**”。
2. 单击“ **添加**”。
3. 输入策略的名称和说明。 例如：**一线工作人员应用设置策略**。
![一线工作人员应用设置策略图像。](media/FLW-FLW-App-Setup-Policy.png)

4. 关闭“**上载自定义应用**”。
5. 关闭“**允许用户固定**”。
![允许用户固定切换图像。](media/FLW-Allow-User-Pinning.png)

6. 如果尚未列出 **班次** 应用，请添加。 有关 **班次** 的详细信息，请单击此处。
![“添加固定的应用”屏幕，显示班次应用（列在“添加”按钮旁边）。](media/FLW-Add-Pinned-Apps.png)

7. 删除显示的会议和呼叫 注意：删除这些功能不会针对用户禁用它们，但会阻止它们出现在应用栏，从而简化最终用户体验。
8. 按以下顺序排列应用以指定其在 Teams 应用栏中的顺序，然后单击“ **保存**”。
    1. 活动
    1. 聊天
    1. Teams
    1. 班次 ![按顺序显示的工作人员应用的屏幕截图。](media/FLW-Worker-Pinned-Apps.png)

### <a name="create-teams-app-permission-policies"></a>创建 Teams 应用权限策略

作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。 你可以允许或阻止 Microsoft、第三方和你的组织发布的所有应用或特定应用。 阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

*最佳实践讨论*：在 Microsoft Teams 管理中心管理应用设置策略。 无法使用 PowerShell 创建它们。 可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。 除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。 出于我们的目的，我们将为一线工作人员和一线管理人员创建了两个新策略，以便为他们提供更安全、更精简的体验，从而轻松地同时加入大量用户。 当然，你也可以选择根据业务需求自定义体验。

#### <a name="create-the-frontline-manager-app-permission-policy"></a>创建一线管理人员应用权限策略

可以自定义以下设置以满足你的业务需求。 这些是基于最佳实践的一些推荐选项，可以提高新用户大规模登录的便利性。 有关详细信息，请单击[此处](teams-app-permission-policies.md)。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **权限策略**”。
2. 单击“ **添加**”。
![显示添加应用权限策略页面，包含针对 Microsoft、第三方和租户应用的部分。](media/FLW-add-app-permission-policy.png)

3. 输入策略的名称和说明。 例如，一线管理人员应用权限策略。
4. 在 Microsoft 应用下，选择“**允许所有应用**”。
5. 在第三方应用下，选择“**允许所有应用**”。
6. 在租户应用下，选择“**允许所有应用**”。
7. 单击“ **保存**”。

#### <a name="create-the-frontline-worker-app-permission-policy"></a>创建一线员工应用权限策略

可以自定义以下设置以满足你的业务需求。 这些是基于最佳实践的一些推荐选项，可以提高新用户大规模登录的便利性。 有关详细信息，请单击[此处](teams-app-permission-policies.md)。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **权限策略**”。
2. 单击“ **添加**”。
![显示添加应用权限策略页面，包含针对 Microsoft、第三方和租户应用的部分。](media/FLW-add-app-permission-policy.png)

3. 输入策略的名称和说明。 例如，一线员工应用权限策略。
4. 在 Microsoft 应用下，选择“**允许所有应用**”。
5. 在第三方应用下，选择“**阻止所有应用**”。
6. 在租户应用下，选择“**允许所有应用**”。
7. 单击“ **保存**”。

## <a name="users-and-security-groups"></a>用户和安全组

### <a name="create-users-and-security-groups"></a>创建用户和安全组

要在 Teams 中处理大量用户，你首先需要在 Azure AD 中创建用户。 有很多方法可以预配大量用户，但我们要强调以下几点：

- 如果这些用户已存在于下面其中一个 HR 系统只中，请使用以下链接设置用户预配：
  - SAP Success Factors - [教程：配置 Active Directory 用户预配的 SAP SuccessFactors](/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial)。
  - Workday - [教程：针对自动用户预配配置 Workday](/azure/active-directory/saas-apps/workday-inbound-tutorial)。
- 如果你的用户信息存在于其他系统中，请继续执行以下步骤。

为了更高效地管理这些用户，你需要为一线工作人员和一线管理人员创建两个安全组，并按照以下步骤直接将这些用户预配到安全组：

1. 在存储库的脚本文件夹中查找 **Users.csv** 文件。
1. 使用组织的特定信息来更新 **Users.csv** 文件。
    1. 默认情况下，我们提供的脚本将创建一个用户，其中临时密码必须在首次登录时更改。 如果你不想使用默认密码，请编辑 **CreateUsers.ps1** 脚本以满足你的需求。
    1. 请确保更新“SecurityGroup”字段以反映先前创建的相应名称。
1. 在存储库的脚本文件夹中查找 **SecurityGroups.csv** 文件。
1. 使用组织的特定安全组信息来更新 **SecurityGroups.csv** 文件。
    1. 务必更新 **MessagePolicy**、**AppPermissionPolicy** 和 **AppSetupPolicy** 的字段，以映射到先前创建的相应策略。
    1. 务必更新 **LicensePlan** 字段，以反映你打算为每个用户提供的许可证。 有关产品名称和服务计划标识符的详细信息，请参阅[此处](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)的文档。
1. 在 PowerShell 中，运行资产中的脚本 **CreateUsers.ps1**。

### <a name="assign-licensing-to-users-via-group-based-licensing"></a>通过基于组的许可向用户分配许可

Microsoft 付费的云服务（如 Microsoft 365、Office 365、企业移动性 + 安全性、Dynamics 365 和其他类似产品）需要许可证。 这些许可证将分配给需要访问这些服务的每个用户。 为管理许可证，管理员将使用其中一个管理门户（Office 或 Azure）和 PowerShell cmdlet。 Azure Active Directory (Azure AD) 是支持所有 Microsoft 云服务标识管理的基础结构。 Azure AD 存储有关用户许可证分配状态的信息。

为了大规模启用许可，Azure AD 现在包含基于组的许可，因此我们在本文前面创建了安全组。 可向组分配一个或多个产品许可证。 Azure AD 可确保许可证分配给组的所有成员。 任何加入该组的新成员都获得了相应的许可证。 离开组的成员的许可证将被删除。 此许可管理无需通过 PowerShell 自动执行许可证管理，以根据用户的具体情况反映组织中的变化和部门结构。

## <a name="assign-users-and-policies"></a>分配用户和策略

### <a name="assign-users-to-teams"></a>向团队分配用户

现在你已创建用户并创建团队，可将所有用户放在适当的团队中。

1. 在存储库的数据文件夹中查找 **Users.csv** 文件，并确保你能准确映射到此文件中的团队。
1. 在 PowerShell 中，运行存储库的脚本文件夹中的脚本 **AssignUserstoTeams.ps1**。

### <a name="assign-teams-policies-to-users"></a>向用户分配 Teams 策略

你已创建用户和策略来修改 Teams 中的体验，现在可以将这些策略分配给合适的用户了。

1. 在存储库的数据文件夹中查找 **SecurityGroups.csv** 文件，并确保你能将策略准确映射到组。
1. 在 PowerShell 中，运行存储库的脚本文件夹中的脚本 **AssignPoliciestoUsers.ps1**。

### <a name="optional-convert-group-membership-type"></a>可选：转换组成员身份类型

> [!NOTE]
> 此步骤适用于拥有 Azure AD P1 或更高版本的用户。

获得 Azure AD P1 或更高版本的许可后，你可以选择使用动态组成员身份，而不是使用分配的成员身份。 创建团队的脚本还创建了成员身份类型为“已分配”的 Office 组，这意味着必须显式添加其成员。

使用动态成员身份，可以编写规则来确定某人是否为团队成员。

> [!NOTE]
> 运行此脚本时，组的当前成员身份将被删除（所有者除外），并且将在成员身份同步作业运行时添加新成员。

1. 在存储库的数据文件夹中查找 **migrateGroups.csv** 文件。
1. 使用将要迁移的组以及动态成员身份规则来更新 CSV 文件 **migrateGroups.csv**。
1. 在存储库的脚本文件夹中查找 **ConvertGroupMembershipType.ps1** 文件。
1. 在 PowerShell 中，运行脚本 **ConvertGroupMembershipType.ps1**

## <a name="test-and-validate"></a>测试和验证

### <a name="login-to-teams-with-a-test-user"></a>以测试用户身份登录 Teams

你已经完成所有步骤，现在可以验证已完成的工作了。

1. 创建的用户的初始密码位于 CreateUsers.ps1 中，他们需要在首次登录时进行更改。
1. 验证 Teams 的外观和风格是否符合你的预期。 如果不符合，请查看 **创建 Teams 策略** 和 **向用户分配 Teams 策略** 部分。
1. 验证用户是否在正确的团队中。 如果不在，请查看 **创建和设置用户** 和 **向团队分配用户** 部分。

> [!NOTE]
> 如果通过“身份和访问管理”团队来管理一线员工配置，则需要遵循他们的流程来为员工提供凭据。

### <a name="check-for-errors"></a>检查错误

运行早期版本的脚本时，将向位于存储库副本的日志文件夹中的 .csv 文件写入错误或异常。 此文件可用于调查可能发生的任何问题。

异常的一个示例是，你试图创建一个租户中已经存在的团队。

1. 查找“**日志**”文件夹，并审查它可能包含的任何 .csv 文件。 如果没有异常，则不会在这里找到异常文件。

### <a name="error-handling"></a>错误处理

这些示例脚本中实现了最少的错误处理。 存在 try/catch 块，如果触发，我们会将错误存储到 catch 块的变量中。 必须根据你的偏好实现其他错误处理。

## <a name="further-reading"></a>延伸阅读

- [新建团队频道 (Powershell)](/powershell/module/teams/new-teamchannel?view=teams-ps)
- [新建团队消息传递策略 (Powershell)](/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)
- [向 Microsoft Teams 中的用户分配策略](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module)
- [使用 Office 365 PowerShell 分配许可证和用户帐户](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)