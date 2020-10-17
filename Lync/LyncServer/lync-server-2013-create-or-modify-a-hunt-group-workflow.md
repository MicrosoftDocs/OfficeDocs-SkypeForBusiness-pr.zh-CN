---
title: Lync Server 2013：创建或修改智能寻线工作流
description: Lync Server 2013：创建或修改智能寻线工作流。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f6374352c87d13b1e5c09bcef267059016eae0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570718"
---
# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改智能寻线工作流

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-09-11_

使用以下过程之一可创建或修改智能寻线工作流。

<div>


> [!NOTE]  
> 您可以使用 Lync Server 命令行管理程序或响应组配置工具来创建和修改智能寻线工作流。 您可以从 Lync Server 控制面板访问响应组配置工具，也可以通过键入以下 URL 直接从 web 浏览器打开网页： <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>。



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>使用响应组配置工具创建或修改智能寻线工作流

1.  以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“响应组”****，然后单击“工作流”****。

4.  在“工作流”**** 页上，单击“创建或编辑工作流”****。

5.  在 " **选择服务** 搜索" 字段中，键入承载要创建或更改的工作流的 **ApplicationServer** 服务的全部或部分名称。 在服务结果列表中，单击想要的服务，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 将打开 "响应组配置" 工具。 您还可以通过键入以下 URL，直接从 web 浏览器打开响应组配置工具： <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>。

    
    </div>

6.  执行下列操作之一：
    
      - 在“创建新的工作流”**** 下，单击“智能寻线”**** 旁边的“创建”。
    
      - 在“管理现有工作流”**** 下，找到要更改的工作流，然后在“操作”**** 下，单击“编辑”****。

7.  如果你已准备好让用户开始呼叫工作流，请选择 **"激活工作流"**。
    
    <div>
    

    > [!NOTE]  
    > 如果要创建托管工作流，则需要选择“激活工作流”<STRONG></STRONG>。在保存活动、托管的工作流之后，可以修改并停用该工作流。

    
    </div>

8.  要允许联盟用户呼叫组，请选中“启用联盟”**** 复选框。 您还必须具有一个适用于为联合配置的响应组应用程序的外部访问策略。
    
    <div>
    

    > [!NOTE]  
    > 全局外部访问策略适用于响应组应用程序。 您可以使用 Lync Server 控制面板或使用 <STRONG>set-csexternalaccesspolicy</STRONG> Cmdlet 将 EnableOutsideAccess 参数设置为 True，从而为响应组联盟配置全局策略。 请记住，除非为全局策略设置分配站点或用户策略，否则这些设置适用于所有用户。 因此，在针对响应组更改此设置之前，请确保联盟设置满足您的组织的要求。 有关如何将策略应用于用户的详细信息，请参阅 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部访问策略</A>。 有关联盟设置的详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">set-csexternalaccesspolicy</A>。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync Online 中托管的用户不能将呼叫放到托管在本地部署中的响应组。 这在混合部署和本地部署与 Lync Online 部署联合的情况下都是如此。

    
    </div>

9.  要在呼叫过程中隐藏代理身份，请选中“启用代理匿名”**** 复选框。
    
    <div>
    

    > [!NOTE]  
    > 尽管建立呼叫后，代理或呼叫者可以添加即时消息 (IM) 和视频，但匿名呼叫无法启动 IM 或视频。 匿名代理还可以将呼叫置于保持状态、转接呼叫（盲转接和咨询转接）、寄存和取回呼叫。 匿名呼叫不支持会议、应用程序共享和桌面共享、文件传输、白板、数据协作和呼叫记录。 使用 Lync VDI 插件的代理可以以匿名方式接收传入呼叫，但不能以匿名方式发出传出呼叫。

    
    </div>

10. 在“输入将接收呼叫的组的地址”**** 下，键入将应答工作流呼叫的组的主 SIP 统一资源标识符 (URI) 地址。
    
    <div>
    

    > [!NOTE]  
    > 工作流的主 URI 是标识和引用工作流的方式。 您输入的 SIP URI 在 Active Directory 域服务中作为联系人对象创建。 若要创建此 URI，则该对象在 Active Directory 中必须是唯一的。

    
    </div>

11. 在“显示名称”**** 中，键入希望显示的工作流名称（例如，销售响应组）。
    
    <div>
    

    > [!NOTE]  
    > 不要 &lt; 在显示名称中包含 "" 或 " &gt; " 字符。 请勿使用以下显示名称，因为它们已被保留： <STRONG>RGS 状态观察</STRONG> 程序或 <STRONG>通知服务</STRONG>。

    
    </div>

12. 在“电话号码”**** 下，键入响应组的线路 URI（例如，+14255550165）。

13. 在“显示号码”**** 中，键入希望显示的响应组号码（例如，+1 (425) 555-0165）。

14.  (可选) 在 " **说明**" 中，键入要在 Lync 客户端中的联系人卡片上显示的工作流的说明。

15. 如果工作流将由响应组管理员进行管理，则在“工作流类型”**** 中，选择“受管理”****。 执行以下操作可向工作流分配响应组管理员：
    
    1.  键入此工作流的管理员的 SIP URI，然后单击 " **添加**"。
    
    2.  键入要添加到工作流的其他管理员的 SIP URI，然后单击 " **添加**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 必须为被指定为响应组管理员的每一位用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。

    
    </div>

16. 在“步骤 2 选择语言”**** 下，单击要用于语音识别和文本到语音转换的语言。

17. 如果要配置欢迎消息，请在“步骤 3 配置欢迎消息”**** 下选中“播放欢迎消息”**** 复选框，然后执行下列操作之一：
    
      - 要为呼叫者输入转换成语音的文本形式的欢迎消息，请单击“使用文本到语音转换”****，然后在文本框中键入欢迎消息。
        
        <div>
        

        > [!NOTE]  
        > 不要在输入的文本中包含 HTML 标记，否则将收到错误消息。

        
        </div>
    
      - 要使用 Wave (.wav) 或 Windows Media 音频 (.wma) 文件录音作为欢迎消息，请单击“选择录音”****。如果要上载新的音频文件，请单击“录音”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的音频文件，然后单击“打开”****。单击“上载”****，加载该音频文件。
        
        <div>
        

        > [!NOTE]  
        > 用户提供的所有音频文件都必须满足特定要求。 有关受支持的文件格式的详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。

        
        </div>

18. 在“步骤 4 指定您的工作时间”**** 下的“您所在的时区”**** 中，单击工作流的时区。
    
    <div>
    

    > [!NOTE]  
    > 该时区是工作流的呼叫者和代理所在的时区。它用于计算开放和关闭的时间点。例如，如果将工作流配置为使用北美东部时间的时区，并安排工作流在上午 7:00 开放，晚上 11:00 关闭，则得出的开放和关闭时间点分别为东部时间 7:00 和东部时间 23:00。（必须以 24 小时制输入时间。)

    
    </div>

19. 通过执行下列操作之一选择要使用的工作时间日程表类型：
    
      - 要使用预定义工作时间日程表，请单击“使用预设日程表”****，然后从下拉列表中选择要使用的日程表。
        
        <div>
        

        > [!NOTE]  
        > 之前您必须至少已定义一个预设日程表才能选择该选项。 可使用 <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet 来定义预设日程表。 有关详细信息，请参阅 <A href="lync-server-2013-optional-define-response-group-business-hours.md"> (Optional) 在 Lync Server 2013 中定义响应组工作时间</A>。

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > 选择预设日程表时，“天”<STRONG></STRONG>、“开放”<STRONG></STRONG>和“关闭”<STRONG></STRONG>中会自动填写响应组可以应答的日期和时间。

        
        </div>
    
      - 要使用仅适用于该工作流的自定义日程表，请单击“使用自定义日程表”****。

20. 如果要创建该工作流的自定义日程表，请单击一周中响应组可以应答的日期对应的复选框。

21. 如果要创建自定义日程表，请键入一周中每一天响应组可以应答的“开放”**** 和“关闭”**** 时间点。
    
    <div>
    

    > [!NOTE]  
    > “开放”<STRONG></STRONG>和“关闭”<STRONG></STRONG>时间点必须采用 24 小时制。例如，如果营业时间为朝九晚五，其中午餐时间不办公，则工作时间指定为 9:00“开放”<STRONG></STRONG>、12:00“关闭”<STRONG></STRONG>、13:00“开放”<STRONG></STRONG>及 17:00“关闭”<STRONG></STRONG>。

    
    </div>

22. 如果要在办公室未开放时播放消息，请选中“响应组在工作时间以外时播放消息”**** 复选框，然后通过执行以下操作之一指定要播放的消息：
    
      - 要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”****，然后在文本框中键入消息。
        
        <div>
        

        > [!NOTE]  
        > 不要在输入的文本中包含 HTML 标记，否则将收到错误消息。

        
        </div>
    
      - 要使用音频文件录音作为消息，请单击“选择录音”****。如果要上载新的音频文件，请单击“录音”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的文件，然后单击“打开”****。单击“上载”****，加载该音频文件。
        
        <div>
        

        > [!NOTE]  
        > 用户提供的所有音频文件都必须满足特定要求。 有关受支持的音频文件格式的详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。

        
        </div>

23. 指定播放消息后如何处理呼叫（如果配置了消息）：
    
      - 要断开呼叫，请单击“断开呼叫”****。
    
      - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”****，然后键入语音邮件地址。 语音邮件地址的格式为 \<username\> @ \<domainName\> (例如，bob@contoso.com) 。
    
      - 要将呼叫转接到另一个用户，请单击“转接到 SIP URI”****，然后键入该用户的地址。 用户地址的格式为 \<username\> @ \<domainName\> 。
    
      - 要将呼叫转接到另一个电话号码，请单击“转接到电话号码”****，然后键入该电话号码。 电话号码的格式为 \<number\> @ \<domainName\> (例如，+ 14255550121@contoso.com) 。 域名可用来将呼叫者路由至正确的目标。

24. 在“步骤 5 指定您的假日”**** 下，单击定义响应组停止营业日期的一个或多个假日集对应的复选框。
    
    <div>
    

    > [!NOTE]  
    > 配置工作流之前，您需要先定义假日和假日集。 使用 <STRONG>New-CsRgsHoliday</STRONG> 和 <STRONG>New-CsRgsHolidaySet</STRONG> cmdlet 可定义假日和假日集。 有关详细信息，请参阅 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md"> (Optional) 在 Lync Server 2013 中定义响应组假日集</A>。

    
    </div>

25. 如果要在假日播放消息，请选中“假期播放消息”**** 复选框，然后通过执行以下操作之一指定要播放的消息：
    
      - 要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”****，然后在文本框中键入消息。
        
        <div>
        

        > [!NOTE]  
        > 不要在输入的文本中包含 HTML 标记，否则将收到错误消息。

        
        </div>
    
      - 要使用音频文件录音作为消息，请单击“选择录音”****。如果要上载新的音频文件，请单击“录音”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的文件，然后单击“打开”****。单击“上载”****，加载该音频文件。
        
        <div>
        

        > [!NOTE]  
        > 用户提供的所有音频文件都必须满足特定要求。 有关受支持的音频文件格式的详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。

        
        </div>

26. 指定播放消息后如何处理呼叫（如果配置了消息）：
    
      - 要断开呼叫，请单击“断开呼叫”****。
    
      - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”****，然后键入语音邮件地址。 语音邮件地址的格式为 \<username\> @ \<domainName\> (例如，bob@contoso.com) 。
    
      - 要将呼叫转接到另一个用户，请单击“转接到 SIP URI”****，然后键入该用户的地址。 用户地址的格式为 \<username\> @ \<domainName\> 。
    
      - 要将呼叫转接到另一个电话号码，请单击“转接到电话号码”****，然后键入该电话号码。 电话号码的格式为 \<number\> @ \<domainName\> (例如，+ 14255550121@contoso.com) 。 域名用于将呼叫者路由至正确的目标。

27. 在“步骤 6 配置队列”**** 下的“选择将接收呼叫的队列”**** 中，选择在出现可以应答的代理之前，使呼叫者处于保持状态的队列。

28. 在“步骤 7 配置保持音乐”**** 下，执行以下操作之一，选择希望呼叫者在等待代理时听到的音乐：
    
      - 要使用默认录音作为保持音乐，请单击“使用默认值”****。
    
      - 要使用音频文件录音作为保持音乐，请单击“选择音乐文件”****。如果要上载新的音频文件，请单击“音乐文件”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的文件，然后单击“打开”****。单击“上载”****，加载该音频文件。
        
        <div>
        

        > [!NOTE]  
        > 用户提供的所有音频文件都必须满足特定要求。 有关受支持的音频文件格式的详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。

        
        </div>

29. 单击“部署”****。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a>使用 Windows PowerShell 创建或修改智能寻线工作流

1.  以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  创建要为欢迎邮件播放的提示，并将其保存在变量中。 在命令行中运行：
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    例如：
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > 要针对提示使用音频文件，请使用 <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet。 有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">CsRgsAudioFile</A>。

    
    </div>

4.  获取将定向到呼叫的队列或问题的标识。 在命令行中运行：
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    有关创建队列的详细信息，请参阅 [CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)。

5.  定义在营业时间打开工作流时要执行的默认操作，并将其保存在变量中。 在命令行中运行：
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > 对于智能寻线工作流，默认操作必须将呼叫定向到队列。 此参数是活动工作流所必需的。 非活动工作流不需要此属性。

    
    </div>
    
    例如：
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  如果要定义营业时间和假日，您需要在创建或修改工作流之前创建它们。 有关详细信息，请参阅 [ (optional) 在 Lync server 2013 中定义响应组工作时间](lync-server-2013-optional-define-response-group-business-hours.md) 和 [ (可选的) 在 lync Server 2013 中定义响应组假日集](lync-server-2013-optional-define-response-group-holiday-sets.md)。

7.  如果您想要对在营业时间内或在假期内收到的呼叫发出提示，请使用 **CsRgsPrompt** cmdlet 定义提示，并使用 **new-csrgscallaction** 定义在提示后要执行的操作。 有关详细信息，请参阅 [CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) 和 [new-csrgscallaction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)。

8.  检索 Lync Server 响应组服务的服务名称，并将其分配给一个变量。 在命令中，运行：
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  创建或修改工作流。 若要创建工作流，请使用 **CsRgsWorkflow**。 若要修改工作流，请使用 **CsRgsWorkflow**。 在命令行中键入：
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    例如：
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > 必须为指定了工作流管理员的所有用户分配 CsResponseGroupManager 角色。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 有关其他可选参数的详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">CsRgsWorkflow</A> 或 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">CsRgsWorkflow</A>

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[ (可选) 在 Lync Server 2013 中定义响应组假日集](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[ (可选) 在 Lync Server 2013 中定义响应组工作时间](lync-server-2013-optional-define-response-group-business-hours.md)  


[新 CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[新 CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[新 New-csrgscallaction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

