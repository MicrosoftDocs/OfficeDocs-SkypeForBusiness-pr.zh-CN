---
title: 更改问候语和电子邮件的默认语言
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
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
ms.openlocfilehash: 1c311436ed9010ea20598aac6a55b4806fe18abb
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="bce30-103">更改问候语和电子邮件的默认语言</span><span class="sxs-lookup"><span data-stu-id="bce30-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="bce30-104">如果你是 [Office 365 全局管理员](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)，你可以将 Skype for Business 设置为以其他语言播放默认语音邮件问候语。</span><span class="sxs-lookup"><span data-stu-id="bce30-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="bce30-105">默认系统问候语类似于“请给 John Smith 留言。</span><span class="sxs-lookup"><span data-stu-id="bce30-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="bce30-106">听到提示音之后，请录制你的消息。</span><span class="sxs-lookup"><span data-stu-id="bce30-106">After the tone, please record your message.</span></span> <span data-ttu-id="bce30-107">完成录制后，挂断电话，或者按井号键了解更多选项。”</span><span class="sxs-lookup"><span data-stu-id="bce30-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="bce30-108">**首先，请阅读以下重要信息：**</span><span class="sxs-lookup"><span data-stu-id="bce30-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="bce30-109">**对你可用的语言取决于组织所在的位置**。</span><span class="sxs-lookup"><span data-stu-id="bce30-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="bce30-110">例如，如果你的组织位于美国，你可以将默认语言设置为英语或西班牙语。</span><span class="sxs-lookup"><span data-stu-id="bce30-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="bce30-111">如果你的组织位于加拿大，你可以在英语和法语之间选择。</span><span class="sxs-lookup"><span data-stu-id="bce30-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="bce30-112">有关受支持语言的列表，请参阅 [Skype for Business 语音邮件问候语和消息的语言](languages-for-voicemail-greetings-and-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="bce30-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="bce30-p103">**无法仅为组织中的一个用户更改系统语言。** 只能为组织中的所有用户更改问候语言。</span><span class="sxs-lookup"><span data-stu-id="bce30-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bce30-115">用户登录后，可以通过设置更改自己的问候语语言。</span><span class="sxs-lookup"><span data-stu-id="bce30-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="bce30-116">**是否要录制你的外出语音邮件消息？**</span><span class="sxs-lookup"><span data-stu-id="bce30-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="bce30-117">请参阅[检查 Skype for Business 语音邮件和选项](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)。</span><span class="sxs-lookup"><span data-stu-id="bce30-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="bce30-118">更改组织内所有用户的系统语言</span><span class="sxs-lookup"><span data-stu-id="bce30-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="bce30-119">使用 [Office 365 全局管理员](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="bce30-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="bce30-120">在管理中心，选择“**设置**” > “**组织资料**”。</span><span class="sxs-lookup"><span data-stu-id="bce30-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![选择“设置”，然后选择“组织资料”。](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="bce30-122">选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="bce30-122">Choose **Edit**.</span></span>
    
    ![选择“编辑”。](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="bce30-124">从“**首选语言**”列表中为组织中的所有用户选择语言。</span><span class="sxs-lookup"><span data-stu-id="bce30-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="bce30-125">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="bce30-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="bce30-126">相关管理员文章</span><span class="sxs-lookup"><span data-stu-id="bce30-126">Related articles for the admin</span></span>

- [<span data-ttu-id="bce30-127">Office 365 中有哪些通话套餐？</span><span class="sxs-lookup"><span data-stu-id="bce30-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="bce30-128">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="bce30-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="bce30-129">在 Skype for Business Server 2015 或 Lync Server 2013 中规划具有本地 PSTN 连接的 Office 365 电话系统</span><span class="sxs-lookup"><span data-stu-id="bce30-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="bce30-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="bce30-130">Related topics</span></span>

- [<span data-ttu-id="bce30-131">在 Office 365 商业版中更改显示语言和时区</span><span class="sxs-lookup"><span data-stu-id="bce30-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="bce30-132">[在 Office 2010 及更高版本中添加语言或设置语言首选项](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="bce30-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="bce30-133">启用或更改键盘布局语言</span><span class="sxs-lookup"><span data-stu-id="bce30-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    

