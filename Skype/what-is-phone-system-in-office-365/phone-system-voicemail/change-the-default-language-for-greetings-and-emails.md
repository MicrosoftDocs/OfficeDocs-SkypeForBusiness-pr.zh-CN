---
title: "更改贺卡和电子邮件的默认语言"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Phone System
description: 'Learn how to setup Skype for Busineses to use another language for your organization''s default voicemail greeting. '
ms.openlocfilehash: cfbdcfec46a79c6fcef2aff970a05837460f6e72
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="50986-103">更改贺卡和电子邮件的默认语言</span><span class="sxs-lookup"><span data-stu-id="50986-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="50986-104">如果您是[Office 365 全局管理员](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)，您可以设置 Skype 为玩另一种语言问候其默认语音邮件的业务。</span><span class="sxs-lookup"><span data-stu-id="50986-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="50986-105">默认系统问候语是类似，"请为 John Smith 将一条消息。</span><span class="sxs-lookup"><span data-stu-id="50986-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="50986-106">后音，请记录您的消息。</span><span class="sxs-lookup"><span data-stu-id="50986-106">After the tone, please record your message.</span></span> <span data-ttu-id="50986-107">完成录制后，挂上，或井按键查看更多选项。</span><span class="sxs-lookup"><span data-stu-id="50986-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="50986-108">**首先，请阅读以下重要信息：**</span><span class="sxs-lookup"><span data-stu-id="50986-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="50986-109">**对您可用的语言取决于组织的位置**。</span><span class="sxs-lookup"><span data-stu-id="50986-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="50986-110">例如，如果您的公司位于美国，您可以设置默认语言为英语或西班牙语。</span><span class="sxs-lookup"><span data-stu-id="50986-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="50986-111">如果您的组织是在加拿大，您可以选择英语和法语。</span><span class="sxs-lookup"><span data-stu-id="50986-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="50986-112">有关支持的语言的列表，请参阅[语音邮件问候语和来自 Skype 业务邮件的语言](languages-for-voicemail-greetings-and-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="50986-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="50986-p103">**无法仅为组织中的一个用户更改系统语言。** 只能为组织中的所有用户更改问候语言。</span><span class="sxs-lookup"><span data-stu-id="50986-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50986-115">用户可以更改自己的问候到其设置的语言，他们签名后。</span><span class="sxs-lookup"><span data-stu-id="50986-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="50986-116">**记录传出语音邮件消息吗？**</span><span class="sxs-lookup"><span data-stu-id="50986-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="50986-117">[检查的 Skype 业务语音邮件和选项](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)，请参阅。</span><span class="sxs-lookup"><span data-stu-id="50986-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="50986-118">更改组织内所有用户的系统语言</span><span class="sxs-lookup"><span data-stu-id="50986-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="50986-119">使用[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)在[Office 365 提供全局管理员](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)帐户登录。</span><span class="sxs-lookup"><span data-stu-id="50986-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="50986-120">在管理中心，选择**设置** > **组织配置文件**。</span><span class="sxs-lookup"><span data-stu-id="50986-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="50986-122">选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="50986-122">Choose **Edit**.</span></span>
    
    ![Choose Edit.](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="50986-124">为您的组织中的每个人都从**首选语言**列表中选择一种语言。</span><span class="sxs-lookup"><span data-stu-id="50986-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="50986-125">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="50986-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="50986-126">相关管理员文章</span><span class="sxs-lookup"><span data-stu-id="50986-126">Related articles for the admin</span></span>

- [<span data-ttu-id="50986-127">Office 365 中调用计划是什么？</span><span class="sxs-lookup"><span data-stu-id="50986-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="50986-128">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="50986-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="50986-129">Office 365 中的电话系统与内部在 Skype 的 PSTN 连接起来计划业务服务器 2015年或 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50986-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="50986-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="50986-130">Related topics</span></span>

- [<span data-ttu-id="50986-131">更改显示语言和 Office 365 商业版中的时区</span><span class="sxs-lookup"><span data-stu-id="50986-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="50986-132">[添加语言或设置语言首选项在 Office 2010 及更高版本](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)）</span><span class="sxs-lookup"><span data-stu-id="50986-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="50986-133">启用或更改键盘布局语言</span><span class="sxs-lookup"><span data-stu-id="50986-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    

