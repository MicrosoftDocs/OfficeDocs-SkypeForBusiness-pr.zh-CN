---
title: Lync Server 2013：创建或修改互动工作流
TOCTitle: 创建或修改互动工作流
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205213(v=OCS.15)
ms:contentKeyID: 49314080
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或修改互动工作流

 

_**上一次修改主题：** 2013-09-11_

可使用以下其中一个过程来创建或修改互动工作流。

> [!NOTE]  
> 您可以使用 Lync Server 命令行管理程序或 响应组配置工具来创建和修改互动工作流。可以从 Lync Server 控制面板访问 响应组配置工具，也可以直接在 Web 浏览器通过键入以下 URL 打开网页来进行访问：<strong>https://</strong><em>&lt;webPoolFqdn&gt;</em><strong>/RgsConfig</strong>。



## 使用 响应组配置工具创建或修改互动工作流

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“响应组”，然后单击“工作流”。

4.  在“工作流”页上，单击“创建或编辑工作流”。

5.  在“选择服务”搜索字段中，键入托管要创建或修改的工作流的 **ApplicationServer** 服务的全部或部分名称。在服务结果列表中，单击想要的服务，然后单击“确定”。
    
    > [!NOTE]  
    > 此时将打开 响应组配置工具。还可以在 Web 浏览器中键入以下 URL 直接打开 响应组配置工具：<strong>https://</strong><em>&lt;webPoolFqdn&gt;</em><strong>/RgsConfig</strong>。
    


6.  执行下列操作之一：
    
      - 在“创建新的工作流”下，单击“交互”旁边的“创建”。
    
      - 在“管理现有工作流”下，找到想要更改的工作流，然后在“操作”下单击“编辑”。

7.  如果尚未准备好让用户开始呼叫工作流，请清除“激活工作流”复选框。
    
    > [!NOTE]  
    > 如果要创建受管理的工作流，则需要选择“激活工作流”。在保存活动、受管理的工作流之后，则可以修改并停用该工作流。
    


8.  要允许联盟用户呼叫组，请选中“启用联盟”复选框。您还必须具有适用于为联盟配置的 响应组应用程序的外部访问策略。
    
    > [!NOTE]  
    > 全局外部访问策略适用于 响应组应用程序。您可以使用 Lync Server 控制面板或使用 <strong>Set-CsExternalAccessPolicy</strong> cmdlet 将 EnableOutsideAccess 参数设置为 True，以为响应组联盟配置全局策略。请记住，除非为全局策略设置分配站点或用户策略，否则这些设置适用于所有用户。因此，在针对响应组更改此设置之前，请确保联盟设置满足您的组织的要求。有关策略如何适用于用户的详细信息，请参阅 <a href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理组织的外部访问策略</a>。有关联盟设置的详细信息，请参阅 Lync Server 命令行管理程序文档中的 <strong>Set-CsExternalAccessPolicy</strong>。
    
    
    > [!NOTE]  
    > 驻留在 Lync Online 中的用户无法向驻留在本地部署中的响应组发出呼叫。在混合部署中以及本地部署已与 Lync Online 部署进行联盟的情形下也是如此。
    


9.  要在呼叫过程中隐藏代理身份，请选中“启用代理匿名”复选框。
    
    > [!NOTE]  
    > 尽管建立呼叫后，代理或呼叫者可以添加即时消息 (IM) 和视频，但匿名呼叫无法启动 IM 或视频。匿名代理还可以将呼叫置于保持状态、转接呼叫（盲转接和咨询转接）、寄存和取回呼叫。匿名呼叫不支持会议、应用程序共享和桌面共享、文件传输、白板、数据协作和呼叫记录。使用 Lync VDI 插件的代理可以匿名方式接听来电，但他们无法以匿名方式拨出电话。
    


10. 在“输入将接收呼叫的组的地址”下，键入将应答工作流呼叫的组的主 SIP 统一资源标识符 (URI) 地址。

11. 在“显示名称”中，键入希望显示的工作流名称（例如，销售 IVR 响应组）。
    
    > [!NOTE]  
    > 不要在显示名称中包含“&lt;”或“&gt;”字符。不要使用以下保留的显示名称：“RGS Presence Watcher”或“Announcement Service”。
    


12. 在“电话号码”中，键入响应组的线路 URI（例如，+14255550165）。

13. 在“显示号码”下，键入希望显示的响应组号码（例如，+1 (425) 555-0165）。

14. （可选）在“说明”中，为要显示在 Lync 客户端中的联系人卡片上的工作流键入说明。

15. 如果此工作流将由响应组管理员管理，则在“工作流类型”中选择“托管”。执行以下操作可向工作流分配 响应组管理员：
    
    1.  键入此工作流的管理员的 SIP URI，然后单击“添加”。
    
    2.  键入要添加到工作流的其他管理员的 SIP URI，然后单击“添加”。
    
    > [!IMPORTANT]
    > 必须为被指定为响应组管理员的每一位用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。


16. 在“步骤 2 选择语言”下，单击要用于语音识别和文本到语音转换的语言。

17. 如果要配置欢迎消息，则在“步骤 3 配置欢迎消息”下选中“播放欢迎消息”复选框，然后执行以下操作之一：
    
      - 要为呼叫者输入转换成语音的文本形式的欢迎消息，请单击“使用文本到语音转换”，然后在文本框中键入欢迎消息。
        
        > [!NOTE]  
		> 不要在输入的文本中包含 HTML 标记，否则将收到错误消息。
        
    
      - 要使用 Wave 或 Windows Media 音频文件录音作为欢迎消息，请单击“选择录音”。如果要上载新的音频文件，请单击“录音”链接。在新浏览器窗口中，单击“浏览”，选择要使用的音频文件，然后单击“打开”。单击“上载”，加载该音频文件。
        
        > [!NOTE]  
		> 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 <a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</a>。
        


18. 在“步骤 4 指定您的工作时间”下的“您所在的时区”框中，单击工作流的时区。
    
    > [!NOTE]  
    > 该时区是工作流的呼叫者和代理所在的时区。它用于计算工作流开放和关闭的时间点。例如，如果将工作流配置为使用北美东部时间的时区，并安排工作流在上午 7:00 开放，晚上 11:00 关闭，则得出的开放和关闭时间点分别为东部时间 7:00 和东部时间 11:00:00。（必须以 24 小时制输入时间。）
    


19. 通过执行下列操作之一选择要使用的工作时间日程表类型：
    
      - 要使用预定义工作时间日程表，请单击“使用预设日程表”，然后从下拉列表中选择要使用的日程表。
        
        > [!NOTE]  
        > 之前您必须至少已定义一个预设日程表才能选择该选项。可使用 <strong>New-CSRgsHoursOfBusiness</strong> cmdlet 来定义预设日程表。有关详细信息，请参阅 <a href="lync-server-2013-optional-define-response-group-business-hours.md">（可选）在 Lync Server 2013 中定义响应组工作时间</a>。选择预设日程表时，“天”、“开放”和“关闭”中会自动填写响应组可以应答的日期和时间。
        
    
      - 要使用仅适用于该工作流的自定义日程表，请单击“使用自定义日程表”。

20. 如果要创建该工作流的自定义日程表，请单击一周中响应组可以应答的日期对应的复选框。

21. 如果要创建自定义日程表，请键入响应组可以应答的“开放”和“关闭”时间点。
    
    > [!NOTE]  
    > “开放”和“关闭”时间点必须采用 24 小时制。例如，如果营业时间为朝九晚五，其中午餐时间不办公，则工作时间指定为 9:00“开放”、12:00“关闭”、13:00“开放”及 17:00“关闭”。
    


22. 如果要在办公室未开放时播放消息，请选中“响应组在工作时间以外时播放消息”复选框，然后通过执行以下操作之一指定要播放的消息：
    
      - 要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”，然后在文本框中键入消息。
        
        > [!NOTE]  
		> 不要在输入的文本中包含 HTML 标记，否则将收到错误消息。
        
    
      - 要使用音频文件录音作为消息，请单击“选择录音”。如果要上载新的音频文件，请单击“录音”链接。在新浏览器窗口中，单击“浏览”，选择要使用的文件，然后单击“打开”。单击“上载”，加载该音频文件。
        
        > [!NOTE]  
		> 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 <a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</a>。
        


23. 指定播放消息后如何处理呼叫（如果配置了消息）：
    
      - 要断开呼叫，请单击“断开呼叫”。
    
      - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”，然后键入语音邮件地址。语音邮件地址的格式为 *\<username\>*@*\<domainname\>*（例如 bob@contoso.com）。
    
      - 要将呼叫转接到另一个用户，请单击“转接到 SIP URI”，然后键入用户地址。用户地址的格式为 *\<username\>*@*\<domainname\>*。
    
      - 要将呼叫转接到另一个电话号码，请单击“转接到电话号码”，然后键入该电话号码。电话号码的格式为 *\<number\>*@*\<domainname\>*（例如，+14255550121@contoso.com）。域名可用来将呼叫者路由至正确的目标。

24. 在“步骤 5 指定您的假日”下，单击定义响应组停止营业日期的一个或多个假日集对应的复选框。
    
    > [!NOTE]  
    > 配置工作流之前，您需要先定义假日和假日集。使用 <strong>New-CsRgsHoliday</strong> 和 <strong>New-CsRgsHolidaySet</strong> cmdlet 可定义假日和假日集。有关详细信息，请参阅 <a href="lync-server-2013-optional-define-response-group-holiday-sets.md">（可选）定义响应组假日设置</a>。
    


25. 如果要在假日播放消息，请选中“假期播放消息”复选框，然后通过执行以下操作之一指定要播放的消息：
    
      - 要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”，然后在文本框中键入消息。
        
        > [!NOTE]  
		> 不要在输入的文本中包含 HTML 标记，否则将收到错误消息。
        
    
      - 要使用音频文件录音作为消息，请单击“选择录音”。如果要上载新的音频文件，请单击“录音”链接。在新浏览器窗口中，单击“浏览”，选择要使用的文件，然后单击“打开”。单击“上载”，加载该音频文件。
        
        > [!NOTE]  
		> 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 <a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</a>。
        


26. 指定播放消息后如何处理呼叫（如果配置了消息）：
    
      - 要断开呼叫，请单击“断开呼叫”。
    
      - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”，然后键入语音邮件地址。语音邮件地址的格式为 *\<username\>*@*\<domainname\>*（例如 bob@contoso.com）。
    
      - 要将呼叫转接到另一个用户，请单击“转接到 SIP URI”，然后键入用户地址。用户地址的格式为 *\<username\>*@*\<domainname\>*。
    
      - 要将呼叫转接到另一个电话号码，请单击“转接到电话号码”，然后键入该电话号码。电话号码的格式为 *\<number\>*@*\<domainname\>*（例如，+14255550121@contoso.com）。域名可用来将呼叫者路由至正确的目标。

27. 在“步骤 6 配置保持音乐”下，执行以下操作之一，选择希望呼叫者在等待代理时听到的音乐：
    
      - 要使用默认保持音乐录音，请单击“使用默认值”。
    
      - 要使用音频文件录音作为保持音乐，请单击“选择音乐文件”。如果要上载新的音频文件，请单击“音乐文件”链接。在新浏览器窗口中，单击“浏览”，选择要使用的文件，然后单击“打开”。单击“上载”，加载该音频文件。
        
        > [!NOTE]  
		> 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 <a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</a>。
        


28. 在“步骤 7 配置互动语音响应”下的“用户将听到以下文本或录制的消息”标题中，指定要向呼叫者提出的问题，具体操作如下所示：
    
      - 要输入文本格式的问题，请单击“使用文本到语音转换”，然后在文本框中键入问题。
        
        > [!NOTE]  
		> 不要在输入的文本中包含 HTML 标记，否则将收到错误消息。
        
        
        > [!NOTE]  
		> 文本到语音转换引擎会将符号“#”转换为“号码”这个词。如果需要指代 # 键，则应该在提示语中使用键名代替符号。例如，“要与销售人员交谈，请按井号键”。
        
    
      - 要使用预先录制的包含问题的音频文件，请单击“选择录音”，然后单击“录音”链接以上载该文件。在新浏览器窗口中，单击“浏览”，选择所需音频文件，然后单击“打开”。单击“上载”加载该文件，然后可以选择在文本框中键入问题。这样便可将问题及呼叫者的响应转接到响应代理。
        
        > [!NOTE]  
		> 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 <a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</a>。
        


29. 在“响应 1”下，指定第一个可能的问题答案，具体操作如下：
    
    > [!IMPORTANT]
    > 不要在任何语音响应中使用引号 (&quot;)。引号会导致 IVR 失败。
    
    > [!NOTE]  
    > 可以选择允许呼叫者使用语音、字母数字键盘输入或同时使用两者进行回答。
    
    
      - 如果要允许呼叫者使用语音进行响应，请在“输入语音响应”中输入答案。
    
      - 如果要允许呼叫者通过按小键盘上的键进行响应，请在“数字”中单击小键盘的数字。

30. 指定将呼叫者路由至队列，还是提出其他问题，如下所示：
    
      - 要将呼叫者路由至某个队列，请单击“发送到队列”，然后在“选择队列”中单击要使用的队列。
    
      - 要提出其他问题，请单击“提出其他问题”，然后单击“使用文本到语音转换”并键入问题，或单击“选择录音”。使用本节中的响应分组指定其他问题的可能响应（最多四个），以及用于每个响应的队列。要指定第三个或第四个可能的响应，请单击“响应 3”或“响应 4”复选框。

31. 通过重复步骤 28 和 29 为原题指定多达三个以上可能的答案，以指定可能的响应以及对于每个响应要采取的操作。要指定第三个或第四个可能的答案，请单击“响应 3”或“响应 4”复选框。

32. 单击“部署”。

## 使用 Windows PowerShell创建或修改互动工作流

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  检索响应组服务的服务名称，并将其分配到某个变量。在该命令行处，运行：
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  互动工作流需要两个或多个队列，以及两个或多个代理组。首先，创建代理组。运行：
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  创建队列。运行：
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  创建第一个响应组提示。运行：
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  然后，创建在提示后要执行的操作。运行：
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  创建第一个响应组应答。运行：
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  现在，创建第二个提示、呼叫操作和应答。首先创建提示。运行：
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. 创建第二个呼叫操作。运行：
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. 创建第二个响应组应答。运行：
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. 创建顶级提示。运行：
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. 创建顶级问题。运行：
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. 现在，创建工作流。运行：
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    > [!NOTE]  
    > 必须为被指定为响应组管理员的所有用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。
    

