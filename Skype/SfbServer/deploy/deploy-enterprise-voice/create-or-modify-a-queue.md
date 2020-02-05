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
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="aca24-103">在 Skype for Business 中创建或修改队列</span><span class="sxs-lookup"><span data-stu-id="aca24-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="aca24-104">在 Skype for Business Server Enterprise Voice 中创建或修改响应组队列。</span><span class="sxs-lookup"><span data-stu-id="aca24-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="aca24-105">队列使呼叫者处于保持状态，直到有代理应答呼叫为止。</span><span class="sxs-lookup"><span data-stu-id="aca24-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="aca24-106">当响应组应用程序搜索可用代理时，它将按列出的顺序搜索代理组。</span><span class="sxs-lookup"><span data-stu-id="aca24-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="aca24-107">可以选择分配给队列的代理组并指定队列的行为，如限制队列可容纳的呼叫数，以及呼叫等待代理应答呼叫的时间长度。</span><span class="sxs-lookup"><span data-stu-id="aca24-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="aca24-108">使用以下其中一个过程来创建或修改队列。</span><span class="sxs-lookup"><span data-stu-id="aca24-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="aca24-109">使用 "Skype for Business 服务器" 控制面板创建或修改队列</span><span class="sxs-lookup"><span data-stu-id="aca24-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="aca24-110">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="aca24-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aca24-111">如果您是托管工作流的委派响应组管理员之一，则可以创建或修改响应组队列，并将其分配给您管理的工作流。</span><span class="sxs-lookup"><span data-stu-id="aca24-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="aca24-112">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="aca24-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="aca24-113">在左侧导航栏中，单击“响应组”\*\*\*\*，然后单击“队列”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="aca24-114">在“队列”\*\*\*\* 页上，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="aca24-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="aca24-115">要创建新队列，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="aca24-116">在“选择服务”\*\*\*\* 中，键入要在搜索字段中添加队列的 **ApplicationServer** 服务的部分或全部名称。</span><span class="sxs-lookup"><span data-stu-id="aca24-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="aca24-117">在服务结果列表中，单击想要的服务，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="aca24-p103">要修改现有的队列，请在搜索字段中键入全部或部分队列名称。在队列结果列表中，单击想要的队列，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="aca24-120">在“名称”\*\*\*\* 中，键入队列的识别名称。</span><span class="sxs-lookup"><span data-stu-id="aca24-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="aca24-121">在“说明”\*\*\*\* 中，键入队列的说明。</span><span class="sxs-lookup"><span data-stu-id="aca24-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="aca24-p104">在“组”\*\*\*\* 中，指定要分配给队列的组。请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="aca24-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="aca24-p105">要将组添加到队列，请单击“选择”\*\*\*\*。在“选择组”\*\*\*\* 搜索字段中，键入要分配给队列的代理组的全部或部分名称，单击想要的代理组，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="aca24-126">要从队列中删除组，在代理组列表中，请单击要删除的组，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="aca24-127">要更改代理的搜索顺序，在代理组列表中，请单击某个组，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="aca24-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="aca24-p106">服务器搜索队列的可用代理时，将使用组顺序。即，首先搜索列表中的第一个组，然后搜索列表中的第二个组，依此类推。</span><span class="sxs-lookup"><span data-stu-id="aca24-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="aca24-130">要指定代理应答呼叫之前呼叫者处于保持状态的最大时间长度，请选中“启用队列超时”\*\*\*\* 复选框，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="aca24-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="aca24-131">a.</span><span class="sxs-lookup"><span data-stu-id="aca24-131">a.</span></span> <span data-ttu-id="aca24-132">在“超时时段(秒)”\*\*\*\* 中，指定呼叫者等待代理应答呼叫的最长时间（秒）。</span><span class="sxs-lookup"><span data-stu-id="aca24-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="aca24-133">b.</span><span class="sxs-lookup"><span data-stu-id="aca24-133">b.</span></span> <span data-ttu-id="aca24-134">在“呼叫操作”\*\*\*\* 中，选择呼叫超时时执行的操作（如下所示）：</span><span class="sxs-lookup"><span data-stu-id="aca24-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="aca24-135">要在超时后断开呼叫，请单击“断开连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="aca24-136">若要将呼叫转移到语音邮件，请单击 "**转发到语音邮件**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的语音邮件地址： \* \<\>用户名\*@ \*\<域名\> \* （例如，sip:bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="aca24-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="aca24-137">若要将呼叫转移到另一个电话号码，请单击 "**转发到电话号码**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的电话号码： \* \<\>号码\*@ \*\<域名\> \* （例如，sip:+14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="aca24-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="aca24-138">若要将呼叫转移到其他用户，请单击 "**转发到 sip 地址**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的用户 URI： _ \<\>用户名_@ _\<域名\>_。</span><span class="sxs-lookup"><span data-stu-id="aca24-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="aca24-139">要将呼叫转接到其他队列，请单击“转接到其他队列”\*\*\*\*，然后浏览至要使用的队列。</span><span class="sxs-lookup"><span data-stu-id="aca24-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="aca24-140">要指定队列可以容纳的最大呼叫数，请选中“启用队列溢出”\*\*\*\* 复选框，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="aca24-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="aca24-141">a.</span><span class="sxs-lookup"><span data-stu-id="aca24-141">a.</span></span> <span data-ttu-id="aca24-142">在“最大呼叫数”\*\*\*\* 中，选择希望队列容纳的最大呼叫数。</span><span class="sxs-lookup"><span data-stu-id="aca24-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="aca24-143">b.</span><span class="sxs-lookup"><span data-stu-id="aca24-143">b.</span></span> <span data-ttu-id="aca24-144">在“转接呼叫”\*\*\*\* 中，选择队列已满时要转接的呼叫：“最新呼叫”\*\*\*\* 或“最早呼叫”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="aca24-145">c.</span><span class="sxs-lookup"><span data-stu-id="aca24-145">c.</span></span> <span data-ttu-id="aca24-146">在“呼叫操作”\*\*\*\* 中，选择达到溢出阈值时要执行的操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aca24-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="aca24-147">要在超时后断开呼叫，请单击“断开连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="aca24-148">若要将呼叫转移到语音邮件，请单击 "**转发到语音邮件**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的语音邮件地址： \* \<\>用户名\*@ \*\<域名\> \* （例如，sip:bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="aca24-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="aca24-149">若要将呼叫转移到另一个电话号码，请单击 "**转发到电话号码**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的电话号码： \* \<\>号码\*@ \*\<域名\> \* （例如，sip:+14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="aca24-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="aca24-150">若要将呼叫转移到其他用户，请单击 "**转发到 sip 地址**"，然后在 " **sip 地址**" 字段中，键入 sip 的格式的用户 URI： _ \<\>用户名_@ _\<域名\>_。</span><span class="sxs-lookup"><span data-stu-id="aca24-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="aca24-151">要将呼叫转接到其他队列，请单击“转接到其他队列”\*\*\*\*，然后浏览至要使用的队列。</span><span class="sxs-lookup"><span data-stu-id="aca24-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="aca24-152">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="aca24-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="aca24-153">使用 Skype for Business Server Management Shell 创建或修改队列</span><span class="sxs-lookup"><span data-stu-id="aca24-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="aca24-154">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="aca24-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aca24-155">如果您是托管工作流的委派响应组管理员，您将能够创建代理组和队列并将代理组分配给队列。</span><span class="sxs-lookup"><span data-stu-id="aca24-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="aca24-156">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aca24-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="aca24-p112">创建在达到队列超时阈值时要显示的提示，并将其保存在变量中。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="aca24-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="aca24-159">例如：</span><span class="sxs-lookup"><span data-stu-id="aca24-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="aca24-160">要针对提示使用音频文件，请使用 **Import-CsRgsAudioFile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aca24-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="aca24-161">有关详细信息，请参阅[导入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="aca24-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="aca24-p114">定义在达到队列超时阈值时要采取的操作，并将其保存在变量中。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="aca24-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="aca24-164">有关可能的操作及其语法的详细信息，请参阅[CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="aca24-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="aca24-165">例如：</span><span class="sxs-lookup"><span data-stu-id="aca24-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="aca24-p115">创建在达到队列溢出阈值时要显示的提示，并将其保存在变量中。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="aca24-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="aca24-168">例如：</span><span class="sxs-lookup"><span data-stu-id="aca24-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="aca24-169">要针对提示使用音频文件，请使用 **Import-CsRgsAudioFile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aca24-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="aca24-170">有关详细信息，请参阅[导入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="aca24-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="aca24-p117">定义在达到队列溢出阈值时要采取的操作，并将其保存在变量中。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="aca24-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="aca24-173">有关可能的操作及其语法的详细信息，请参阅[CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="aca24-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="aca24-174">例如：</span><span class="sxs-lookup"><span data-stu-id="aca24-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="aca24-p118">检索响应组服务的服务名称，并将其分配到某个变量。在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="aca24-p118">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="aca24-p119">获取要分配给队列的代理组的标识。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="aca24-p119">Get the identity of the agent group to be assigned to the queue. At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="aca24-179">有关创建代理组的详细信息，请参阅[新 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="aca24-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="aca24-p120">创建队列。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="aca24-p120">Create the queue. At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="aca24-182">例如：</span><span class="sxs-lookup"><span data-stu-id="aca24-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="aca24-p121">确认已创建队列。运行：</span><span class="sxs-lookup"><span data-stu-id="aca24-p121">Confirm that the queue is created. Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="aca24-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aca24-185">See also</span></span>

[<span data-ttu-id="aca24-186">新-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="aca24-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="aca24-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="aca24-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="aca24-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="aca24-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="aca24-189">新-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="aca24-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="aca24-190">CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="aca24-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="aca24-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="aca24-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="aca24-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="aca24-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
