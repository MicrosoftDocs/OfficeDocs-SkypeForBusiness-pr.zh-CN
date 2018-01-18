---
title: "将第三方指定为音频会议提供商"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: a53a2e63f15aa40eb6a88ab13daba2022b35e3b6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="ddb9a-103">将第三方指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="ddb9a-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="ddb9a-104">音频会议提供商提供*会议桥*。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-104">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="ddb9a-105">会议桥提供拨入电话号码、 针和为会议创建的会议 Id。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-105">The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="ddb9a-106">您只需要将音频会议提供商给人打算安排或导致 Skype 业务或 Microsoft 小组会议。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-106">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ddb9a-107">对于 Microsoft 团队，用户将无法使用第三方音频会议提供商，他们必须在 Office 365，将音频会议提供商设置为 Microsoft 中使用音频会议。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="ddb9a-108">完成分配的第三方音频会议提供商之前操作的步骤</span><span class="sxs-lookup"><span data-stu-id="ddb9a-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="ddb9a-109">这取决于您的 Office 365 计划，您可能需要购买**音频会议**附加许可的组织中的人来说要安排或导致 Skype 业务或 Microsoft 小组使用音频会议的会议。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-109">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing.</span></span> <span data-ttu-id="ddb9a-110">若要了解详细信息，请参阅[附加业务和 Microsoft 小组授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-110">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="ddb9a-111">如果您购买**音频会议**附加许可，则将它们分配给您的组织中将安排或会导致使用音频会议的会议的人。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-111">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing.</span></span> <span data-ttu-id="ddb9a-112">请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ddb9a-113">如果将**音频会议**许可分配给某人**之后**将它们指派第三方音频会议提供商，此人将自动设置 Microsoft 改为用作其音频会议提供商 ！</span><span class="sxs-lookup"><span data-stu-id="ddb9a-113">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead!</span></span> <span data-ttu-id="ddb9a-114">如果发生这种情况，您需要首先将 Microsoft 作为音频会议提供商删除之前可以将第三方音频会议提供商分配给它们。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-114">If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="ddb9a-115">在[Microsoft 查明其](https://go.microsoft.com/fwlink/?LinkId=797530)查找第三方音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-115">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span></span> <span data-ttu-id="ddb9a-116">请与他们联系，了解如何使用这些设置。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-116">Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="ddb9a-117">他们会向你提供：</span><span class="sxs-lookup"><span data-stu-id="ddb9a-117">They will give you:</span></span>
    
  - <span data-ttu-id="ddb9a-118">**拨入号码 （收费）** ，如果有免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="ddb9a-p106">**会议 ID** ：供每个安排会议的人使用。有些 ACP 将它们称为会议密码。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-p106">**Conference IDs** that are used for each person who schedules meetings. Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ddb9a-121">如果您已完成初始设置的第三方 ACP 但现在需要进行更改，请**单击此处以配置第三方音频会议提供商，** **Microsoft 桥**页面底部。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="ddb9a-122">当启用音频会议，有关人员并将它们指派第三方音频会议提供商时，音频数字和会议 Id （密码） 自动添加到任何**新**Skype 为他们创建的联机业务会议。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="ddb9a-123">如何为用户分配第三方音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="ddb9a-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="ddb9a-p107">在 **Skype for Business 管理中心**中选择" **用户**"。从列表中选择用户，并在操作窗格中单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-p107">In the **Skype for Business admin center**, choose **Users**. Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="ddb9a-126">在用户的属性页上单击**音频会议**并输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="ddb9a-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="ddb9a-127">**提供程序名称**从列表中选择第三方提供程序。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="ddb9a-128">**默认收费电话号码**这是必需的。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="ddb9a-129">**默认免费电话号码**这不是必需。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="ddb9a-130">**会议 ID**这是由您的音频会议提供商提供的。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="ddb9a-131">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="ddb9a-132">向每个人发送您从音频会议提供商处接收的 PIN。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-132">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="ddb9a-133">作为领导者的会议呼叫管理器调用中可能需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-133">The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ddb9a-134">当您使用第三方音频会议提供商时，没有为您要查看或设置针脚代表会议组织者的一种方法。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="ddb9a-135">如何在同一时间向许多人指派第三方音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="ddb9a-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="ddb9a-136">在**Skype 的业务管理中心**，选择**音频会议** > **Microsoft 桥**。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-136">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="ddb9a-137">在页面的底部，单击**如果您想要配置第三方音频会议提供商，请单击此处**链接。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-137">At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ddb9a-138">如果您已完成初始设置的第三方 ACP 但现在需要进行更改，请在**Microsoft 桥**页上，**单击此处以配置第三方音频会议提供商**的底部。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="ddb9a-139">在**第三方音频会议提供商的配置**页上，在**导入和导出用户**，单击**导出向导**，然后按照**导出用户向导**中的步骤。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-139">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**.</span></span> <span data-ttu-id="ddb9a-140">完成后，将有一个文件，列出您想要设置音频会议的人。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-140">When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="ddb9a-141">将发送到第三方音频会议提供商创建的文件。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-141">Send the file you created to your third-party audio conferencing provider.</span></span> <span data-ttu-id="ddb9a-142">他们将添加在文件中，列出的人员的音频会议信息，然后将该文件返回给您。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-142">They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="ddb9a-p112">请仔细检查返回的文件是否包含正确的信息。 我们曾听说过并非文件中列出的所有人都包含正确信息的情况。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-p112">Double-check that the returned file has the right information in it. We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="ddb9a-145">在" **配置第三方音频会议提供商**"页面上的" **导入和导出用户**"下方，单击" **导入向导**"，然后按照 **导入用户向导**中的步骤进行操作</span><span class="sxs-lookup"><span data-stu-id="ddb9a-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="ddb9a-146">向每个人发送您从音频会议提供商处接收的 PIN。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-146">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="ddb9a-147">PIN 可能需要调用中作为会议呼叫管理器或主管。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-147">The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ddb9a-148">当您使用第三方音频会议提供商时，没有为您要查看或设置针脚代表会议组织者的一种方法。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="ddb9a-149">何时使用第三方音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="ddb9a-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="ddb9a-150">如果您是在一个国家或地区在 Office 365 中的音频会议不可用、 服务质量不好因为它的位置，或现有合同具有第三方音频会议提供商，我们建议使用第三方音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-150">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider.</span></span> <span data-ttu-id="ddb9a-151">否则，我们建议您使用 Microsoft 为您的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-151">Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="ddb9a-152">通过使用 Windows PowerShell 自动指定第三方音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="ddb9a-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="ddb9a-153">为节省时间或自动执行此操作，可以使用 [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ddb9a-154">要更改音频提供商从 Microsoft 为第三方音频会议提供商，您必须删除 Microsoft 作为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-154">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="ddb9a-155">若要执行此操作，请使用[禁用 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-155">To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="ddb9a-156">有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="ddb9a-157">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="ddb9a-157">What else do I need to know?</span></span>

<span data-ttu-id="ddb9a-158">您的组织中的用户只能使用一个音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-158">A person in your organization can only use one audio conferencing provider.</span></span> <span data-ttu-id="ddb9a-159">若要更改 Microsoft 个人的音频会议提供商，请参阅[移动用户的音频会议提供商向 Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)或[作为音频会议提供商指定的 Microsoft](assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="ddb9a-159">To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ddb9a-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="ddb9a-160">Related Topics</span></span>

[<span data-ttu-id="ddb9a-161">设置音频会议 for Skype Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="ddb9a-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="ddb9a-162">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ddb9a-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

