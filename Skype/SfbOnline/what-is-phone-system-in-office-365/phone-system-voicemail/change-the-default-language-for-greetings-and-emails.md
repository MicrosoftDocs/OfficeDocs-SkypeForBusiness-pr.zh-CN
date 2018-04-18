---
title: 更改问候语和电子邮件的默认语言
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: '了解如何设置 Skype for Busineses 以便将其他语言用于贵组织的默认语音邮箱问候语。 '
ms.openlocfilehash: 5ee5b3e307e21e4b7225fadfbe2a079dd40f72de
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="cd846-103">更改问候语和电子邮件的默认语言</span><span class="sxs-lookup"><span data-stu-id="cd846-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="cd846-104">如果你是 [Office 365 全局管理员](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)，你可以将 Skype for Business 设置为以其他语言播放默认语音邮件问候语。</span><span class="sxs-lookup"><span data-stu-id="cd846-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="cd846-105">默认系统问候语类似于“请给 John Smith 留言。</span><span class="sxs-lookup"><span data-stu-id="cd846-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="cd846-106">听到提示音之后，请录制你的消息。</span><span class="sxs-lookup"><span data-stu-id="cd846-106">After the tone, please record your message.</span></span> <span data-ttu-id="cd846-107">完成录制后，挂断电话，或者按井号键了解更多选项。”</span><span class="sxs-lookup"><span data-stu-id="cd846-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="cd846-108">**首先，请阅读以下重要信息：**</span><span class="sxs-lookup"><span data-stu-id="cd846-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="cd846-109">**对你可用的语言取决于组织所在的位置**。</span><span class="sxs-lookup"><span data-stu-id="cd846-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="cd846-110">例如，如果你的组织位于美国，你可以将默认语言设置为英语或西班牙语。</span><span class="sxs-lookup"><span data-stu-id="cd846-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="cd846-111">如果你的组织位于加拿大，你可以在英语和法语之间选择。</span><span class="sxs-lookup"><span data-stu-id="cd846-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="cd846-112">有关受支持语言的列表，请参阅 [Skype for Business 语音邮件问候语和消息的语言](languages-for-voicemail-greetings-and-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="cd846-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="cd846-p103">**无法仅为组织中的一个用户更改系统语言。** 只能为组织中的所有用户更改问候语言。</span><span class="sxs-lookup"><span data-stu-id="cd846-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cd846-115">用户登录后，可以通过设置更改自己的问候语语言。</span><span class="sxs-lookup"><span data-stu-id="cd846-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="cd846-116">**是否要录制你的外出语音邮件消息？**</span><span class="sxs-lookup"><span data-stu-id="cd846-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="cd846-117">请参阅[检查 Skype for Business 语音邮件和选项](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)。</span><span class="sxs-lookup"><span data-stu-id="cd846-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>

- <span data-ttu-id="cd846-118">**若要更改语音邮件提示语言吗？**</span><span class="sxs-lookup"><span data-stu-id="cd846-118">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="cd846-119">转到[https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail)，然后选择一种新的语言**提示语言**下。</span><span class="sxs-lookup"><span data-stu-id="cd846-119">Go to [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="cd846-120">更改组织内所有用户的系统语言</span><span class="sxs-lookup"><span data-stu-id="cd846-120">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="cd846-121">使用您的[Office 365 提供全局管理员](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)帐户，登录[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="cd846-121">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="cd846-122">在管理中心，选择“**设置**” > “**组织资料**”。</span><span class="sxs-lookup"><span data-stu-id="cd846-122">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![选择“设置”，然后选择“组织资料”。](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="cd846-124">选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="cd846-124">Choose **Edit**.</span></span>
    
    ![选择“编辑”。](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="cd846-126">从“**首选语言**”列表中为组织中的所有用户选择语言。</span><span class="sxs-lookup"><span data-stu-id="cd846-126">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="cd846-127">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cd846-127">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="cd846-128">相关管理员文章</span><span class="sxs-lookup"><span data-stu-id="cd846-128">Related articles for the admin</span></span>

- [<span data-ttu-id="cd846-129">Office 365 中有哪些通话套餐？</span><span class="sxs-lookup"><span data-stu-id="cd846-129">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="cd846-130">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="cd846-130">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="cd846-131">在 Skype for Business Server 2015 或 Lync Server 2013 中规划具有本地 PSTN 连接的 Office 365 电话系统</span><span class="sxs-lookup"><span data-stu-id="cd846-131">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="cd846-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="cd846-132">Related topics</span></span>

- [<span data-ttu-id="cd846-133">在 Office 365 商业版中更改显示语言和时区</span><span class="sxs-lookup"><span data-stu-id="cd846-133">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="cd846-134">[在 Office 2010 及更高版本中添加语言或设置语言首选项](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="cd846-134">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="cd846-135">启用或更改键盘布局语言</span><span class="sxs-lookup"><span data-stu-id="cd846-135">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
