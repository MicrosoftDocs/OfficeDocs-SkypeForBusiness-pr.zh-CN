---
title: 配置运算符连接
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
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
description: 详细了解如何配置运算符连接。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e82c862810448552bb9d2dc2d721815b5db43f55
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689884"
---
# <a name="configure-operator-connect"></a>配置运算符连接

>[!NOTE]
>运算符连接目前仅在公共 **预览版中可用**。 公共预览版允许测试即将推出的功能并提供反馈。 公共预览版中包含的功能可能不完整、可能发生更改，并且不受云Office 365 政府版支持。

本文介绍如何配置运算符连接。 在配置操作员连接，请务必阅读操作员计划连接，了解先决条件[](operator-connect-plan.md)和许可的信息。

## <a name="enable-an-operator"></a>启用操作员

可以在管理中心启用、编辑和删除Teams运算符。 在左侧导航窗格中，转到"语音">**运算符"。**

启用操作员：

1. **选择运算符。** 在" **所有运算符** "选项卡中，按区域或服务筛选可用的运算符，以查找满足语音需求的合适运算符。 然后选择要启用的运算符。  

2. **选择国家/地区。** 在 **"操作员设置**"下，选择要通过所选操作员启用的国家/地区。

3. **提供联系信息 (可选) 。** 如果希望操作员联系您，并提供有关接线员连接，请选中该框并提供联系信息。  

4. **接受数据传输通知。**

5. **添加运算符。** 选择 **"添加为我的运算符"** 以保存。

## <a name="set-up-phone-numbers"></a>设置电话号码

设置电话号码的方式取决于你是为新用户设置号码，还是从 Microsoft 呼叫计划或直接路由移动现有号码。

- 如果需要获取新用户的电话号码，请参阅[获取新用户Teams号码](#acquire-numbers-for-new-teams-users)。

- 如果要将现有号码从"呼叫计划"移动到"接线员连接，请参阅将号码从"呼叫套餐"移动到"接线[员连接"。](#move-numbers-from-calling-plans-to-operator-connect)

- 如果要将现有号码从"直接路由"移动到"操作员连接，请参阅将数字从"直接路由"移动到["连接"。](#move-numbers-from-direct-routing-to-operator-connect)

>[!IMPORTANT]
>**紧急地址：** 与从操作员获取的号码关联的紧急地址直接与操作员管理。 请联系接线员进行任何更改。

### <a name="acquire-numbers-for-new-teams-users"></a>获取新用户Teams号码

若要获取新用户Teams号码，请执行以下步骤：

1. **分配电话系统许可证。** 可以从管理中心电话系统 PowerShell 为用户Microsoft 365许可证。 有关详细信息，请参阅[将Teams许可证分配给用户](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. **确保你已进入 TeamsOnly 模式。** 若要检查，请在Teams中心，转到"组织范围的设置"，> Teams **升级"。** 共存模式应设置为仅Teams模式。

3. **创建和验证紧急地址。** 在Teams管理中心，转到"位置 **">"紧急地址**"以设置紧急地址。 有关详细信息，请参阅为组织添加、更改或删除 [紧急位置](add-change-remove-emergency-location-organization.md)。

4. **获取数字。** 转到接线员的网站以订购和获取电话号码。 有关运算符网站的列表，请参阅 [运算符](#operators)。 需要提供租户 ID。 如果不知道租户 ID，请参阅查找租户Microsoft 365 [ID](/onedrive/find-your-office-365-tenant-id)了解详细信息。

5. **分配数字。** 操作员完成订单后，将测试编号上传到租户。 可以通过在"语音"Teams管理中心查看号码和> 电话 **提供商**。 使用管理中心或 PowerShell Teams向用户分配号码。 有关详细信息，请参阅 [分配数字](#assign-numbers)。
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>将号码从通话套餐移动到接线员连接

1. 联系接线员将号码移植到接线员连接。 请参阅 [运算符](#operators) 以查找操作员的网站。

2. 运营商完成移植订单后，可以取消分配用户的"呼叫计划"电话号码，并删除"呼叫计划许可证"。 然后，操作员可以将数字上传到租户。

3. 使用 连接管理中心或 PowerShell 为Teams分配操作员编号。 有关详细信息，请参阅 [分配数字](#assign-numbers)。

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>将数字从"直接路由"移动到"操作员连接

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

3. 转到接线员的网站以订购和获取电话号码。 有关运算符网站的列表，请参阅 [运算符](#operators)。 需要提供租户 ID。 如果不知道租户 ID，请参阅查找租户Microsoft 365 [ID](/onedrive/find-your-office-365-tenant-id)了解详细信息。

4. 操作员完成订单后，将测试编号上传到租户。 可以通过在"语音"Teams管理中心查看号码和> 电话 **提供商**。 使用 连接管理中心或 PowerShell 为Teams分配操作员编号。 有关详细信息，请参阅 [分配数字](#assign-numbers)。

   

### <a name="assign-numbers"></a>分配数字

无论是添加新用户Teams还是将现有用户移动到接线员连接，分配号码的步骤如下：

若要使用管理中心Teams号码，请转到电话 **号码**。 步骤与为呼叫计划分配号码相同。 有关详细信息，请参阅 [向用户分配电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)。

若要使用 PowerShell 分配数字，请使用 Set-CsOnlineVoiceUser cmdlet，如下所示：

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

例如：

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

若要详细了解如何向用户分配电话号码，请参阅为用户分配、更改 [或删除电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)。



## <a name="manage-your-operators"></a>管理操作员

在"我的运算符"选项卡中，可以查看运算符及其状态，并更改所选内容：  

- 按国家/地区管理运营商服务
- 暂停操作员
- 删除运算符

> [!NOTE]
> 在从组织或国家/地区中删除接线员之前，必须删除分配给组织或国家/地区用户的所有电话号码，并联系接线员释放号码。

## <a name="operators"></a>运算符

您可以通过访问此处链接的网站，从以下运营商获取电话号码：


|接线员  |运营商网站  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
