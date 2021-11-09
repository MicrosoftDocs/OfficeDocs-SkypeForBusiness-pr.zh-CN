---
title: Create or modify a Group Call Pickup number range in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Create or modify a Group Call Pickup number range in Skype for Business Server 企业语音.
ms.openlocfilehash: 5bf69f06078d45cd12e7f21cffd03ea40028a543
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859599"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Create or modify a Group Call Pickup number range in Skype for Business

Create or modify a Group Call Pickup number range in Skype for Business Server 企业语音.

组内呼叫接听基于呼叫管理应用程序。 部署组内呼叫分拣时，必须使用指定为呼叫接听组号码的电话号码范围来配置呼叫安排通道表。 这些组号码是用户为接听为其他用户响铃的呼叫而拨打的号码。

与呼叫管理通道号码一样，呼叫接听组号码需要是未为其分配用户或电话的虚拟分机。 部署组内呼叫接听的每个前端池可以有一个或多个呼叫接听组号码范围。 组号码范围在部署中必须全局唯一，并且必须分配为 **GroupPickup** 类型。

使用以下过程可创建或修改呼叫管理通道表中的呼叫接听组号码范围。

> [!NOTE]
> 必须使用命令行Skype for Business Server来创建、修改、删除和查看呼叫管理程序通道表中的组内呼叫接听号码范围。 "控制面板"中未提供Skype for Business Server呼叫接听号码范围。

呼叫接听组号码范围必须符合以下规则：

- 该范围的起始号码必须小于或等于该范围的结束号码。

- 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。

- 号码范围必须是唯一的。该范围不能与其他任何范围重叠。

- 如果号码范围以字符或 #开头，则范围 \* 必须大于 100。

- 有效值：必须与正则表达式字符串匹配 ([ \\ *|#]？[1-9]\d {0,7}) | ([1-9]\d {0,8}) 。 这意味着该值必须是以字符或 # 开头的字符串，或以 1 到 9 (第一个字符不能为 \* 零) 。 如果第一个字符是 或 #，则下面的字符必须是 1 到 \* 9 (不能是零) 。 后续字符可以是 0 到 9 之间的任意数字，最多附加七个字符 (例如 \* ，"#6000"、"92000"、"95551212"和 \* "915551212") 。 如果第一个字符不是 或 #，则第一个字符必须是 1 到 9 个数字 (不能为零) ，后跟最多八个字符，每个字符从 0 到 9 (例如 \* ，"915551212"、"41212"、"300") 。

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>创建或修改呼叫接听组范围

1. 以 RTCUniversalServerAdmins 组的成员或所需的用户权限（如D delegate **Setup Permissions** 中所述）登录到安装了命令行管理程序Skype for Business Server的计算机。

2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

3. 使用 **New-CsCallParkOrbit** 创建呼叫接听组号码的新范围。 使用 **Set-CsCallParkOrbit** 修改呼叫接听号码的现有范围。

    在命令行中运行：

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    例如：

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    以下示例演示如何将号码范围从呼叫呼叫轨道更改为呼叫接听组。

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > 只有在最初指定的类型不正确且组范围尚未使用时，使用此 cmdlet 才能更改分配给号码范围的类型。 如果将号码范围从 CallPark 更改为 GroupPickup，反之亦然，并且该号码范围已在使用中，则呼叫等待或组内呼叫接听将停止处理该号码范围。 例如，如果您将号码范围从 CallPark 更改为 GroupPick，则呼叫等待应用程序不能再使用该通道范围来呼叫。

## <a name="see-also"></a>另请参阅

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[删除呼叫寄存通道范围](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)