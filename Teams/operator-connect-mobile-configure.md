---
title: 配置 Teams Phone Mobile
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
description: 详细了解如何配置 Teams Phone Mobile。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e0e5c349610e9f8ad73b9b7a50b4c219304ea4
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551676"
---
# <a name="configure-teams-phone-mobile"></a>配置 Teams Phone Mobile

有关参与Microsoft Teams 电话移动计划以及其服务可用的国家或地区的运营商列表，请参阅 [Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/connect-mobile)。

本文介绍如何配置 Teams Phone Mobile。 在配置 Teams Phone Mobile 之前，请务必阅读 [Teams Phone Mobile 计划](operator-connect-mobile-plan.md) ，了解有关权益、先决条件和许可的信息。

## <a name="enable-an-operator"></a>启用运算符

可以在 Teams 管理中心启用、编辑和删除运算符。 在左侧导航窗格中，转到 **语音>运算符**。

若要启用运算符，请执行以下操作：

1. 选择支持 Teams Phone Mobile 的操作员。 在“ **所有操作员** ”选项卡下，按区域或服务筛选可用运算符，以找到支持 Teams Phone Mobile 的正确运算符。 然后选择要启用的运算符。

2. 在 **“操作员”设置** 下，选择要使用所选运算符启用的国家/地区。

3. **提供联系人信息。** 联系人信息（包括您的全名和电子邮件地址）将自动与您的操作员共享。 稍后可以更改此信息。 此外，还需要提供公司规模，并且可以选择提供电话号码。 操作员将使用此信息与你联系，了解有关 Teams Phone Mobile 的更多详细信息。

4. 接受数据传输通知。

5. 选择 **“添加为我的运算符** ”进行保存。

## <a name="set-up-phone-numbers"></a>设置电话号码

如果要将现有的已启用 SIM 的公司付费电话号码添加到 Teams，请联系您的运营商，确保你拥有符合条件的 Teams Phone Mobile 订阅，并且他们可以将您的号码上传到 Teams。 操作员完成订单后，可以将这些数字分配给用户。 

若要查找操作员的网站，请参阅 [Microsoft 365 Teams Phone Mobile 目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。

需要提供租户 ID。 如果不知道租户 ID，请 [参阅“查找 Microsoft 365 租户 ID](/onedrive/find-your-office-365-tenant-id.md)”。 如果你的区域和运营商支持现有桌面电话号码或有线号码，则可以将其移植到无线语音订阅。 

如何设置电话号码取决于是为新用户设置号码，还是从 Microsoft 呼叫计划、运营商连接或直接路由移动现有号码。

- [获取新 Teams 用户的数字](#acquire-numbers-for-new-teams-users)。  

- [将号码从通话套餐移动到 Teams Phone Mobile](#move-numbers-from-calling-plans-to-teams-phone-mobile)。  

- [将号码从操作员连接移动到 Teams Phone Mobile](#move-numbers-from-operator-connect-to-teams-phone-mobile)。  

- [将号码从直接路由移动到 Teams Phone Mobile](#move-numbers-from-direct-routing-to-teams-phone-mobile)。  


### <a name="assign-numbers-to-emergency-addresses"></a>将号码分配到紧急地址

紧急地址是通过 Microsoft Teams 终结点/客户端访问时与数字关联的静态位置。 在 Teams 管理中心创建紧急地址后，分配地址或稍后更改地址的方式将取决于操作员。

若要将数字分配给 Microsoft Teams 终结点正在使用的紧急地址，操作员将实现以下三种方案之一：

- 操作员将紧急地址分配给电话号码，并允许你稍后在 Teams 管理中心更改这些地址。

- 操作员不分配地址，并允许你将紧急地址分配给 Teams 管理中心的电话号码。

- 操作员将紧急地址分配给电话号码，不允许您更改这些地址。 在此方案中，需要与操作员联系，以更改电话号码及其分配的紧急地址。

当通过启用 SIM 的智能手机的本机拨号器进行呼叫时，操作员可以使用地理坐标或单元格塔处理呼叫，以接近紧急位置获取帮助。

有关紧急呼叫的详细信息，请参阅 [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md) 和 [计划并配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="acquire-numbers-for-new-teams-users"></a>获取新 Teams 用户的数字

若要获取新 Teams 用户的数字，请执行以下步骤：

1. **分配电话系统许可证和 Teams Phone Mobile 加载项许可证。** 可以从Microsoft 365 管理中心或使用 PowerShell 向用户分配电话系统许可证和 Teams Phone Mobile 加载项许可证。 有关详细信息，请参阅 [向用户分配 Teams 加载项许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. **将分配使用 Teams Phone Mobile 获取的电话号码的用户需要处于 TeamsOnly 模式。** 如果组织处于 TeamsOnly 模式，则所有用户都处于 TeamsOnly 模式。 

   若要在 Teams 管理中心进行检查，请转到 **Teams > Teams 升级设置**。 如果组织处于 Islands 模式，请检查特定用户是否处于 TeamsOnly 模式。 转到 **“用户** ”并选择用户帐户。 在 **“帐户”** 选项卡中，在 **Teams 升级下，** 共存模式应设置为 TeamsOnly。

3. **获取数字。** 转到操作员网站或联系他们，订购并获取启用了 Teams Phone Mobile 服务的已启用移动 SIM 的电话号码。 

   操作员完成订单后，会将启用 SIM 的移动号码上传到租户。 通过转到 **语音>电话号码**，可以在 Teams 管理中心查看号码和提供程序。 

4. **分配数字。** 可以从 Teams 管理中心或使用 PowerShell 向用户分配数字。 有关详细信息，请参阅 [分配数字](assign-change-or-remove-a-phone-number-for-a-user.md)。

### <a name="move-numbers-from-calling-plans-to-teams-phone-mobile"></a>将号码从通话套餐移动到 Teams Phone Mobile

1. 确保你拥有适用于 Teams Phone Mobile 和 Teams Phone Mobile 加载项许可证的符合条件的 Microsoft 365 订阅。 需要 [删除要为相应用户移动的电话号码](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user)。 

2. 请联系您的运营商，以启用 SIM 的符合条件的无线语音计划将号码移植到 Teams Phone Mobile。 

3. 操作员完成移植订单后，操作员会将数字上传到租户。  通过转到 **语音>电话号码**，可以在 Teams 管理中心查看号码和提供程序。 

4. 可以使用 Teams 管理中心或使用 PowerShell 向用户分配数字。 有关详细信息，请参阅 [分配数字](assign-change-or-remove-a-phone-number-for-a-user.md)。

### <a name="move-numbers-from-operator-connect-to-teams-phone-mobile"></a>将号码从操作员连接移动到 Teams Phone Mobile

1. 确保你拥有适用于 Teams Phone Mobile 和 Teams Phone Mobile 加载项许可证的符合条件的 Microsoft 365 订阅。 需要 [删除要为相应用户移动的电话号码](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user)。 请联系现有的 Operator Connect 提供程序，从租户中删除电话号码。

2. 请联系您的运营商，以启用 SIM 的符合条件的无线语音计划将号码移植到 Teams Phone Mobile。 

3. 操作员完成移植订单后，操作员会将数字上传到租户。 通过转到 **语音>电话号码**，可以在 Teams 管理中心查看号码和提供程序。 

4. 可以使用 Teams 管理中心或使用 PowerShell 向用户分配数字。 有关详细信息，请参阅 [分配数字](assign-change-or-remove-a-phone-number-for-a-user.md)。

### <a name="move-numbers-from-direct-routing-to-teams-phone-mobile"></a>将号码从直接路由移动到 Teams Phone Mobile   

若要将号码从直接路由移动到 Teams Phone Mobile，需要完成以下步骤：

1. [确定现有直接路由号码是联机还是本地分配](#determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises)。

2. [将号码从直接路由迁移到 Teams Phone Mobile](#migrate-the-numbers-from-direct-routing-to-teams-phone-mobile)。

2. [删除与用户关联的联机语音路由策略](#remove-the-online-voice-routing-policy-associated-with-your-user)。

3. [获取电话号码](#acquire-phone-numbers)。

4. [分配电话号码](#assign-phone-numbers)。

以下部分更详细地介绍了这些步骤。

#### <a name="determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>确定现有直接路由号码是联机还是本地分配。

删除现有直接路由号码的方式取决于该号码是分配在本地还是联机。

1. 首先，运行以下 Teams PowerShell 命令，检查是否为用户分配了直接路由号码。 NumberType 应为 DirectRouting：

   ```PowerShell
   Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
   ```

2. 通过运行以下 Teams PowerShell 命令确定数字是联机还是在本地分配：

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

   如果 OnPremLineUri 填充了 E.164 电话号码，则电话号码已在本地分配并同步到 Microsoft 365。

#### <a name="migrate-the-numbers-from-direct-routing-to-teams-phone-mobile"></a>将号码从直接路由迁移到 Teams Phone Mobile

若要迁移数字，请执行以下步骤。  

> [!Important]
> 在迁移期间，电话号码将处于服务外。 在开始迁移之前，请与 Teams Phone Mobile 操作员协调。

- **若要将在线分配的现有直接路由号码迁移到 Teams Phone Mobile**，请联系您的运营商。 若要查找操作员的网站，请参阅 [Microsoft 365 Teams Phone Mobile 目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 在约定的日期和时间，操作员会将号码从直接路由迁移到 Teams Phone Mobile。 这可能涉及从租户中删除要迁移的电话号码，并将其再次添加为与 Teams Phone Mobile 关联的新电话号码。

- **若要将本地分配的直接路由号码迁移到 Teams Phone Mobile**，请运行以下 Skype for Business Server PowerShell 命令：

   ```PowerShell
   Set-CsUser -Identity <user> -LineURI $null 
   ```
  若要检查本地号码是否已删除且更改已从本地同步到 Microsoft 365，请运行以下 Teams PowerShell 命令：

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

更改同步到 Microsoft 365 联机目录后，预期输出为：

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

若要检查是否删除了电话号码，请运行以下 Teams PowerShell 命令：

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

> [!NOTE]
> 删除生效所需的时间取决于配置。 删除电话号码可能需要长达 10 分钟，在极少数情况下，最多可能需要 24 小时。 

#### <a name="remove-the-online-voice-routing-policy-associated-with-your-user"></a>删除与用户关联的联机语音路由策略

取消分配号码后，通过运行以下 Teams PowerShell 命令删除与用户关联的联机语音路由策略：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="acquire-phone-numbers"></a>获取电话号码

请联系您的运营商，以启用 SIM 的符合条件的无线语音计划将号码移植到 Teams Phone Mobile。

操作员完成订单后，会将数字上传到租户。 通过转到 **语音>电话号码**，可以在 Teams 管理中心查看号码和提供程序。 

#### <a name="assign-phone-numbers"></a>分配电话号码

可以使用 Teams 管理中心或使用 PowerShell 向用户分配 Teams 手机号码。 有关详细信息，请参阅 [分配数字](assign-change-or-remove-a-phone-number-for-a-user.md)。


## <a name="manage-your-operators"></a>管理运算符

在“ **我的运算符** ”选项卡中，可以查看运算符及其状态，然后对所选内容进行以下更改：  

- 按国家/地区管理运营商服务
- 挂起运算符
- 删除运算符

> [!NOTE]
> 从组织或国家/地区删除操作员之前，必须删除分配给组织或国家/地区用户的所有电话号码，并联系运营商以释放号码。

## <a name="release-numbers"></a>发布编号

若要从 Teams 管理中心释放电话号码，请转到 **“电话号码** ”页，然后选择一个号码。

- 如果未将电话号码分配给用户，请选择 **“发布**”。

- 如果将电话号码分配给用户，则需要取消分配号码。 选择 **“编辑**”，然后 **删除用户**。 保存更改后，选择 **“发布**”。

## <a name="manage-user-incoming-calling-policies"></a>管理用户传入呼叫策略

可以使用 Teams 管理中心或使用 PowerShell 管理用户的传入调用策略。 默认情况下，Teams Phone Mobile 用户的传入呼叫将首先在已启用 SIM 的移动设备上拨打 Teams 应用。 

- 如果用户的传入呼叫首选项设置为 Teams 应用，则所有传入呼叫都将同时在启用 SIM 的智能手机和其他任何 Teams 终结点上拨打 Teams 应用。 

- 如果用户的传入呼叫首选项设置为本机拨号器，则所有传入呼叫都会在启用 SIM 的智能手机上拨打本机拨号器，同时在其他设备上拨打所有其他 Teams 终结点。 

### <a name="use-the-teams-admin-center"></a>使用 Teams 管理中心

若要使用 Teams 管理中心管理用户的传入调用策略，

1. 在语音选项卡下，选择 **移动策略**。 

2. 若要添加新的移动策略，请单击 **“添加**”。

3. 选择一个名称，添加策略的说明，然后从 **“选择移动拨号器** 下拉列表”选项中选择下列选项之一：

   -  **Microsoft Teams** 首先在启用 SIM 的智能手机上拨打 Teams 应用。 

   - **本机拨号器** 首先在启用 SIM 的智能手机上拨打本机拨号器。

4. 将策略分配给用户。 请参阅 [分配策略](assign-policies-users-and-groups.md)。


### <a name="use-powershell"></a>使用 PowerShell

1. 连接到租户：Connect-MicrosoftTeams。
 
2. 为传入呼叫创建策略，以便先拨打本机拨号器或 Teams 应用。  (可以选择策略名称;此示例使用 TeamsFirst 和 NativeFirst.)  

   ```PowerShell
   New-CsTeamsMobilityPolicy -identity TeamsFirst -MobileDialerPreference Teams 
   New-CsTeamsMobilityPolicy -identity NativeFirst -MobileDialerPreference Native 
   ```

3. 向用户授予策略： 

   ```PowerShell
   Grant-CsTeamsMobilityPolicy NativeFirst -Identity user@xyz.onmicrosoft.com
   Grant-CsTeamsMobilityPolicy TeamsFirst -Identity user@xyz.onmicrosoft.com
   ```

4. 检查用户策略： 

   ```PowerShell
   get-CsUserpolicyassignment -identity user@xyz.onmicrosoft.com
   ```
 
 5. 检查所有移动策略选项： 
    
    ```PowerShell
    Get-CsTeamsMobilityPolicy
    ```  

 








