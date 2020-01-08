---
title: 将用户从本地迁移到 Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
ms.openlocfilehash: ddf25614afae48ef647dc325e53ccbab8ac2e5d0
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963020"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>将用户从本地迁移到 Skype for Business Online

将用户从本地迁移到 Skype for business Online 后，用户将与 Skype for Business Online 进行交互，了解其功能。 在 Skype for Business Online 中将提供本地的所有联系人，并且在将来组织的任何现有会议将更新为，以便这些链接指向 Skype for Business Online。 如果用户已启用音频会议，则会议还将包括拨入坐标。  若要将用户从本地环境移动到 Skype for Business Online，请使用 Get-csuser cmdlet 或 Skype for Business Server 控制面板，这两个控制面板都是本地工具。 

在移动任何用户之前，请务必查看将用户移动到云的[先决条件](move-users-between-on-premises-and-cloud.md#prerequisites)。
 
## <a name="move-users-with-move-csuser"></a>将用户移动到 Get-csuser 

Get-csuser 可从本地 Skype for Business 命令行管理程序 PowerShell PowerShell PowerShell 窗口中获取。 在本地环境和 Office 365 租户中都必须具有足够的权限，如[所需管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 您可以使用在两个环境中具有权限的单个帐户，也可以使用本地凭据启动本地 Skype for Business Server Management Shell 窗口，并使用`-Credential`参数指定具有必要的 office 365 管理角色的 office 365 帐户的凭据。

使用 Get-csuser 将用户移动到联机状态的步骤：

- 使用 Identity 参数指定要移动的用户。
- 指定值为 "sipfed.online.lync.com>" 的-Target 参数。<span>com "。
- 如果您没有一个帐户在本地和 Office 365 中具有足够的权限，请使用-credential 参数在 Office 365 中提供具有足够权限的帐户。
- 如果在 Office 365 中具有权限的帐户不以 "on. microsoft" 结尾。<span>com "，则必须使用[所需管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的正确值指定-HostedMigrationOverrideUrl 参数。

 > [!NOTE]
 > 您必须为您的租户确定正确的 HostedMigrationOverrideUrl 值。 通过导航到旧版 Skype for Business 管理中心，可以轻松完成此操作。 确定前缀-XXXXXXX.online.lync.com 和 append/Hostedmigration/hostedmigrationservice.svc。 例如： https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc一旦您标识了值，请将其用于 $url 变量，如下所示。

可以使用以下 cmdlet 序列将用户移动到 Skype for business Online，并假定 Office 365 凭据是单独的帐户并作为 Get Credential 提示的输入提供。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

如果管理员帐户已启用 MFA （多重身份验证），请不要指定-Credential 参数。 系统将提示管理员输入凭据。

## <a name="move-users-with-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板移动用户 

1. 打开 "Skype for Business Server 控制面板" 应用。
2. 在左侧导航栏中，选择 "**用户**"。
3. 使用 "**查找**" 查找要迁移到 Skype For business Online 的用户。
4. 选择用户，然后从列表上方的 "**操作**" 下拉列表中选择 "**将所选用户移动到 Skype for business Online**"。
5. 在向导中，单击“下一步”****。
6. 如果出现提示，请使用以 onmicrosoft.com 结尾的帐户登录 Office 365 并拥有足够的权限。
7. 单击 "**下一步**"，然后再单击一次以移动用户。 ****
8. 请注意，有关成功或失败的状态消息是在主控制面板应用程序的顶部提供的，而不是在向导中提供的。

## <a name="see-also"></a>另请参阅

[移动-Get-csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
