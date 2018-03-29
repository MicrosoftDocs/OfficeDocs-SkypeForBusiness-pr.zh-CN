---
title: 在 Skype for Business 2015 中创建或修改代理组
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: 创建或修改在响应组的业务服务器企业语音的 Skype 代理组。
ms.openlocfilehash: 441b6fb738ba6489c046990b32b27f16c7fb41b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business-2015"></a>在 Skype for Business 2015 中创建或修改代理组
 
创建或修改在响应组的业务服务器企业语音的 Skype 代理组。
  
创建代理组时要选择分配给该组的代理并指定其他组设置，如路由方法以及代理能否登录到组和从组注销。 
  
必须对内部和外部的组中，这是不同于登录或从 Skype 业务，代理将调用正式代理。 正式代理必须登录到组，然后才能接收路由至该组的呼叫。 这对于以兼职形式应答组中的呼叫的代理很有用。 正式代理签名和他们组通过单击 Skype 为企业打开 Windows Internet Explorer Internet 浏览器并显示网页控制台中的菜单项。
  
代理用户或从组中不签署被称为非正式的代理。 非正式的代理自动登录到组时登录 Skype 的业务，并不能退出组。
  
仅本地用户可成为代理。 如果代理从内部移动到在线，响应组调用不会将路由到该代理。
  
使用下列过程之一可创建或修改代理组。
  
> [!IMPORTANT]
> 如果将用户分配为响应组代理，需告知用户，如果用户已启用隐私模式，则需搜索“RGS Presence Watcher”联系人并将其添加到联系人列表。已启用隐私模式但未将“RGS Presence Watcher”添加到联系人列表中的代理将无法接收拨打到响应组的呼叫。未启用隐私模式的代理不受影响。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>若要使用 Skype 业务服务器的控制面板来创建或修改代理组

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
    > [!NOTE]
    > 如果您是托管工作流的委派响应组管理员之一，则可创建组并在管理的工作流中使用这些组。 
  
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左侧导航栏中，单击“响应组”****，然后单击“组”****。
    
4. 在“组”****页上执行下列操作之一：
    
   - 要创建新的代理组，请单击“新建”****。在“选择服务”****搜索字段中，键入要添加组的“ApplicationServer”****服务的全部或部分名称，在服务的结果列表中单击所需的服务，然后单击“确定”****。
    
   - 要修改现有的代理组，在搜索字段中键入代理组的全部或部分名称。在结果列表中，单击您需要的组，单击“编辑”****，然后单击“显示详细信息”****。
    
5. 在“名称”****中，键入代理组的标识名称。
    
6. 在“说明”****中，键入对该组的说明。
    
7. 在“参与策略”****中，选择下列操作之一，从而设置组的登录行为：
    
   - 选择“非正式”****指定组中的代理无需登录组和从组中注销。 代理自动登录到组时登录 Skype 业务。
    
   - 选择“正式”****指定组中的代理必须登录到组和从组中注销。 当选中此选项时，代理将单击 Skype 为企业打开 Internet Explorer 并显示为传入和传出组签名的网页控制台中的菜单项。
    
8. 在“警报时间(秒)”****中，指定将呼叫转至下一个空闲的代理之前，向某位代理响铃的秒数（默认为 20 秒）。
    
    > [!IMPORTANT]
    > 代理警报时间设置不能超出 180 秒，如果代理警报时间超过 180 秒，客户端应用程序会拒绝呼叫，因为 SIP 事务计时器达到其最长等待时间。 
  
9. 在“路由方法”****中，选择将呼叫路由至组中代理的方法，具体如下：
    
   - 发送给代理已空闲时间最长的第一次提供一个新呼叫 （已存在**可用**或**停用**在业务时间最长的 Skype），请单击**最长空闲**。 
    
   - 若要将新呼叫同时路由至所有空闲的代理，请单击“并行”****。呼叫将发往第一个接受该呼叫的代理。
    
   - 若要将新呼叫轮流路由至每个代理，请单击“循环”****。 
    
   - 若要将新呼叫始终按照“代理”****列表中代理的排列顺序路由至代理，请单击“串行”****。 
    
   - 单击**助理**提供新业务和在同一时间，而不考虑其当前状态的响应组应用登录到 Skype 的所有代理调用。 配置为代理的用户可查看所有正在等待的呼叫，并可以按任意顺序应答等待中的呼叫。 呼叫将发往第一个接受该呼叫的代理，之后，其他代理不会再看到此呼叫。
    
10. 在“代理”****中，指定创建代理列表要采用的方式：
    
   - 要使用自定义的代理列表，请单击“定义自定义代理组”****，并执行下列操作之一：
    
   - 要向代理组添加用户，请单击“选择”****，然后在“选择代理”****搜索字段中，键入要添加到该组的用户的全部或部分名称，再单击“查找”****。在结果代理列表中，单击该用户，然后单击“确定”****。
    
   - 要从代理组中删除用户，请在代理列表中，单击要删除的用户，然后单击“删除”****。
    
   - 对于使用循环路由或串行路由的组，要更改呼叫路由至该组中代理的顺序，请在代理列表中，单击用户，然后单击向上箭头或向下箭头。 
    
   - 要将 Microsoft Exchange Server 通讯组列表用作代理组，请单击“使用现有的电子邮件通讯组列表”****，然后在“通讯组列表地址”****中键入该通讯组列表的电子邮件地址（例如 NetworkSupport@contoso.com）。
    
     如果使用电子邮件通讯组列表，则将受到以下约束：
    
     - 不能为代理组选择多个通讯组列表。每个组仅支持一个通讯组列表。
    
     - 如果通讯组列表包含一个或多个通讯组列表，则不会将嵌套的通讯组列表的成员添加到代理列表。
    
     - 如果选择串行路由或循环路由，则服务器会根据路由方法和通讯组列表中代理的排列顺序，将传入呼叫路由至相应的代理。
    
     - 如果通讯组列表包含已启用 Lync Server 2010 但未启用企业语音的用户，它们将作为不正常的代理添加到代理组。确保通信组列表的所有成员已为其用户帐户启用企业语音。
    
    > [!IMPORTANT]
    > 如果您使用电子邮件通讯组列表，则可能会隐藏成员身份或隐藏的列表可见于响应组管理员或用户。 
  
    在下列情况中，可以看见隐藏成员身份或隐藏列表：
    
     - 如果通讯组列表进行配置，以便隐藏成员身份并响应组管理员将通讯组列表分配给代理列表，用户可以调用要找出谁是成员的组。 
    
     - 如果通讯组列表进行配置，以便在 Exchange 全球通讯簿中隐藏，响应组管理员可能能够分发列表并将其分配给代理列表中，如果响应组过程具有适当的用户权限，请参阅和权限，即使管理员不具有适当的用户权限和权限。
    
11. 单击“**提交**”。
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>若要使用 Skype 的业务服务器管理外壳程序创建或修改代理组

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 使用**New CsRgsAgentGroup**来创建新的代理组。 使用**一组 CsRgsAgentGroup**修改现有代理组。 在该命令行处，运行：
    
   ```
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    例如：
    
   ```
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
 
   ```

    > [!IMPORTANT]
    > 代理警报时间设置不能超出 180 秒，如果代理警报时间超过 180 秒，客户端应用程序会拒绝呼叫，因为 SIP 事务计时器达到其最长等待时间。 
  
4. 确认是否已创建代理组。运行：
    
   ```
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>另请参阅

#### 

[获得 CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[新 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[一组 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[获得 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)

