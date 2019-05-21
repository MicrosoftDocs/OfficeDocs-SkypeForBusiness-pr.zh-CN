---
title: 在 Skype for Business 服务器中创建或修改未分配的号码范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 在 Skype for business Server 企业版中创建、修改或删除用于公告应用的未分配号码范围。 这将影响如何处理打给未分配号码的呼叫。
ms.openlocfilehash: 5b9afa463d6eaff2f6ba3ed283d11556bd95bc03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286181"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建或修改未分配的号码范围
 
在 Skype for business Server 企业版中创建、修改或删除用于公告应用的未分配号码范围。 这将影响如何处理打给未分配号码的呼叫。
  
Skype for Business 服务器使您能够说拨入的电话号码对您的组织有效, 但未分配给用户或电话。 为了处理此类呼叫，请设置未分配号码表。 可以使用表将呼叫路由到公告应用程序或 Exchange UM 服务器。
  
配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。
  
## <a name="configure-unassigned-phone-numbers"></a>配置未分配电话号码

使用以下过程之一为公告应用程序配置未分配的号码范围。
  
> [!IMPORTANT]
> 配置 "未分配的号码" 表之前, 您的系统必须已定义公告或 "Exchange 统一消息 (UM)" 自动助理设置。 
  
> [!TIP]
> 当某人呼叫未分配的号码时, Skype for Business 服务器将从上到下搜索 "未分配的号码" 表, 并使用第一个匹配区域。 因此，要在万不得已时执行的操作应指定给表中最后一个范围。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>使用 "Skype for Business 服务器" 控制面板配置未分配的电话号码

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅**Delegate Setup Permissions**。
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“语音功能”****，然后单击“未分配号码”****。
    
4. 在“未分配号码”**** 页上，执行下列操作之一：
    
   - 若要创建新的号码范围，请单击“新建”****。在“名称”**** 中，键入此号码范围的标识名称。
    
     > [!NOTE]
     > 新的未分配号码范围提交到数据库后，将无法更改该名称。 
  
   - 若要修改现有号码范围，请在搜索字段中键入号码范围的全部或部分名称。在号码范围的结果列表中，单击所需的名称，再单击“编辑”****，然后单击“显示详细信息”****。
    
5. 在第一个“号码范围”**** 字段中，键入号码范围的起始号码，在第二个“号码范围”**** 字段中，键入该范围的结束号码。
    
   - 该范围的起始号码必须小于或等于该范围的结束号码。
    
   - 如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。
    
   - 该号码必须匹配正则表达式 (电话: ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?。 这意味着该号码可能会以字符串电话开始: (如果不指定该字符串, 将自动为您添加该字符串)、加号 (+) 和数字1到9。 电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。
    
6. 在“通知服务”**** 中，执行下列操作之一： 
    
   - 单击“通知”****。
    
   - 单击“Exchange UM”****。
    
7. 如果在上一步中单击了“通知”****，则执行下列操作：
    
    a. 在 "**目标服务器的 FQDN**" 下, 单击 "**选择**", 单击运行通知应用程序的应用程序服务的服务 ID, 该应用程序将处理传入呼叫到此范围的未分配号码, 然后单击 **"确定"**。
    
    b. 在“通知”**** 中，单击要为此未分配号码范围播放的通知。
    
8. 如果在上一步中单击了“Exchange UM”****，则在“自动助理电话号码”**** 下，单击“选择”****，再单击将用于此未分配号码范围的电话号码，然后单击“确定”****。
    
9. 单击“**确定**”。
    
10. 在“未分配号码”**** 页上，确保未分配号码范围按照所需顺序排列。要更改号码范围在表中的位置，请在范围列表中单击一个或多个连续名称，然后单击向上箭头或向下箭头。
    
    > [!TIP]
    > Skype for Business 服务器从上到下搜索 "未分配的号码" 表, 并使用与未分配号码匹配的第一个区域。 如果有重叠的范围并且有一个范围指定了最后的操作，请确保将该范围置于列表底部。 
  
11. 按照希望的顺序排列未分配号码范围后，单击“全部提交”****。
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>使用 Skype for Business Server Management Shell 配置未分配的电话号码

1. 登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限 (如 "**委派设置权限**" 中所述) 进行安装的计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 使用 **New-CsUnassignedNumber** 可创建新的未分配号码范围。 使用 **Set-CsUnassignedNumber** 可修改现有未分配号码范围。
    
    > [!TIP]
    > 如果您具有重叠的范围并希望按某个特定顺序应用这些范围，请包含 Priority 参数。 优先级最高的范围将应用于呼叫。 值0表示最高优先级。
  
    在命令行中，执行下列操作之一：
    
   - 若要创建公告服务的号码范围，请运行：
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - 或者，若要创建 Exchange UM 自动助理的号码范围，请运行：
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     例如：
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     或
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     以下示例介绍如何修改现有未分配号码范围中的号码：
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>删除未分配号码范围

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>使用 Skype for Business 服务器 "控制面板" 删除未分配的号码范围

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅**Delegate Setup Permissions**。
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“语音功能”****，然后单击“未分配号码”****。
    
4. 在“未分配号码”**** 页上的搜索字段中，键入要删除的未分配号码范围的全部或部分名称。
    
5. 在号码范围的结果列表中，单击名称，再单击“编辑”****，然后单击“删除”****。
    
6. 单击“全部提交”****。
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>使用 Skype for Business Server 命令行管理程序删除未分配的号码范围

1. 登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限 (如 "**委派设置权限**" 中所述) 进行安装的计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 在命令行中键入：
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    例如：
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > 有关更多选项的详细信息, 请参阅[Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。 
  
## <a name="see-also"></a>另请参阅

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
