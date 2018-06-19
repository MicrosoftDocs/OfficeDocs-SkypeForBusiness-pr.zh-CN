---
title: 在 Skype for Business 2015 中创建或修改组内呼叫应答号码范围
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 创建或修改业务 Server 企业语音中 Skype 的组呼叫分拣号码范围。
ms.openlocfilehash: b0fd219fb415439712d73e0c5dad22ba3f92b4fa
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500833"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business-2015"></a>在 Skype for Business 2015 中创建或修改组内呼叫应答号码范围
 
创建或修改业务 Server 企业语音中 Skype 的组呼叫分拣号码范围。
  
组呼叫分拣基于呼叫寄存应用程序。 当您部署组呼叫分拣时，必须使用范围指定为呼叫分拣组电话号码的电话号码的配置呼叫寄存通道表。 这些组号码是用户拨打以应答为另一个用户响铃的呼叫的号码。
  
与呼叫寄存轨道号码类似，呼叫应答组号码需要是没有为其分配用户或电话的虚拟分机号。 在部署组呼叫分拣每个前端池可以有一个或多个呼叫分拣组号码范围。 组号码范围在部署中必须是全局唯一的，并且必须作为 **GroupPickup** 类型分配。
  
使用下面的过程在呼叫寄存轨道表中创建或修改呼叫应答组号码范围。 
  
> [!NOTE]
> 您必须使用 Skype 的业务 Server 命令行管理程序创建、 修改、 删除和查看呼叫寄存通道表中的组呼叫分拣号码范围。 组呼叫分拣号码范围中的业务 Server Control Panel Skype 不可。 
  
呼叫应答组号码范围必须符合以下规则：
  
- 该范围的起始号码必须小于或等于该范围的结束号码。
    
- 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。
    
- 号码范围必须是唯一的。该范围不能与其他任何范围重叠。
    
- 如果号码范围以字符开头\*或 #，该范围必须大于 100。
    
- 有效值： 必须匹配的正则表达式的字符串 ([\\* | #] ? [1-9] \d{0,7}) |([1-9] \d{0,8})。 这意味着的值必须是字符开头的字符串\*或 # 或数字 1 至 9 （的第一个字符不能为零）。 如果第一个字符是\*或 #，以下字符必须是数字 1 至 9 （不能为零）。 后续字符可以是任何数字 0 到 9 最多七个其他字符 (例如，"#6000"、"\*92000"，"\*95551212" 和"915551212")。 如果第一个字符不是\*或 #、 第一个字符必须是数字 1 至 9 （不能为零），最多八个字符后, 跟每个数字 0 到 9 （例如，"915551212"、"41212"、"300"）。
    
### <a name="to-create-or-modify-a-call-pickup-group-range"></a>创建或修改呼叫应答组范围

1. 登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 使用**New-cscallparkorbit**创建新的呼叫分拣组号码范围。 **设置 CsCallParkOrbit**用于修改现有的呼叫分拣号码范围。
    
    在该命令行处，运行：
    
   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    例如：
    
   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    下面的示例演示如何将号码范围从呼叫寄存轨道更改为呼叫应答组。
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > 仅在你最初指定了错误的类型并且组范围尚未使用时，才能使用此 cmdlet 更改分配到号码范围的类型。 如果你将号码范围从 CallPark 更改为 GroupPickup 或相反，并且号码范围已在使用中，则呼叫寄存或组内呼叫应答将不再对该号码范围起作用。 例如，如果您更改从 CallPark 为 GroupPick 号码范围，则呼叫寄存应用程序不再使用呼叫寄存轨道的范围。 
  
## <a name="see-also"></a>另请参阅

[新 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[设置 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[删除呼叫寄存通道范围](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)