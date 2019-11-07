---
title: 使用“入门”向导设置商务语音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46f6f75ce0ac14193a4f7a8cfccadf8312f92a98
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972193"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a><span data-ttu-id="60bf6-102">使用“入门”向导设置商务语音</span><span class="sxs-lookup"><span data-stu-id="60bf6-102">Use the Getting Started wizard to set up Business Voice</span></span>

<span data-ttu-id="60bf6-103">借助 Microsoft 365 商务语音的“入门”向导，用户可以轻松快速地开始在 Microsoft Teams 中接听和拨打电话。</span><span class="sxs-lookup"><span data-stu-id="60bf6-103">The Getting Started wizard for Microsoft 365 Business Voice gives you an easy and quick way to start receiving and making phone calls in Microsoft Teams.</span></span> <span data-ttu-id="60bf6-104">如果是一家刚创立的小型企业，此向导可在几分钟内启动并运行电话号码、呼叫菜单、问候语等。</span><span class="sxs-lookup"><span data-stu-id="60bf6-104">If you're a small business just starting out, the wizard can get you up and running in a few minutes with phone numbers, call menus, greetings, and more.</span></span> <span data-ttu-id="60bf6-105">如果是已创建电话解决方案的大型企业，此向导可帮助设置商务语音试点，这样可以先对一些用户试用它，然后再面向所有人进行设置。</span><span class="sxs-lookup"><span data-stu-id="60bf6-105">If you're a larger business with an established telephony solution, the wizard can help you set up a Business Voice pilot so you can try it out with a few users before you set it up for everyone.</span></span> <span data-ttu-id="60bf6-106">无论你的企业是哪种规模，都可以在完成向导后立刻开始使用商务语音！</span><span class="sxs-lookup"><span data-stu-id="60bf6-106">Either way, you can start using Business Voice as soon as the wizard is finished!</span></span>

<span data-ttu-id="60bf6-107">启动向导前，建议先阅读本文。</span><span class="sxs-lookup"><span data-stu-id="60bf6-107">It's a good idea to read this article before you start the wizard.</span></span> <span data-ttu-id="60bf6-108">准备就绪时，可以从 [Microsoft 365 管理中心](https://admin.microsoft.com/AdminPortal/Home#/homepage)打开向导。</span><span class="sxs-lookup"><span data-stu-id="60bf6-108">When you're ready, you can open the wizard from the [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/Home#/homepage).</span></span> <span data-ttu-id="60bf6-109">请务必使用创建订阅所用的帐户或作为全局管理员的其他帐户登录。</span><span class="sxs-lookup"><span data-stu-id="60bf6-109">Make sure you sign in either with the account you used to create your subscription or another account that's a Global Administrator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60bf6-110">目前商务语音适用于加拿大和英国。</span><span class="sxs-lookup"><span data-stu-id="60bf6-110">Business Voice is currently available in Canada and the United Kingdom.</span></span> <span data-ttu-id="60bf6-111">在 2020 年，它将适用于更多国家和地区。</span><span class="sxs-lookup"><span data-stu-id="60bf6-111">More countries and regions will become available in 2020.</span></span>
>
> <span data-ttu-id="60bf6-112">只有在用户的邮箱位于 Microsoft 365 中时，Microsoft Teams 和商务语音才可用。</span><span class="sxs-lookup"><span data-stu-id="60bf6-112">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="60bf6-113">不支持位于本地 Exchange Server 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="60bf6-113">We don't support mailboxes located on on-premises Exchange server.</span></span>

<!-- After you've finished the wizard, here are a couple articles you can check out to see what you can do with Business Voice and learn how to customize it. If you don't want to customize anything, you're done! You can start using Business Voice right away.

* [Things to try with Business Voice](things-to-try.md)
* [Customize Business Voice](customize-business-voice.md)
-->

## <a name="emergency-services-location"></a><span data-ttu-id="60bf6-114">紧急服务位置</span><span class="sxs-lookup"><span data-stu-id="60bf6-114">Emergency services location</span></span>

<table>
    <tr>
        <td><span data-ttu-id="60bf6-115">若要更改紧急地址，请单击“编辑”，然后输入新地址<b></b>。</span><span class="sxs-lookup"><span data-stu-id="60bf6-115">If you'd like to change the emergency address, click <b>Edit</b> and enter a new address.</span></span> <span data-ttu-id="60bf6-116">系统将验证所提供的地址，确保它合规并且符合紧急响应服务的正确格式。</span><span class="sxs-lookup"><span data-stu-id="60bf6-116">The address you provide is validated to make sure that it's legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="60bf6-117">如果该地址有效，系统会将它分配给所有用户（将在下一步中为这些用户分配号码）。</span><span class="sxs-lookup"><span data-stu-id="60bf6-117">If it's valid, the address is assigned to all of the users you assign a number to in the next step.</span></span> <span data-ttu-id="60bf6-118">如果你的员工分布在多个位置，在完成“入门”向导后，“自定义商务语音”主题将向你介绍如何添加并分配多个紧急地址。</span><span class="sxs-lookup"><span data-stu-id="60bf6-118">If you have employees in more than one location, the Customize Business Voice topic will show you how to add and assign more emergency addresses after you finish the Getting Started wizard.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

<span data-ttu-id="60bf6-119">若要了解更多信息，请参阅[什么是紧急位置、地址和呼叫路由？](../what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="60bf6-119">If you want to know more about emergency addresses, see [What are emergency locations, addresses and call routing?](../what-are-emergency-locations-addresses-and-call-routing.md)</span></span>

## <a name="company-phone-number"></a><span data-ttu-id="60bf6-120">公司电话号码</span><span class="sxs-lookup"><span data-stu-id="60bf6-120">Company phone number</span></span>

<table>
    <tr>
        <td><span data-ttu-id="60bf6-121">除设置新的本地电话号码以外，还可以选择购买免付费号码，或将现有号码移植到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="60bf6-121">In addition to setting up a new phone local phone number, you can choose to purchase a toll-free number or port an existing number to Microsoft 365.</span></span> <span data-ttu-id="60bf6-122">如果选择设置免付费号码，必须购买通话套餐。</span><span class="sxs-lookup"><span data-stu-id="60bf6-122">If you choose to set up a toll-free number, you'll need to purchase a calling plan.</span></span> <span data-ttu-id="60bf6-123">若要将号码移植到 Microsoft 365，在向导完成后，可选择在 [Teams 管理中心](https://admin.teams.microsoft.com)执行此操作。</span><span class="sxs-lookup"><span data-stu-id="60bf6-123">If you want to port a number to Microsoft 365, you'll have an option to do so in the [Teams admin center](https://admin.teams.microsoft.com) after the wizard completes.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="60bf6-124">如果选择将现有的电话号码移植到 Microsoft 365，向导仍然会显示临时电话号码。</span><span class="sxs-lookup"><span data-stu-id="60bf6-124">If you choose to port an existing phone number to Microsoft 365, you'll still see a temporary phone number in the wizard.</span></span> <span data-ttu-id="60bf6-125">这是正常的。</span><span class="sxs-lookup"><span data-stu-id="60bf6-125">This is ok.</span></span> <span data-ttu-id="60bf6-126">完成向导并完成移植过程后，你的电话号码将替代临时电话号码。</span><span class="sxs-lookup"><span data-stu-id="60bf6-126">After you complete the wizard, and you complete the porting process, the temporary phone number will be replaced with your phone number.</span></span>

## <a name="assigning-licenses-to-users"></a><span data-ttu-id="60bf6-127">将许可证分配给用户</span><span class="sxs-lookup"><span data-stu-id="60bf6-127">Assigning licenses to users</span></span>

<table>
    <tr>
        <td><span data-ttu-id="60bf6-128">选择要呼叫或接听 Teams 外部电话（例如呼叫供应商）的组织人员。</span><span class="sxs-lookup"><span data-stu-id="60bf6-128">Select the people in your organization that want to make or receive phone calls outside of Teams (such as calling a supplier).</span></span> <span data-ttu-id="60bf6-129">可选择的人数最多可为你可以提供的可用商务语音许可证数。</span><span class="sxs-lookup"><span data-stu-id="60bf6-129">You can select up to the number of available Business Voice licenses you have available.</span></span> <span data-ttu-id="60bf6-130">如果需要选择更多人数，可在完成向导后购买额外的许可证。</span><span class="sxs-lookup"><span data-stu-id="60bf6-130">If you need more, you can buy additional licenses when the wizard is finished.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="60bf6-131">若要为单个用户将现有的电话号码移植到 Microsoft 365，可在完成向导后执行此操作。</span><span class="sxs-lookup"><span data-stu-id="60bf6-131">If you want to port existing phone numbers to Microsoft 365 for individual users, you can do so after the wizard is complete.</span></span> <span data-ttu-id="60bf6-132">完成移植过程后，移植的电话号码将替代向导选择的临时电话号码。</span><span class="sxs-lookup"><span data-stu-id="60bf6-132">After you complete the porting process, the ported phone numbers will replace the temporary phone numbers selected by the wizard.</span></span>

## <a name="incoming-call-greeting"></a><span data-ttu-id="60bf6-133">传入呼叫问候语</span><span class="sxs-lookup"><span data-stu-id="60bf6-133">Incoming call greeting</span></span>

<table>
    <tr>
        <td><span data-ttu-id="60bf6-134">可以上传多达 5 MB 的声音文件（MP3 或 WAV）来用作问候语。也可以输入自己的问候语，Microsoft 365 将使用文本到语音转换向呼叫方播放它。</span><span class="sxs-lookup"><span data-stu-id="60bf6-134">You can upload a sound file (MP3 or WAV) that's up to 5 Megabytes (MB) to use as a greeting, or you can type out your greeting and Microsoft 365 will use text-to-speech to read it to a caller.</span></span> <span data-ttu-id="60bf6-135">呼叫方呼叫你的公司电话号码时，将首先听到问候语。</span><span class="sxs-lookup"><span data-stu-id="60bf6-135">The greeting will be the first time callers hear when they call your company phone number.</span></span> <span data-ttu-id="60bf6-136">可能需要将字词拼错或使用音标拼写，以确保发音正确。</span><span class="sxs-lookup"><span data-stu-id="60bf6-136">You might need to mis-spell the words or use phonetic spellings to get the pronunciations correct.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a><span data-ttu-id="60bf6-137">呼叫菜单和转接</span><span class="sxs-lookup"><span data-stu-id="60bf6-137">Call menu and forwarding</span></span>

<table>
    <tr>
        <td><span data-ttu-id="60bf6-138">可以将所有呼叫转接到特定用户，也可以设置呼叫菜单供用户选择选项。</span><span class="sxs-lookup"><span data-stu-id="60bf6-138">You can forward all calls to a specific user, or you can set up a call menu they can choose options from.</span></span> <span data-ttu-id="60bf6-139">如果创建呼叫菜单，可以指定选项，使呼叫方可以通过在电话拨号键盘上按号码或通过语音命令读出选项进行选择。</span><span class="sxs-lookup"><span data-stu-id="60bf6-139">If you create a call menu, you can specify options that a caller can select either by pressing a number on a phone's keypad, or by speaking the option via the voice command.</span></span> <span data-ttu-id="60bf6-140">每个菜单选项均可以转接到一位用户。</span><span class="sxs-lookup"><span data-stu-id="60bf6-140">Each menu option can be forwarded to one user.</span></span> <br>
<span data-ttu-id="60bf6-141">可以选择是上传声音文件（MP3 或 WAV，最高达 5MB ）向呼叫方提供指令，还是输入指令。</span><span class="sxs-lookup"><span data-stu-id="60bf6-141">You can choose whether to upload a sound file (MP3 or WAV) that's up to 5MB that gives instructions to the caller or you can type out the instructions instead.</span></span> <span data-ttu-id="60bf6-142">Microsoft 365 将使用文本到语音转换向呼叫方播放指令。</span><span class="sxs-lookup"><span data-stu-id="60bf6-142">Microsoft 365 will use text-to-speech to read the instructions to the caller.</span></span> <span data-ttu-id="60bf6-143">可能需要根据发音拼写字词，以确保发音正确。</span><span class="sxs-lookup"><span data-stu-id="60bf6-143">You might need to spell words phonetically to get the pronunciations right.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

<table>
    <tr>
        <td> <p><span data-ttu-id="60bf6-144">在“概述”页上，“入门”向导采用已输入的所有内容，为你设置商务语音<b></b>。</span><span class="sxs-lookup"><span data-stu-id="60bf6-144">On the <b>Overview</b> page, the Getting Started wizard takes everything you've entered and sets up Business Voice for you.</span></span> <span data-ttu-id="60bf6-145">可以查看将为用户分配哪些电话号码，查看呼叫菜单，听取你的问候语。</span><span class="sxs-lookup"><span data-stu-id="60bf6-145">You can see what phone numbers will be assigned to your users, take a look at your call menu, listen to your greeting, and more.</span></span> </p>
             <p><span data-ttu-id="60bf6-146">设置商务语音需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="60bf6-146">Setting up Business Voice takes several minutes.</span></span> <span data-ttu-id="60bf6-147">可以单击“完成”，我们将继续在后台设置商务语音，也可以等待它完成<b></b>。</span><span class="sxs-lookup"><span data-stu-id="60bf6-147">You can click on <b>Done</b> and we'll continue to set up Business Voice in the background, or you can wait until it's finished.</span></span> <span data-ttu-id="60bf6-148">完成后，转到 <a href="https://admin.teams.microsoft.com" target="_blank">Teams 管理中心</a>中的“语音”，设置其他商务语音功能<b></b>。</span><span class="sxs-lookup"><span data-stu-id="60bf6-148">After it's finished, go to <b>Voice</b> in the <a href="https://admin.teams.microsoft.com" target="_blank">Teams admin center</a> to set up more Business Voice features.</span></span></p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>