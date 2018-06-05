---
title: 在 Skype for Business 2015 中创建或修改代理组
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
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: 创建或修改代理组在响应组的 Skype 业务 Server 企业语音。
ms.openlocfilehash: 5555272fdcaa7b9a3576dc2b943eaeda064e3bb5
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568343"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business-2015"></a>在 Skype for Business 2015 中创建或修改代理组
 
创建或修改代理组在响应组的 Skype 业务 Server 企业语音。
  
创建代理组时要选择分配给该组的代理并指定其他组设置，如路由方法以及代理能否登录到组和从组注销。 
  
必须登录组和从组中，这是不同签名或从中注销 for Business 的 Skype，注销的代理称为正式代理。 正式代理必须登录到组，然后才能接收路由至该组的呼叫。 这对于以兼职形式应答组中的呼叫的代理很有用。 通过单击 Skype for Business 打开 Windows Internet Explorer Internet 浏览器并显示网页控制台中的菜单项，正式代理登录其组中注销。
  
不登录到组或从组注销的代理称为非正式代理。 非正式代理都自动登录到组中登录到 Skype for Business，和从组注销的他们不能登录时。
  
仅本地用户可成为代理。 如果代理从内部部署移到 online 时，响应组呼叫将不会被路由到的代理。
  
使用下列过程之一可创建或修改代理组。
  
> [!IMPORTANT]
> 如果将用户分配为响应组代理，需告知用户，如果用户已启用隐私模式，则需搜索“RGS Presence Watcher”联系人并将其添加到联系人列表。已启用隐私模式但未将“RGS Presence Watcher”添加到联系人列表中的代理将无法接收拨打到响应组的呼叫。未启用隐私模式的代理不受影响。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>若要使用的业务 Server Control Panel Skype 创建或修改代理组

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
    > [!NOTE]
    > 如果您是托管工作流的委派响应组管理员之一，则可创建组并在管理的工作流中使用这些组。 
  
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左侧导航栏中，单击“响应组”****，然后单击“组”****。
    
4. 在“组”**** 页上执行下列操作之一：
    
   - 要创建新的代理组，请单击“新建”****。在“选择服务”**** 搜索字段中，键入要添加组的“ApplicationServer”**** 服务的全部或部分名称，在服务的结果列表中单击所需的服务，然后单击“确定”****。
    
   - 要修改现有的代理组，在搜索字段中键入代理组的全部或部分名称。在结果列表中，单击您需要的组，单击“编辑”****，然后单击“显示详细信息”****。
    
5. 在“名称”**** 中，键入代理组的标识名称。
    
6. 在“说明”**** 中，键入对该组的说明。
    
7. 在“参与策略”**** 中，选择下列操作之一，从而设置组的登录行为：
    
   - 选择“非正式”**** 指定组中的代理无需登录组和从组中注销。 代理是自动登录到组中登录到 for Business 的 Skype 时。
    
   - 选择“正式”**** 指定组中的代理必须登录到组和从组中注销。 时选择此选项，单击代理中的业务问题需要打开 Internet Explorer 并显示网页控制台进行签名和从组注销的 Skype 的菜单项。
    
8. 在“警报时间(秒)”**** 中，指定将呼叫转至下一个空闲的代理之前，向某位代理响铃的秒数（默认为 20 秒）。
    
    > [!IMPORTANT]
    > 代理警报时间设置不能超出 180 秒，如果代理警报时间超过 180 秒，客户端应用程序会拒绝呼叫，因为 SIP 事务计时器达到其最长等待时间。 
  
9. 在“路由方法”**** 中，选择将呼叫路由至组中代理的方法，具体如下：
    
   - 若要将新呼叫首先交给空闲时间最长的代理 （已**空闲**或**非活动**状态时间最长的业务的 Skype 中），单击**最长空闲时间**。 
    
   - 若要将新呼叫同时路由至所有空闲的代理，请单击“并行”****。呼叫将发往第一个接受该呼叫的代理。
    
   - 若要将新呼叫轮流路由至每个代理，请单击“循环”****。 
    
   - 若要将新呼叫始终按照“代理”**** 列表中代理的排列顺序路由至代理，请单击“串行”****。 
    
   - 若要将新呼叫路由至所有代理已经商业和相同时间，而不考虑其当前状态，响应组应用程序登录到 Skype 单击**助理**。 配置为代理的用户可查看所有正在等待的呼叫，并可以按任意顺序应答等待中的呼叫。 呼叫将发往第一个接受该呼叫的代理，之后，其他代理不会再看到此呼叫。
    
10. 在“代理”**** 中，指定创建代理列表要采用的方式：
    
   - 要使用自定义的代理列表，请单击“定义自定义代理组”****，并执行下列操作之一：
    
   - 要向代理组添加用户，请单击“选择”****，然后在“选择代理”**** 搜索字段中，键入要添加到该组的用户的全部或部分名称，再单击“查找”****。在结果代理列表中，单击该用户，然后单击“确定”****。
    
   - 要从代理组中删除用户，请在代理列表中，单击要删除的用户，然后单击“删除”****。
    
   - 对于使用循环路由或串行路由的组，要更改呼叫路由至该组中代理的顺序，请在代理列表中，单击用户，然后单击向上箭头或向下箭头。 
    
   - 要将 Microsoft Exchange Server 通讯组列表用作代理组，请单击“使用现有的电子邮件通讯组列表”****，然后在“通讯组列表地址”**** 中键入该通讯组列表的电子邮件地址（例如 NetworkSupport@contoso.com）。
    
     如果使用电子邮件通讯组列表，则将受到以下约束：
    
     - 不能为代理组选择多个通讯组列表。每个组仅支持一个通讯组列表。
    
     - 如果通讯组列表包含一个或多个通讯组列表，则不会将嵌套的通讯组列表的成员添加到代理列表。
    
     - 如果选择串行路由或循环路由，则服务器会根据路由方法和通讯组列表中代理的排列顺序，将传入呼叫路由至相应的代理。
    
     - 如果通讯组列表包含已启用 Lync Server 2010 但未启用企业语音的用户，它们将作为不正常的代理添加到代理组。确保通信组列表的所有成员已为其用户帐户启用企业语音。
    
    > [!IMPORTANT]
    > 如果使用电子邮件通讯组列表，隐藏成员身份或隐藏的列表可能会变为可见响应组管理员或用户。 
  
    在下列情况中，可以看见隐藏成员身份或隐藏列表：
    
     - 如果配置了通讯组列表，以便隐藏成员身份和响应组管理员将通讯组列表分配到代理列表，用户可以呼叫要了解谁是成员的组。 
    
     - 如果配置了通讯组列表，以便其 Exchange 全球通讯簿中隐藏，响应组管理员可能能够看到通讯组列表并将其分配到代理列表中，如果响应组过程具有相应的用户的权限和权限，即使管理员没有适当的用户权限和权限。
    
11. 单击“**提交**”。
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>若要使用 Skype 的业务 Server 命令行管理程序创建或修改代理组

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 使用**New-csrgsagentgroup**创建新的代理组。 **设置 CsRgsAgentGroup**用于修改现有的代理组。 在该命令行处，运行：
    
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

[Get-csservice](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[新 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[设置 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-csrgsagentgroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)