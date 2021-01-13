---
title: 在 Skype for Business Server 中创建或修改未分配号码范围
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 在 Skype for Business Server 企业语音 创建、修改或删除通知应用程序的未分配号码企业语音。 这会影响如何处理对未分配号码的呼叫。
ms.openlocfilehash: 180db35a5ea7c2c55dcdbbdcb3be70f868149d88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837082"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>在 Skype for Business Server 中创建或修改未分配号码范围
 
在 Skype for Business Server 企业语音 创建、修改或删除通知应用程序的未分配号码企业语音。 这会影响如何处理对未分配号码的呼叫。
  
Skype for Business Server 使你可以说出对对贵组织有效但不分配给用户或电话的电话号码的传入呼叫会发生什么情况。 若要处理此类呼叫，请设置未分配号码表。 可以使用该表将呼叫路由到通知应用程序或 Exchange UM 服务器。
  
配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。
  
## <a name="configure-unassigned-phone-numbers"></a>配置未分配的电话号码

使用以下过程之一为通知应用程序配置未分配号码范围。
  
> [!IMPORTANT]
> 在配置未分配号码表之前，系统必须已定义通知或已 (UM) 自动助理 Exchange 统一消息。 
  
> [!TIP]
> 当有人呼叫未分配号码时，Skype for Business Server 会从上到下搜索未分配号码表，并使用第一个匹配范围。 因此，要在万不得已时执行的操作应指定给表中最后一个范围。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>使用 Skype for Business Server 控制面板配置未分配的电话号码

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅 **Delegate Setup Permissions**。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。  
    
3. 在左侧导航栏中，单击“语音功能”，然后单击“未分配号码”。
    
4. 在“未分配号码”页上，执行下列操作之一：
    
   - 若要创建新的号码范围，请单击“新建”。在“名称”中，键入此号码范围的标识名称。
    
     > [!NOTE]
     > 新的未分配号码范围提交到数据库后，将无法更改该名称。 
  
   - 若要修改现有号码范围，请在搜索字段中键入号码范围的全部或部分名称。在号码范围的结果列表中，单击所需的名称，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在第一个“号码范围”字段中，键入号码范围的起始号码，在第二个“号码范围”字段中，键入该范围的结束号码。
    
   - 该范围的起始号码必须小于或等于该范围的结束号码。
    
   - 如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。
    
   - 该号码必须与 tel： (？) ？ () ？[ \+ 1-9]\d {0,17} (;ext=[1-9]\d {0,9}) ？。 这意味着该号码可能以字符串 tel： (开头，如果不指定该字符串，系统将自动为) 添加该号码、加号 (+) 以及 1 到 9 的数字。 电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。
    
6. 在 **“通知服务”** 中，执行下列操作之一： 
    
   - 单击 **“通知”**。
    
   - 单击 **“Exchange UM”**。
    
7. 如果在上一步中单击了 **“通知”**，则执行下列操作：
    
    a. 在 **“目标服务器的 FQDN”** 下，单击 **“选择”**，再单击运行通知应用程序的应用程序服务的服务 ID（该通知应用程序将处理到此未分配号码范围的传入呼叫），然后单击 **“确定”**。
    
    b. 在 **“通知”** 中，单击要为此未分配号码范围播放的通知。
    
8. 如果在上一步中单击了 **“Exchange UM”**，则在 **“自动助理电话号码”** 下，单击 **“选择”**，再单击将用于此未分配号码范围的电话号码，然后单击 **“确定”**。
    
9. 单击“确定”。
    
10. 在“未分配号码”页上，确保未分配号码范围按照所需顺序排列。要更改号码范围在表中的位置，请在范围列表中单击一个或多个连续名称，然后单击向上箭头或向下箭头。
    
    > [!TIP]
    > Skype for Business Server 从上到下搜索未分配号码表，并使用与未分配号码匹配的第一个范围。 如果有重叠的范围并且有一个范围指定了最后的操作，请确保将该范围置于列表底部。 
  
11. 按照希望的顺序排列未分配号码范围后，单击“全部提交”。
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>使用 Skype for Business Server 命令行管理程序 配置未分配的电话号码

1. 以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 的计算机 **。**
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 使用 **New-CsUnassignedNumber** 可创建新的未分配号码范围。 使用 **Set-CsUnassignedNumber** 可修改现有未分配号码范围。
    
    > [!TIP]
    > 如果您具有重叠的范围并希望按某个特定顺序应用这些范围，请包含 Priority 参数。 优先级最高的范围将应用于呼叫。 值 0 表示最高优先级。
  
    在命令行中，执行下列操作之一：
    
   - 若要创建公告服务的号码范围，请运行：
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - 或者，若要创建 Exchange UM 自动助理的号码范围，请运行：
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     例如：
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     或
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     以下示例介绍如何修改现有未分配号码范围中的号码：
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>删除未签名号码范围

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>使用 Skype for Business Server 控制面板删除未分配号码范围

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅 **Delegate Setup Permissions**。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。  
    
3. 在左侧导航栏中，单击“语音功能”，然后单击“未分配号码”。
    
4. 在“未分配号码”页上的搜索字段中，键入要删除的未分配号码范围的全部或部分名称。
    
5. 在号码范围的结果列表中，单击名称，再单击“编辑”，然后单击“删除”。
    
6. 单击“全部提交”。
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>使用 Skype for Business Server 命令行管理程序 删除未分配号码范围

1. 以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 的计算机 **。**
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 在命令行中键入：
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    例如：
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > 有关更多选项的详细信息，请参阅 [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。 
  
## <a name="see-also"></a>另请参阅

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
