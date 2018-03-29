---
title: 在 Skype for Business 2015 中创建或修改组内呼叫应答号码范围
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- IT_Skype16
ms.custom:
- Strat_SB_Admin
- Strat_SB_Admin
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 创建或修改组调用装货数量范围在 Skype 业务服务器企业语音。
ms.openlocfilehash: 3a717f5607764ef1d5677e7bc70368f8803fc854
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business-2015"></a>在 Skype for Business 2015 中创建或修改组内呼叫应答号码范围
 
创建或修改组调用装货数量范围在 Skype 业务服务器企业语音。
  
调用公园应用基于组调用装货。 部署组调用装货时，您必须配置呼叫公园轨道表区域的指定为呼叫分拣组电话号码的电话号码。 这些组号码是用户拨打以应答为另一个用户响铃的呼叫的号码。
  
与呼叫寄存轨道号码类似，呼叫应答组号码需要是没有为其分配用户或电话的虚拟分机号。 在哪里部署组调用拾取每个前端池可以有一个或多个调用分拣组号范围。 组号码范围在部署中必须是全局唯一的，并且必须作为 **GroupPickup** 类型分配。
  
使用下面的过程在呼叫寄存轨道表中创建或修改呼叫应答组号码范围。 
  
> [!NOTE]
> 必须使用 Skype 的业务服务器管理外壳程序来创建、 修改、 删除和查看调用公园轨道表中的组调用拾取数字范围。 不可用 Skype 业务服务器控件面板中组调用拾取数字范围。 
  
呼叫应答组号码范围必须符合以下规则：
  
- 该范围的起始号码必须小于或等于该范围的结束号码。
    
- 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。
    
- 号码范围必须是唯一的。该范围不能与其他任何范围重叠。
    
- 如果字符开头的数字范围\*或 #，范围必须是大于 100。
    
- 有效值： 必须匹配的正则表达式字符串 ([\\* | #] ?[1-9]\d{0,7}) |([1-9] \d {0,8})。 这意味着该值必须是一个任意的字符开头的字符串\*# 或数字 1 到 9 （第一个字符不能为零）。 如果第一个字符是\*或 #，下面的字符必须是一个数字 1 到 9 （不能为零）。 后面的字符可以是任意数字 0 到 9，最多七个其他字符 (例如，"#6000"、"\*92000"、"\*95551212"，和"915551212")。 如果第一个字符不是\*#，第一个字符必须为最多八个字符后, 跟一个数字 1 到 9 （不能为零），或每个数字 0 到 9 （例如，"915551212"、"41212"、"300"）。
    
### <a name="to-create-or-modify-a-call-pickup-group-range"></a>创建或修改呼叫应答组范围

1. 登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或**委托安装程序权限**中所述的必要的用户权限的安装位置的计算机上。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 使用**New CsCallParkOrbit**创建新呼叫分拣组电话号码的范围。 **一组 CsCallParkOrbit**用于修改现有范围的拾取呼叫电话号码。
    
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
    > 仅在你最初指定了错误的类型并且组范围尚未使用时，才能使用此 cmdlet 更改分配到号码范围的类型。 如果你将号码范围从 CallPark 更改为 GroupPickup 或相反，并且号码范围已在使用中，则呼叫寄存或组内呼叫应答将不再对该号码范围起作用。 例如，如果更改数量范围从 CallPark 到 GroupPick，调用公园应用程序可以不再使用轨道式公园调用该范围。 
  
## <a name="see-also"></a>另请参阅

#### 

[新 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[一组 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[删除调用公园轨道范围](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

