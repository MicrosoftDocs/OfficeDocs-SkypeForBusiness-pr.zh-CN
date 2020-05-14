---
title: 将用户从云移动到本地
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
description: 了解如何将用户从 Skype for Business Online 迁移到本地。
ms.openlocfilehash: 64a5561fda35669be6ce7718c3ec037dcb8b9264
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221332"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>将用户从云移动到本地 

如果需要，您可以将以前从本地迁移的用户移动到云（无论是仅使用 Skype for Business Online 还是仅将团队）回本地。 若要将用户从 Skype for Business Online 或 TeamsOnly 模式移回 Skype for Business Server 的本地部署，请使用 Get-csuser cmdlet 或 Skype for Business Server 控制面板，这两个控制面板都是本地工具。 将用户移回本地部署时，必须决定将用户移动到哪个池。

> [!Important]
> 如果用户以前在 TeamsOnly 模式下，而您使用的是 Skype for Business Server 2015 with CU8 的早期版本，则还必须为该用户删除 TeamsUpgradePolicy 的 TeamsOnly 模式分配。 本地用户不能具有 mode = TeamsOnly。  后续版本的 Skype for Business Server 将自动删除此工作分配。 有关更多详细信息，请参阅[CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)。

## <a name="prerequisites"></a>先决条件

- 组织必须正确配置 Azure AD Connect 并同步用户的所有相关属性，如[Configure AZURE AD Connect](configure-azure-ad-connect.md)中所述。
- 从联机恢复到本地的用户必须已存在于本地 Active Directory 中。
- 必须配置 skype for Business 混合，如[配置 skype For business 混合](configure-federation-with-skype-for-business-online.md)中所述。

## <a name="moving-users-back-to-on-premises"></a>将用户移回本地

将用户从云移回本地之后：

- 用户与你的 Skype for Business Server 部署进行交互，了解其功能。 
- Skype for business Online 或团队中存在的所有联系人都将迁移到 Skype for Business Server。 两组联系人合并，然后再迁移回本地。  此外，团队中预先存在的联系人仍保留在团队中。
- 如果用户也使用团队，则他们将无法与 Skype for Business 用户进行互操作，也无法与联盟组织中的用户进行通信。
- Skype for Business Online 中的会议*不*会自动迁移回本地。 用户应重新安排其会议，如果需要，可以使用[会议迁移工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。

### <a name="move-users-with-move-csuser"></a>将用户移动到 Get-csuser

Get-csuser 可从本地 Skype for Business 命令行管理程序 PowerShell PowerShell PowerShell 窗口中获取。 在本地环境以及云服务组织（Microsoft 365 或 Office 365）中，您必须具有足够的权限，如[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 您可以使用在两个环境中具有权限的单个帐户，也可以使用本地凭据启动本地 Skype for Business Server Management Shell 窗口，并使用 `-Credential` 参数指定具有必要管理角色的 Microsoft 365 或 Office 365 帐户的凭据。

使用 Get-csuser 将用户移动到本地的步骤：

- 使用 Identity 参数指定要移动的用户。
- 使用要承载用户的所需本地池的完全限定域名指定-Target 参数。
- 如果您没有一个帐户在本地和云服务（Microsoft 365 或 Office 365）中具有足够的权限，请使用-credential 参数提供在 Microsoft 365 或 Office 365 中具有足够权限的帐户。
- 如果在 Microsoft 365 或 Office 365 中具有权限的帐户不以 "on.microsoft.com" 结尾，则必须使用[所需管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的正确值指定-HostedMigrationOverrideUrl 参数。

可以使用以下 cmdlet 序列将用户移动到 Skype for business Server，并假设 Microsoft 365 或 Office 365 凭据是一个单独的帐户并作为 Get Credential 提示的输入提供。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板移动用户

1. 打开 "Skype for Business Server 控制面板" 应用。
2. 在左侧导航栏中，选择 "**用户**"。
3. 使用 "**查找**" 查找要移回到本地的用户。
4. 选择用户，然后从列表上方的 "**操作**" 下拉列表中选择 "**将所选用户移动到本地"**。
5. 在向导中，选择将承载用户的用户池并单击 "**下一步**"。
6. 如果出现提示，请使用以 onmicrosoft.com 结尾的帐户登录 Microsoft 365 或 Office 365 并拥有足够的权限。
7. 单击 "**下一步**"，然后再单击一次以移动用户。 **Next**
8. 请注意，有关成功或失败的状态消息是在主控制面板应用程序的顶部提供的，而不是在向导中提供的。

### <a name="removing-teamsonly-mode"></a>删除 TeamsOnly 模式

如果您使用早于 Skype for Business 2015 的版本与 CU8，并且用户将在 TeamsOnly 模式下移回本地，则必须在 `TeamsUpgradePolicy` 移动本地用户之前删除 UpgradeToTeams 实例。 您可以使用其他模式显式授予策略，也可以仅删除该用户的现有策略分配以使用全局策略（前提是租户的全局策略不 UpgradeToTeams）。

若要删除用户对 TeamsUpgradePolicy 的分配，请从 Skype for Business Online PowerShell 窗口中运行以下 cmdlet：

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

或者，若要分配不具有 mode = TeamsOnly 的 TeamsUpgradePolicy 的另一个实例，可以将所需实例的名称指定为 cmdlet 中的 PolicyName 参数的值。 若要查看 TeamsUpgradePolicy 的可用实例的列表，请运行 CsTeamsUpgradePolicy。


## <a name="see-also"></a>另请参阅

[移动-Get-csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
