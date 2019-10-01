---
title: 更改问候语和电子邮件的默认语言
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解如何设置 Skype for Business，以便为您的组织的默认语音邮件问候语使用另一种语言。 '
ms.openlocfilehash: 085262a4ae4362aa40d20d3da657db6bcac694a3
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328338"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="5666b-103">更改问候语和电子邮件的默认语言</span><span class="sxs-lookup"><span data-stu-id="5666b-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="5666b-104">如果你是 [Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)，你可以将 Skype for Business 设置为以其他语言播放默认语音邮件问候语。</span><span class="sxs-lookup"><span data-stu-id="5666b-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="5666b-105">默认系统问候语类似于“请给 John Smith 留言。</span><span class="sxs-lookup"><span data-stu-id="5666b-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="5666b-106">听到提示音之后，请录制你的消息。</span><span class="sxs-lookup"><span data-stu-id="5666b-106">After the tone, please record your message.</span></span> <span data-ttu-id="5666b-107">完成录制后，挂断电话，或者按井号键了解更多选项。”</span><span class="sxs-lookup"><span data-stu-id="5666b-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="5666b-108">**首先，请阅读以下重要信息：**</span><span class="sxs-lookup"><span data-stu-id="5666b-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="5666b-109">**对你可用的语言取决于组织所在的位置**。</span><span class="sxs-lookup"><span data-stu-id="5666b-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="5666b-110">例如，如果你的组织位于美国，你可以将默认语言设置为英语或西班牙语。</span><span class="sxs-lookup"><span data-stu-id="5666b-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="5666b-111">如果你的组织位于加拿大，你可以在英语和法语之间选择。</span><span class="sxs-lookup"><span data-stu-id="5666b-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="5666b-112">有关受支持语言的列表，请参阅 [Skype for Business 语音邮件问候语和消息的语言](languages-for-voicemail-greetings-and-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="5666b-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="5666b-p103">**无法仅为组织中的一个用户更改系统语言。** 只能为组织中的所有用户更改问候语言。</span><span class="sxs-lookup"><span data-stu-id="5666b-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5666b-115">用户登录后，可以通过设置更改自己的问候语语言。</span><span class="sxs-lookup"><span data-stu-id="5666b-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="5666b-116">**是否要录制你的外出语音邮件消息？**</span><span class="sxs-lookup"><span data-stu-id="5666b-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="5666b-117">请参阅[检查 Skype for Business 语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)。</span><span class="sxs-lookup"><span data-stu-id="5666b-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="5666b-118">对于 Microsoft 团队-用户可以从[团队桌面客户端设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)更改其语音邮件设置</span><span class="sxs-lookup"><span data-stu-id="5666b-118">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="5666b-119">**是否要更改语音邮件提示语言？**</span><span class="sxs-lookup"><span data-stu-id="5666b-119">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="5666b-120">对于 Skype for Business- [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail)并在 "**提示语言**" 下选择一种新语言。</span><span class="sxs-lookup"><span data-stu-id="5666b-120">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="5666b-121">对于 Microsoft 团队-用户可以从[团队桌面客户端设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)更改其语音邮件设置</span><span class="sxs-lookup"><span data-stu-id="5666b-121">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="5666b-122">更改组织内所有用户的系统语言</span><span class="sxs-lookup"><span data-stu-id="5666b-122">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="5666b-123">在上[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)通过[Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5666b-123">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="5666b-124">在 Microsoft 365 管理中心，选择 "**设置** > **组织配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="5666b-124">In the Microsoft 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![屏幕截图，显示选择 "设置"，然后选择 "组织配置文件"。](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="5666b-126">选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="5666b-126">Choose **Edit**.</span></span>
    
    ![显示 "编辑" 选项的屏幕截图。](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="5666b-128">从“**首选语言**”列表中为组织中的所有用户选择语言。</span><span class="sxs-lookup"><span data-stu-id="5666b-128">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="5666b-129">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5666b-129">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="5666b-130">相关管理员文章</span><span class="sxs-lookup"><span data-stu-id="5666b-130">Related articles for the admin</span></span>

- [<span data-ttu-id="5666b-131">电话系统和通话套餐</span><span class="sxs-lookup"><span data-stu-id="5666b-131">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="5666b-132">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="5666b-132">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="5666b-133">在 Skype for business Server 中通过本地 PSTN 连接计划 Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="5666b-133">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="5666b-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="5666b-134">Related topics</span></span>

- [<span data-ttu-id="5666b-135">在 Office 365 商业版中更改显示语言和时区</span><span class="sxs-lookup"><span data-stu-id="5666b-135">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="5666b-136">[在 Office 2010 及更高版本中添加语言或设置语言首选项](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="5666b-136">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="5666b-137">启用或更改键盘布局语言</span><span class="sxs-lookup"><span data-stu-id="5666b-137">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
