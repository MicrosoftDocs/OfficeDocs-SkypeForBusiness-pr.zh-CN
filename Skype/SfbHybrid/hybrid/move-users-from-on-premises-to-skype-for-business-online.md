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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 了解如何将用户移动到 Skype for Business Online。
ms.openlocfilehash: 4d74cdebc5477d0204f69b64c2c05a4435212b3f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110618"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>将用户从本地迁移至 Skype for Business Online

将用户从本地移动到 Skype for Business Online 后，用户与 Skype for Business Online 交互，了解其功能。 本地存在的任何联系人都将在 Skype for Business Online 中可用，用户为将来组织的任何现有会议都将更新为 ，以便链接指向 Skype for Business Online。 如果用户启用了音频会议，则会议还将包括拨入坐标。  若要将用户从本地环境移动到 Skype for Business Online，请使用 Move-CsUser cmdlet 或 Skype for Business Server 控制面板，这两者都是本地工具。 

在移动任何用户之前，请务必查看 [将](move-users-between-on-premises-and-cloud.md#prerequisites) 用户迁移到云的先决条件。
 
## <a name="move-users-with-move-csuser"></a>使用迁移功能Move-CsUser 

Move-CsUser本地 Skype for Business 命令行管理程序 PowerShell 窗口提供。 您必须在本地环境和 Microsoft 365/Office 365 组织中具有足够的权限，如所需的管理 [凭据中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。 可以在两个环境中使用具有特权的单个帐户，或者可以使用本地凭据启动本地 Skype for Business Server 命令行管理程序窗口，并使用 参数指定具有所需 管理角色 的 `-Credential` Microsoft 365 或 Office 365 帐户的凭据。

若要使用 Move-CsUser 将用户移动到联机：

- 使用 Identity 参数指定要移动的用户。
- 使用值"sipfed.online.lync"指定 -Target 参数。 <span>com"。
- 如果您没有一个在本地和 Office 365 中具有足够权限的帐户，请使用 -credential 参数在 Office 365 中为帐户提供足够权限。
- 如果在 Office 365 中具有权限的帐户没有以".onmicrosoft"结尾。 <span>com"， then you must specify the -HostedMigrationOverrideUrl parameter， with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

以下 cmdlet 序列可用于将用户移动到 Skype for Business Online。 它假定 Microsoft 365 或 Office 365 凭据是单独的帐户，并作为输入提供给 Get-Credential 提示。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

如果管理员帐户启用了 MFA (多重身份验证) ，则不要指定 -Credential 参数。 将提示管理员输入凭据。

## <a name="move-users-with-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板移动用户 

1. 打开 Skype for Business Server 控制面板应用。
2. 在左侧导航栏中，选择"**用户"。**
3. 使用 **"** 查找"查找 (要) Skype for Business Online 的用户。
4. Select the user (s) ， and then， from the **Action** dropdown above the list， choose **Move selected users to Skype for Business Online**.
5. 在向导中，单击“下一步”。
6. 如果系统提示，使用以 .onmicrosoft.com 结尾且具有足够权限的帐户登录到 Microsoft 365 或 Office 365。
7. 单击 **"下****一步**"，再单击"下一步"以移动用户。
8. 请注意，有关成功或失败的状态消息在主"控制面板"应用的顶部提供，而不是在向导中提供。

## <a name="see-also"></a>另请参阅

[Move-CsUser](/powershell/module/skype/move-csuser)