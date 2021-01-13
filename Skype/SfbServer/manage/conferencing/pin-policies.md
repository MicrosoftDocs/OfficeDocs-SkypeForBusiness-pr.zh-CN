---
title: 在 Skype for Business Server 中管理电话拨入式会议 PIN 策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 摘要：了解如何在 Skype for Business Server 中管理电话拨入式会议 PIN 策略。
ms.openlocfilehash: 6544586071f1107537232a117de196dfbffeb4aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827948"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>在 Skype for Business Server 中管理电话拨入式会议 PIN 策略
 
**摘要：** 了解如何在 Skype for Business Server 中管理电话拨入式会议 PIN 策略。
  
组织中具有 Active Directory 域服务 (AD DS) 凭据的 Skype for Business Server 用户可以使用个人标识号 (PIN) 以经过身份验证的用户身份加入电话拨入式会议。 PIN 策略定义电话拨入式会议 PIN 工作方式的规则。
  
 如果要在整个组织中使用相同的 PIN 策略，则可以使用全局 PIN 策略并根据需要对其进行修改。 全局 PIN 策略在林级别定义电话拨入式会议 PIN 的规则。 可以修改全局 PIN 策略，但无法将其删除。
  
如果要将特定策略应用于某个站点或某个用户组，可以创建新的 PIN 策略。
  
PIN 策略既可以应用于少数用户，也可以应用于众多用户。 如果为用户分配用户级别的 PIN 策略，则优先应用这些设置。 如果没有分配用户策略，则将应用站点级别的 PIN 策略（如果存在）。 如果未应用用户策略或站点策略，则全局 PIN 策略会提供默认设置。
  
## <a name="view-information-about-pin-policies"></a>查看有关 PIN 策略的信息

可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序查看有关 PIN 策略的信息。
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板查看有关 PIN 策略的信息

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”，然后单击“PIN 策略”。
    
4. 在 **"PIN 策略**"页上，单击要查看的 PIN 策略，单击"编辑"，然后单击"**显示详细信息"。**
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序查看有关 PIN 策略的信息

若要查看有关 PIN 策略的信息，请使用 **Get-CsPinPolicy** cmdlet。 例如，以下命令返回有关 Identity 为 site：Redmond 的单个 PIN 策略的信息：
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

有关详细信息，包括完整的语法说明和参数列表，请参阅 [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)。
  
## <a name="modify-the-global-pin-policy"></a>修改全局 PIN 策略

可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序修改全局 PIN 策略。
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板修改全局电话拨入式会议 PIN 策略

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”，然后单击“PIN 策略”。
    
4. 在“PIN 策略”页上，单击“全局”策略，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在“编辑 PIN 策略”的“最小 PIN 长度”中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。
    
6. 为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。
    
7. 如果选中了“指定最大登录尝试数”复选框，请在“最大登录尝试次数”中键入或选择希望允许的最大登录尝试次数。
    
8. 要使 PIN 过期，请选中“启用 PIN 有效期”复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。
    
9. 如果选中了“启用 PIN 有效期”复选框，请在“PIN 有效期(天)”中键入或选择 PIN 保持有效的天数。
    
10. 在“PIN 历史记录计数”中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。
    
11. 要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。
    
    > [!IMPORTANT]
    > 出于安全考虑，Microsoft 建议你不允许使用通用模式。 
  
12. 单击“提交”。
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序修改全局电话拨入式会议 PIN 策略

若要修改全局电话拨入式会议 PIN 策略，请使用 **Set-CsPinPolicy** cmdlet。
  
以下命令更改配置为在组织使用的所有 PIN 策略的 MinPasswordLength 的值。 为执行此操作，该命令首先调用不带任何参数的 **Get-CsPinPolicy** cmdlet 以检索所有现有 PIN 策略的集合。 然后，将集合通过管道通过管道到 **Set-CsPinPolicy** cmdlet，该 cmdlet 将修改集合中每个策略的 MinPasswordLength 属性值：
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

有关详细信息，包括完整的语法说明和参数列表，请参阅 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="create-a-user-or-site-pin-policy"></a>创建用户或站点 PIN 策略

可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序创建用户或站点 PIN 策略。
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板创建用户或站点 PIN 策略

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”，然后单击“PIN 策略”。
    
4. 在“PIN 策略”页上，单击“新建”，然后执行下列操作之一：
    
   - 要创建用户级别的策略，请单击“用户策略”。在“新建 PIN 策略”的“名称”中，键入描述该策略的名称。
    
   - 要创建站点级别的策略，请单击“站点策略”。在“选择站点”搜索字段中，键入要为其创建策略的站点的全部或部分名称。在站点列表中，单击所需的站点，然后单击“确定”。
    
5. 在“说明”字段中，键入 PIN 策略的说明。
    
6. 在“最小 PIN 长度”字段中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。
    
7. 为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。
    
8. 如果选中了“指定最大登录尝试数”复选框，请在“最大登录尝试次数”中键入或选择希望允许的最大登录尝试次数。
    
9. 要使 PIN 过期，请选中“启用 PIN 有效期”复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。
    
10. 如果选中了“启用 PIN 有效期”复选框，请在“PIN 有效期(天)”中键入或选择 PIN 保持有效的天数。
    
11. 在“PIN 历史记录计数”中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。
    
12. 要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。
    
    > [!IMPORTANT]
    > 出于安全考虑，Microsoft 建议你不允许使用通用模式。 
  
13. 单击“提交”。
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序创建用户或站点 PIN 策略

若要创建用户或站点 PIN 策略，请使用 **New-CsPinPolicy** cmdlet。
  
以下命令创建 Identity 为 site：Redmond 的新 PIN 策略。 此命令仅包含一个可选参数 MinPasswordLength，它用于将 MinPasswordLength 属性设置为 7。 其余所有策略属性都将使用默认值进行配置。
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 有关详细信息，包括完整的语法说明和参数列表，请参阅 [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)。
  
## <a name="modify-a-user-or-site-pin-policy"></a>修改用户或站点 PIN 策略

可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序修改用户或站点 PIN 策略。
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板修改用户或站点 PIN 策略

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”，然后单击“PIN 策略”。
    
4. 在“PIN 策略”页上，单击要更改的 PIN 策略，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在“编辑 PIN 策略”中，修改任意策略设置（不能修改的策略名称除外）。
    
6. 单击“提交”。
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序修改用户或站点 PIN 策略

若要修改电话拨入式会议 PIN 策略，请使用 **Set-CsPinPolicy** cmdlet。
  
以下命令修改分配给 Redmond 站点的 PIN 策略。 在这种情况下，该命令将 MinPasswordLength 属性的值更改为 10;这意味着新 PIN 必须至少包含 10 个数字：
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

有关详细信息，包括完整的语法说明和参数列表，请参阅 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="delete-a-user-or-site-pin-policy"></a>删除用户或站点 PIN 策略

可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序删除用户或站点 PIN 策略。
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板删除用户或站点 PIN 策略

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”，然后单击“PIN 策略”。
    
4. 在 **"PIN 策略**"页上，单击要更改的 PIN 策略，单击"编辑"，然后单击"**删除"。**
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序删除用户或站点 PIN 策略

若要删除用户或站点 PIN 策略，请使用 **Remove-CsPinPolicy** cmdlet。
  
以下命令删除在站点范围配置的所有 PIN 策略。 为此，请使用 **Get-CsPinPolicy** cmdlet 和 Filter 参数返回 Identity 以字符"site："开头的所有策略的集合。 然后，通过管道将此集合通过管道到 **Remove-CsPinPolicy** cmdlet，该 cmdlet 将删除集合中的每个策略：
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

有关详细信息，包括完整的语法说明和参数列表，请参阅 [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)。
  

