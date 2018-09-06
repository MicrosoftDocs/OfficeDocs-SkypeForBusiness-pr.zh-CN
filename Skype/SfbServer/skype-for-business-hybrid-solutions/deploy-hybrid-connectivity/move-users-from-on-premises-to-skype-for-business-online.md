---
title: 将用户从本地迁移至 Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 摘要： 了解如何迁移用户设置和业务 online 将用户移至 Skype。
ms.openlocfilehash: 0731a5307523e875d2f58ca33ecfcfbd62b0c768
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250537"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>将用户从本地迁移至 Skype for Business Online

**摘要：** 了解如何迁移用户设置和业务 online 将用户移至 Skype。

在实际将用户迁移到 Office 365 时，必须首先确认用户帐户已同步到云并为他们分配许可证。为此，请使用 Office 365 管理中心。

### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>确认本地用户帐户是否已与 Office 365 同步

1. 使用租户管理帐户，打开您的租户的[Office 365 管理中心](https://portal.office.com/)。  租户管理员帐户应被授予业务管理员角色和用户管理角色 （或全局管理员角色） 来执行此功能在 Office 365 中的两个 Skype

2. 在左侧导航窗格中，单击“**用户**”，然后单击“**活动用户**”。

3. 单击“**搜索用户**”，然后键入用户的名称。

4. 确认您看到用户，并且其状态为“**已与 Active Directory 同步**”。

    如果用户尚未同步，则应在三小时内执行下一次自动同步。 你还可以更早地强制同步。 有关详细信息，请参阅[强制目录同步](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx)。

若要分配 Office 365 中的许可证，请参阅[将企业的 Office 365 的许可证分配](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)。

## <a name="migrate-user-settings-to-skype-for-business-online"></a>为业务 Online 将用户设置迁移至 Skype

在开始迁移到 Skype 业务 online 的用户之前，应备份与要移动的帐户关联的用户数据。 并非所有用户数据都会与用户帐户一并移动。 信息，请参阅[备份和还原要求： 数据](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx)。

用户设置随用户帐户一起移动。一些本地设置不随用户帐户一起移动。

## <a name="move-pilot-users-to-skype-for-business-online"></a>将试点用户移至 Skype 业务 online

为业务 Online 将用户移至 Skype 之前，可能要移动的一些试点用户，以确认已正确配置您的环境。 然后，你可以在尝试移动其他用户之前验证功能和服务是否按预期运行。

若要将内部部署用户移动到您的业务 Online 租户的 Skype 中 Skype, 的业务 Server Management Shell，使用 Microsoft Office 365 租户管理员凭据运行以下 cmdlet。 使用要移动的用户的信息替换“username@contoso.com”。

```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds
```

## <a name="move-users-to-skype-for-business-online"></a>将用户迁移至 Skype for Business Online

您可以通过使用[Get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 移动多个用户使用-Filter 参数与特定属性分配给的用户帐户，如 RegistrarPool 选择的用户。 您可以通过管道给[Move-csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet，返回的用户，如下面的示例中所示。

```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds
```

此外可以使用-OU 参数检索指定的 OU 中的所有用户在下面的示例所示。

```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds
```

## <a name="verify-online-user-settings-and-features"></a>验证 Online 用户设置和功能

可通过以下方式验证用户是否已成功移动：

- 在 Skype for Business Online 控制面板中查看用户的状态。用于本地用户和联机用户的可视指示器不同。

- 运行以下 cmdlet：

  ```
  Get-CsUser -Identity
  ```