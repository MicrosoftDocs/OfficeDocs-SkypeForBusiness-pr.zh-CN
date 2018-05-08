---
title: 在 Skype for Business 2015 中创建或修改呼叫寄存通道范围
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 创建或修改业务 Server 企业语音的呼叫寄存通道范围表 Skype 中。
ms.openlocfilehash: 805323783cee06f76ee4bf0c1c2ecdb427070a8f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business-2015"></a>在 Skype for Business 2015 中创建或修改呼叫寄存通道范围
 
创建或修改业务 Server 企业语音的呼叫寄存通道范围表 Skype 中。
  
呼叫寄存使用的呼叫寄存轨道。 用户可寄存并取回呼叫之前，您必须配置呼叫寄存通道表。 您需要指定的范围的分机号 （轨道），您的组织将保留用于寄存呼叫，并定义这些区域路由通过指定的呼叫寄存池处理每个范围。 定义通道范围时，目标是具有足够的通道，以便不会在短时间内重用任何一个通道，但又不能有太多通道，以致于不得不限制用户或其他服务可使用的分机数量。 您可以为每个 Skype 部署呼叫寄存应用程序的业务服务器池创建多个呼叫寄存轨道范围。 每个呼叫寄存通道范围必须具有一个全局唯一的名称和一组唯一的扩展。
  
> [!IMPORTANT]
> 每个通道范围包含的通道数通常不超过 100。范围可以更大一点，只要每个范围的通道数小于最大值 10,000 且每个池的通道数小于 50,000。如果范围太小，很快就会重用通道。 
  
请使用虚拟分机（未向其分配用户或电话的分机）块作为通道范围。 
  
> [!NOTE]
> 不支持将外线直拨分机 (DID) 号码分配为通道号码的呼叫寄存通道表。 
  
使用下列过程之一可创建或修改呼叫寄存通道范围。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>若要使用的业务 Server Control Panel Skype 创建或修改寄存呼叫的号码范围

1. 以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员身份登录到计算机。 有关详细信息，请参阅**Delegate Setup Permissions**。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左侧导航栏中，单击“语音功能”****，然后单击“呼叫寄存”****。
    
4. 在“呼叫寄存”**** 页上，执行下列操作之一：
    
  - 若要创建新的通道范围，请单击“新建”****。在“名称”**** 中，键入此号码范围的标识名称。
    
    > [!NOTE]
    > 在将通道范围提交到数据库后，将无法更改该名称。 
  
  - 若要修改现有通道范围，请在搜索字段中键入通道范围的全部或部分名称。在通道的结果列表中，单击所需的通道，再单击“编辑”****，然后单击“显示详细信息”****。
    
5. 在第一个“号码范围”**** 字段中，键入此呼叫寄存通道的分机范围中的起始号码，在第二个“号码范围”**** 字段中，键入该范围的结束号码。 注意：
    
   - 该范围的起始号码必须小于或等于该范围的结束号码。
    
   - 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。
    
   - 通道范围必须是唯一的。该范围不能与其他任何范围重叠。
    
   - 如果通道范围以字符开头\*或 #，该范围必须大于 100。
    
   - 有效值： 必须匹配的正则表达式的字符串 ([\\* | #] ? [1-9] \d{0,7}) |([1-9] \d{0,8})。 这意味着的值必须是字符开头的字符串\*或 # 或数字 1 至 9 （的第一个字符不能为零）。 如果第一个字符是\*或 #，以下字符必须是数字 1 至 9 （不能为零）。 后续字符可以是任何数字 0 到 9 最多七个其他字符 (例如，"#6000"、"\*92000"，"\*95551212" 和"915551212")。 如果第一个字符不是\*或 #、 第一个字符必须是数字 1 至 9 （不能为零），最多八个字符后, 跟每个数字 0 到 9 （例如，"915551212"、"41212"、"300"）。
    
   - 每个池不应包含 50,000 个以上的通道。每个通道范围包含的通道数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。
    
6. 在**目标服务器的 FQDN**中，单击的完全限定的域名 (FQDN) 或服务 ID 承载呼叫寄存应用程序的应用程序服务。 寄存在由通道范围中的起始号码和结束号码指定的范围内的号码的所有呼叫都将路由到此服务器或池。
    
7. 单击“**提交**”。
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>使用 Skype 的业务 Server 命令行管理程序创建或修改寄存呼叫的号码范围

1. 登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 使用**New-cscallparkorbit**创建新的通道号码范围。 **设置 CsCallParkOrbit**用于修改现有的通道号码范围。
    
    在该命令行处，运行：
    
   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    例如：
     
   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    以下示例说明如何修改现有通道范围中的号码。
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>另请参阅

#### 

[新 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[设置 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[删除呼叫寄存通道范围](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

