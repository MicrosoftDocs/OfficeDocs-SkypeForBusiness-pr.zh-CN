---
title: 管理 Microsoft 团队中的紧急呼叫策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中使用和管理动态 E911 功能的紧急呼叫策略。
f1keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 4a1846217734142388fdf3466f68ccadea49c829
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573172"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的紧急呼叫策略

[!INCLUDE [preview-feature](includes/preview-feature.md)]

如果您的组织使用呼叫计划或部署的电话系统直接路由，则可以使用 Microsoft 团队中的紧急呼叫策略定义当组织中的团队用户进行紧急呼叫时发生的情况。 你可以设置被分配了策略的用户呼叫紧急服务时通知的人员以及通知的方式。 例如，你可以将策略设置配置为自动通知组织的安全桌面，并让他们在紧急呼叫中进行侦听。  

通过转到 Microsoft 团队管理中心或使用 Windows PowerShell 中的**语音** > **紧急策略**来管理紧急呼叫策略。 可将策略分配给用户和[网络站点](location-based-routing-terminology.md)。

对于用户，你可以使用全局（组织范围默认）策略或创建并分配自定义策略。 除非你创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。 对于网络站点，您可以创建和分配自定义策略。

如果你为某个网络网站和用户分配了紧急呼叫策略，并且该用户在该网络站点上，则分配给网络网站的策略将覆盖分配给该用户的策略。

## <a name="create-a-custom-emergency-calling-policy"></a>创建自定义紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。
2. 单击“添加”****。
3. 输入策略的名称和说明。
4. 设置当进行紧急呼叫时，您希望将组织中的人员（通常是安全桌面）通知的方式。 若要执行此操作，请在 "**通知模式**" 下，选择下列操作之一：
    - **仅通知**：将团队聊天消息发送给你指定的用户和组。
    - **Conferenced in 但静音**：将团队聊天消息发送给你指定的用户和组，他们可以在呼叫方和 PSAP 运营商之间的对话中侦听（但不参与）。
5.  如果在 "**通知的拨出号码**" 框中选择了 "Conferenced"，**但处于静音**通知模式，则可以输入用户或组的 PSTN 电话号码呼叫并加入紧急呼叫。 例如，输入您的组织的安全桌面号码，当进行紧急呼叫时，您将收到呼叫，然后可以接听或参与呼叫。
6. 搜索并选择一个或多个用户或组（如组织的安全桌面），以便在发生紧急呼叫时发出通知。  通知可以发送到用户、通讯组和安全组的电子邮件地址。 最多可通知50用户。
7. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[新-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>编辑紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心

你可以编辑全局策略或你创建的任何自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。
2. 通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。
3. 进行所需的更改，然后单击 "**保存**"。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[设置-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>为用户分配自定义紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。
2. 单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。
3. 在 "**紧急呼叫策略**" 下，选择要分配的策略，然后单击 "**保存**"。

若要一次为多个用户分配自定义团队策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。

或者，您也可以执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。
2. 通过单击策略名称的左侧，选择策略。
3. 选择 "**管理用户**"。
4. 在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。 对要添加的每个用户重复此步骤。
5. 添加完用户后，单击 "**保存**"。

### <a name="using-powershell"></a>使用 PowerShell

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a>为用户分配自定义紧急呼叫策略

请参阅[授权-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a>为组中的用户分配自定义紧急呼叫策略

您可能希望将自定义紧急呼叫策略分配给已标识的多个用户。 例如，你可能想要向安全组中的所有用户分配策略。 你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。

在此示例中，我们将名为 "操作紧急呼叫策略" 的策略分配给 "Contoso 操作" 组中的所有用户。  

> [!NOTE]
> 请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。

获取特定组的 GroupObjectId。
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
获取指定组的成员。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
将组中的所有用户分配到特定团队策略。 在此示例中，它是运行紧急呼叫路由策略的操作。
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.EmailAddress}
``` 
此命令可能需要几分钟才能执行，具体取决于组中的成员数量。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>将自定义紧急呼叫策略分配给网络站点

使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫策略分配给网络站点。

以下示例显示了如何将名为 Contoso 紧急呼叫策略1的策略分配给 Site1 网站。

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a>相关主题

- [管理团队中的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
