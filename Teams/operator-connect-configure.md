---
title: 配置运算符连接
author: cazawideh
ms.author: czawideh
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
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 详细了解如何配置操作员连接。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa31a954bb36369417f408734fa3b1622e101e69
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384160"
---
# <a name="configure-operator-connect"></a>配置运算符连接

本文介绍如何配置运算符连接。 在配置操作员连接，请务必阅读接线员连接计划，[](operator-connect-plan.md)了解先决条件和许可的信息。

## <a name="enable-an-operator"></a>启用操作员

可以在管理中心启用、编辑和删除Teams运算符。 在左侧导航窗格中，转到"语音"> **运算符"**。

启用操作员：

1. **选择运算符。** 在" **所有运算符** "选项卡中，按区域或服务筛选可用的运算符，以查找满足语音需求的合适运算符。 然后选择要启用的运算符。  

2. **选择国家/地区。** 在 **"操作员** 设置"下，选择要通过所选操作员启用的国家/地区。

3. **提供联系信息** 您的联系信息（包括您的全名和电子邮件地址）将自动与您的运营商共享。 稍后可以更改此信息。 此外，你需要提供公司大小，并且可以选择提供电话号码。 操作员将使用此信息来联系你，了解有关接线员和连接。

4. 接受数据传输通知。

5. **添加运算符。** 选择 **"添加为我的运算符"** 以保存。

## <a name="set-up-phone-numbers"></a>设置电话号码

设置电话号码的方式取决于你是为新用户设置号码，还是从 Microsoft 呼叫计划或直接路由移动现有号码。

- 如果需要获取新用户的电话号码，请参阅[获取新用户Teams号码](#acquire-numbers-for-new-teams-users)。

- 如果要将现有号码从"呼叫计划"移动到"接线员连接，请参阅将号码从"呼叫套餐"移动到"[接线员连接"](#move-numbers-from-calling-plans-to-operator-connect)。

- 如果要将现有号码从"直接路由"移动到"操作员连接，请参阅将号码从直接路由移动到操作员[连接。](#move-numbers-from-direct-routing-to-operator-connect)

### <a name="acquire-numbers-for-new-teams-users"></a>获取新用户Teams号码

若要获取新用户Teams号码，请执行以下步骤：

1. **分配电话系统许可证。** 可以从应用程序电话系统 PowerShell 为用户Microsoft 365 管理中心许可证。 有关详细信息，请参阅[将Teams许可证分配给用户](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. 将分配通过接线员获取的电话号码的用户连接 TeamsOnly 模式。 如果组织在 TeamsOnly 模式下，则所有用户都使用 TeamsOnly 模式。 若要检查此状态，Teams管理中心，转到Teams > Teams **设置**。 如果你的组织在群岛模式下，请检查特定用户是否位于 TeamsOnly 模式下。 转到" **用户** "并选择用户帐户。 在"**帐户"****选项卡** Teams"下，共存模式应设置为"TeamsOnly"。

3. **获取数字。** 转到运营商的网站订购和获取电话号码。 有关操作员网站的列表，请转到"Microsoft 365[运算符连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 需要提供租户 ID。 如果不知道租户 ID，请参阅查找租户Microsoft 365 [ID](/onedrive/find-your-office-365-tenant-id) 了解详细信息。

4. **分配数字。** 操作员完成订单后，会向租户上传号码。 可以通过在管理中心内通过语音Teams号码来 **查看号码> 电话提供商**。 从管理中心或Teams PowerShell 向用户分配号码。 有关详细信息，请参阅 [分配号码](#assign-numbers)。

> [!NOTE]
> 除了为用户 [](getting-phone-numbers-for-your-users.md)忘记电话号码外，还可以获取音频会议 (（用于会议网桥) 、自动助理和呼叫队列 (也称为服务号码) ）等服务的收费或免费电话号码。 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 例如，服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。 若要获取服务号码，请联系操作员。

### <a name="emergency-addresses"></a>紧急地址

紧急地址是一个与号码关联的静态位置。 在管理中心内创建Teams地址后，如何分配地址或稍后更改地址将取决于操作员。

若要向紧急地址分配号码，操作员将实现以下三种方案之一：

- 接线员为电话号码分配紧急地址，并允许你稍后在管理中心Teams地址。

- 接线员不会分配地址，并允许你将紧急地址分配给管理中心Teams电话号码。

- 接线员为电话号码分配紧急地址，不允许你更改紧急地址。 在这种情况下，你需要联系接线员，以更改电话号码及其分配的紧急地址。

有关紧急呼叫详细信息，请参阅 [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md) 和 [计划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>将号码从通话套餐移动到接线员连接

1. 联系接线员将号码移植到接线员连接。 请参阅[Microsoft 365"连接"目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)以查找您的运营商的网站。

2. 运营商完成移植订单后，可以取消分配用户的"呼叫计划"电话号码，并删除"呼叫计划许可证"。 然后，操作员可以将数字上传到租户。

3. 使用 连接 管理中心或 PowerShell Teams为用户分配运算符编号。 有关详细信息，请参阅 [分配号码](#assign-numbers)。

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>将数字从"直接路由"移动到"操作员连接

若要将号码从"直接路由"移动到"连接"，必须将操作员上载到租户的现有直接路由号码从分配给的用户中删除。 然后，将号码迁移到接线员连接，可以将号码重新分配给用户。 若要使用本地或连接从直接路由转移到接线员，请按照以下步骤操作：

>[!IMPORTANT]
> 电话号码在迁移期间将服务不工作，因此在开始之前，请连接接线员。

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>步骤 1 - 删除现有的直接路由号码。

删除现有直接路由号码的方式取决于是在本地还是在线分配该号码。 若要检查，请运行以下命令：
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```

如果 `OnPremLineUriManuallySet` 设置为 `False` 且`LineUri`填充了 E.164 电话号码，则电话号码已在本地分配并同步到Office 365。
    
**若要删除本地分配的直接路由号码，请** 运行以下命令：
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

删除生效所花的时间取决于配置。 若要检查本地号码是否已删除且更改已同步，请运行以下 PowerShell 命令： 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```
       
将更改同步到联机Office 365后，预期输出为： 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
 OnPremLineURIManuallySet             : True
 OnPremLineURI                        : 
LineURI                              : 
```

<br> **若要删除联机分配的现有联机直接路由号码，请** 运行以下 PowerShell 命令：


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

删除电话号码最多可能需要 10 分钟。 在极少数情况下，可能最多需要 24 小时。 若要检查本地号码是否已删除且更改已同步，请运行以下 PowerShell 命令： 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl Number
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>步骤 2 - 删除与用户关联的联机语音路由策略

取消分配号码后，通过运行以下 PowerShell 命令删除与用户关联的联机语音路由策略：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>步骤 3 - 获取电话号码

转到运营商的网站订购和获取电话号码。 若要查找操作员网站，请参阅 Microsoft 365 [运算符连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 需要提供租户 ID。 如果不知道租户 ID，请参阅查找租户Microsoft 365 [ID](/onedrive/find-your-office-365-tenant-id) 了解详细信息。

#### <a name="step-4---assign-phone-numbers"></a>步骤 4 - 分配电话号码

操作员完成订单后，会向租户上传号码。 可以通过在管理中心内通过语音Teams号码来 **查看号码> 电话提供商**。 使用 连接管理中心或 PowerShell 为Teams分配操作员编号。 有关详细信息，请参阅 [分配号码](#assign-numbers)。

### <a name="assign-numbers"></a>分配数字

若要了解如何向用户分配电话号码，请参阅为用户分配、更改 [或删除电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)。

## <a name="manage-your-operators"></a>管理操作员

在 **"我的运算符** "选项卡中，可以查看运算符及其状态，并更改所选内容：  

- 按国家/地区管理运营商服务
- 暂停操作员
- 删除运算符

> [!NOTE]
> 在从组织或国家/地区中删除接线员之前，必须删除分配给组织或国家/地区用户的所有电话号码，并联系接线员释放号码。

## <a name="release-numbers"></a>版本号

若要从管理中心Teams电话号码，请转到"电话 **"页** 并选择一个号码。

- 如果未将电话号码分配给用户，请选择"释放 **"**。

- 如果电话号码已分配给用户，则需要取消分配该号码。 选择 **"编辑**"，然后选择" **删除用户"**。 保存更改后，选择"发布 **"**。

## <a name="related-topics"></a>相关主题

- [规划Teams自动助理和呼叫队列](plan-auto-attendant-call-queue.md)
