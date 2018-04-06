---
title: 将用户从本地迁移至 Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 摘要： 了解如何迁移用户设置并进入用户 Skype 的在线业务。
ms.openlocfilehash: 352798c217cb7495134cb32996db783f7e498ded
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>将用户从本地迁移至 Skype for Business Online
 
**摘要：**了解如何迁移用户设置并进入用户 Skype 的在线业务。
  
在实际将用户迁移到 Office 365 时，必须首先确认用户帐户已同步到云并为他们分配许可证。为此，请使用 Office 365 管理中心。
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>确认本地用户帐户是否已与 Office 365 同步

1. 为您的租户使用租户管理帐户，打开[Office 365 管理中心](https://portal.office.com/)。  租户管理员帐户应被授予两个 Skype 业务管理员角色和用户管理角色 （或全局管理员角色） 在 Office 365 中执行此功能
    
2. 在左侧导航窗格中，单击“**用户**”，然后单击“**活动用户**”。
    
3. 单击“**搜索用户**”，然后键入用户的名称。
    
4. 确认您看到用户，并且其状态为“**已与 Active Directory 同步**”。
    
    如果用户尚未同步，则应在三小时内执行下一次自动同步。 你还可以更早地强制同步。 有关详细信息，请参阅[强制目录同步](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx)。
    
若要指定 Office 365 中的许可，请参阅[分配业务的 Office 365 的许可证](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)。
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a>对于在线业务迁移到 Skype 的用户设置

在开始的在线业务迁移到 Skype 的用户之前，您应该备份与要移动的帐户关联的用户数据。 并非所有用户数据都会与用户帐户一并移动。 有关信息，请参阅[备份和还原要求： 数据](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx)。
  
用户设置随用户帐户一起移动。一些本地设置不随用户帐户一起移动。
  
## <a name="move-pilot-users-to-skype-for-business-online"></a>进入试生产用户 Skype 的在线业务

转向用户 Skype 的在线业务之前，您可能需要移动几个试用的用户，以确认正确配置您的环境。 然后，你可以在尝试移动其他用户之前验证功能和服务是否按预期运行。
  
要移动到您的在线业务的租户的 Skype 的内部用户，运行以下 cmdlet 在 Skype 业务管理程序，对 Microsoft Office 365 租户使用管理员凭据。 使用要移动的用户的信息替换“username@contoso.com”。
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a>将用户迁移至 Skype for Business Online

您可以通过使用[Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 移动多个用户使用-筛选器参数选择的用户与特定属性分配给用户帐户，如 RegistrarPool。 下面的示例中所示，您可以通过管道[移动 CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet，返回的用户。
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

此外可以使用 OU 参数来检索所有用户在指定的 OU 中，如下面的示例中所示。
  
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


