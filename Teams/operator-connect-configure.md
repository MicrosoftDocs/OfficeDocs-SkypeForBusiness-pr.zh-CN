---
title: 配置运营商连接
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
description: 详细了解如何配置运营商连接。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d3b56a7935f31413829c89285fc81ee70023ab4
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675764"
---
# <a name="configure-operator-connect"></a>配置运营商连接

本文介绍如何配置运营商连接。 在配置运营商连接之前，请务必阅读[运营商连接计划](operator-connect-plan.md)，了解有关先决条件和许可的信息。

## <a name="enable-an-operator"></a>启用运算符

可以在Teams管理中心启用、编辑和删除运算符。 在左侧导航窗格中，转到 **语音>运算符**。

若要启用运算符，请执行以下操作：

1. **选择运算符。** 在“ **所有运算符** ”选项卡中，按区域或服务筛选可用运算符，以查找适合语音需求的运算符。 然后选择要启用的运算符。  

2. **选择国家/地区。** 在 **“操作员”设置** 下，选择要使用所选运算符启用的国家/地区。

3. **提供联系人信息** 联系人信息（包括您的全名和电子邮件地址）将自动与您的操作员共享。 稍后可以更改此信息。 此外，还需要提供公司规模，并且可以选择提供电话号码。 操作员将使用此信息与你联系，了解有关运营商连接的更多详细信息。

4. 接受数据传输通知。

5. **添加运算符。** 选择 **“添加为我的运算符** ”进行保存。

## <a name="set-up-phone-numbers"></a>设置电话号码

如何设置电话号码取决于是为新用户设置号码，还是从 Microsoft 呼叫计划或直接路由移动现有号码。

- 如果需要获取新用户的电话号码，请参阅[新Teams用户的获取号码](#acquire-numbers-for-new-teams-users)。

- 如果要将现有号码从呼叫计划移到运营商连接，请参阅[将号码从呼叫计划移动到运营商连接](#move-numbers-from-calling-plans-to-operator-connect)。

- 如果要将现有数字从直接路由移到运营商连接，请参阅[将数字从直接路由移动到运营商连接](#move-numbers-from-direct-routing-to-operator-connect)。

### <a name="acquire-numbers-for-new-teams-users"></a>获取新Teams用户的数字

若要获取新Teams用户的数字，请执行以下步骤：

1. **分配电话系统许可证。** 可以从Microsoft 365 管理中心或使用 PowerShell 向用户分配电话系统许可证。 有关详细信息，请参阅[向用户分配Teams加载项许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. 将分配使用运营商连接获取的电话号码的用户需要处于 TeamsOnly 模式。 如果组织处于 TeamsOnly 模式，则所有用户都处于 TeamsOnly 模式。 若要检查此问题，请在Teams管理中心转到 **Teams > Teams升级设置**。 如果组织处于 Islands 模式，请检查特定用户是否处于 TeamsOnly 模式。 转到 **“用户** ”并选择用户帐户。 在 **“帐户”** 选项卡中，**在Teams升级下，** 共存模式应设置为“TeamsOnly”。

3. **获取数字。** 转到操作员的网站以订购和获取电话号码。 有关操作员网站的列表，请转到[Microsoft 365 运营商连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 需要提供租户 ID。 如果不知道租户 ID，请参阅[“查找Microsoft 365租户 ID](/onedrive/find-your-office-365-tenant-id) 以获取详细信息。

4. **分配数字。** 操作员完成订单后，会将数字上传到租户。 可以通过转到语音> 电话数字来查看Teams管理中心 **中的数字** 和提供程序。 从Teams管理中心或使用 PowerShell 向用户分配数字。 有关详细信息，请参阅 [分配数字](#assign-numbers)。

> [!NOTE]
> 除了[为用户获取电话号码](getting-phone-numbers-for-your-users.md)外，还可以为会议桥 音频会议 () 、自动助理和呼叫队列等服务获取收费或免费电话号码 (也称为服务号码) 。 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 例如，服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。 若要获取服务号码，请联系你的操作员。

### <a name="emergency-addresses"></a>紧急地址

紧急地址是与数字关联的静态位置。 在Teams管理中心创建紧急地址后，分配地址或稍后更改地址的方式将取决于操作员。

若要将号码分配到紧急地址，操作员将实现以下三种方案之一：

- 操作员将紧急地址分配给电话号码，并允许您稍后在Teams管理中心更改这些地址。

- 操作员不分配地址，并允许你将紧急地址分配给Teams管理中心的电话号码。

- 操作员将紧急地址分配给电话号码，不允许您更改这些地址。 在此方案中，需要与操作员联系，以更改电话号码及其分配的紧急地址。

有关紧急呼叫的详细信息，请参阅 [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md) 和 [计划并配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>将号码从呼叫计划移到运营商连接

1. 请联系操作员，将号码移植到运营商连接。 请参阅[Microsoft 365 运营商连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)以查找操作员的网站。

2. 操作员完成移植订单后，可以取消分配用户的呼叫计划电话号码，并删除呼叫计划许可证。 然后，操作员可以将数字上传到租户。

3. 使用Teams管理中心或使用 PowerShell 向用户分配运营商连接号码。 有关详细信息，请参阅 [分配数字](#assign-numbers)。

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>将数字从直接路由移到运营商连接

若要将数字从直接路由移到运营商连接，必须从分配给的用户中删除操作员上传到租户的现有直接路由号码。 然后，将数字迁移到运营商连接后，可以将该号码重新分配给用户。 若要使用本地或联机电话号码从直接路由移动到运营商连接，请执行以下步骤：

>[!IMPORTANT]
> 在迁移期间，电话号码将处于服务外，因此在开始之前，请与运营商连接操作员协调。

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>步骤 1 - 删除现有的直接路由编号。

删除现有直接路由号码的方式取决于该号码是分配在本地还是联机。 若要检查，请运行以下 Teams PowerShell 模块命令：
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

如果`OnPremLineUri`用 E.164 电话号码填充，则将电话号码分配到本地并同步到Office 365。
    
**若要删除在本地分配的直接路由号码，** 请运行以下 Skype for Business Server PowerShell 命令：
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

删除生效所需的时间取决于配置。 若要检查本地号码是否已删除且更改已同步，请运行以下 Teams PowerShell 模块命令： 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
更改同步到联机目录Office 365后，预期输出为： 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```

<br> **若要删除联机分配的现有联机直接路由号码，** 请运行以下 Teams PowerShell 模块命令：


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

删除电话号码可能需要长达 10 分钟的时间。 在极少数情况下，最多可能需要 24 小时。 若要检查是否删除了电话号码，请运行以下 Teams PowerShell 模块命令： 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>步骤 2 - 删除与用户关联的联机语音路由策略

取消分配号码后，请运行以下 Teams PowerShell 模块命令，删除与用户关联的联机语音路由策略：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>步骤 3 - 获取电话号码

转到操作员的网站以订购和获取电话号码。 若要查找操作员网站，请参阅[Microsoft 365 运营商连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 需要提供租户 ID。 如果不知道租户 ID，请参阅[“查找Microsoft 365租户 ID](/onedrive/find-your-office-365-tenant-id) 以获取详细信息。

#### <a name="step-4---assign-phone-numbers"></a>步骤 4 - 分配电话号码

操作员完成订单后，会将数字上传到租户。 可以通过转到语音> 电话数字来查看Teams管理中心 **中的数字** 和提供程序。 使用Teams管理中心或使用 PowerShell 向用户分配运营商连接号码。 有关详细信息，请参阅 [分配数字](#assign-numbers)。

### <a name="assign-numbers"></a>分配数字

有关如何向用户分配电话号码的信息，请参阅 [分配、更改或删除用户的电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)。

## <a name="manage-your-operators"></a>管理运算符

在“ **我的运算符** ”选项卡中，可以查看运算符及其状态，对所选内容进行以下更改：  

- 按国家/地区管理运营商服务
- 挂起运算符
- 删除运算符

> [!NOTE]
> 从组织或国家/地区删除操作员之前，必须删除分配给组织或国家/地区用户的所有电话号码，并联系运营商以释放号码。

## <a name="release-numbers"></a>发布编号

若要从Teams管理中心释放电话号码，请转到 **电话号码** 页，然后选择一个号码。

- 如果未将电话号码分配给用户，请选择 **“发布**”。

- 如果将电话号码分配给用户，则需要取消分配号码。 选择 **“编辑**”，然后 **删除用户**。 保存更改后，选择 **“发布**”。

## <a name="related-topics"></a>相关主题

- [规划Teams自动助理和呼叫队列](plan-auto-attendant-call-queue.md)
