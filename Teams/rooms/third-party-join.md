---
title: 启用 Teams 会议室设备以加入第三方会议
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
description: 本文讨论如何配置组织和 Teams 会议室设备，以支持第三方会议加入 Cisco WebEx 和 Zoom。
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682381"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="cbe1b-103">启用 Teams 会议室设备以加入第三方会议</span><span class="sxs-lookup"><span data-stu-id="cbe1b-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="cbe1b-104">Microsoft Teams 会议室设备支持一键式体验，用于加入第三方在线会议，也称为直接来宾加入。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="cbe1b-105">启用后，可以使用 Teams 会议室设备加入 Cisco WebEx 和 Zoom 上托管的会议，就像加入 Microsoft Teams 中托管的会议一样简单。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="cbe1b-106">在从 Teams 会议室设备加入第三方会议之前，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cbe1b-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="cbe1b-107">配置 Teams 会议室设备的 Exchange Online 会议室邮箱，处理第三方会议的邀请。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="cbe1b-108">请确保您的组织没有任何阻止您连接到第三方会议服务的策略。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="cbe1b-109">配置 Teams 会议室设备以允许第三方会议。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="cbe1b-110">以下部分将展示如何执行上述每个步骤。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="cbe1b-111">步骤 1：允许处理第三方会议的日历邀请</span><span class="sxs-lookup"><span data-stu-id="cbe1b-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="cbe1b-112">若要从 Team Room 设备启用一触式加入体验，首先需要设置设备的 Exchange Online 会议室邮箱的日历处理规则。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="cbe1b-113">会议室邮箱需要允许外部会议并保留邮件正文和主题，以便它可以看到加入第三方会议所需的 URL。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="cbe1b-114">若要使用 [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet 设置这些会议室邮箱选项，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cbe1b-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="cbe1b-115">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="cbe1b-116">有关详细信息，请参阅"使用基本身份验证连接到 [Exchange Online PowerShell"](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) 或"使用多重身份验证连接到 [Exchange Online PowerShell"，](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)具体取决于身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="cbe1b-117">运行以下 () ，从会议室邮箱的 UPN 获取用户主体名称：</span><span class="sxs-lookup"><span data-stu-id="cbe1b-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="cbe1b-118">查找与 Teams 会议室设备关联的会议室邮箱的名称，并记下其 UPN。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="cbe1b-119">找到会议室邮箱的 UPN 后，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="cbe1b-120">替换为 `<UserPrincipalName>` 会议室邮箱的 UPN：</span><span class="sxs-lookup"><span data-stu-id="cbe1b-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="cbe1b-121">了解有关 [Exchange Online PowerShell 的更多内容](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="cbe1b-122">步骤 2：配置 Office 365 威胁防护和链接重写</span><span class="sxs-lookup"><span data-stu-id="cbe1b-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="cbe1b-123">若要启用一触式加入体验，会议邀请中需要显示并阅读来自第三方会议的会议加入链接信息。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="cbe1b-124">如果您的组织使用 [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) 高级威胁防护安全链接功能，或者如果您使用第三方解决方案扫描所有传入和传出 URL 中的威胁，则可能会更改会议加入 URL，使 Teams 会议室设备无法识别会议。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="cbe1b-125">若要确保不会发生这种情况，需要将第三方会议服务的 URL 添加到 ATP 安全链接"不重写"列表或第三方 URL 重写异常列表。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="cbe1b-126">若要将第三方会议服务 URL 添加到 ATP 安全链接"不重写"列表，请按照使用 [ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)安全链接设置自定义不重写 URL 列表中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="cbe1b-127">如果使用第三方解决方案，请参阅该解决方案的说明，将 URL 添加到其 URL 重写异常列表。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="cbe1b-128">下面是可能需要添加到 ATP 安全链接"不重写"列表或第三方 URL 重写异常列表的一些示例条目：</span><span class="sxs-lookup"><span data-stu-id="cbe1b-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="cbe1b-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="cbe1b-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="cbe1b-130">**"缩放** `*.zoom.us*` `*.zoom.com*` "， `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="cbe1b-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="cbe1b-131">有关要添加到 ATP 安全链接"不重写"列表或第三方 URL 重写异常列表的完整 URL 列表，请联系要接受其会议邀请的第三方会议服务提供商。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="cbe1b-132">仅将信任的 URL 添加到 ATP 安全链接"不重写"列表或第三方 URL 重写异常列表。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="cbe1b-133">步骤 3：在设备上启用第三方会议</span><span class="sxs-lookup"><span data-stu-id="cbe1b-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="cbe1b-134">需要执行的最后一个步骤是允许每个 Teams 会议室设备加入第三方会议。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="cbe1b-135">第三方会议需要用户名和电子邮件地址来加入。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="cbe1b-136">如果您需要使用的用户名和电子邮件地址不同于设备的会议室邮箱，则需要将它们添加到您的设备。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="cbe1b-137">可以在设备设置或 XML 设置中执行此操作配置文件。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="cbe1b-138">使用设备设置</span><span class="sxs-lookup"><span data-stu-id="cbe1b-138">Use device settings</span></span>

<span data-ttu-id="cbe1b-139">若要使用触摸屏配置 Teams 会议室设备，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cbe1b-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="cbe1b-140">在 Microsoft Teams 会议室设备上，选择"更多 **..."。**</span><span class="sxs-lookup"><span data-stu-id="cbe1b-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="cbe1b-141">选择 **"** 设置"，然后输入设备管理员用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="cbe1b-142">转到"会议 **"** 选项卡，选择 **Cisco WebEx** 和 **/或缩放**。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="cbe1b-143">如果要使用与会议室邮箱关联的用户名和电子邮件地址加入会议，请选择"使用会议室信息 **加入"。**</span><span class="sxs-lookup"><span data-stu-id="cbe1b-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="cbe1b-144">如果要使用备用用户名和电子邮件地址加入会议，请选择"使用自定义信息加入"，并输入想要使用的用户名和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="cbe1b-145">选择 **"保存"并退出**。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-145">Select **Save and exit**.</span></span> <span data-ttu-id="cbe1b-146">设备将重启。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="cbe1b-147">使用 SkypeSettings.xml 配置文件</span><span class="sxs-lookup"><span data-stu-id="cbe1b-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="cbe1b-148">可以将以下设置添加到 `SkypeSettings.xml` 位于 . `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`</span><span class="sxs-lookup"><span data-stu-id="cbe1b-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="cbe1b-149">有关该文件详细信息，请参阅"使用 XML 配置文件远程管理 `SkypeSettings.xml` [Microsoft Teams 会议室控制台设置"。](xml-config-file.md)</span><span class="sxs-lookup"><span data-stu-id="cbe1b-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="cbe1b-150">若要启用 Cisco WebEx 会议，将 `WebExMeetingsEnabled` XML 元素设置为 **True，** 如下所示。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="cbe1b-151">若要启用 Zoom 会议，将 `ZoomMeetingsEnabled` XML 元素设置为 **True，** 如下所示。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="cbe1b-152">可以选择性地指定自定义用户名和电子邮件地址，以通过以下 XML 元素加入第三方会议。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="cbe1b-153">如果提供的值无效，Teams 会议室设备将默认使用会议室邮箱用户名和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="cbe1b-154">若要从 Teams 会议室设备加入 Cisco WebEx 会议，需使用 Cisco WebEx Web 应用程序版本 WBS 40.7 或更高版本托管 Cisco 会议。</span><span class="sxs-lookup"><span data-stu-id="cbe1b-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

