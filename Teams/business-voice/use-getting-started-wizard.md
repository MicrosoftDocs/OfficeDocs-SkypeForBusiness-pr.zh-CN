---
title: 使用“入门”向导设置商务语音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 443a59513d3a3151bdcc83250bf40ec4ac4398bb
ms.sourcegitcommit: 2295a668a6f118b95f010e81150351741572b076
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412619"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a><span data-ttu-id="c69cc-102">使用“入门”向导设置商务语音</span><span class="sxs-lookup"><span data-stu-id="c69cc-102">Use the Getting Started wizard to set up Business Voice</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c69cc-103">本文中的信息仅适用于**包含**通话套餐的商务语音。</span><span class="sxs-lookup"><span data-stu-id="c69cc-103">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="c69cc-104">含通话套餐的商业语音仅在所选国家和地区可用。</span><span class="sxs-lookup"><span data-stu-id="c69cc-104">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="c69cc-105">阅读本文前，请查看[商务语音的国家和地区可用性](country-region-availability.md)，查看你所在的国家或地区是否支持使用包含通话套餐的商务语音。</span><span class="sxs-lookup"><span data-stu-id="c69cc-105">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="c69cc-106">如果你的租户所在的国家或地区不支持含通话套餐的商务语音，请查看[从 Microsoft 经销商或合作伙伴处获取帮助](reseller-partner-support.md)。</span><span class="sxs-lookup"><span data-stu-id="c69cc-106">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="c69cc-107">Microsoft 365 商务语音“入门”向导可让你快速设置以在 Microsoft Teams 中拨打和接听电话。</span><span class="sxs-lookup"><span data-stu-id="c69cc-107">The Getting Started wizard for Microsoft 365 Business Voice gets you set up quickly to make and receive phone calls in Microsoft Teams.</span></span> <span data-ttu-id="c69cc-108">如果是一家刚创立的小型企业，此向导可在几分钟内启动并运行电话号码、呼叫菜单、问候语等。</span><span class="sxs-lookup"><span data-stu-id="c69cc-108">If you're a small business just starting out, the wizard can get you up and running in a few minutes with phone numbers, call menus, greetings, and more.</span></span> <span data-ttu-id="c69cc-109">如果是已创建电话解决方案的大型企业，此向导可帮助设置试点，这样可以让一些用户先试用它，然后再面向所有人推出。</span><span class="sxs-lookup"><span data-stu-id="c69cc-109">If you're a larger business with an established telephony solution, the wizard can help you set up a pilot so a few users can try Business Voice before you roll it out for everyone.</span></span> <span data-ttu-id="c69cc-110">无论你的企业是哪种规模，都可以在完成向导后立刻开始使用商务语音！</span><span class="sxs-lookup"><span data-stu-id="c69cc-110">Either way, you can start using Business Voice as soon as the wizard is finished!</span></span>

<span data-ttu-id="c69cc-111">启动向导前，建议先阅读本文。</span><span class="sxs-lookup"><span data-stu-id="c69cc-111">It's a good idea to read this article before you start the wizard.</span></span> <span data-ttu-id="c69cc-112">当你做好运行此向导的准备后，请选择“[开始使用 Microsoft 365 商务语音](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice)”页面上的“**入门**”。</span><span class="sxs-lookup"><span data-stu-id="c69cc-112">When you're ready to run the wizard, select **Get started** on the [Get started with Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice) page.</span></span> <span data-ttu-id="c69cc-113">请使用创建订阅所用的帐户或作为全局管理员的其他帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c69cc-113">Sign in by using the account you used to create your subscription or another account that's a Global Administrator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c69cc-114">只有在用户的邮箱位于 Microsoft 365 中时，Microsoft Teams 和商务语音才可用。</span><span class="sxs-lookup"><span data-stu-id="c69cc-114">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="c69cc-115">不支持本地 Exchange Server 上的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c69cc-115">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="c69cc-116">入门向导不支持 Skype for Business 混合部署。</span><span class="sxs-lookup"><span data-stu-id="c69cc-116">The Getting Started Wizard doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="c69cc-117">如果你有 Skype for Business 混合部署，并且想要设置商务语音，请检查[在组织中设置电话系统](../setting-up-your-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="c69cc-117">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

<span data-ttu-id="c69cc-118">如果你不想立即自定义任何内容，那就完成了！</span><span class="sxs-lookup"><span data-stu-id="c69cc-118">If you don't want to customize anything immediately, you're done!</span></span> <span data-ttu-id="c69cc-119">你可以立即开始使用商务语音。</span><span class="sxs-lookup"><span data-stu-id="c69cc-119">You can start using Business Voice right away.</span></span>

## <a name="emergency-services-location"></a><span data-ttu-id="c69cc-120">紧急服务位置</span><span class="sxs-lookup"><span data-stu-id="c69cc-120">Emergency services location</span></span>

<table>
    <tr>
        <td><span data-ttu-id="c69cc-121">若要更改紧急地址，请单击“<b>编辑</b>”，然后输入新地址。</span><span class="sxs-lookup"><span data-stu-id="c69cc-121">If you want to change the emergency address, click <b>Edit</b>, and then enter a new address.</span></span> <span data-ttu-id="c69cc-122">系统将验证所提供的地址，确保它合规并且符合紧急响应服务的正确格式。</span><span class="sxs-lookup"><span data-stu-id="c69cc-122">The address that you provide is validated to make sure that it's legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="c69cc-123">系统会将此地址分配给所有用户（将在下一步中为这些用户分配号码）。</span><span class="sxs-lookup"><span data-stu-id="c69cc-123">This address is then assigned to all users that you assign a number to in the next step.</span></span> <span data-ttu-id="c69cc-124">如果你的员工分布在多个位置，请参阅<a href="./customize-business-voice.md">商务语音设计自定义</a>，以便在准备好“入门”向导后添加和分配更多紧急地址。</span><span class="sxs-lookup"><span data-stu-id="c69cc-124">If you have employees in more than one location, see <a href="./customize-business-voice.md">Business Voice design customization</a> to add and assign more emergency addresses after you prepare the Getting Started wizard.</span></span></td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400"></td></tr>
</table>

<span data-ttu-id="c69cc-125">有关详细信息，请参阅[什么是紧急位置、地址和呼叫路由？](../what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="c69cc-125">For more information, see [What are emergency locations, addresses, and call routing](../what-are-emergency-locations-addresses-and-call-routing.md)?</span></span>

## <a name="company-phone-number"></a><span data-ttu-id="c69cc-126">公司电话号码</span><span class="sxs-lookup"><span data-stu-id="c69cc-126">Company phone number</span></span>

<table>
    <tr>
        <td><span data-ttu-id="c69cc-127">除新的本地电话号码以外，还可以购买免付费号码，或将现有号码移植到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c69cc-127">In addition to a new local phone number, you can purchase a toll-free number or port an existing number to Microsoft 365.</span></span> <span data-ttu-id="c69cc-128">若要设置免费电话号码，需购买通讯信用额度。</span><span class="sxs-lookup"><span data-stu-id="c69cc-128">To set up a toll-free number, you need to purchase Communications Credits.</span></span> <span data-ttu-id="c69cc-129">若要将一个或多个号码移植到 Microsoft 365，请在向导完成后，转到 <a href="https://admin.teams.microsoft.com">Teams 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="c69cc-129">To port one or more numbers to Microsoft 365, go to the <a href="https://admin.teams.microsoft.com">Teams admin center</a> after the wizard finishes.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="c69cc-130">如果将现有的电话号码移植到 Microsoft 365，向导仍然会显示临时电话号码。</span><span class="sxs-lookup"><span data-stu-id="c69cc-130">If you port an existing phone number to Microsoft 365, you'll still see a temporary phone number in the wizard.</span></span> <span data-ttu-id="c69cc-131">这是正常情况。</span><span class="sxs-lookup"><span data-stu-id="c69cc-131">This is expected.</span></span> <span data-ttu-id="c69cc-132">完成向导和移植过程后，预先存在的号码将替代临时电话号码。</span><span class="sxs-lookup"><span data-stu-id="c69cc-132">After you complete the wizard and the porting process, the temporary phone number will be replaced by the pre-existing number.</span></span>

## <a name="user-licenses"></a><span data-ttu-id="c69cc-133">用户许可证</span><span class="sxs-lookup"><span data-stu-id="c69cc-133">User licenses</span></span>

<table>
    <tr>
        <td><span data-ttu-id="c69cc-134">若要分配用户许可证，请选择要呼叫或接听 Teams 外部电话（例如呼叫供应商）的组织人员。</span><span class="sxs-lookup"><span data-stu-id="c69cc-134">To assign user licenses, select the people in your organization who need to make or receive phone calls outside of Teams (such as calling a supplier).</span></span> <span data-ttu-id="c69cc-135">你只能分配可供使用的商务语音许可证数量。</span><span class="sxs-lookup"><span data-stu-id="c69cc-135">You can only assign as many Business Voices licenses as you have available.</span></span> <span data-ttu-id="c69cc-136">如果需要选择更多许可证，可在完成向导后购买额外的许可证。</span><span class="sxs-lookup"><span data-stu-id="c69cc-136">If you need more, you can buy additional licenses after the wizard is finished.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="c69cc-137">向导完成后，可将现有的电话号码移植到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c69cc-137">You can port existing phone numbers to Microsoft 365 after the wizard is finished.</span></span> <span data-ttu-id="c69cc-138">完成移植过程后，移植的电话号码将替代向导提供的临时电话号码。</span><span class="sxs-lookup"><span data-stu-id="c69cc-138">After you complete the porting process, the ported phone numbers will replace the temporary phone numbers that the wizard provided.</span></span>

## <a name="incoming-call-greeting"></a><span data-ttu-id="c69cc-139">传入呼叫问候语</span><span class="sxs-lookup"><span data-stu-id="c69cc-139">Incoming-call greeting</span></span>

<table>
    <tr>
        <td><span data-ttu-id="c69cc-140">可以上传高达 5 MB 的声音文件（MP3 或 WAV）来用作呼叫问候语，也可以输入自己的问候语，Microsoft 365 将使用文本到语音转换向呼叫方播放它。</span><span class="sxs-lookup"><span data-stu-id="c69cc-140">You can upload a sound file (MP3 or WAV) of up to 5 Megabytes (MB) to use as a call greeting, or you can type your greeting, and Microsoft 365 will use text-to-speech to read it to the caller.</span></span> <span data-ttu-id="c69cc-141">呼叫方呼叫你的公司电话号码时，将首先听到问候语。</span><span class="sxs-lookup"><span data-stu-id="c69cc-141">The greeting will be the first thing callers hear when they call your company phone number.</span></span> <span data-ttu-id="c69cc-142">对于文本到语音转换，可能需要使用音标拼写来确保发音正确。</span><span class="sxs-lookup"><span data-stu-id="c69cc-142">For text-to-speech, you might need to use phonetic spellings to get the pronunciations correct.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a><span data-ttu-id="c69cc-143">呼叫菜单和转接</span><span class="sxs-lookup"><span data-stu-id="c69cc-143">Call menu and forwarding</span></span>

<table>
    <tr>
        <td><span data-ttu-id="c69cc-144">可以将所有呼叫转接到特定用户，也可以设置菜单供呼叫方选择选项。</span><span class="sxs-lookup"><span data-stu-id="c69cc-144">You can forward all calls to a specific user, or you can set up a menu that the caller can choose options from.</span></span> <span data-ttu-id="c69cc-145">如果创建呼叫菜单，则可以指定选项，使呼叫方可以通过语音或通过按下电话键盘上的数字来进行选择。</span><span class="sxs-lookup"><span data-stu-id="c69cc-145">If you create a call menu, you specify options that the caller can select by voice or by pressing a number on a phone's keypad.</span></span> <span data-ttu-id="c69cc-146">每个菜单选项都可以将用户转接到特定用户。</span><span class="sxs-lookup"><span data-stu-id="c69cc-146">Each menu option can forward calls to a specific user.</span></span><br><br>
        <span data-ttu-id="c69cc-147">你可以上传高达 5 MB 的声音文件（MP3 或 WAV），以便向呼叫方提供指令，也可以输入指令。</span><span class="sxs-lookup"><span data-stu-id="c69cc-147">You can upload a sound file (MP3 or WAV) of up to 5 MB that gives instructions to the caller, or you can type the instructions.</span></span> <span data-ttu-id="c69cc-148">Microsoft 365 将使用文本到语音转换向呼叫方播放这些指令。</span><span class="sxs-lookup"><span data-stu-id="c69cc-148">Microsoft 365 will use text-to-speech to read them to the caller.</span></span> <span data-ttu-id="c69cc-149">可能需要根据发音拼写字词，以确保发音正确。</span><span class="sxs-lookup"><span data-stu-id="c69cc-149">You might need to spell words phonetically to get the pronunciations right.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="c69cc-150">入门向导可帮助你设置简单的呼叫菜单，让你快速启动并运行。</span><span class="sxs-lookup"><span data-stu-id="c69cc-150">The Getting Started wizard helps you set up a simple call menu to get you up and running quickly.</span></span> <span data-ttu-id="c69cc-151">如果你有多个想要设置呼叫菜单的电话号码，或者如果想要设置更复杂的呼叫菜单（也称为自动助理），请在完成该向导后参阅[设置云自动助理](set-up-auto-attendants.md)。</span><span class="sxs-lookup"><span data-stu-id="c69cc-151">If you have multiple phone numbers that you want to set up call menus for or you want to set up more complex call menus (also called auto attendants), see [Set up a Cloud auto attendant](set-up-auto-attendants.md) after you finish the wizard.</span></span>

<table>
    <tr>
        <td> <p><span data-ttu-id="c69cc-152">“入门”向导可获取你输入的信息并设置商务语音。</span><span class="sxs-lookup"><span data-stu-id="c69cc-152">The Getting Started wizard takes the information that you enter and sets up Business Voice.</span></span> <span data-ttu-id="c69cc-153">在“<b>概述</b>”页面上，可以查看将为用户分配哪些电话号码，查看呼叫菜单，听取你的问候语。</span><span class="sxs-lookup"><span data-stu-id="c69cc-153">On the <b>Overview</b> page, you can see what phone numbers are assigned to your users, look at your call menu, listen to your greeting, and more.</span></span></p>
             <p><span data-ttu-id="c69cc-154">设置需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="c69cc-154">Setup takes several minutes.</span></span> <span data-ttu-id="c69cc-155">如果你选择“<b>完成</b>”，我们将继续在后台设置商务语音。</span><span class="sxs-lookup"><span data-stu-id="c69cc-155">If you select <b>Done</b>, we'll continue to set up Business Voice in the background.</span></span> <span data-ttu-id="c69cc-156">或者只是等到设置完成。</span><span class="sxs-lookup"><span data-stu-id="c69cc-156">Or just wait until setup is finished.</span></span> <span data-ttu-id="c69cc-157">完成后，转到 <a href="https://admin.teams.microsoft.com" target="_blank">Teams 管理中心</a>中的“语音”，设置其他商务语音功能<b></b>。</span><span class="sxs-lookup"><span data-stu-id="c69cc-157">After it's finished, go to <b>Voice</b> in the <a href="https://admin.teams.microsoft.com" target="_blank">Teams admin center</a> to set up more Business Voice features.</span></span></p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>
