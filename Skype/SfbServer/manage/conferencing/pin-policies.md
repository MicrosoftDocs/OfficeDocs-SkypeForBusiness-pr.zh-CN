---
title: 管理 Business Server （英文） 中 Skype 电话拨入式会议 PIN 策略
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 摘要： 了解如何管理业务服务器中 Skype 电话拨入式会议 PIN 策略。
ms.openlocfilehash: 29fd3e2fff1628eaa96d7296e8fe9d7b9183d690
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197819"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>管理 Business Server （英文） 中 Skype 电话拨入式会议 PIN 策略
 
**摘要：** 了解如何管理业务服务器中 Skype 电话拨入式会议 PIN 策略。
  
Skype 的组织中拥有 Active Directory 域服务 (AD DS) 凭据的企业服务器用户可以加入电话拨入式会议作为经过身份验证的用户使用个人标识号 (PIN)。 PIN 策略定义电话拨入式会议 PIN 工作方式的规则。
  
 如果要在整个组织中使用相同的 PIN 策略，则可以使用全局 PIN 策略并根据需要对其进行修改。全局 PIN 策略在林级别定义电话拨入式会议 PIN 的规则。可以修改全局 PIN 策略，但是不能将其删除。
  
如果要将特定策略应用于某个站点或某个用户组，可以创建新的 PIN 策略。
  
PIN 策略既可以应用于少数用户，也可以应用于众多用户。 如果为用户分配用户级别的 PIN 策略，则优先应用这些设置。 如果没有分配用户策略，则将应用站点级别的 PIN 策略（如果存在）。 如果未应用用户策略或站点策略，则全局 PIN 策略会提供默认设置。
  
## <a name="view-information-about-pin-policies"></a>查看有关 PIN 策略的信息

使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以查看有关 PIN 策略的信息。
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>查看有关使用适用于业务 Server Control Panel Skype 的 PIN 策略的信息

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。
    
4. 在“**PIN 策略**”页上，单击要查看的 PIN 策略，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>查看有关使用 Skype 业务 Server Management Shell 的 PIN 策略的信息

若要查看有关 PIN 策略的信息，请使用 **Get-CsPinPolicy** cmdlet。 例如，下面的命令返回有关 Identity 为 site:Redmond 的单个 PIN 策略的信息：
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

有关详细信息，包括完整语法说明和参数的列表，，请参阅[Get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)。
  
## <a name="modify-the-global-pin-policy"></a>修改全局 PIN 策略

使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以修改全局 PIN 策略。
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 修改全局电话拨入式会议 PIN 策略

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。
    
4. 在“**PIN 策略**”页上，单击“**全局**”策略，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“编辑 PIN 策略”**** 的“最小 PIN 长度”**** 中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。
    
6. 为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”**** 复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。
    
7. 如果选中了“指定最大登录尝试数”**** 复选框，请在“最大登录尝试次数”**** 中键入或选择希望允许的最大登录尝试次数。
    
8. 要使 PIN 过期，请选中“启用 PIN 有效期”**** 复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。
    
9. 如果选中了“启用 PIN 有效期”**** 复选框，请在“PIN 有效期(天)”**** 中键入或选择 PIN 保持有效的天数。
    
10. 在“PIN 历史记录计数”**** 中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。
    
11. 要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”**** 复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。
    
    > [!IMPORTANT]
    > 出于安全原因，Microsoft 建议你不要允许使用通用模式。 
  
12. 单击“**提交**”。
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序修改全局电话拨入式会议 PIN 策略

若要修改全局电话拨入式会议 PIN 策略，可使用 **Set-CsPinPolicy** cmdlet。
  
下面的命令更改配置为在组织中使用的所有 PIN 策略的 MinPasswordLength 的值。为执行此操作，该命令首先调用不带任何参数的 **Get-CsPinPolicy** cmdlet 以检索所有现有 PIN 策略的集合。然后，将此集合通过管道传递到 **Set-CsPinPolicy cmdlet**，后者将修改集合中每个策略的 MinPasswordLength 属性的值：
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

有关详细信息，包括完整语法说明和参数的列表，，请参阅[Set-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="create-a-user-or-site-pin-policy"></a>创建用户或站点 PIN 策略

使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以创建的用户或站点 PIN 策略。
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 创建的用户或站点 PIN 策略

1. 从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。
    
4. 在“PIN 策略”**** 页上，单击“新建”****，然后执行下列操作之一：
    
   - 要创建用户级别的策略，请单击“用户策略”****。在“新建 PIN 策略”**** 的“名称”**** 中，键入描述该策略的名称。
    
   - 若要创建站点级别的策略，请单击“**站点策略**”。在“**选择站点**”搜索字段中，键入要为其创建策略的站点的全部或部分名称。在站点列表中，单击所需的站点，然后单击“**确定**”。
    
5. 在“说明”**** 字段中，键入 PIN 策略的说明。
    
6. 在“最小 PIN 长度”**** 字段中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。
    
7. 为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”**** 复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。
    
8. 如果选中了“指定最大登录尝试数”**** 复选框，请在“最大登录尝试次数”**** 中键入或选择希望允许的最大登录尝试次数。
    
9. 要使 PIN 过期，请选中“启用 PIN 有效期”**** 复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。
    
10. 如果选中了“启用 PIN 有效期”**** 复选框，请在“PIN 有效期(天)”**** 中键入或选择 PIN 保持有效的天数。
    
11. 在“PIN 历史记录计数”**** 中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。
    
12. 要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”**** 复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。
    
    > [!IMPORTANT]
    > 出于安全原因，Microsoft 建议你不要允许使用通用模式。 
  
13. 单击“**提交**”。
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序创建的用户或站点 PIN 策略

若要创建用户或站点 PIN 策略，可使用 **New-CsPinPolicy** cmdlet。
  
下面的命令创建 Identity 为 site:Redmond 的新 PIN 策略。此命令只包含一个可选参数 MinPasswordLength，该参数用于将 MinPasswordLength 属性设置为 7。其余所有策略属性都将配置为使用默认值。
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 有关详细信息，包括完整语法说明和参数的列表，，请参阅[新建 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)。
  
## <a name="modify-a-user-or-site-pin-policy"></a>修改用户或站点 PIN 策略

使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，可以修改用户或站点 PIN 策略。
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 修改的用户或站点 PIN 策略

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。
    
4. 在“**PIN 策略**”页上，单击要更改的 PIN 策略，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑 PIN 策略**”中，修改任意策略设置（不能修改的策略名称除外）。
    
6. 单击“**提交**”。
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序修改的用户或站点 PIN 策略

若要修改电话拨入式会议 PIN 策略，可使用 **Set-CsPinPolicy** cmdlet。
  
下面的命令修改分配给 Redmond 站点的 PIN 策略。在此示例中，此命令将 MinPasswordLength 属性的值更改为 10，这意味着新的 PIN 必须至少包含 10 位数字：
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

有关详细信息，包括完整语法说明和参数的列表，，请参阅[Set-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="delete-a-user-or-site-pin-policy"></a>删除用户或站点 PIN 策略

使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以删除用户或站点 PIN 策略。
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 中删除用户或站点 PIN 策略

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。
    
4. 在“**PIN 策略**”页上，单击要更改的 PIN 策略，再单击“**编辑**”，然后单击“**删除**”。
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序中删除用户或站点 PIN 策略

若要删除用户或站点 PIN 策略，可使用 **Remove-CsPinPolicy** cmdlet。
  
下面的命令将删除已在站点范围配置的所有 PIN 策略。为此，应使用带 Filter 参数的 **Get-CsPinPolicy** cmdlet 返回 Identity 以字符“site:”开头的所有策略的集合。然后将此集合通过管道传递到 **Remove-CsPinPolicy** cmdlet，后者会删除集合中的每一项：
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

有关详细信息，包括完整语法说明和参数的列表，，请参阅[Remove-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)。
  

