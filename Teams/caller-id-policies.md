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
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的呼叫者 ID 策略更改或阻止组织中的团队用户的来电显示 ID。
ms.openlocfilehash: aed6e3cbe2053ddc16b049608247f56705626249
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992882"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的呼叫者 ID 策略

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

作为管理员，你可以使用 Microsoft 团队中的来电显示策略来更改或阻止来电显示（也称为呼叫线路 ID）。 默认情况下，当用户呼叫 PSTN 电话时，可以看到团队用户的电话号码，并且在呼叫团队用户时可以看到 PSTN 呼叫者的电话号码。 可以使用来电显示策略为组织中的团队用户显示备用电话号码，或阻止显示传入号码。

例如，当用户进行呼叫时，您可以更改来电显示以显示组织的主要电话号码，而不是用户的电话号码。

通过转到 "Microsoft 团队管理中心" 中的 "**语音** > **来电**显示" 策略来管理呼叫者 id 策略。 你可以使用全局（组织范围默认）策略或创建自定义策略并将其分配给用户。 除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。

你可以编辑全局策略，也可以创建并分配自定义策略。 如果向用户分配了自定义策略，则该策略将应用于用户。 如果未向用户分配自定义策略，则全局策略将应用于该用户。

## <a name="create-a-custom-caller-id-policy"></a>创建自定义呼叫方 ID 策略

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **呼叫者 ID 策略**"。
2. 单击“添加”****。
![管理中心中新来电显示策略页面的屏幕截图](media/caller-id-policies-add-policy.png)
3. 输入策略的名称和说明。
4. 在此处，选择所需的设置：

    - **阻止来电呼叫者 id**：启用此设置可阻止显示传入呼叫的来电显示。
    - **用户可以替代呼叫方 ID 策略**：启用此设置可让用户替代策略中的设置，将其号码显示为 callees。 这意味着用户可以选择是否要显示其呼叫者 ID。
    - **替换呼叫者 id**：通过选择下列操作之一，设置要为用户显示的来电显示：

        - **用户号码**：显示用户的号码。 
        - **服务号码**：允许您将服务电话号码设置为显示为呼叫方 ID。
        - **匿名**：以匿名方式显示呼叫方 ID。

    - 用于**替换呼叫方 id 的服务号码**：选择服务号码以替换用户的来电显示。 如果在 "**替换呼叫方 ID**" 中选择了 "**服务号码**"，则此选项可用。

5. 单击“**保存**”。

## <a name="edit-a-caller-id-policy"></a>编辑呼叫者 ID 策略

你可以编辑全局策略或你创建的任何自定义策略。 

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **呼叫者 ID 策略**"。
2. 通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。
3. 更改所需的设置，然后单击 "**保存**"。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>为用户分配自定义呼叫者 ID 策略

你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块，以便为用户组（如安全组或通讯组）分配自定义策略。

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a>为用户分配自定义呼叫者线路 ID 策略

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。
2. 单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。
3. 在 "**呼叫者 ID 策略**" 下，选择要分配的策略，然后选择 "**保存**"。

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a>一次为多个用户分配自定义呼叫线路 ID 策略

若要一次为多个用户分配自定义呼叫线路 Id 策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。

或者，您也可以执行以下操作：

1. 转到**Microsoft 团队管理中心** > **语音** > **呼叫方 ID 策略**。
2. 通过单击策略名称的左侧，选择策略。
3. 选择 "**管理用户**"。
4. 在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。 对要添加的每个用户重复此步骤。
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

