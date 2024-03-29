---
title: 将用户从本地迁移至 Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 了解如何将用户移动到 Skype for Business Online。
ms.openlocfilehash: a865b5ece2802f11bbbd103b10e52ff82f1ef804
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614976"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>将用户从本地迁移至 Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

将用户从本地移动到 Skype for Business Online 后，用户与 Skype for Business Online 进行交互，以使用其功能。 本地存在的任何联系人都将在 Skype for Business Online 中可用，并且用户为将来组织的任何现有会议都将更新为 ，以便链接指向 Skype for Business Online。 如果用户启用了音频会议，则会议还将包括拨入坐标。  若要将用户从本地环境移动到 Skype for Business Online，请使用 Move-CsUser cmdlet 或 Skype for Business Server 控制面板，这两者都是本地工具。 

在移动任何用户之前，请务必查看 [将](move-users-between-on-premises-and-cloud.md#prerequisites) 用户迁移到云的先决条件。

> [!NOTE]
> 为准备即将停用 Skype for Business Online，Microsoft 简化了组织移动到 Teams。 将用户从本地迁移到云时，现在会自动为用户分配 TeamsOnly 模式，其会议从本地自动转换为 Teams 会议，就像已指定交换机一样，无论是否实际指定了交换机。 `-MoveToTeams`  在停用 Skype for Business Online 之前，需要将用户从本地迁移到 Skype for Business Online 的组织可以在将用户移至 *TeamsOnly* 后更新用户模式，分两步完成此操作。 但是，在近期内，将不再可以将 TeamsOnly 模式分配给托管在云中的用户。  
 
## <a name="move-users-with-move-csuser"></a>使用迁移功能Move-CsUser 

Move-CsUser命令行管理程序 PowerShell Skype for Business中提供。 您必须在内部部署环境和 Microsoft 365 组织中具有足够的权限，如所需的管理[凭据 中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。 您可以使用在两个环境中具有特权的单个帐户，或者可以使用本地凭据启动本地 Skype for Business Server 命令行管理程序窗口，并使用 参数指定具有所需 管理角色 的 Microsoft 365 帐户 `-Credential` 的凭据。

若要使用 Move-CsUser 将用户移至联机：

- 使用 Identity 参数指定要移动的用户。
- 使用值"sipfed.online.lync"指定 -Target 参数。 <span>com"。
- 如果您没有一个在本地和 Microsoft 365 中具有足够权限的帐户，请使用 -credential 参数在 Microsoft 365 中为帐户提供足够权限。
- 如果具有权限的帐户Microsoft 365".onmicrosoft"结尾。 <span>com"， then you must specify the -HostedMigrationOverrideUrl parameter， with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

以下 cmdlet 序列可用于将用户移动到 Skype for Business Online 并将租户默认模式分配给用户。 它假定Microsoft 365凭据是单独的帐户，并作为输入提供给 Get-Credential 提示。

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

如果管理员帐户为 MFA (多重身份验证) ，则不要指定 -Credential 参数。 将提示管理员输入凭据。

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a>使用控制面板Skype for Business Server管理中心Teams用户

1. 打开Skype for Business Server控制面板"应用。
2. 在左侧导航栏中，选择"**用户"。**
3. 使用 **"** 查找"查找 (要移动到) Online 的用户Skype for Business用户。
4. Select the user (s) ， and then， from the **Action** dropdown above the list， choose **Move selected users to Skype for Business Online** or Move selected users to **Teams**. 这两个选项最初都会将用户移动到 TeamsOnly 模式，但在移动后，你可以分配另一种模式。 
5. 在向导中，单击“下一步”。
6. 如果系统提示，请Microsoft 365以 .onmicrosoft.com 结尾且具有足够权限的帐户登录。
7. 单击 **"下****一步**"，再单击"下一步"以移动用户。
8. 请注意，有关成功或失败的状态消息在主"控制面板"应用的顶部提供，而不是在向导中提供。
9. 打开Teams管理中心，然后选择左侧导航栏中的"用户"。 
10. 在 listview 中单击所需的用户。 
11. 单击 **"升级**"部分中的"编辑 **Teams升级"。**
12. 在右侧飞出中，选择所需的共存模式， **然后单击应用**。
 

## <a name="see-also"></a>另请参阅

[Move-CsUser](/powershell/module/skype/move-csuser)
