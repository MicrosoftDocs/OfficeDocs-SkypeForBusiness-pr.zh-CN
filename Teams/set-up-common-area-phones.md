---
title: 设置"公共区域"电话许可证
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '了解如何为大厅、接收区和会议室设置公用区域电话 '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117110"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="15ba0-103">为 Microsoft Teams 设置公共区域电话许可证</span><span class="sxs-lookup"><span data-stu-id="15ba0-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="15ba0-104">公用区域电话不支持语音邮件。</span><span class="sxs-lookup"><span data-stu-id="15ba0-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="15ba0-105">公用区域电话通常放置在大厅等区域，或者供许多人进行呼叫的另一区域;例如，前台区域、大厅或会议电话。</span><span class="sxs-lookup"><span data-stu-id="15ba0-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="15ba0-106">常用区域电话使用与公用区域服务许可证绑定电话登录。</span><span class="sxs-lookup"><span data-stu-id="15ba0-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="15ba0-107">还必须适当设置 TeamsIPPhone 策略，使手机具有共同的区域用户体验。</span><span class="sxs-lookup"><span data-stu-id="15ba0-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="15ba0-108">在以下步骤中，我们将帮助你设置一个帐户电话系统为组织部署公用区域电话。</span><span class="sxs-lookup"><span data-stu-id="15ba0-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="15ba0-109">为获得更完整的会议室体验（包括音频会议），请考虑购买具有会议室设备的专用会议许可证。</span><span class="sxs-lookup"><span data-stu-id="15ba0-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="15ba0-110">首先，需要购买公共区域电话 (CAP) 许可证，并确保拥有经过认证的电话。</span><span class="sxs-lookup"><span data-stu-id="15ba0-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="15ba0-111">若要搜索并了解有关认证电话的信息，请转到["Microsoft Teams设备"。](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="15ba0-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="15ba0-112">第 1 步 - 购买许可证</span><span class="sxs-lookup"><span data-stu-id="15ba0-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="15ba0-113">在Microsoft 365中心，转到"**计费**  >  **购买服务**"，然后展开"**其他计划"。**</span><span class="sxs-lookup"><span data-stu-id="15ba0-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![显示"公共区域"磁贴电话屏幕截图](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="15ba0-115">选择 **"公共区域电话**  >  **立即购买"。**</span><span class="sxs-lookup"><span data-stu-id="15ba0-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="15ba0-116">在"结帐"页面上，单击"**立即购买"。**</span><span class="sxs-lookup"><span data-stu-id="15ba0-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="15ba0-117">展开 **附加内容订阅，** 然后单击购买通话套餐。</span><span class="sxs-lookup"><span data-stu-id="15ba0-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="15ba0-118">选择"国内 **呼叫计划"或\*\*\*\*"国内和国际呼叫计划"。**</span><span class="sxs-lookup"><span data-stu-id="15ba0-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="15ba0-119">如果使用 Microsoft 电话直接路由，则不需要呼叫计划许可证。</span><span class="sxs-lookup"><span data-stu-id="15ba0-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="15ba0-120">无需添加许可证电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="15ba0-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="15ba0-121">许可证包含在公共区域电话许可证中。</span><span class="sxs-lookup"><span data-stu-id="15ba0-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="15ba0-122">有关许可证详细信息，请参阅Microsoft Teams[附加许可。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="15ba0-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="15ba0-123">公共区域电话支持：</span><span class="sxs-lookup"><span data-stu-id="15ba0-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="15ba0-124">公共区域电话</span><span class="sxs-lookup"><span data-stu-id="15ba0-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="15ba0-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="15ba0-125">Skype for Business</span></span> |   <span data-ttu-id="15ba0-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="15ba0-126">&#x2714;</span></span> |
|<span data-ttu-id="15ba0-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15ba0-127">Microsoft Teams</span></span> |   <span data-ttu-id="15ba0-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="15ba0-128">&#x2714;</span></span> |
|<span data-ttu-id="15ba0-129">电话系统</span><span class="sxs-lookup"><span data-stu-id="15ba0-129">Phone System</span></span> |    <span data-ttu-id="15ba0-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="15ba0-130">&#x2714;</span></span> |
|<span data-ttu-id="15ba0-131">音频会议</span><span class="sxs-lookup"><span data-stu-id="15ba0-131">Audio Conferencing</span></span> |       <span data-ttu-id="15ba0-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="15ba0-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="15ba0-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="15ba0-133">Microsoft Intune</span></span> |    <span data-ttu-id="15ba0-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="15ba0-134">&#x2718;</span></span> |
|<span data-ttu-id="15ba0-135">全球可用性</span><span class="sxs-lookup"><span data-stu-id="15ba0-135">Worldwide Availability</span></span> |       <span data-ttu-id="15ba0-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="15ba0-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="15ba0-137">频道可用性</span><span class="sxs-lookup"><span data-stu-id="15ba0-137">Channel Availability</span></span> |    <span data-ttu-id="15ba0-138">EA、EAS、CSP、GCC、EES、Web Direct</span><span class="sxs-lookup"><span data-stu-id="15ba0-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="15ba0-139">&sup1;公用区域电话可以通过会议组织者提供的拨入号码加入音频会议</span><span class="sxs-lookup"><span data-stu-id="15ba0-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="15ba0-140">&sup2;在主权云中不可用</span><span class="sxs-lookup"><span data-stu-id="15ba0-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="15ba0-141">第 2 步 - 为手机创建一个新的用户帐户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="15ba0-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="15ba0-142">在Microsoft 365管理中心，转到 **"活动**  >  **用户""**  >  **添加用户"。**</span><span class="sxs-lookup"><span data-stu-id="15ba0-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="15ba0-143">输入用户名，例如"Main"作为名字，输入"接收"作为第二个名称。</span><span class="sxs-lookup"><span data-stu-id="15ba0-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="15ba0-144">如果没有自动生成显示名称如"主前台"，请输入一个密码。</span><span class="sxs-lookup"><span data-stu-id="15ba0-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="15ba0-145">输入用户名，例如"MainReception"或"Mainlobby"。</span><span class="sxs-lookup"><span data-stu-id="15ba0-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="15ba0-146">对于公用区域电话，你可能希望手动设置密码，或者拥有所有公用区域电话的相同密码。</span><span class="sxs-lookup"><span data-stu-id="15ba0-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="15ba0-147">此外，还可以考虑清除" **使此用户首次登录时更改** 其密码"复选框。</span><span class="sxs-lookup"><span data-stu-id="15ba0-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="15ba0-148">将许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="15ba0-148">Assign the licenses to the user.</span></span> <span data-ttu-id="15ba0-149">在同一页面上，点击展开 **产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="15ba0-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="15ba0-150">打开"公用区域"电话，选择"国内呼叫计划"**或"\*\*\*\*国内和国际呼叫计划"。**</span><span class="sxs-lookup"><span data-stu-id="15ba0-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="15ba0-152">如果使用 Microsoft 电话直接路由，则无需分配呼叫计划许可证。</span><span class="sxs-lookup"><span data-stu-id="15ba0-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="15ba0-153">有关详细信息，请参阅 [向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="15ba0-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="15ba0-154">第 3 步 - 将电话号码分配给公共区域电话用户帐户</span><span class="sxs-lookup"><span data-stu-id="15ba0-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="15ba0-155">使用Teams管理中心向用户分配号码。</span><span class="sxs-lookup"><span data-stu-id="15ba0-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="15ba0-156">在"Teams管理中心"中，选择 **"语音**  >  **电话号码"。**</span><span class="sxs-lookup"><span data-stu-id="15ba0-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="15ba0-157">从电话号码列表中选择一个号码，然后点击 **分配**。</span><span class="sxs-lookup"><span data-stu-id="15ba0-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="15ba0-158">在 **"分配** "页面上的"语音用户"框中，键入将使用该电话的用户名，然后在"选择语音用户" **下拉列表中选择该用户** 。</span><span class="sxs-lookup"><span data-stu-id="15ba0-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="15ba0-159">接下来，需要添加紧急地址。</span><span class="sxs-lookup"><span data-stu-id="15ba0-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="15ba0-160">从 **下拉列表中选择**"按城市搜索、按说明搜索"或"按位置搜索"，然后在文本框中输入城市、说明或位置。</span><span class="sxs-lookup"><span data-stu-id="15ba0-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="15ba0-161">搜索后，在" **选择紧急地址"** 下查找以选择正确的地址。</span><span class="sxs-lookup"><span data-stu-id="15ba0-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="15ba0-162">点击 **保存**，你的用户将显示如下：</span><span class="sxs-lookup"><span data-stu-id="15ba0-162">Click **Save** and your user should look like this:</span></span>

   ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="15ba0-164">用户只有在应用了许可证后电话系统显示。</span><span class="sxs-lookup"><span data-stu-id="15ba0-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="15ba0-165">如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。</span><span class="sxs-lookup"><span data-stu-id="15ba0-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="15ba0-166">有关详细信息，请参阅 [获取用户的电话号码](getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="15ba0-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="15ba0-167">您也可以将您拥有的电话号码与另一家运营商联系并"转Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="15ba0-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="15ba0-168">请参阅[将电话号码转移到 Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="15ba0-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>