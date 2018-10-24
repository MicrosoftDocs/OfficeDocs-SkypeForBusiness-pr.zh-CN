---
title: Lync Server 2013：创建或修改队列
TOCTitle: 创建或修改队列
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205207(v=OCS.15)
ms:contentKeyID: 49314042
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或修改队列

 

_**上一次修改主题：** 2013-02-23_

使用以下其中一个过程来创建或修改队列。

## 使用 Lync Server 控制面板创建或修改队列

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
    > [!NOTE]  
    > 如果您是托管工作流的委派响应组管理员之一，则可以创建或修改响应组队列，并将其分配给您管理的工作流。
    


2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“响应组”，然后单击“队列”。

4.  在“队列”页上，请执行以下操作之一：
    
      - 要创建新队列，请单击“新建”。在“选择服务”中，键入要在搜索字段中添加队列的 **ApplicationServer** 服务的部分或全部名称。在服务结果列表中，单击想要的服务，然后单击“确定”。
    
      - 要修改现有的队列，请在搜索字段中键入全部或部分队列名称。在队列结果列表中，单击想要的队列，再单击“编辑”，然后单击“显示详细信息”。

5.  在“名称”中，键入队列的识别名称。

6.  在“说明”中，键入队列的说明。

7.  在“组”中，指定要分配给队列的组。请执行以下操作之一：
    
      - 要将组添加到队列，请单击“选择”。在“选择组”搜索字段中，键入要分配给队列的代理组的全部或部分名称，单击想要的代理组，然后单击“确定”。
    
      - 要从队列中删除组，在代理组列表中，请单击要删除的组，然后单击“删除”。
    
      - 要更改代理的搜索顺序，在代理组列表中，请单击某个组，然后单击向上箭头或向下箭头。
        
        > [!NOTE]  
		> 服务器搜索队列的可用代理时，将使用组顺序。即，首先搜索列表中的第一个组，然后搜索列表中的第二个组，依此类推。
        


8.  要指定代理应答呼叫之前呼叫者处于保持状态的最大时间长度，请选中“启用队列超时”复选框，然后执行下列操作：
    
    1.  在“超时时段(秒)”中，指定呼叫者等待代理应答呼叫的最长时间（秒）。
    
    2.  在“呼叫操作”中，选择呼叫超时时执行的操作（如下所示）：
    
    <!-- end list -->
    
      - 要在超时后断开呼叫，请单击“断开连接”。
    
      - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”，然后在“SIP 地址”字段中按格式 sip:*\<username\>*@*\<domainname\>*（例如 sip:bob@contoso.com）键入语音邮件地址。
    
      - 要将呼叫转接到其他电话号码，请单击“转接到电话号码”，然后在“SIP 地址”字段中按格式 sip:*\<number\>*@*\<domainname\>*（例如 sip:+14255550121@contoso.com）键入电话号码。
    
      - 要将呼叫转接到其他用户，请单击“转接到 SIP 地址”，然后在“SIP 地址”字段中按格式 sip:*\<username\>*@*\<domainname\>* 键入用户的 URI。
    
      - 要将呼叫转接到其他队列，请单击“转接到其他队列”，然后浏览至要使用的队列。

9.  要指定队列可以容纳的最大呼叫数，请选中“启用队列溢出”复选框，然后执行下列操作：
    
    1.  在“最大呼叫数”中，选择希望队列容纳的最大呼叫数。
    
    2.  在“转接呼叫”中，选择队列已满时要转接的呼叫：“最新呼叫”或“最早呼叫”。
    
    3.  在“呼叫操作”中，选择达到溢出阈值时要执行的操作，如下所示：
    
    <!-- end list -->
    
      - 要在超时后断开呼叫，请单击“断开连接”。
    
      - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”，然后在“SIP 地址”字段中按格式 sip:*\<username\>*@*\<domainname\>*（例如 sip:bob@contoso.com）键入语音邮件地址。
    
      - 要将呼叫转接到其他电话号码，请单击“转接到电话号码”，然后在“SIP 地址”字段中按格式 sip:*\<number\>*@*\<domainname\>*（例如 sip:+14255550121@contoso.com）键入电话号码。
    
      - 要将呼叫转接到其他用户，请单击“转接到 SIP 地址”，然后在“SIP 地址”字段中按格式 sip:*\<username\>*@*\<domainname\>* 键入用户的 URI。
    
      - 要将呼叫转接到其他队列，请单击“转接到其他队列”，然后浏览至要使用的队列。

10. 单击“提交”。

## 使用 Windows PowerShell创建或修改队列

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
    > [!NOTE]  
    > 如果您是托管工作流的委派响应组管理员，您将能够创建代理组和队列并将代理组分配给队列。
    


2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  创建在达到队列超时阈值时要显示的提示，并将其保存在变量中。在命令行中运行：
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    例如：
    
        "All agents are currently busy. Please call back later."
    
    > [!NOTE]  
    > 要针对提示使用音频文件，请使用 <strong>Import-CsRgsAudioFile</strong> cmdlet。有关详细信息，请参阅 <a href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</a>。
    


4.  定义在达到队列超时阈值时要采取的操作，并将其保存在变量中。在命令行中运行：
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    > [!NOTE]  
    > 有关可能的操作及其语法的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</a>。
    
    
    例如：
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  创建在达到队列溢出阈值时要显示的提示，并将其保存在变量中。在命令行中运行：
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    例如：
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    > [!NOTE]  
    > 要针对提示使用音频文件，请使用 <strong>Import-CsRgsAudioFile</strong> cmdlet。有关详细信息，请参阅 <a href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</a>。
    


6.  定义在达到队列溢出阈值时要采取的操作，并将其保存在变量中。在命令行中运行：
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    > [!NOTE]  
    > 有关可能的操作及其语法的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</a>。
    
    
    例如：
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  检索响应组服务的服务名称，并将其分配到某个变量。在该命令行处，运行：
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  获取要分配给队列的代理组的标识。在命令行中运行：
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    > [!NOTE]  
    > 有关创建代理组的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</a>。
    


9.  创建队列。在命令行中运行：
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    例如：
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. 确认已创建队列。运行：
    
        Get-CsRgsQueue -Name "Help Desk"

## 另请参阅

#### 其他资源

[New-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsRgsQueue)

