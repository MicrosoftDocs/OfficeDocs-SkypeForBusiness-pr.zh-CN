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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 了解如何将 Skype for Businesses 设置为使用另一种语言作为组织的默认语音邮件问候语。
ms.openlocfilehash: f6fb890d52e052afffccbfe753ab5b3b8a1bb338
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102668"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="dd79e-103">更改问候语和电子邮件的默认语言</span><span class="sxs-lookup"><span data-stu-id="dd79e-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="dd79e-104">如果你是全局 [管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)，你可以设置 Skype for Business 以使用另一种语言播放其默认语音邮件问候语。</span><span class="sxs-lookup"><span data-stu-id="dd79e-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="dd79e-105">默认系统问候语类似于“请给 John Smith 留言。</span><span class="sxs-lookup"><span data-stu-id="dd79e-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="dd79e-106">听到提示音之后，请录制你的消息。</span><span class="sxs-lookup"><span data-stu-id="dd79e-106">After the tone, please record your message.</span></span> <span data-ttu-id="dd79e-107">完成录制后，挂断电话，或者按井号键了解更多选项。”</span><span class="sxs-lookup"><span data-stu-id="dd79e-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="dd79e-108">**首先，请阅读以下重要信息：**</span><span class="sxs-lookup"><span data-stu-id="dd79e-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="dd79e-109">**对你可用的语言取决于组织所在的位置**。</span><span class="sxs-lookup"><span data-stu-id="dd79e-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="dd79e-110">例如，如果你的组织位于美国，你可以将默认语言设置为英语或西班牙语。</span><span class="sxs-lookup"><span data-stu-id="dd79e-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="dd79e-111">如果你的组织位于加拿大，你可以在英语和法语之间选择。</span><span class="sxs-lookup"><span data-stu-id="dd79e-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="dd79e-112">有关受支持语言的列表，请参阅 [Skype for Business 语音邮件问候语和消息的语言](languages-for-voicemail-greetings-and-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="dd79e-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="dd79e-113">**更改单个用户的语音邮件问候语和语音邮件的语言。**</span><span class="sxs-lookup"><span data-stu-id="dd79e-113">**Changing languages for individual user's voicemail greeting and voicemail messages.**</span></span> <span data-ttu-id="dd79e-114">您可以更改用户的首选语言，这将更改发送到其 Outlook 邮箱的语音邮件问候语和语音邮件的语言。</span><span class="sxs-lookup"><span data-stu-id="dd79e-114">You can change the preferred lanaguage for users, which will change the language of the their voicemail greeting and voicemail messages sent to their Outlook mailbox.</span></span> <span data-ttu-id="dd79e-115">有关说明，请参阅 [如何为 Microsoft 365 或 Office 365 设置语言和地区设置] https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region) (。</span><span class="sxs-lookup"><span data-stu-id="dd79e-115">For instruction please see [How to set language and region settings for Microsoft 365 or Office 365] (https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="dd79e-116">用户可以按照在[Microsoft 365 商业](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)版中更改显示语言和时区中的说明登录后，通过设置更改自己的问候语语言</span><span class="sxs-lookup"><span data-stu-id="dd79e-116">Users can change their own greeting language through their settings after they sign in by following instructions found in [Change your display language and time zone in Microsoft 365 for Business](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span></span>
  
- <span data-ttu-id="dd79e-117">**是否要录制你的外出语音邮件消息？**</span><span class="sxs-lookup"><span data-stu-id="dd79e-117">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="dd79e-118">请参阅[检查 Skype for Business 语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)。</span><span class="sxs-lookup"><span data-stu-id="dd79e-118">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="dd79e-119">对于 Microsoft Teams - 用户可以从 Teams 桌面客户端设置 [更改其语音邮件设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="dd79e-119">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="dd79e-120">**是否要更改语音邮件提示语言？**</span><span class="sxs-lookup"><span data-stu-id="dd79e-120">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="dd79e-121">对于 Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) 在"提示语言"下选择 **新语言**。</span><span class="sxs-lookup"><span data-stu-id="dd79e-121">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="dd79e-122">对于 Microsoft Teams - 用户可以从 Teams 桌面客户端设置更改 [语音邮件问候语](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="dd79e-122">For Microsoft Teams - Users can change their voicemail greeting from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="dd79e-123">更改组织内所有用户的系统语言</span><span class="sxs-lookup"><span data-stu-id="dd79e-123">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="dd79e-124">在 使用 [全局管理员帐户](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。</span><span class="sxs-lookup"><span data-stu-id="dd79e-124">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="dd79e-125">在 Microsoft 365 管理中心中，选择"**设置""**  >  **设置""**  >  **组织配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="dd79e-125">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span> 
    
     ![显示选择"设置"，然后选择"组织配置文件"的屏幕截图。](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="dd79e-127">选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="dd79e-127">Choose **Edit**.</span></span>
    
    ![显示"编辑"选项的屏幕截图。](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="dd79e-129">从“**首选语言**”列表中为组织中的所有用户选择语言。</span><span class="sxs-lookup"><span data-stu-id="dd79e-129">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="dd79e-130">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="dd79e-130">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="dd79e-131">相关管理员文章</span><span class="sxs-lookup"><span data-stu-id="dd79e-131">Related articles for the admin</span></span>

- [<span data-ttu-id="dd79e-132">电话系统和通话套餐</span><span class="sxs-lookup"><span data-stu-id="dd79e-132">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="dd79e-133">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="dd79e-133">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="dd79e-134">在 Microsoft 365 或 Office 365 中使用本地 PSTN 连接在 Skype for Business Server 中规划电话系统</span><span class="sxs-lookup"><span data-stu-id="dd79e-134">Plan Phone System in Microsoft 365 or Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
    
## <a name="related-topics"></a><span data-ttu-id="dd79e-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="dd79e-135">Related topics</span></span>

- [<span data-ttu-id="dd79e-136">在 Microsoft 365 或 Office 365 商业版中更改显示语言和时区</span><span class="sxs-lookup"><span data-stu-id="dd79e-136">Change your display language and time zone in Microsoft 365 or Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="dd79e-137">[在 Office 2010 及更高版本中添加语言或设置语言首选项](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="dd79e-137">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="dd79e-138">启用或更改键盘布局语言</span><span class="sxs-lookup"><span data-stu-id="dd79e-138">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
