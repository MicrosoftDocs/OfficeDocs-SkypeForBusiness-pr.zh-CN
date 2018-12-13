---
title: 将用户从本地迁移至 Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 了解如何为业务 Online 将用户移至 Skype。
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243995"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>将用户从本地迁移至 Skype for Business Online

移动用户从内部部署到 Skype 业务 online 后，用户与交互 Skype 业务 online 其功能。 存在内部部署的任何联系人将 Skype 业务 online 中可用，并且用户组织未来的任何现有会议更新为以便链接指向 Skype 业务 online。 如果为用户启用音频会议，会议也将包括电话拨入式坐标。  将用户从内部部署环境迁移到 Skype 业务 online，用于 Move-csuser cmdlet 或 Skype 业务 Server Control Panel，二者是内部部署工具。 

任何用户之前，请确保查看[先决条件](move-users-between-on-premises-and-cloud.md#prerequisites)将用户移动到云。
 
## <a name="move-users-with-move-csuser"></a>具有 Move-csuser 移动用户 

可从业务管理命令行管理程序 PowerShell 窗口本地 Skype Move-csuser。 [所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述，您必须具有足够的权限，这两个内部部署环境中以及与 Office 365 租户。 您可以使用一个帐户的具有权限在这两个环境中，也可以开始业务 Server 命令行管理程序窗口内部 Skype 与内部部署凭据，并使用`-Credential`参数指定的 Office 365 的凭据与所需的 Office 365 管理角色的帐户。

将用户移动到 online 使用 Move-csuser:

- 指定的用户将使用 Identity 参数。
- 指定-Target 参数的值"sipfed.online.lync。<span>com"。
- 如果两上部署和 Office 365 中没有足够的权限与一个帐户，使用-credential 参数，以提供足够的权限，在 Office 365 中使用的帐户。
- 如果在 Office 365 中权限帐户不是以"on.microsoft 结尾。<span>com"，则必须指定-HostedMigrationOverrideUrl 参数，用正确的值[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。

以下 cmdlet 序列可用于将用户移至 Skype，业务 online，并假定的 Office 365 凭据是单独的帐户，并提供作为 Get-credential 提示输入。

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a>与 Skype 的业务 Server 控制面板移动用户 

1. 打开业务服务器控件 Skype 面板应用程序。
2. 在左侧导航窗格中，选择**用户**。
3. 使用**查找**来查找您想要移动到 Skype 的业务联机用户。
4. 选择的用户，，然后，从列表上方的**操作**下拉列表中选择**移动到业务 online Skype 的所选的用户**。
5. 在向导中，单击**下一步**。
6. 如果出现提示，登录到 Office 365 帐户以。 onmicrosoft.com 和具有足够的权限。
7. 单击**下一步**，然后**下**一次将用户移动。
8. 请注意，顶部的主要控制面板中的应用程序，不向导提供了有关成功或失败状态邮件。

## <a name="see-also"></a>另请参阅

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)