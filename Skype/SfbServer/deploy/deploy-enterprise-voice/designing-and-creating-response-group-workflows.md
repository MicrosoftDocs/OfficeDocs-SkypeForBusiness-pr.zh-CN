---
title: 在 Skype for Business 中设计和创建响应组工作流
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: 在 Skype for Business Server Enterprise Voice 中设计和创建响应组工作流。 包括智能寻线工作流和互动工作流。
ms.openlocfilehash: 9e056070bb01b5ee3cc7f32a8f9d07520fcb2030
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240523"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>在 Skype for Business 中设计和创建响应组工作流

在 Skype for Business Server Enterprise Voice 中设计和创建响应组工作流。 包括智能寻线工作流和互动工作流。

工作流定义了从电话响铃到有人接听电话这段时间内呼叫的行为。 工作流指定用于保留呼叫的队列，并指定用于 智能寻线工作流的路由方法或用于 互动响应组工作流的问题和答案。

工作流还定义了诸如欢迎消息、保持音乐、工作时间和假日等设置。

> [!NOTE]
> 必须先创建代理组和队列，然后再创建使用这些组和队列的工作流。

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>创建或修改查寻组工作流

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>使用 "响应组配置" 工具创建或修改查寻组工作流

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。

3. 在左侧导航栏中，单击“响应组”****，然后单击“工作流”****。

4. 在“工作流”**** 页上，单击“创建或编辑工作流”****。

5. 在“选择服务”**** 搜索字段中，键入承载您想要创建或修改的工作流的 **ApplicationServer** 服务的全部或部分名称。 在服务结果列表中，单击想要的服务，然后单击“确定”****。

    > [!NOTE]
    > 此时将打开 "响应组配置" 工具。 您也可以通过键入以下 URL 直接从 web 浏览器打开 "响应组配置" 工具: https://\<webPoolFqdn\>/RgsConfig。

6. 请执行下列操作之一：

   - 在 "新建**工作流**" 下的 "**查寻组**" 旁边, 单击 "**创建**"。

   - 在“管理现有工作流”**** 下，找到想要更改的工作流，然后在“操作”**** 下单击“编辑”****。

7. 如果已准备好让用户开始呼叫工作流，请选中“激活工作流”****。

    > [!NOTE]
    >  如果你要创建托管工作流, 你需要选择 "**激活工作流"**。 在保存活动、受管理的工作流之后，则可以修改并停用该工作流。

8. 要允许联盟用户呼叫组，请选中“启用联盟”**** 复选框。 还必须具有适用于为联盟配置的响应组应用程序的外部访问策略。

    > [!NOTE]
    > 全局外部访问策略适用于响应组应用程序。 你可以使用 Skype for Business Server 控制面板或通过使用**CsExternalAccessPolicy** Cmdlet 将 EnableOutsideAccess 参数设置为 True, 为响应组联盟配置全局策略。 请记住，除非为全局策略设置分配站点或用户策略，否则这些设置适用于所有用户。 因此，在针对响应组更改此设置之前，请确保联盟设置满足您的组织的要求。 有关策略如何适用于用户的详细信息，请参阅[Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)。 有关联盟设置的详细信息, 请参阅[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)。

    > [!NOTE]
    > Skype for Business Online 中托管的用户不能将调用放到内部部署中托管的响应组。 这在混合部署中以及内部部署与 Skype for Business Online 部署联合的情况下是如此。

9. 要在呼叫过程中隐藏代理身份，请选中“启用代理匿名”**** 复选框。

    > [!NOTE]
    > 尽管建立呼叫后，代理或呼叫者可以添加即时消息 (IM) 和视频，但匿名呼叫无法启动 IM 或视频。匿名代理还可以将呼叫置于保持状态、转接呼叫（盲转接和咨询转接）、寄存和取回呼叫。匿名呼叫不支持会议、应用程序共享和桌面共享、文件传输、白板、数据协作和呼叫记录。使用 Lync VDI 插件的代理可以匿名方式接听来电，但他们无法以匿名方式拨出电话。

10. 在“输入将接收呼叫的组的地址”**** 下，键入将应答工作流呼叫的组的主 SIP 统一资源标识符 (URI) 地址。

    > [!NOTE]
    > 工作流的主 URI 是标识和引用工作流的方式。 您输入的 SIP URI 在 Active Directory 域服务中创建为联系人对象。 若要创建 URI, 对象在 Active Directory 中必须是唯一的。

11. 在 "**显示名称**" 中, 键入要为工作流显示的名称 (例如, "销售" 响应组)。

    > [!NOTE]
    > 不要在显示名称中包含“<”或“>”字符。不要使用以下保留的显示名称：“RGS Presence Watcher”**** 或“Announcement Service”****。

12. 在“电话号码”**** 下，键入响应组的线路 URI（例如，+14255550165）。

13. 在“显示号码”**** 下，键入希望显示的响应组号码（例如，+1 (425) 555-0165）。

14. 可选在 "**说明**" 中, 键入要在 Skype for business 的联系人卡片上显示的工作流的说明。

15. 如果此工作流将由响应组管理员管理，则在“工作流类型”**** 中选择“托管”****。 执行以下操作以将响应组管理器分配给工作流:

    a. 键入此工作流的管理员的 SIP URI，单击“添加”****。

    b. 键入要添加到工作流的其他管理员的 SIP URI，单击“添加”****。

    > [!IMPORTANT]
    > 必须为被指定为响应组管理员的每一位用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。

16. 在“步骤 2 选择语言”**** 下，单击要用于语音识别和文本到语音转换的语言。

17. 如果要配置欢迎消息，则在“步骤 3 配置欢迎消息”**** 下选中“播放欢迎消息”**** 复选框，然后执行以下操作之一：

    - 要为呼叫者输入转换成语音的文本形式的欢迎消息，请单击“使用文本到语音转换”****，然后在文本框中键入欢迎消息。

    > [!NOTE]
    > 不要在输入的文本中包含 HTML 标记。 如果包含 HTML 标记, 则会收到一条错误消息。

    - 要使用 Wave (.wav) 或 Windows Media 音频 (.wma) 文件录音作为欢迎消息，请单击“选择录音”****。如果要上载新的音频文件，请单击“录音”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的音频文件，然后单击“打开”****。单击“上载”**** 加载该音频文件。

    > [!NOTE]
    > 用户提供的所有音频文件都必须满足特定要求。 有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

18. 在“步骤 4 指定您的工作时间”**** 下的“您所在的时区”**** 中，单击工作流的时区。

    > [!NOTE]
    > 该时区是工作流的呼叫者和代理所在的时区。它用于计算工作流开放和关闭的时间点。例如，如果将工作流配置为使用北美东部时间的时区，并安排工作流在上午 7:00 开放，晚上 11:00 关闭，则得出的开放和关闭时间点分别为东部时间 7:00 和东部时间 23:00。（必须以 24 小时制输入时间。）

19. 通过执行下列操作之一选择要使用的工作时间日程表类型：

    - 要使用预定义工作时间日程表，请单击“使用预设日程表”****，然后从下拉列表中选择要使用的日程表。

      > [!NOTE]
      > 之前您必须至少已定义一个预设日程表才能选择该选项。 可使用  **New-CSRgsHoursOfBusiness** cmdlet 来定义预设日程表。 有关详细信息, 请参阅[(可选) 在 Skype For business 中定义响应组工作时间](optional-define-response-group-business-hours.md)。

      > [!NOTE]
      > 选择预设日程表时，“天”****、“开放”**** 和“关闭”**** 中会自动填写响应组可以应答的日期和时间。

    - 要使用仅适用于该工作流的自定义日程表，请单击“使用自定义日程表”****。

20. 如果要创建该工作流的自定义日程表，请单击一周中响应组可以应答的日期对应的复选框。

21. 如果要创建自定义计划, 请键入响应组可用的一周中的每一天的 "**打开**" 和 "**关闭**" 小时数。

    > [!NOTE]
    > “开放”**** 和“关闭”**** 时间点必须采用 24 小时制。例如，如果营业时间为朝九晚五，其中午餐时间不办公，则工作时间指定为 9:00“开放”****、12:00“关闭”****、13:00“开放”**** 及 17:00“关闭”****。

22. 如果要在办公室未开放时播放消息，请选中“响应组在工作时间以外时播放消息”**** 复选框，然后通过执行以下操作之一指定要播放的消息：

    - 要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”****，然后在文本框中键入消息。

      > [!NOTE]
      > 不要在输入的文本中包含 HTML 标记。 如果包含 HTML 标记, 则会收到一条错误消息。

    - 要使用音频文件录音作为消息，请单击“选择录音”****。如果要上载新的音频文件，请单击“录音”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的文件，然后单击“打开”****。单击“上载”****，加载该音频文件。

      > [!NOTE]
      > 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

23. 指定播放消息后如何处理呼叫（如果配置了消息）：

    - 要断开呼叫，请单击“断开呼叫”****。

    - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”****，然后键入语音邮件地址。 语音邮件地址的格式是* \<用户名\>*@*\<域名\> * (例如, bob@contoso.com)。

    - 要将呼叫转接到另一个用户，请单击“转接到 SIP URI”****，然后键入用户地址。 用户地址的格式是_ \<用户名\>_@_\<域名\>_。

    - 要将呼叫转接到另一个电话号码，请单击“转接到电话号码”****，然后键入该电话号码。 电话号码的格式为* \<\>*@"*\<域名域名\> * " (例如 + 14255550121@contoso.com)。 域名可用来将呼叫者路由至正确的目标。

24. 在“步骤 5 指定您的假日”**** 下，单击定义响应组停止营业日期的一个或多个假日集对应的复选框。

    > [!NOTE]
    > 配置工作流之前，您需要先定义假日和假日集。 使用 **New-CsRgsHoliday** 和 **New-CsRgsHolidaySet** cmdlet 可定义假日和假日集。 有关详细信息, 请参阅[(可选) 在 Skype For business 中定义 "响应组" 假日集](optional-define-response-group-holiday-sets.md)。

25. 如果要在假日播放消息，请选中“假期播放消息”**** 复选框，然后通过执行以下操作之一指定要播放的消息：

    - 要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”****，然后在文本框中键入消息。

    > [!NOTE]
    > 不要在输入的文本中包含 HTML 标记。 如果包含 HTML 标记, 则会收到一条错误消息。

    - 要使用音频文件录音作为消息，请单击“选择录音”****。如果要上载新的音频文件，请单击“录音”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的文件，然后单击“打开”****。单击“上载”****，加载该音频文件。

      > [!NOTE]
      > 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

26. 指定播放消息后如何处理呼叫（如果配置了消息）：

    - 要断开呼叫，请单击“断开呼叫”****。

    - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”****，然后键入语音邮件地址。 语音邮件地址的格式是* \<用户名\>*@*\<域名\> * (例如, bob@contoso.com)。

    - 要将呼叫转接到另一个用户，请单击“转接到 SIP URI”****，然后键入用户地址。 用户地址的格式是_ \<用户名\>_@_\<域名\>_。

    - 要将呼叫转接到另一个电话号码，请单击“转接到电话号码”****，然后键入该电话号码。 电话号码的格式为* \<\>*@"*\<域名域名\> * " (例如 + 14255550121@contoso.com)。 域名可用来将呼叫者路由至正确的目标。

27. 在“步骤 6 配置队列”**** 下的“选择将接收呼叫的队列”**** 中，选择在出现可以应答的代理之前，使呼叫者处于保持状态的队列。

28. 在“步骤 7 配置保持音乐”**** 下，执行以下操作之一，选择希望呼叫者在等待代理时听到的音乐：

    - 要使用默认录音作为保持音乐，请单击“使用默认值”****。

    - 要使用音频文件录音作为保持音乐，请单击“选择音乐文件”****。如果要上载新的音频文件，请单击“音乐文件”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的文件，然后单击“打开”****。单击“上载”****，加载该音频文件。

      > [!NOTE]
      > 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

29. 单击“部署”****。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>使用 Skype for Business Server 命令行管理程序创建或修改查寻组工作流

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

3. 为欢迎消息创建要播放的提示，然后将其保存在变量中。在命令行中运行：

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    例如：

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > 要针对提示使用音频文件，请使用 **Import-CsRgsAudioFile** cmdlet。 有关详细信息, 请参阅[导入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。

4. 获取将在其中定向呼叫的队列或问题的标识。 在命令行中运行：

   ```
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    有关创建队列的详细信息, 请参阅[CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)。

5. 定义在工作时间打开工作流时要执行的默认操作，并将其保存在变量中。在命令行中运行：

   ```
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > 对于智能寻线工作流，默认操作必须将呼叫定向到队列。 此参数是活动工作流所必需的。 对于非活动工作流则不需要。

    例如：

   ```
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. 如果要定义工作时间和假日，则需要在创建或修改工作流之前创建工作时间和假日。 有关详细信息, 请参阅[(可选) 在 skype For business 中定义响应组工作时间](optional-define-response-group-business-hours.md)和[(可选) 在 skype For business 中定义 "响应组" 假日集](optional-define-response-group-holiday-sets.md)。

7. 如果您希望在工作时间之外或在假日收到的呼叫带有提示，请使用  **New-CsRgsPrompt** cmdlet 定义该提示，并使用  **New-CsRgsCallAction** 定义要在提示后执行的操作。 有关详细信息, 请参阅[CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)和[CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。

8. 检索 Lync Server 响应组服务的服务名称, 并将其分配给变量。 在命令行中运行：

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. 创建或修改工作流。 要创建工作流，请使用  **New-CsRgsWorkflow**。 要修改工作流，请使用  **Set-CsRgsWorkflow**。 在命令行中键入：

   ```
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    例如：

   ```
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > 必须为所有指定为工作流管理员的用户分配 CsResponseGroupManager 角色。

     > [!NOTE]
     > 有关其他可选参数的详细信息, 请参阅[CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)或[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>设计互动工作流

使用互动语音响应 (IVR) 可从呼叫者获取信息，并将呼叫引导到相应的队列。 问题/答案对确定要使用哪个队列。 根据呼叫者的响应, 呼叫者可以听到后续问题, 或者路由到相应的队列。 IVR 问题和呼叫者的答复将提供给接受呼叫的响应代理, 向该代理提供有价值的信息。

### <a name="overview-of-ivr-features"></a>IVR 功能概述

响应组应用程序提供了在26种语言中的语音识别和文本到语音功能。 可以使用文本到语音转换功能或 Wave (.wav) 或 Windows Media 音频 (.wma) 文件输入 IVR 问题。 呼叫者可以使用语音或双音多频 (DTMF) 响应进行响应。

互动工作流最多支持两级问题，每个问题最多有四个可能的答案。 IVR 将询问呼叫者一个问题, 具体取决于呼叫者的响应、将呼叫者路由到队列或提出第二个问题。 第二个问题也可以有四个可能的答案。 根据呼叫者对第二级问题的回答，将呼叫者路由至相应的队列。

> [!NOTE]
> 使用 Skype for Business Server Management Shell 设计通话流时, 可以定义任意数量的 IVR 问题和任意数量的答案。 但是，为了方便呼叫者使用，建议不要使用三个级别以上的问题，并且每个问题的答案不要超过五个。 此外, 如果你设计的通话流程的两个级别的问题超过四个级别, 则不能使用 Skype for Business Server 控制面板编辑通话流。

IVR 问题和呼叫者的答复将提供给接受呼叫的响应代理。

### <a name="working-with-speech-technologies"></a>使用语音技术

语音识别和文本到语音转换等语音技术可以增强用户体验，并使用户能够更自然和更有效地获得信息。但是，语音引擎在有些情况下无法正确识别所指定的文本或用户语音响应。例如，文本到语音转换引擎会将“#”符号转换为“编号”这个词。通过以下方式可以缓解这一问题：

- 语音引擎让呼叫者尝试回答问题五次。如果呼叫者回答问题有误（即答案不是所指定的响应之一）或根本未提供答案，则呼叫者将再获得一次回答问题的机会。呼叫者有五次机会来回答问题，然后才会被挂断。可以将 IVR 配置为呼叫者每次出错后播放自定义消息。每次都将重复该问题。

- 为了尽量避免语音引擎将环境噪声识别为响应，请使用长一点的响应。例如，响应应包含多个音节，并且不同响应之间应有明显的发音区别。

- 如果问题同时包括语音和 DTMF 响应，请将语音响应配置为表示具体概念的语句，而不是 DTMF 响应。例如，不要使用“请按或说 1”，而应使用“请按 1 或说出帐单”。

- 设计 IVR 之后，请呼叫工作流、收听提示、使用语音对每个提示做出响应，并确认 IVR 的声音和行为符合预期。然后，可以修改 IVR 以更正任何释读问题。在前一个示例中，如果需要指代 # 键，则可以重新编写 IVR 提示，使用键名代替 # 符号。例如，“要与销售人员交谈，请按井号键”。

### <a name="ivr-design-examples"></a>IVR 设计示例

以下各节包含不同 IVR 方案和问题/答案对的示例。

#### <a name="ivr-with-one-level-of-questions"></a>只有单级问题的 IVR

下例介绍使用单级问题的 IVR。 它使用语音识别检测呼叫方的响应。

 **问题：**“感谢您致电人力资源部。如果要与薪酬组通话，请说‘薪酬’。否则，请说‘人力资源’。”

- **选择选项 1：** 将呼叫者路由至薪酬组。

- **选择选项 2：** 将呼叫者路由至人力资源组。

下图显示了相应的呼叫流。

 **单级互动呼叫流**

![使用互动语音响应设计呼叫流](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>含有两级问题的 IVR

下例介绍使用两级问题的 IVR。该 IVR 允许呼叫者使用语音或 DTMF 小键盘输入进行响应。

 **问题：**“感谢您致电 IT 技术支持。如果有网络访问问题，请按 1 或说网络。如果有软件问题，则按 2 或说软件。如果有硬件问题，则按 3 或说硬件。”

- **选择选项 1：** 将呼叫者路由至网络支持组。

- **选择选项 2：** 向呼叫者提出后续问题：

    **问题：**“如果是操作系统的问题，请按 1 或说操作系统。如果是内部应用程序的问题，请按 2 或说内部应用程序。否则，请按 3 或说其他。”

  - **选择选项 1：** 将呼叫者路由至操作系统支持组。

  - **选择选项 2：** 将呼叫者路由至内部应用程序支持组。

  - **选择选项 3：** 将呼叫者路由至软件支持组。

- **选择选项 3：** 向呼叫者提出后续问题：

    **问题：**“如果是打印机问题，请按 1。否则，请按 2。”

  - **选择选项 1：** 将呼叫者路由至打印机支持组。

  - **选择选项 2：** 将呼叫者路由至硬件支持组。

下图显示了相应的呼叫流。

 **两级互动呼叫流**

![使用互动语音响应设计呼叫流](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>最佳做法

下面列出了用于设计 IVR 的一些最佳做法：

- 让呼叫者快速开始任务。避免在 IVR 中提供过多信息或过长的营销消息。

- 如果要包含过长的消息，可以考虑将其附加到第一个问题后面，而不要附加到欢迎消息中。如果该消息作为第一个问题的一部分，呼叫者可以通过回答问题来跳过该消息，但是呼叫者无法跳过欢迎消息。

- 用呼叫者的语言讲话。 避免造作的语言。 自然地讲话。

- 高效书写和有效提示。 删除任何不必要的选项。 对信息进行结构, 以便调用方的预期响应位于句子的末尾。 例如, "要向销售团队讲话, 请按1。"

- 使语音响应用户友好。例如，如果同时指定 DTMF 和语音响应，请使用与此类似的格式：“要与销售团队通话，请按 1 或说销售。”

- 在组织中部署 IVR 之前，请先对一组用户测试该 IVR。

## <a name="creating-or-modifying-an-interactive-workflow"></a>创建或修改互动工作流

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>使用 "响应组配置" 工具创建或修改交互式工作流

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。

3. 在左侧导航栏中，单击“响应组”****，然后单击“工作流”****。

4. 在“工作流”**** 页上，单击“创建或编辑工作流”****。

5. 在“选择服务”**** 搜索字段中，键入托管要创建或修改的工作流的  **ApplicationServer** 服务的全部或部分名称。 在服务结果列表中，单击想要的服务，然后单击“确定”****。

    > [!NOTE]
    > 此时将打开 "响应组配置" 工具。 您也可以通过键入以下 URL 直接从 web 浏览器打开 "响应组配置" 工具: https://\<webPoolFqdn\>/RgsConfig。

6. 请执行下列操作之一：

   - 在“创建新的工作流”**** 下，单击“交互”**** 旁边的“创建”****。

   - 在“管理现有工作流”**** 下，找到想要更改的工作流，然后在“操作”**** 下单击“编辑”****。

7. 如果尚未准备好让用户开始呼叫工作流，请清除“激活工作流”**** 复选框。

    > [!NOTE]
    >  如果你要创建托管工作流, 你需要选择 "**激活工作流"**。 在保存活动、受管理的工作流之后，则可以修改并停用该工作流。

8. 要允许联盟用户呼叫组，请选中“启用联盟”**** 复选框。 还必须具有适用于为联盟配置的响应组应用程序的外部访问策略。

    > [!NOTE]
    > 全局外部访问策略适用于响应组应用程序。 你可以使用 Skype for Business Server 控制面板或通过使用**CsExternalAccessPolicy** Cmdlet 将 EnableOutsideAccess 参数设置为 True, 为响应组联盟配置全局策略。 请记住，除非为全局策略设置分配站点或用户策略，否则这些设置适用于所有用户。 因此，在针对响应组更改此设置之前，请确保联盟设置满足您的组织的要求。 有关策略如何适用于用户的详细信息，请参阅[Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)。 有关联盟设置的详细信息, 请参阅文档中的 "**设置 CsExternalAccessPolicy** "。。

    > [!NOTE]
    > Skype for Business Online 中托管的用户不能将调用放到内部部署中托管的响应组。 这在混合部署中以及内部部署与 Skype for Business Online 部署联合的情况下是如此。

9. 要在呼叫过程中隐藏代理身份，请选中“启用代理匿名”**** 复选框。

    > [!NOTE]
    > 尽管建立呼叫后，代理或呼叫者可以添加即时消息 (IM) 和视频，但匿名呼叫无法启动 IM 或视频。匿名代理还可以将呼叫置于保持状态、转接呼叫（盲转接和咨询转接）、寄存和取回呼叫。匿名呼叫不支持会议、应用程序共享和桌面共享、文件传输、白板、数据协作和呼叫记录。使用 Lync VDI 插件的代理可以匿名方式接听来电，但他们无法以匿名方式拨出电话。

10. 在“输入将接收呼叫的组的地址”**** 下，键入将应答工作流呼叫的组的主 SIP 统一资源标识符 (URI) 地址。

11. 在“显示名称”**** 中，键入希望显示的工作流名称（例如，销售 IVR 响应组）。

    > [!NOTE]
    > 不要在显示名称中\<包含 ""\>或 "" 字符。 不要使用以下保留的显示名称：“RGS Presence Watcher”**** 或“Announcement Service”****。

12. 在“电话号码”**** 中，键入响应组的线路 URI（例如，+14255550165）。

13. 在“显示号码”**** 下，键入希望显示的响应组号码（例如，+1 (425) 555-0165）。

14. 可选在 "**说明**" 中, 键入要在 Skype for business 中的联系人卡片上显示的工作流的说明。

15. 如果此工作流将由响应组管理员管理，则在“工作流类型”**** 中选择“托管”****。 执行以下操作以将响应组管理器分配给工作流:

    a. 键入此工作流的管理员的 SIP URI，单击“添加”****。

    b. 键入要添加到工作流的其他管理员的 SIP URI，单击“添加”****。

    > [!IMPORTANT]
    > 必须为被指定为响应组管理员的每一位用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。

16. 在“步骤 2 选择语言”**** 下，单击要用于语音识别和文本到语音转换的语言。

17. 如果要配置欢迎消息，则在“步骤 3 配置欢迎消息”**** 下选中“播放欢迎消息”**** 复选框，然后执行以下操作之一：

    - 要为呼叫者输入转换成语音的文本形式的欢迎消息，请单击“使用文本到语音转换”****，然后在文本框中键入欢迎消息。

    > [!NOTE]
    > 不要在输入的文本中包含 HTML 标记，否则将收到错误消息。

    - 要使用 Wave 或 Windows Media 音频文件录音作为欢迎消息，请单击“选择录音”****。如果要上载新的音频文件，请单击“录音”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的音频文件，然后单击“打开”****。单击“上载”****，加载该音频文件。

    > [!NOTE]
    > 用户提供的所有音频文件都必须满足特定要求。 有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

18. 在“步骤 4 指定您的工作时间”**** 下的“您所在的时区”**** 框中，单击工作流的时区。

    > [!NOTE]
    > 该时区是工作流的呼叫者和代理所在的时区。它用于计算工作流开放和关闭的时间点。例如，如果将工作流配置为使用北美东部时间的时区，并安排工作流在上午 7:00 开放，晚上 11:00 关闭，则得出的开放和关闭时间点分别为东部时间 7:00 和东部时间 11:00。（必须以 24 小时制输入时间。）

19. 通过执行下列操作之一选择要使用的工作时间日程表类型：

    - 要使用预定义工作时间日程表，请单击“使用预设日程表”****，然后从下拉列表中选择要使用的日程表。

      > [!NOTE]
      > 之前您必须至少已定义一个预设日程表才能选择该选项。 使用**CsRgsHoursOfBusiness** cmdlet 定义预置的计划。 有关详细信息, 请参阅[(可选) 在 Skype For business 中定义响应组工作时间](optional-define-response-group-business-hours.md)。 选择预设日程表时，“天”****、“开放”**** 和“关闭”**** 中会自动填写响应组可以应答的日期和时间。

    - 要使用仅适用于该工作流的自定义日程表，请单击“使用自定义日程表”****。

20. 如果要创建该工作流的自定义日程表，请单击一周中响应组可以应答的日期对应的复选框。

21. 如果要创建自定义计划, 请在 "响应" 组可用时键入 "**打开**" 和 "**关闭**" 时间。

     > [!NOTE]
     > “开放”**** 和“关闭”**** 时间点必须采用 24 小时制。例如，如果营业时间为朝九晚五，其中午餐时间不办公，则工作时间指定为 9:00“开放”****、12:00“关闭”****、13:00“开放”**** 及 17:00“关闭”****。

22. 如果要在办公室未开放时播放消息，请选中“响应组在工作时间以外时播放消息”**** 复选框，然后通过执行以下操作之一指定要播放的消息：

    - 要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”****，然后在文本框中键入消息。

      > [!NOTE]
      > 不要在输入的文本中包含 HTML 标记。 如果包含 HTML 标记, 则会收到一条错误消息。

    - 要使用音频文件录音作为消息，请单击“选择录音”****。如果要上载新的音频文件，请单击“录音”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的文件，然后单击“打开”****。单击“上载”****，加载该音频文件。

    > [!NOTE]
    > 用户提供的所有音频文件都必须满足特定要求。 有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

23. 指定播放消息后如何处理呼叫（如果配置了消息）：

    - 要断开呼叫，请单击“断开呼叫”****。

    - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”****，然后键入语音邮件地址。 语音邮件地址的格式是* \<用户名\>*@*\<域名\> * (例如, bob@contoso.com)。

    - 要将呼叫转接到另一个用户，请单击“转接到 SIP URI”****，然后键入用户地址。 用户地址的格式是_ \<用户名\>_@_\<域名\>_。

    - 要将呼叫转接到另一个电话号码，请单击“转接到电话号码”****，然后键入该电话号码。 电话号码的格式为* \<\>*@"*\<域名域名\> * " (例如 + 14255550121@contoso.com)。 域名可用来将呼叫者路由至正确的目标。

24. 在“步骤 5 指定您的假日”**** 下，单击定义响应组停止营业日期的一个或多个假日集对应的复选框。

    > [!NOTE]
    > 配置工作流之前，您需要先定义假日和假日集。 使用 **New-CsRgsHoliday** 和 **New-CsRgsHolidaySet** cmdlet 可定义假日和假日集。 有关详细信息, 请参阅[(可选) 在 Skype For business 中定义 "响应组" 假日集](optional-define-response-group-holiday-sets.md)。

25. 如果要在假日播放消息，请选中“假期播放消息”**** 复选框，然后通过执行以下操作之一指定要播放的消息：

    - 要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”****，然后在文本框中键入消息。

      > [!NOTE]
      > 不要在输入的文本中包含 HTML 标记。 如果包含 HTML 标记, 则会收到一条错误消息。

    - 要使用音频文件录音作为消息，请单击“选择录音”****。如果要上载新的音频文件，请单击“录音”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的文件，然后单击“打开”****。单击“上载”****，加载该音频文件。

      > [!NOTE]
      > 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

26. 指定播放消息后如何处理呼叫（如果配置了消息）：

    - 要断开呼叫，请单击“断开呼叫”****。

    - 要将呼叫转接到语音邮件，请单击“转接到语音邮件”****，然后键入语音邮件地址。 语音邮件地址的格式是* \<用户名\>*@*\<域名\> * (例如, bob@contoso.com)。

    - 要将呼叫转接到另一个用户，请单击“转接到 SIP URI”****，然后键入用户地址。 用户地址的格式是_ \<用户名\>_@_\<域名\>_。

    - 要将呼叫转接到另一个电话号码，请单击“转接到电话号码”****，然后键入该电话号码。 电话号码的格式为* \<\>*@"*\<域名域名\> * " (例如 + 14255550121@contoso.com)。 域名可用来将呼叫者路由至正确的目标。

27. 在“步骤 6 配置保持音乐”**** 下，执行以下操作之一，选择希望呼叫者在等待代理时听到的音乐：

    - 要使用默认保持音乐录音，请单击“使用默认值”****。

    - 要使用音频文件录音作为保持音乐，请单击“选择音乐文件”****。如果要上载新的音频文件，请单击“音乐文件”**** 链接。在新浏览器窗口中，单击“浏览”****，选择要使用的文件，然后单击“打开”****。单击“上载”****，加载该音频文件。

    > [!NOTE]
    > 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

28. 在“步骤 7 配置互动语音响应”**** 下的“用户将听到以下文本或录制的消息”**** 标题中，指定要向呼叫者提出的问题，具体操作如下所示：

    - 要输入文本格式的问题，请单击“使用文本到语音转换”****，然后在文本框中键入问题。

    > [!NOTE]
    > 不要在输入的文本中包含 HTML 标记，否则将收到错误消息。

    > [!NOTE]
    > 文本到语音转换引擎会将符号“#”转换为“号码”这个词。 如果需要指代 # 键，则应该在提示语中使用键名代替符号。 例如，“要与销售人员交谈，请按井号键”。

    - 若要使用包含问题的预先录制音频文件, 请单击 "**选择录制**", 然后单击 "**录制**" 链接以上载文件。 在新浏览器窗口中, 单击 "**浏览**", 选择音频文件, 然后单击 "**打开**"。 单击 "**上载**" 加载文件, 然后可以选择在文本框中键入问题 (这将允许问题以及呼叫者的响应被转发到响应的代理)。

      > [!NOTE]
      > 用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

29. 在“响应 1”**** 下，指定第一个可能的问题答案，具体操作如下：

    > [!IMPORTANT]
    > 不要在任何语音响应中使用引号 (")。引号会导致 IVR 失败。

    > [!NOTE]
    > 可以选择允许呼叫者使用语音、字母数字键盘输入或同时使用两者进行回答。

    - 如果要允许呼叫者使用语音进行响应，请在“输入语音响应”**** 中输入答案。

    - 如果要允许呼叫者通过按小键盘上的键进行响应，请在“数字”**** 中单击小键盘的数字。

30. 指定将呼叫者路由至队列，还是提出其他问题，如下所示：

    - 要将呼叫者路由至某个队列，请单击“发送到队列”****，然后在“选择队列”**** 中单击要使用的队列。

    - 要提出其他问题，请单击“提出其他问题”****，然后单击“使用文本到语音转换”**** 并键入问题，或单击“选择录音”****。使用本节中的响应分组指定其他问题的可能响应（最多四个），以及用于每个响应的队列。要指定第三个或第四个可能的响应，请单击“响应 3”**** 或“响应 4”**** 复选框。

31. 通过重复步骤 28 和 29 为原题指定多达三个以上可能的答案，以指定可能的响应以及对于每个响应要采取的操作。要指定第三个或第四个可能的答案，请单击“响应 3”**** 或“响应 4”**** 复选框。

32. 单击“部署”****。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>使用 Skype for Business Server Management Shell 创建或修改交互式工作流

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

3. 检索响应组服务的服务名称，并将其分配到某个变量。在该命令行处，运行：

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. 互动工作流需要两个或多个队列，以及两个或多个代理组。首先，创建代理组。运行：

   ```
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. 创建队列。运行：

   ```
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. 创建第一个响应组提示。运行：

   ```
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. 然后，创建在提示后要执行的操作。运行：

   ```
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. 创建第一个响应组应答。运行：

   ```
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. 现在，创建第二个提示、呼叫操作和应答。首先创建提示。运行：

   ```
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. 创建第二个呼叫操作。运行：

    ```
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. 创建第二个响应组应答。运行：

    ```
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. 创建顶级提示。运行：

    ```
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. 创建顶级问题。运行：

    ```
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. 现在，创建工作流。运行：

    ```
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > 必须向已被指定为响应组管理者的所有用户分配 CsResponseGroupManager 角色。 如果没有为用户分配此角色，他们无法管理响应组。

## <a name="see-also"></a>另请参阅

[可选在 Skype for Business 中定义响应组假日集](optional-define-response-group-holiday-sets.md)

[可选在 Skype for Business 中定义响应组工作时间](optional-define-response-group-business-hours.md)

[新-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[新-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

