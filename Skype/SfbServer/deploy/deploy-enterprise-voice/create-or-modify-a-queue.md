---
title: 在 Skype for Business 中创建或修改队列
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 在 Skype for Business Server Enterprise Voice 中创建或修改响应组队列。
ms.openlocfilehash: 8cd306e849eeddd8a11b76604826084c0eb9b41d
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767865"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>在 Skype for Business 中创建或修改队列
 
在 Skype for Business Server Enterprise Voice 中创建或修改响应组队列。
  
队列使呼叫者处于保持状态，直到有代理应答呼叫为止。 当响应组应用程序搜索可用代理时，它将按列出的顺序搜索代理组。 可以选择分配给队列的代理组并指定队列的行为，如限制队列可容纳的呼叫数，以及呼叫等待代理应答呼叫的时间长度。
  
使用以下其中一个过程来创建或修改队列。
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>使用 "Skype for Business 服务器" 控制面板创建或修改队列

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
    > [!NOTE]
    > 如果您是托管工作流的委派响应组管理员之一，则可以创建或修改响应组队列，并将其分配给您管理的工作流。 
  
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“响应组”****，然后单击“队列”****。
    
4. 在“队列”**** 页上，请执行以下操作之一：
    
   - 要创建新队列，请单击“新建”****。 在“选择服务”**** 中，键入要在搜索字段中添加队列的 **ApplicationServer** 服务的部分或全部名称。 在服务结果列表中，单击想要的服务，然后单击“确定”****。
    
   - 要修改现有的队列，请在搜索字段中键入全部或部分队列名称。在队列结果列表中，单击想要的队列，再单击“编辑”****，然后单击“显示详细信息”****。
    
5. 在“名称”**** 中，键入队列的识别名称。
    
6. 在“说明”**** 中，键入队列的说明。
    
7. 在“组”**** 中，指定要分配给队列的组。请执行以下操作之一： 
    
   - 要将组添加到队列，请单击“选择”****。在“选择组”**** 搜索字段中，键入要分配给队列的代理组的全部或部分名称，单击想要的代理组，然后单击“确定”****。
    
   - 要从队列中删除组，在代理组列表中，请单击要删除的组，然后单击“删除”****。
    
   - 要更改代理的搜索顺序，在代理组列表中，请单击某个组，然后单击向上箭头或向下箭头。
    
     > [!NOTE]
     > 服务器搜索队列的可用代理时，将使用组顺序。即，首先搜索列表中的第一个组，然后搜索列表中的第二个组，依此类推。 
  
8. 要指定代理应答呼叫之前呼叫者处于保持状态的最大时间长度，请选中“启用队列超时”**** 复选框，然后执行下列操作：
    
    a. 在“超时时段(秒)”**** 中，指定呼叫者等待代理应答呼叫的最长时间（秒）。
    
    b. 在“呼叫操作”**** 中，选择呼叫超时时执行的操作（如下所示）：
    
   - 要在超时后断开呼叫，请单击“断开连接”****。
    
   - 若要将呼叫转移到语音邮件，请单击 "**转发到语音邮件**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的语音邮件地址： * \<\>用户名*@ *\<域名\> * （例如，sip:bob@contoso.com）。
    
   - 若要将呼叫转移到另一个电话号码，请单击 "**转发到电话号码**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的电话号码： * \<\>号码*@ *\<域名\> * （例如，sip:+14255550121@contoso.com）。
    
   - 若要将呼叫转移到其他用户，请单击 "**转发到 sip 地址**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的用户 URI： _ \<\>用户名_@ _\<域名\>_。
    
   - 要将呼叫转接到其他队列，请单击“转接到其他队列”****，然后浏览至要使用的队列。
    
9. 要指定队列可以容纳的最大呼叫数，请选中“启用队列溢出”**** 复选框，然后执行下列操作：
    
    a. 在“最大呼叫数”**** 中，选择希望队列容纳的最大呼叫数。 
    
    b. 在“转接呼叫”**** 中，选择队列已满时要转接的呼叫：“最新呼叫”**** 或“最早呼叫”****。
    
    c. 在“呼叫操作”**** 中，选择达到溢出阈值时要执行的操作，如下所示：
    
   - 要在超时后断开呼叫，请单击“断开连接”****。
    
   - 若要将呼叫转移到语音邮件，请单击 "**转发到语音邮件**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的语音邮件地址： * \<\>用户名*@ *\<域名\> * （例如，sip:bob@contoso.com）。
    
   - 若要将呼叫转移到另一个电话号码，请单击 "**转发到电话号码**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的电话号码： * \<\>号码*@ *\<域名\> * （例如，sip:+14255550121@contoso.com）。
    
   - 若要将呼叫转移到其他用户，请单击 "**转发到 sip 地址**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的用户 URI： _ \<\>用户名_@ _\<域名\>_。
    
   - 要将呼叫转接到其他队列，请单击“转接到其他队列”****，然后浏览至要使用的队列。
    
10. 单击“**提交**”。
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>使用 Skype for Business Server Management Shell 创建或修改队列

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
    > [!NOTE]
    > 如果您是托管工作流的委派响应组管理员，您将能够创建代理组和队列并将代理组分配给队列。 
  
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 创建在达到队列超时阈值时要显示的提示，并将其保存在变量中。在命令行中运行：
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   例如：
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > 要针对提示使用音频文件，请使用 **Import-CsRgsAudioFile** cmdlet。 有关详细信息，请参阅[导入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。 
  
4. 定义在达到队列超时阈值时要采取的操作，并将其保存在变量中。在命令行中运行：
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > 有关可能的操作及其语法的详细信息，请参阅[CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。 
  
    例如：
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. 创建在达到队列溢出阈值时要显示的提示，并将其保存在变量中。在命令行中运行：
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   例如：
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > 要针对提示使用音频文件，请使用 **Import-CsRgsAudioFile** cmdlet。 有关详细信息，请参阅[导入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。 
  
6. 定义在达到队列溢出阈值时要采取的操作，并将其保存在变量中。在命令行中运行：
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > 有关可能的操作及其语法的详细信息，请参阅[CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。 
  
    例如：
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. 检索响应组服务的服务名称，并将其分配到某个变量。在该命令行处，运行：
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. 获取要分配给队列的代理组的标识。在命令行中运行：
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > 有关创建代理组的详细信息，请参阅[新 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. 创建队列。在命令行中运行：
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   例如：
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. 确认已创建队列。运行：
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>另请参阅

[新-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[新-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
