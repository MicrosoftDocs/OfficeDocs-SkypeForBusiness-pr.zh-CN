---
title: 配置 Operator Connect
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
description: 详细了解如何配置 Operator Connect。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4f4ec3d1d7cf39402da562e5939d794ac9f1624
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947574"
---
# <a name="configure-operator-connect"></a>配置 Operator Connect

>[!NOTE]
>Operator Connect 目前仅在公共预览 **版中可用**。 公共预览版允许测试即将推出的功能并提供反馈。 公共预览版中包含的功能可能不完整、可能发生更改，在 Office 365 政府云中不受支持。

本文介绍如何配置 Operator Connect。 配置 Operator Connect 之前，请务必阅读 [Operator Connect](operator-connect-plan.md) 计划，了解先决条件和许可信息。

## <a name="enable-an-operator"></a>启用操作员

可以在 Teams 管理中心启用、编辑和删除操作员。 在左侧导航窗格中，转到"语音">**运算符"。**

启用操作员：

1. **选择运算符。** 在" **所有运算符** "选项卡中，按区域或服务筛选可用的运算符，以查找满足语音需求的合适运算符。 然后选择要启用的运算符。  

2. **选择国家/地区。** 在 **"操作员设置**"下，选择要通过所选操作员启用的国家/地区。

3. **提供联系信息 (可选) 。** 如果希望操作员联系你有关 Operator Connect 的其他信息，请选中该框并提供联系信息。  

4. **接受数据传输通知。**

5. **添加运算符。** 选择 **"添加为我的运算符"** 以保存。

## <a name="set-up-phone-numbers"></a>设置电话号码

设置电话号码的方式取决于你是为新用户设置号码，还是从 Microsoft 呼叫计划或直接路由移动现有号码。

- 如果需要获取新用户的电话号码，请参阅 [获取新 Teams 用户的电话号码](#acquire-numbers-for-new-teams-users)。

- 如果要将现有号码从"呼叫计划"移动到"接线员连接"，请参阅将号码从"呼叫计划"[移动到"接线员连接"。](#move-numbers-from-calling-plans-to-operator-connect)

- 如果要将现有号码从直接路由移动到 Operator Connect，请参阅将号码[从直接路由移动到 Operator Connect。](#move-numbers-from-direct-routing-to-operator-connect)

>[!IMPORTANT]
>**紧急地址：** 与紧急地址关联的电话号码由接线员管理。 在 Teams 管理中心创建紧急地址后，接线员将电话号码分配给这些紧急地址。 若要更改紧急地址及其分配的电话号码，请联系接线员。

### <a name="acquire-numbers-for-new-teams-users"></a>获取新 Teams 用户的数字

若要获取新 Teams 用户的数字，请执行以下步骤：

1. **分配电话系统许可证。** 可以从 Microsoft 365 管理中心或 PowerShell 向用户分配电话系统许可证。 有关详细信息，请参阅 [向用户分配 Teams 附加许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. **确保你已进入"仅 Teams"模式。** 若要检查组织是否仅在 Teams 模式下，请在 Teams 管理中心转到"组织范围的设置"，> **Teams 升级"。** 若要检查用户是否仅位于 Teams 模式，请转到" **用户"并选择** 用户帐户。 在" **帐户"** 选项卡的 **"Teams** 升级"下，验证共存模式是否设置为"仅 Teams"。

3. **创建和验证紧急地址。** 在 Teams 管理中心，转到"位置 **">"紧急地址** "以设置紧急地址。 有关详细信息，请参阅为组织添加、更改或删除 [紧急位置](add-change-remove-emergency-location-organization.md)。

4. **获取数字。** 转到接线员的网站以订购和获取电话号码。 有关运算符网站的列表，请参阅 [运算符](#operators)。 需要提供租户 ID。 如果不知道租户 ID，请参阅查找 Microsoft [365 租户 ID](/onedrive/find-your-office-365-tenant-id) 了解详细信息。

5. **分配数字。** 操作员完成订单后，会向租户上传号码。 可以通过在 Teams 管理中心中通过"语音"或"电话号码"> **提供商**。 使用 Teams 管理中心或 PowerShell 向用户分配号码。 有关详细信息，请参阅 [分配数字](#assign-numbers)。
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>将号码从呼叫计划移动到 Operator Connect

1. 联系接线员将号码移植到 Operator Connect。 请参阅 [运算符](#operators) 以查找操作员的网站。

2. 运营商完成移植订单后，可以取消分配用户的"呼叫计划"电话号码，并删除"呼叫计划许可证"。 然后，操作员可以将数字上传到租户。

3. 使用 Teams 管理中心或 PowerShell 向用户分配接线员连接号码。 有关详细信息，请参阅 [分配数字](#assign-numbers)。

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>将号码从直接路由移动到 Operator Connect

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

3. 转到接线员的网站以订购和获取电话号码。 有关运算符网站的列表，请参阅 [运算符](#operators)。 需要提供租户 ID。 如果不知道租户 ID，请参阅查找 Microsoft [365 租户 ID](/onedrive/find-your-office-365-tenant-id) 了解详细信息。

4. 操作员完成订单后，会向租户上传号码。 可以通过在 Teams 管理中心中通过"语音"或"电话号码"> **提供商**。 使用 Teams 管理中心或 PowerShell 向用户分配接线员连接号码。 有关详细信息，请参阅 [分配数字](#assign-numbers)。

   

### <a name="assign-numbers"></a>分配数字

无论是添加新的 Teams 用户还是将现有用户移动到 Operator Connect，分配号码的步骤如下所示：

若要使用 Teams 管理中心分配号码，请转到"**电话号码"。** 步骤与为呼叫计划分配号码相同。 有关详细信息，请参阅 [向用户分配电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)。

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
