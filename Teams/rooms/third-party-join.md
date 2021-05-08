---
title: 启用Teams 会议室设备加入第三方会议
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
description: 本文讨论如何配置组织和设备Teams 会议室以支持加入 Cisco WebEx 和 Zoom 的第三方会议。
ms.openlocfilehash: c8f6bda7680ccd3107c313c87001902e442518c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117370"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="04e3c-103">启用Teams会议室设备加入第三方会议</span><span class="sxs-lookup"><span data-stu-id="04e3c-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="04e3c-104">Microsoft Teams 会议室设备支持一键式体验来加入第三方联机会议，也称为直接来宾加入。</span><span class="sxs-lookup"><span data-stu-id="04e3c-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="04e3c-105">启用后，可以使用 Teams 会议室 设备加入 Cisco WebEx 和 Zoom 上托管的会议，就像加入在 Microsoft Teams 中托管的会议一样。</span><span class="sxs-lookup"><span data-stu-id="04e3c-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="04e3c-106">在从设备加入第三方Teams 会议室之前，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="04e3c-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="04e3c-107">将Teams 会议室设备Exchange Online会议室邮箱配置为处理第三方会议的邀请。</span><span class="sxs-lookup"><span data-stu-id="04e3c-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="04e3c-108">确保您的组织没有任何阻止您连接到第三方会议服务的策略。</span><span class="sxs-lookup"><span data-stu-id="04e3c-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="04e3c-109">配置Teams 会议室设备以允许第三方会议。</span><span class="sxs-lookup"><span data-stu-id="04e3c-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="04e3c-110">以下部分将展示如何执行上述每个步骤。</span><span class="sxs-lookup"><span data-stu-id="04e3c-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="04e3c-111">步骤 1：允许处理第三方会议的日历邀请</span><span class="sxs-lookup"><span data-stu-id="04e3c-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="04e3c-112">若要从 Team Room 设备启用一键式加入体验，首先需要为设备的会议室邮箱设置Exchange Online规则。</span><span class="sxs-lookup"><span data-stu-id="04e3c-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="04e3c-113">会议室邮箱需要允许外部会议并保留邮件正文和主题，以便它可以看到加入第三方会议所需的 URL。</span><span class="sxs-lookup"><span data-stu-id="04e3c-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="04e3c-114">若要使用 [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet 设置这些会议室邮箱选项，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="04e3c-114">To set these room mailbox options using the [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="04e3c-115">连接 PowerShell Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="04e3c-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="04e3c-116">有关详细信息，请参阅 连接 Exchange Online 使用基本身份验证连接[PowerShell，](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)或者Exchange Online多重身份验证将 PowerShell 与[PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)相连接，具体取决于身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="04e3c-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="04e3c-117">通过运行以下 (，) 获取会议室邮箱的用户主体名称或 UPN 名称：</span><span class="sxs-lookup"><span data-stu-id="04e3c-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="04e3c-118">查找与设备关联的会议室邮箱Teams 会议室并记下其 UPN。</span><span class="sxs-lookup"><span data-stu-id="04e3c-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="04e3c-119">找到会议室邮箱的 UPN 后，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="04e3c-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="04e3c-120">将 `<UserPrincipalName>` 替换为会议室邮箱的 UPN：</span><span class="sxs-lookup"><span data-stu-id="04e3c-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="04e3c-121">详细了解[PowerShell Exchange Online。](/powershell/exchange/exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="04e3c-121">Learn more about [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="04e3c-122">步骤 2：配置Office 365威胁防护和链接重写</span><span class="sxs-lookup"><span data-stu-id="04e3c-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="04e3c-123">若要启用一键式加入体验，会议邀请中需要显示并阅读来自第三方会议的会议加入链接信息。</span><span class="sxs-lookup"><span data-stu-id="04e3c-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="04e3c-124">如果你的组织使用 Office 365 高级威胁防护[保险箱 链接](/microsoft-365/security/office-365-security/atp-safe-links)功能，或者如果你使用扫描所有传入和传出 URL 以发现威胁的第三方解决方案，它可能会更改会议加入 URL，使 Teams 会议室 设备无法识别会议。</span><span class="sxs-lookup"><span data-stu-id="04e3c-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="04e3c-125">若要确保不会发生此情况，需要将第三方会议服务的 URL 添加到 ATP 保险箱 链接"不重写"列表或第三方 URL 重写异常列表。</span><span class="sxs-lookup"><span data-stu-id="04e3c-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="04e3c-126">若要将第三方会议服务 URL 添加到 ATP 保险箱 链接"不重写"列表，请按照使用[ATP](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)链接设置自定义不重写 URL 列表中的步骤保险箱链接。</span><span class="sxs-lookup"><span data-stu-id="04e3c-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="04e3c-127">如果使用第三方解决方案，请参阅该解决方案的说明，将 URL 添加到其 URL 重写异常列表。</span><span class="sxs-lookup"><span data-stu-id="04e3c-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="04e3c-128">下面是可能需要添加到 AT 保险箱P 链接链接"不重写"列表或第三方 URL 重写异常列表的一些示例条目：</span><span class="sxs-lookup"><span data-stu-id="04e3c-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="04e3c-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="04e3c-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="04e3c-130">**缩放** `*.zoom.us*` `*.zoom.com*` 、、 `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="04e3c-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="04e3c-131">有关要添加到 ATP 保险箱 链接"不重写"列表或第三方 URL 重写异常列表的完整 URL 列表，请联系要接受其会议邀请的第三方会议服务提供商。</span><span class="sxs-lookup"><span data-stu-id="04e3c-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="04e3c-132">仅将信任的 URL 添加到 ATP 保险箱链接"不重写"列表或第三方 URL 重写异常列表。</span><span class="sxs-lookup"><span data-stu-id="04e3c-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="04e3c-133">步骤 3：在设备上启用第三方会议</span><span class="sxs-lookup"><span data-stu-id="04e3c-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="04e3c-134">需要执行的最后一个步骤是允许Teams 会议室设备加入第三方会议。</span><span class="sxs-lookup"><span data-stu-id="04e3c-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="04e3c-135">第三方会议需要用户名和密码来加入。</span><span class="sxs-lookup"><span data-stu-id="04e3c-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="04e3c-136">如果需要使用的用户名和电子邮件地址不同于设备的会议室邮箱，则需要将其添加到设备。</span><span class="sxs-lookup"><span data-stu-id="04e3c-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="04e3c-137">可以在设备设置或 XML 设置中执行此操作配置文件。</span><span class="sxs-lookup"><span data-stu-id="04e3c-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="04e3c-138">使用设备设置</span><span class="sxs-lookup"><span data-stu-id="04e3c-138">Use device settings</span></span>

<span data-ttu-id="04e3c-139">若要使用Teams 会议室配置设备，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="04e3c-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="04e3c-140">在"Microsoft Teams 会议室上，选择"更多 **..."。**</span><span class="sxs-lookup"><span data-stu-id="04e3c-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="04e3c-141">选择 **设置"，** 然后输入设备管理员用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="04e3c-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="04e3c-142">转到"会议 **"选项卡** ，选择 **"Cisco WebEx"** 和 **"缩放"** 或两者。</span><span class="sxs-lookup"><span data-stu-id="04e3c-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="04e3c-143">如果要使用与会议室邮箱关联的用户名和电子邮件地址加入会议，请选择"**使用会议室信息加入"。**</span><span class="sxs-lookup"><span data-stu-id="04e3c-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="04e3c-144">如果要使用备用用户名和电子邮件地址加入会议，请选择"使用自定义信息加入"，并输入想要使用的用户名和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="04e3c-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="04e3c-145">选择 **"保存并退出"。**</span><span class="sxs-lookup"><span data-stu-id="04e3c-145">Select **Save and exit**.</span></span> <span data-ttu-id="04e3c-146">设备将重启。</span><span class="sxs-lookup"><span data-stu-id="04e3c-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="04e3c-147">使用 SkypeSettings.xml 配置文件</span><span class="sxs-lookup"><span data-stu-id="04e3c-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="04e3c-148">可以将以下设置添加到 `SkypeSettings.xml` 位于 中的 文件 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。</span><span class="sxs-lookup"><span data-stu-id="04e3c-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="04e3c-149">有关文件详细信息，请参阅使用 XML 配置文件 `SkypeSettings.xml` [Microsoft Teams 会议室远程管理主机设置](xml-config-file.md)。</span><span class="sxs-lookup"><span data-stu-id="04e3c-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="04e3c-150">若要启用 Cisco WebEx 会议，将 `WebExMeetingsEnabled` XML 元素设置为 **True，** 如下所示。</span><span class="sxs-lookup"><span data-stu-id="04e3c-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="04e3c-151">若要启用 Zoom 会议，将 `ZoomMeetingsEnabled` XML 元素设置为 **True，** 如下所示。</span><span class="sxs-lookup"><span data-stu-id="04e3c-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="04e3c-152">可以选择性地指定自定义用户名和电子邮件地址，以使用以下 XML 元素加入第三方会议。</span><span class="sxs-lookup"><span data-stu-id="04e3c-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="04e3c-153">如果提供的值无效，则Teams 会议室默认使用会议室邮箱用户名和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="04e3c-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="04e3c-154">若要从 Teams 会议室加入 Cisco WebEx 会议，需使用 Cisco WebEx Web 应用程序版本 WBS 40.7 或更高版本来托管 Cisco 会议。</span><span class="sxs-lookup"><span data-stu-id="04e3c-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>