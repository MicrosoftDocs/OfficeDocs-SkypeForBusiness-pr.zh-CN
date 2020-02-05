---
title: 在 Skype for Business 中创建或修改组呼叫装货号码范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 在 Skype for Business Server Enterprise Voice 中创建或修改组呼叫装货号码范围。
ms.openlocfilehash: 98fc59f12165e6299fafc5ed79797e6d25d151e3
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767875"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>在 Skype for Business 中创建或修改组呼叫装货号码范围

在 Skype for Business Server Enterprise Voice 中创建或修改组呼叫装货号码范围。

组呼叫分拣基于呼叫寄存应用程序。 当您部署组呼叫时，您必须配置 "呼叫驻留" 轨道表，其中包含指定为 "呼叫装货组号码" 的电话号码范围。 这些组号码是用户拨打以应答为另一个用户响铃的呼叫的号码。

与呼叫寄存轨道号码类似，呼叫应答组号码需要是没有为其分配用户或电话的虚拟分机号。 你在其中部署组呼叫装货的每个前端池都可以具有一个或多个呼叫装货组编号范围。 组号码范围在部署中必须是全局唯一的，并且必须作为 **GroupPickup** 类型分配。

使用下面的过程在呼叫寄存轨道表中创建或修改呼叫应答组号码范围。

> [!NOTE]
> 您必须使用 Skype for Business 服务器管理外壳程序来创建、修改、删除和查看 "呼叫驻留" 轨道表中的组呼叫装货号码范围。 组呼叫装货号码范围在 Skype for Business 服务器控制面板中不可用。

呼叫应答组号码范围必须符合以下规则：

- 该范围的起始号码必须小于或等于该范围的结束号码。

- 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。

- 号码范围必须是唯一的。该范围不能与其他任何范围重叠。

- 如果数字范围以字符\*或 # 开头，则范围必须大于100。

- 有效值：必须匹配正则表达式字符串（[\\* | #]？ [1-9] \d{0,7}） |（[1-9] \d{0,8}）。 这意味着该值必须是以字符\*或 # 或数字1到9开头的字符串（第一个字符不能为零）。 如果第一个字符是\*或 #，则以下字符必须是1到9的数字（不能为零）。 后续字符可以是0到9的任何数字，最多可有7个附加字符（例如，"\*#6000"、"\*92000"、"95551212" 和 "915551212"）。 如果第一个字符不\*是或 #，则第一个字符必须是数字1到9（不能为零），后跟八个字符，每个字符都是数字0到9（例如，"915551212"、"41212"、"300"）。

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>创建或修改呼叫应答组范围

1. 登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限（如 "**委派设置权限**" 中所述）进行安装的计算机。

2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

3. 使用 **New-CsCallParkOrbit** 创建呼叫应答组号码的新范围。 使用 **Set-CsCallParkOrbit** 修改呼叫应答号码的现有范围。

    在命令行中运行：

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    例如：

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    下面的示例演示如何将号码范围从呼叫寄存轨道更改为呼叫应答组。

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > 仅在你最初指定了错误的类型并且组范围尚未使用时，才能使用此 cmdlet 更改分配到号码范围的类型。 如果你将号码范围从 CallPark 更改为 GroupPickup 或相反，并且号码范围已在使用中，则呼叫寄存或组内呼叫应答将不再对该号码范围起作用。 例如，如果将数字范围从 CallPark 更改为 GroupPick，则调用寄存应用程序无法再将该范围的轨道式转到寄存通话。

## <a name="see-also"></a>另请参阅

[新-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[删除呼叫寄存的轨道范围](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
