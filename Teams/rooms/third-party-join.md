---
title: 允许团队聊天室设备加入第三方会议
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文介绍如何配置组织和团队室设备以支持加入 Cisco WebEx 和缩放的第三方会议。
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372211"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="92b54-103">允许团队会议室设备加入第三方会议</span><span class="sxs-lookup"><span data-stu-id="92b54-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="92b54-104">Microsoft 团队会议室设备支持连接第三方在线会议的一种触摸体验。</span><span class="sxs-lookup"><span data-stu-id="92b54-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings.</span></span> <span data-ttu-id="92b54-105">启用后，你可以使用团队聊天室设备加入在 Cisco WebEx 和缩放<sup>1</sup>上托管的会议，就像可以加入 Microsoft 团队中托管的会议一样轻松。</span><span class="sxs-lookup"><span data-stu-id="92b54-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom<sup>1</sup> just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="92b54-106">在你可以从团队聊天室设备加入第三方会议之前，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="92b54-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="92b54-107">配置团队聊天室设备的 Exchange Online 聊天室邮箱以处理第三方会议的邀请</span><span class="sxs-lookup"><span data-stu-id="92b54-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings</span></span>
2. <span data-ttu-id="92b54-108">请确保你的组织没有任何策略，这些策略将阻止你连接到第三方会议服务</span><span class="sxs-lookup"><span data-stu-id="92b54-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services</span></span>
3. <span data-ttu-id="92b54-109">将团队聊天室设备配置为允许第三方会议</span><span class="sxs-lookup"><span data-stu-id="92b54-109">Configure your Teams Rooms devices to allow third-party meetings</span></span>

<span data-ttu-id="92b54-110">以下部分介绍了如何执行每个步骤。</span><span class="sxs-lookup"><span data-stu-id="92b54-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="92b54-111">步骤1：允许第三方会议的日历邀请处理</span><span class="sxs-lookup"><span data-stu-id="92b54-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="92b54-112">若要从团队聊天室设备启用一条触摸式加入体验，首先需要为设备的 Exchange Online 会议室邮箱设置日历处理规则。</span><span class="sxs-lookup"><span data-stu-id="92b54-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="92b54-113">会议室邮箱需要允许外部会议并保留邮件正文和主题，以便它可以看到加入第三方会议所需的 URL。</span><span class="sxs-lookup"><span data-stu-id="92b54-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="92b54-114">若要使用[CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet 设置这些聊天室邮箱选项，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="92b54-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="92b54-115">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="92b54-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="92b54-116">有关详细信息，请参阅使用[基本身份验证连接到 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)或[使用多重身份验证连接到 exchange online powershell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)，具体取决于你的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="92b54-116">For more information, see [Connect to Exchange Online Powershell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="92b54-117">通过运行以下命令来获取聊天室邮箱的用户主体名称（UPN）：</span><span class="sxs-lookup"><span data-stu-id="92b54-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. <span data-ttu-id="92b54-118">查找与团队聊天室设备关联的聊天室邮箱的名称，并记下其 UPN</span><span class="sxs-lookup"><span data-stu-id="92b54-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN</span></span>

4. <span data-ttu-id="92b54-119">找到聊天室邮箱的 UPN 后，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="92b54-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="92b54-120">替换 `<UserPrincipalName>` 为聊天室邮箱的 UPN：</span><span class="sxs-lookup"><span data-stu-id="92b54-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="92b54-121">了解有关[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="92b54-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="92b54-122">步骤2：配置 Office 365 威胁防护和链接重写</span><span class="sxs-lookup"><span data-stu-id="92b54-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="92b54-123">若要启用单一触控的连接体验，需要在会议邀请中演示和阅读会议邀请中的会议加入链接信息。</span><span class="sxs-lookup"><span data-stu-id="92b54-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="92b54-124">如果你的组织使用[Office 365 高级威胁防护安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)   功能，或者你使用第三方解决方案来扫描所有传入和传出的威胁，则可能会更改会议加入 Url 并使团队聊天室设备无法识别会议。</span><span class="sxs-lookup"><span data-stu-id="92b54-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="92b54-125">若要确保不会发生这种情况，你需要将第三方会议服务的 Url 添加到 ATP 安全链接 "不重写" 列表或第三方 URL 重写例外列表。</span><span class="sxs-lookup"><span data-stu-id="92b54-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="92b54-126">若要将第三方会议服务 Url 添加到 ATP 安全链接 "不重写" 列表，请按照[使用 ATP 安全链接设置自定义的 "不重写 url" 列表](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="92b54-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="92b54-127">如果你使用第三方解决方案，请参阅该解决方案的说明，将 Url 添加到其 URL 重写例外列表。</span><span class="sxs-lookup"><span data-stu-id="92b54-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="92b54-128">下面是一些可能需要添加到 ATP 安全链接 "不重写" 列表或第三方 URL 重写例外列表的示例条目：</span><span class="sxs-lookup"><span data-stu-id="92b54-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="92b54-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="92b54-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="92b54-130">**缩放** `*zoom.us*` 、 `*zoom.com*``*zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="92b54-130">**Zoom** `*zoom.us*`, `*zoom.com*`, `*zoomgov.com*`</span></span>

<span data-ttu-id="92b54-131">若要将 Url 的完整列表添加到你的 ATP 安全链接 "请勿重写" 列表或第三方 URL 重写例外列表，请联系你想要接受会议邀请的第三方会议服务提供商。</span><span class="sxs-lookup"><span data-stu-id="92b54-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="92b54-132">仅将你信任的 Url 添加到你的 ATP 安全链接 "请勿重写" 列表或第三方 URL 重写例外列表。</span><span class="sxs-lookup"><span data-stu-id="92b54-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="92b54-133">步骤3：在设备上启用第三方会议</span><span class="sxs-lookup"><span data-stu-id="92b54-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="92b54-134">您需要执行的最后一步是允许每个团队房间设备加入第三方会议。</span><span class="sxs-lookup"><span data-stu-id="92b54-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="92b54-135">第三方会议需要用户名和电子邮件地址才能加入。</span><span class="sxs-lookup"><span data-stu-id="92b54-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="92b54-136">如果需要使用的用户名和电子邮件地址与设备的会议室邮箱不同，则需要将其添加到你的设备。</span><span class="sxs-lookup"><span data-stu-id="92b54-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="92b54-137">你可以在设备设置或 XML 配置文件中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="92b54-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="92b54-138">使用设备设置</span><span class="sxs-lookup"><span data-stu-id="92b54-138">Use device settings</span></span>

<span data-ttu-id="92b54-139">若要使用其触摸屏配置团队聊天室设备，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="92b54-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="92b54-140">在 Microsoft 团队聊天室设备上，选择 " **更多 ...** "</span><span class="sxs-lookup"><span data-stu-id="92b54-140">On the Microsoft Teams Rooms device, select **More ...**</span></span>
2. <span data-ttu-id="92b54-141">选择 " **设置**"，然后输入设备管理员的用户名和密码</span><span class="sxs-lookup"><span data-stu-id="92b54-141">Select **Settings**, and then enter the device administrator username and password</span></span>
3. <span data-ttu-id="92b54-142">转到 " **会议"**   选项卡，选择 " **Cisco WebEx**"、"**缩放**<sup>1</sup>" 或两者</span><span class="sxs-lookup"><span data-stu-id="92b54-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**<sup>1</sup>, or both</span></span>
4. <span data-ttu-id="92b54-143">如果要加入与会议室邮箱关联的用户名和电子邮件地址的会议，请选择 "**加入会议室信息**"</span><span class="sxs-lookup"><span data-stu-id="92b54-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**</span></span>
5. <span data-ttu-id="92b54-144">如果想要使用备用用户名和电子邮件地址加入会议，请选择 "**使用自定义信息加入**"，然后输入要使用的用户名和电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="92b54-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use</span></span>
6. <span data-ttu-id="92b54-145">选择 " **保存并退出**"。</span><span class="sxs-lookup"><span data-stu-id="92b54-145">Select **Save and exit**.</span></span> <span data-ttu-id="92b54-146">您的设备将重新启动。</span><span class="sxs-lookup"><span data-stu-id="92b54-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="92b54-147">使用 SkypeSettings.xml 配置文件</span><span class="sxs-lookup"><span data-stu-id="92b54-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="92b54-148">可将以下设置添加到 `SkypeSettings.xml` 位于中的文件 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。</span><span class="sxs-lookup"><span data-stu-id="92b54-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="92b54-149">有关文件的详细信息 `SkypeSettings.xml` ，请参阅[使用 XML 配置文件远程管理 Microsoft 团队聊天室控制台设置](xml-config-file.md)。</span><span class="sxs-lookup"><span data-stu-id="92b54-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="92b54-150">若要启用 Cisco WebEx 会议，请将 `WebExMeetingsEnabled` XML 元素设置为 **True**，如下所示。</span><span class="sxs-lookup"><span data-stu-id="92b54-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="92b54-151">若要启用 "缩放<sup>1</sup>会议"，请将 `ZoomMeetingsEnabled` XML 元素设置为 **True**，如下所示。</span><span class="sxs-lookup"><span data-stu-id="92b54-151">To enable Zoom<sup>1</sup> meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="92b54-152">你可以选择指定自定义用户名和电子邮件地址，以便使用以下 XML 元素加入第三方会议。</span><span class="sxs-lookup"><span data-stu-id="92b54-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="92b54-153">如果你提供的值无效，团队聊天室设备将默认为使用会议室邮箱用户名和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="92b54-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="92b54-154">要从团队房间设备加入 Cisco WebEx 会议，需要使用 Cisco WebEx web 应用程序版本 WBS 40.7 或更高版本托管 Cisco 会议。</span><span class="sxs-lookup"><span data-stu-id="92b54-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

<span data-ttu-id="92b54-155"><sup>1</sup>缩放会议目前仅可通过技术访问计划选择 Microsoft 团队聊天室客户（点击）。</span><span class="sxs-lookup"><span data-stu-id="92b54-155"><sup>1</sup> Zoom meetings join is currently only available to select Microsoft Teams Rooms customers through Technology Access Program (TAP).</span></span>
