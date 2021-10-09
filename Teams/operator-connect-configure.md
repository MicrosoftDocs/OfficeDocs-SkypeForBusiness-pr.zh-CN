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
ms.openlocfilehash: 47ed8fc4f8ca36a1d987456ff393a1b771c6fb10
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249674"
---
# <a name="configure-operator-connect"></a>配置运算符连接

本文介绍如何配置运算符连接。 在配置操作员连接，请务必阅读操作员计划连接，了解先决条件[](operator-connect-plan.md)和许可的信息。

## <a name="enable-an-operator"></a>启用操作员

可以在管理中心启用、编辑和删除Teams运算符。 在左侧导航窗格中，转到"语音">**运算符"。**

启用操作员：

1. **选择运算符。** 在" **所有运算符** "选项卡中，按区域或服务筛选可用的运算符，以查找满足语音需求的合适运算符。 然后选择要启用的运算符。  

2. **选择国家/地区。** 在 **"操作员设置**"下，选择要通过所选操作员启用的国家/地区。

3. **提供联系信息** 您的联系信息（包括您的全名和电子邮件地址）将自动与您的运营商共享。 稍后可以更改此信息。 此外，你需要提供公司大小，并且可以选择提供电话号码。 操作员将使用此信息来联系你，了解有关接线员连接。

4. 接受数据传输通知。

5. **添加运算符。** 选择 **"添加为我的运算符"** 以保存。

## <a name="set-up-phone-numbers"></a>设置电话号码

设置电话号码的方式取决于你是为新用户设置号码，还是从 Microsoft 呼叫计划或直接路由移动现有号码。

- 如果需要获取新用户的电话号码，请参阅[获取新用户Teams号码](#acquire-numbers-for-new-teams-users)。

- 如果要将现有号码从"呼叫计划"移动到"接线员连接，请参阅将号码从"呼叫套餐"移动到"接线[员连接"。](#move-numbers-from-calling-plans-to-operator-connect)

- 如果要将现有号码从"直接路由"移动到"操作员连接，请参阅将数字从"直接路由"移动到["连接"。](#move-numbers-from-direct-routing-to-operator-connect)

### <a name="acquire-numbers-for-new-teams-users"></a>获取新用户Teams号码

若要获取新用户Teams号码，请执行以下步骤：

1. **分配电话系统许可证。** 可以从应用程序电话系统 PowerShell 为用户Microsoft 365 管理中心许可证。 有关详细信息，请参阅[将Teams许可证分配给用户](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. 使用接线员许可证获得的电话号码分配连接需要位于 TeamsOnly 模式下。 如果组织在 TeamsOnly 模式下，则所有用户都使用 TeamsOnly 模式。 若要检查此状态，Teams管理中心，转到"组织范围的设置"，> Teams **升级"。** 如果你的组织在群岛模式下，请检查特定用户是否位于 TeamsOnly 模式下。 转到" **用户** "并选择用户帐户。 在"**帐户"****选项卡的Teams** 下，共存模式应设置为"TeamsOnly"。

3. **获取数字。** 转到接线员的网站以订购和获取电话号码。 有关操作员网站的列表，请转到"Microsoft 365[运算符连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 需要提供租户 ID。 如果不知道租户 ID，请参阅查找租户Microsoft 365 [ID](/onedrive/find-your-office-365-tenant-id)了解详细信息。

4. **分配数字。** 操作员完成订单后，会向租户上传号码。 可以通过在"语音"Teams管理中心查看号码和> 电话 **提供商**。 从管理中心或Teams PowerShell 向用户分配号码。 有关详细信息，请参阅 [分配号码](#assign-numbers)。

> [!NOTE]
> 除了为用户 [](getting-phone-numbers-for-your-users.md)获取电话号码外，还可以获取音频会议 (（用于会议网桥) 、自动助理和呼叫队列 (也称为服务号码) ）的收费或免费电话号码。 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 例如，服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。 若要获取服务号码，请联系操作员。

### <a name="emergency-addresses"></a>紧急地址

紧急地址是一个与号码关联的静态位置。 在管理中心内创建Teams地址后，如何分配地址或稍后更改地址将取决于操作员。

若要向紧急地址分配号码，操作员将实现以下三种方案之一：

- 接线员为电话号码分配紧急地址，并允许你稍后在管理中心Teams地址。

- 接线员不会分配地址，并允许你将紧急地址分配给管理中心内Teams电话号码。

- 接线员为电话号码分配紧急地址，不允许你更改紧急地址。 在这种情况下，你需要联系你的接线员以更改电话号码及其分配的紧急地址。

有关紧急呼叫详细信息，请参阅 [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md) 和 [计划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>将号码从"通话套餐"移动到"接线员连接

1. 联系接线员将号码移植到接线员连接。 请参阅[Microsoft 365操作员连接](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)目录以查找您的运营商的网站。

2. 运营商完成移植订单后，可以取消分配用户的"呼叫计划"电话号码，并删除"呼叫计划许可证"。 然后，操作员可以将数字上传到租户。

3. 使用 连接管理中心或 PowerShell Teams为用户分配运算符编号。 有关详细信息，请参阅 [分配号码](#assign-numbers)。

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>将号码从"直接路由"移动到"操作员连接

1. 删除用户的现有电话号码，如下所示：  

   通过运行以下 PowerShell 命令获取现有的 On-prem 行 URI：

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   通过运行以下 PowerShell 命令删除 On-prem Line URI：  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. 删除与用户关联的任何 PSTNUsage，否则呼叫将路由到 PSTN 使用中指定的网关。 若要了解如何删除 PSTN 使用情况，请参阅[Set-CsOnlinePstnUsage。](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)

3. 转到接线员的网站以订购和获取电话号码。 若要查找操作员网站，请参阅 Microsoft 365[运算符连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 需要提供租户 ID。 如果不知道租户 ID，请参阅查找租户Microsoft 365 [ID](/onedrive/find-your-office-365-tenant-id)了解详细信息。

4. 操作员完成订单后，会向租户上传号码。 可以通过在"语音"Teams管理中心查看号码和> 电话 **提供商**。 使用 连接管理中心或 PowerShell Teams为用户分配运算符编号。 有关详细信息，请参阅 [分配号码](#assign-numbers)。

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

若要从管理中心Teams电话号码，请转到"电话 **号码**"页并选择一个号码。

- 如果未将电话号码分配给用户，请选择"释放 **"。**

- 如果电话号码已分配给用户，则需要取消分配该号码。 选择 **"编辑**"，然后选择"**删除用户"。** 保存更改后，选择"发布 **"。**

## <a name="related-topics"></a>相关主题

- [规划Teams助理和呼叫队列](plan-auto-attendant-call-queue.md)
