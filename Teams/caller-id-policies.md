---
title: 管理 Microsoft 团队中的呼叫者 ID 策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的呼叫者 ID 策略更改或阻止组织中的团队用户的来电显示 ID。
ms.openlocfilehash: dde534d0c74b11b3c3131a7d5c9eb8611135f70f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349776"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的呼叫者 ID 策略

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

作为管理员，你可以使用 Microsoft 团队中的来电显示策略来更改或阻止来电显示（也称为呼叫线路 ID）。 默认情况下，当用户呼叫 PSTN 电话时，可以看到团队用户的电话号码，并且在呼叫团队用户时可以看到 PSTN 呼叫者的电话号码。 可以使用来电显示策略为组织中的团队用户显示备用电话号码，或阻止显示传入号码。

例如，当用户进行呼叫时，您可以更改来电显示以显示组织的主要电话号码，而不是用户的电话号码。

通过转到**Voice**  >  "Microsoft 团队管理中心" 中的 "语音来电显示"**策略**来管理呼叫者 id 策略。 可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。 除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。

你可以编辑全局策略，也可以创建并分配自定义策略。 如果向用户分配了自定义策略，则该策略将应用于用户。 如果未向用户分配自定义策略，则全局策略将应用于该用户。

## <a name="create-a-custom-caller-id-policy"></a>创建自定义呼叫方 ID 策略

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫者 ID 策略**"。
2. 单击“添加”****。 <br>
![管理中心中新来电显示策略页面的屏幕截图](media/caller-id-policies-add-policy.png)
3. 输入策略的名称和说明。
4. 在此处，选择所需的设置：

    - **阻止来电呼叫者 id**：启用此设置可阻止显示传入呼叫的来电显示。
    - **替代呼叫方 ID 策略**：启用此设置，让用户覆盖策略中的设置以将其号码显示为 callees。 这意味着用户可以选择是否要显示其呼叫者 ID。 有关详细信息，请参阅[最终用户对出站呼叫程序 ID 的控制](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)。
    - 将**来电显示替换**为：通过选择下列操作之一，设置要为用户显示的呼叫者 id：

        - **用户号码**：显示用户的号码。 
        - **服务号码**：允许您将服务电话号码设置为显示为呼叫方 ID。
        - **匿名**：以匿名方式显示呼叫方 ID。

    - **将呼叫方 Id 替换为此服务号码**：选择服务号码以替换用户的来电显示。 如果在 **"将呼叫方 ID 替换为**" 中选择了 "**服务编号**"，则此选项可用。

5. 单击“**保存**”。

## <a name="edit-a-caller-id-policy"></a>编辑呼叫者 ID 策略

你可以编辑全局策略或你创建的任何自定义策略。 

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫者 ID 策略**"。
2. 通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。
3. 更改所需的设置，然后单击 "**保存**"。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>为用户分配自定义呼叫者 ID 策略

你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块，以便将自定义策略分配给组中的用户，例如安全组或通讯组。

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a>为用户分配自定义呼叫者线路 ID 策略

若要向一个用户分配策略，请执行以下操作：

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。****
2. 单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。
3. 在 "**呼叫者 ID 策略**" 下，选择要分配的策略，然后选择 "**保存**"。

要一次为多个用户分配策略，请执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后搜索用户或筛选视图以显示所需的用户。
2. 在 " **&#x2713;** " （复选标记）列中，选择用户。 若要选择 "所有用户"，请单击表格顶部的 "&#x2713;" （复选标记）。
3. 单击 "**编辑设置**"，进行所需的更改，然后单击 "**应用**"。  

或者，您也可以执行以下操作：

1. 转到**Microsoft 团队管理中心**  >  **语音**  >  **呼叫方 ID 策略**。
2. 单击策略名称的左侧以选择该策略。
3. 选择“管理用户”****。
4. 在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。 对想要添加的每一个用户重复此步骤。
5. 添加完用户后，请选择 "**保存**"。

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>将自定义呼叫方 ID 策略分配给组中的用户

你可能需要向已标识的多个用户分配自定义策略。 例如，你可能想要向安全组中的所有用户分配策略。 你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。 有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。

在此示例中，我们为 Contoso 支持组中的所有用户分配一个名为支持呼叫者 ID 策略的自定义呼叫者盖子策略。  

> [!NOTE]
> 请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。

获取特定组的 GroupObjectId。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
获取指定组的成员。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
将组中的所有用户分配给特定的呼叫者 ID 策略。 在此示例中，它支持呼叫方 ID 策略。
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
此命令可能需要几分钟才能执行，具体取决于组中的成员数量。

 ## <a name="related-topics"></a>相关主题

- [新-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)
- [向团队中的用户分配策略](assign-policies.md)
