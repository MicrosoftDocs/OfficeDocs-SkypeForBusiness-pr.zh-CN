---
title: Lync Server 2013：创建或修改代理组
TOCTitle: 创建或修改代理组
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205370(v=OCS.15)
ms:contentKeyID: 49314703
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或修改代理组

 

_**上一次修改主题：** 2014-02-07_

使用下列过程之一可创建或修改代理组。

> [!NOTE]  
> 例如，作为 CsVoiceAdministrator 的管理员，必须为用户启用企业语音和 Lync Server，然后才能将这些用户分配到代理组。如果您是托管工作流的委派响应组管理员之一，则将能够创建代理组并您管理的工作流中使用这些代理组。



> [!IMPORTANT]
> 如果将用户分配为响应组代理，需告知用户，如果用户已启用隐私模式，则需搜索“RGS Presence Watcher”联系人并将其添加到联系人列表。已启用隐私模式但未将“RGS Presence Watcher”添加到联系人列表中的代理将无法接收拨打到响应组的呼叫。未启用隐私模式的代理不受影响。


## 使用 Lync Server 控制面板创建或修改代理组

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
    > [!NOTE]  
    > 如果您是托管工作流的委派响应组管理员之一，则可创建组并在管理的工作流中使用这些组。
    


2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“响应组”，然后单击“组”。

4.  在“组”页上执行下列操作之一：
    
      - 要创建新的代理组，请单击“新建”。在“选择服务”搜索字段中，键入要添加组的“ApplicationServer”服务的全部或部分名称，在服务的结果列表中单击所需的服务，然后单击“确定”。
    
      - 要修改现有的代理组，在搜索字段中键入代理组的全部或部分名称。在结果列表中，单击您需要的组，单击“编辑”，然后单击“显示详细信息”。

5.  在“名称”中，键入代理组的标识名称。

6.  在“说明”中，键入对该组的说明。

7.  在“参与策略”中，选择下列操作之一，从而设置组的登录行为：
    
      - 选择“非正式”指定组中的代理无需登录组和从组中注销。代理登录 Lync Server 2013 后，将自动登录到组。
    
      - 选择“正式”指定组中的代理必须登录到组和从组中注销。选择此选项后，当代理单击 Lync 中的菜单项时，会打开 Internet Explorer 并显示登录到组和从组中注销的网页控制台。

8.  在“警报时间(秒)”中，指定将呼叫转至下一个空闲的代理之前，向某位代理响铃的秒数（默认为 20 秒）。
    
    > [!IMPORTANT]
    > 代理警报时间设置不能超出 180 秒，如果代理警报时间超过 180 秒，客户端应用程序会拒绝呼叫，因为 SIP 事务计时器达到其最长等待时间。


9.  在“路由方法”中，选择将呼叫路由至组中代理的方法，具体如下：
    
      - 若要将新呼叫首先路由至空闲时间最长的代理（在 Lync Server 中，处于“空闲”或“非活动”状态时间最长），请单击“最长空闲时间”。
    
      - 若要将新呼叫同时路由至所有空闲的代理，请单击“并行”。呼叫将发往第一个接受该呼叫的代理。
    
      - 若要将新呼叫轮流路由至每个代理，请单击“循环”。
    
      - 若要将新呼叫始终按照“代理”列表中代理的排列顺序路由至代理，请单击“串行”。
    
      - 要将新呼叫同时提供至登录到 Lync Server 2013 和响应组应用程序的所有代理（无论其当前状态如何），请单击“助理”。配置为代理的 Lync 2010 Attendant 用户可查看所有正在等待的呼叫，并可以按任意顺序应答等待中的呼叫。呼叫将发往第一个接受该呼叫的代理，之后，其他 Lync 2010 Attendant 用户不会再看到此呼叫。

10. 在“代理”中，指定创建代理列表要采用的方式：
    
      - 要使用自定义的代理列表，请单击“定义自定义代理组”，并执行下列操作之一：
        
          - 要向代理组添加用户，请单击“选择”，然后在“选择代理”搜索字段中，键入要添加到该组的用户的全部或部分名称，再单击“查找”。在结果代理列表中，单击该用户，然后单击“确定”。
        
          - 要从代理组中删除用户，请在代理列表中，单击要删除的用户，然后单击“删除”。
        
          - 对于使用循环路由或串行路由的组，要更改呼叫路由至该组中代理的顺序，请在代理列表中，单击用户，然后单击向上箭头或向下箭头。
    
      - 要将 Microsoft Exchange Server 通讯组列表用作代理组，请单击“使用现有的电子邮件通讯组列表”，然后在“通讯组列表地址”中键入该通讯组列表的电子邮件地址（例如 NetworkSupport@contoso.com）。
        
        如果使用电子邮件通讯组列表，则将受到以下约束：
        
          - 不能为代理组选择多个通讯组列表。每个组仅支持一个通讯组列表。
        
          - 如果通讯组列表包含一个或多个通讯组列表，则不会将嵌套的通讯组列表的成员添加到代理列表。
        
          - 如果选择串行路由或循环路由，则服务器会根据路由方法和通讯组列表中代理的排列顺序，将传入呼叫路由至相应的代理。
        
          - 如果通讯组列表包含已启用 Lync Server 2010 但未启用企业语音的用户，它们将作为不正常的代理添加到代理组。确保通信组列表的所有成员已为其用户帐户启用企业语音。
        
        > [!IMPORTANT]  
        > 如果使用电子邮件通讯组列表，则 响应组管理员或用户可以看到隐藏成员身份或隐藏列表。
        
        在下列情况中，可以看见隐藏成员身份或隐藏列表：
        
          - 如果通讯组列表配置为隐藏成员身份，并且 响应组管理员将通讯组列表分配到代理列表，则用户可以呼叫组以查看成员身份。
        
          - 如果通讯组列表配置为在 Exchange 全局地址列表中隐藏，并且 响应组过程具有相应的用户权限，则即使 响应组管理员没有相应的用户权限，该管理员也可以看到该通讯组列表并将其分配到代理列表。

11. 单击“提交”。

## 使用 Windows PowerShell创建或修改代理组

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  使用 **New-CsRgsAgentGroup** 可创建新代理组。使用 **Set-CsRgsAgentGroup** 可修改现有代理组。在该命令行处，运行：
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    例如：
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    > [!IMPORTANT]
    > 代理警报时间设置不能超出 180 秒，如果代理警报时间超过 180 秒，客户端应用程序会拒绝呼叫，因为 SIP 事务计时器达到其最长等待时间。


4.  确认是否已创建代理组。运行：
    
        Get-CsRgsAgentGroup -Name "Help Desk"

## 另请参阅

#### 任务

[删除代理组](lync-server-2013-delete-an-agent-group.md)  

#### 其他资源

[管理响应组代理组](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)

