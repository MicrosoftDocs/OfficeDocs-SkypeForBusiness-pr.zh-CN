---
title: 从云到本地移动用户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 了解如何移动用户从 Skype 业务 online 到本地。
ms.openlocfilehash: fadb3a485cac691a97f0786aea78000b6b48c344
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247621"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>从云到本地移动用户 

如果需要您可以向后移动以前迁移从本地到云 （无论业务联机或团队仅使用 Skype） 的用户在本地。 要将用户从业务联机或 TeamsOnly 模式任一 Skype 移到内部部署的 Skype 业务服务器，用于 Move-csuser cmdlet 或 Skype 业务 Server Control Panel，二者是内部部署工具。 在将用户移回内部部署到，必须确定哪个池移动到用户。

> [!Important]
> 如果用户是以前在 TeamsOnly 模式下，并且您将 Skype 比早期版本与 CU8 业务服务器 2015年，然后您还必须删除 TeamsOnly 模式的分配的 TeamsUpgradePolicy 为该用户。 本地用户不能有模式 = TeamsOnly。  Skype 业务服务器的后续版本自动删除此工作分配。 有关详细信息，请参阅[授予 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)。

## <a name="prerequisites"></a>先决条件

- 组织必须具有正确的 Azure AD 连接，并且同步的用户的所有相关属性[配置 Azure AD 连接](configure-azure-ad-connect.md)中所述。
- 正在从 online 回至本地移动用户必须已经存在内部部署 Active Directory 中。
- 必须配置为业务混合的 Skype，[业务混合配置 Skype](configure-federation-with-skype-for-business-online.md)中所述。

## <a name="moving-users-back-to-on-premises"></a>移动用户后在本地

一旦您移动用户从云回内部部署：

- 用户与您为其功能的业务服务器部署的 Skype 交互。 
- 业务 online Skype 中存在的任何联系人都将迁移回 Skype 业务服务器。 目前，团队中的联系人不会迁移回本地。
- 如果用户还使用团队，不会与 Skype 业务用户的互操作的功能，也不能将他们能够与联盟组织中的用户进行通信。
- Skype 中的业务联机会议是*不*回自动迁移在本地。 用户应之一重新其会议或者，如果需要，使用[会议迁移工具](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。

### <a name="move-users-with-move-csuser"></a>具有 Move-csuser 移动用户

可从业务管理命令行管理程序 PowerShell 窗口本地 Skype Move-csuser。 您必须具有足够的权限，在内部部署环境以及 Office 365 租户，[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 您可以使用一个帐户的具有权限在这两个环境中，也可以开始业务 Server 命令行管理程序窗口内部 Skype 与内部部署凭据，并使用`-Credential`参数指定的 Office 365 的凭据与所需的 Office 365 管理角色的帐户。

若要将用户移动本地使用 Move-csuser:

- 指定的用户将使用 Identity 参数。
- 指定将承载用户的所需的本地池的完全限定的域名-目标参数。
- 如果两上部署和 Office 365 中没有足够的权限与一个帐户，使用-credential 参数，以提供足够的权限，在 Office 365 中使用的帐户。
- 如果 Office 365 中的权限的帐户不是以"on.microsoft.com"结尾，则必须用正确的值指定-HostedMigrationOverrideUrl 参数，[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。

以下 cmdlet 序列可用于将用户移至 Skype，对于业务服务器，并假定的 Office 365 凭据是单独的帐户，并提供作为 Get-credential 提示输入。

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>具有业务 Server Control Panel Skype 移动用户

1. 打开业务服务器控件 Skype 面板应用程序。
2. 在左侧导航窗格中，选择**用户**。
3. 使用**查找**来查找您想要将移回本地用户。
4. 选择的用户，，然后从列表上方的**操作**下拉列表中选择**移动到内部部署的所选的用户**。
5. 在向导中，选择的用户池的承载用户和单击**下一步**。
6. 如果出现提示，登录到 Office 365 帐户以。 onmicrosoft.com 和具有足够的权限。
7. 单击**下一步**，然后**下**一次将用户移动。
8. 请注意，顶部的主要控制面板中的应用程序，不向导提供了有关成功或失败状态邮件。

### <a name="removing-teamsonly-mode"></a>删除 TeamsOnly 模式

如果您正在使用版本早于 Skype 与 CU8 业务 2015年和用户移回到本地 TeamsOnly 模式中，则必须删除 UpgradeToTeams 实例`TeamsUpgradePolicy`本地移动用户之前。 您可以明确授予具有不同的模式的策略，或只需在删除现有的策略分配的用户 （只要租户的全局策略不 UpgradeToTeams） 使用全局策略。

若要删除的 TeamsUpgradePolicy 的用户的工作分配，请从业务 Online PowerShell 窗口 Skype 运行以下 cmdlet:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

此外，分配的 TeamsUpgradePolicy 另一个实例，它没有模式 = TeamsOnly，您可以为 cmdlet 中的 PolicyName 参数的值指定所需的实例的名称。 若要查看可用的 TeamsUpgradePolicy 实例的列表，请运行 Get CsTeamsUpgradePolicy。


## <a name="see-also"></a>另请参阅

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)