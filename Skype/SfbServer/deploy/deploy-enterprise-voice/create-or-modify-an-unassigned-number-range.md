---
title: 在 Skype for Business Server 2015 中创建或修改未分配号码范围
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 创建、 修改或删除为 Skype 业务服务器企业语音的发布应用程序未指定数字的范围。 这将影响如何处理打给未分配号码的呼叫。
ms.openlocfilehash: e4a62072eeffd1cfe8d1cb81fceeb4e52cc68199
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建或修改未分配号码范围
 
创建、 修改或删除为 Skype 业务服务器企业语音的发布应用程序未指定数字的范围。 这将影响如何处理打给未分配号码的呼叫。
  
Skype 业务服务器可以说为适用于您的组织，但未指派给一个用户或一部电话的电话号码的来电会发生什么情况。 为了处理此类呼叫，请设置未分配号码表。 该表用于将呼叫路由到发布应用程序或 Exchange UM 服务器。
  
配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。
  
## <a name="configure-unassigned-phone-numbers"></a>配置未分配电话号码

使用以下过程之一来配置发布应用程序未指定数字的范围。
  
> [!IMPORTANT]
> 您的系统配置未指定编号的表之前，必须已经定义的通知有两种： 或者 Exchange 统一消息 (UM) 自动助理设置。 
  
> [!TIP]
> 当有人呼叫未分配的号码时，Skype 业务服务器的搜索从上到下的未分配数字表，并使用第一个匹配的范围。 因此，要在万不得已时执行的操作应指定给表中最后一个范围。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>若要使用 Skype 业务服务器控制面板配置未指定的电话号码

1. 作为 RTCUniversalServerAdmins 组的成员身份或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员登录到该计算机。 有关详细信息，请参阅**代理安装程序权限**。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左侧导航栏中，单击“语音功能”****，然后单击“未分配号码”****。
    
4. 在“未分配号码”****页上，执行下列操作之一：
    
   - 若要创建新的号码范围，请单击“新建”****。在“名称”****中，键入此号码范围的标识名称。
    
    > [!NOTE]
    > 新的未分配号码范围提交到数据库后，将无法更改该名称。 
  
   - 若要修改现有号码范围，请在搜索字段中键入号码范围的全部或部分名称。在号码范围的结果列表中，单击所需的名称，再单击“编辑”****，然后单击“显示详细信息”****。
    
5. 在第一个“号码范围”****字段中，键入号码范围的起始号码，在第二个“号码范围”****字段中，键入该范围的结束号码。
    
   - 该范围的起始号码必须小于或等于该范围的结束号码。
    
   - 如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。
    
   - 数量必须匹配的正则表达式 (tel:) ? (\+) ? [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ?。 这意味着数可能开始与字符串 tel: （如果不指定该字符串，它将会自动为您添加），加号 （+） 和数字 1 到 9。 电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。
    
6. 在“通知服务”****中，执行下列操作之一： 
    
   - 单击“通知”****。
    
   - 单击“Exchange UM”****。
    
7. 如果在上一步中单击了“通知”****，则执行下列操作：
    
    a. 在**目标服务器的 FQDN**，单击**选择**下，单击运行发布应用程序将处理传入呼叫到未分配的编号，该范围，然后单击**确定**应用程序服务的服务 ID。
    
    b. 在“通知”****中，单击要为此未分配号码范围播放的通知。
    
8. 如果在上一步中单击了“Exchange UM”****，则在“自动助理电话号码”****下，单击“选择”****，再单击将用于此未分配号码范围的电话号码，然后单击“确定”****。
    
9. 单击“**确定**”。
    
10. 在“未分配号码”****页上，确保未分配号码范围按照所需顺序排列。要更改号码范围在表中的位置，请在范围列表中单击一个或多个连续名称，然后单击向上箭头或向下箭头。
    
    > [!TIP]
    > Skype 业务服务器从顶部到底部未分配数字表中搜索，并使用未赋值的号相匹配的第一个范围。 如果有重叠的范围并且有一个范围指定了最后的操作，请确保将该范围置于列表底部。 
  
11. 按照希望的顺序排列未分配号码范围后，单击“全部提交”****。
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>若要使用 Skype 业务服务器管理外壳的配置未指定的电话号码

1. 登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或**委托安装程序权限**中所述的必要的用户权限的安装位置的计算机上。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 使用**New CsUnassignedNumber**创建一个新的未分配编号范围。 使用**一组 CsUnassignedNumber**修改现有未分配编号范围。
    
    > [!TIP]
    > 如果您具有重叠的范围并希望按某个特定顺序应用这些范围，请包含 Priority 参数。优先级最高的范围将应用于呼叫。 
  
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

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>若要使用 Skype 业务服务器控件面板中删除未分配的编号范围

1.  作为 RTCUniversalServerAdmins 组的成员身份或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员登录到该计算机。 有关详细信息，请参阅**代理安装程序权限**。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左侧导航栏中，单击“语音功能”****，然后单击“未分配号码”****。
    
4. 在“未分配号码”****页上的搜索字段中，键入要删除的未分配号码范围的全部或部分名称。
    
5. 在号码范围的结果列表中，单击名称，再单击“编辑”****，然后单击“删除”****。
    
6. 单击“全部提交”****。
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>若要使用 Skype 的业务服务器管理外壳程序若要删除未分配的编号范围

1. 登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或**委托安装程序权限**中所述的必要的用户权限的安装位置的计算机上。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 在命令行中键入：
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    例如：
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > 有关更多选项的详细信息，请参阅[删除 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。 
  
## <a name="see-also"></a>另请参阅

#### 

[新 CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[一组 CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[获得 CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)

