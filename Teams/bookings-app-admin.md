---
title: Microsoft 团队中的预订应用和虚拟访问
author: mattpennathe3rd
ms.author: v-mapenn
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: 通过预定应用进行 Microsoft 团队和虚拟访问
ms.openlocfilehash: b00a42ab7d0b590d706b8e3218f24d13b945b731
ms.sourcegitcommit: ebdad71a8d393466e33a2fdc8606d882a6007588
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280282"
---
# <a name="bookings-app-and-virtual-visits-in-microsoft-teams"></a><span data-ttu-id="6cefa-103">Microsoft 团队中的预订应用和虚拟访问</span><span class="sxs-lookup"><span data-stu-id="6cefa-103">Bookings app and virtual visits in Microsoft Teams</span></span>

<span data-ttu-id="6cefa-104">Microsoft 团队中的 "预定" 应用提供了一种简单的方式来安排人员和虚拟约会，例如医疗保健走访、财务咨询、访谈、客户支持、教育办公时间等。</span><span class="sxs-lookup"><span data-stu-id="6cefa-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="6cefa-105">计划程序可以管理多个部门和员工日历，以及与内部和外部与会者的通信，从单个体验开始。</span><span class="sxs-lookup"><span data-stu-id="6cefa-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="6cefa-106">虚拟约会本身是通过 Microsoft 团队会议举行的，它提供了强健的视频会议功能。</span><span class="sxs-lookup"><span data-stu-id="6cefa-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="6cefa-107">只有计划程序需要在团队中安装预定应用。</span><span class="sxs-lookup"><span data-stu-id="6cefa-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="6cefa-108">从事虚拟约会或参与虚拟约会的职员不需要该应用。</span><span class="sxs-lookup"><span data-stu-id="6cefa-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="6cefa-109">他们可以直接从其 Outlook 或团队日历或其预订确认电子邮件中的链接加入约会。</span><span class="sxs-lookup"><span data-stu-id="6cefa-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="6cefa-110">在团队中使用预定应用的先决条件</span><span class="sxs-lookup"><span data-stu-id="6cefa-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="6cefa-111">Exchange 邮箱必须位于 Exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="6cefa-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="6cefa-112">不支持本地 Exchange Server 邮箱。</span><span class="sxs-lookup"><span data-stu-id="6cefa-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="6cefa-113">必须为组织启用 Microsoft 预定。</span><span class="sxs-lookup"><span data-stu-id="6cefa-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="6cefa-114">用户必须具有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="6cefa-114">Users must have an appropriate license.</span></span> <span data-ttu-id="6cefa-115">Office 365 A3、A5、E3 和 E5 以及 Microsoft 365 商业标准、A3、A5、E3 和 E5 均受支持。</span><span class="sxs-lookup"><span data-stu-id="6cefa-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="6cefa-116">预定应用和参与会议的所有员工的所有用户都必须拥有支持团队会议计划的许可证。</span><span class="sxs-lookup"><span data-stu-id="6cefa-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="6cefa-117">您的系统必须满足所有[软件和浏览器先决条件](hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="6cefa-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="6cefa-118">团队中的预订可用性</span><span class="sxs-lookup"><span data-stu-id="6cefa-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="6cefa-119">适用于团队的 Microsoft 预定应用可在桌面和 web 上使用。</span><span class="sxs-lookup"><span data-stu-id="6cefa-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="6cefa-120">可在[Microsoft 团队内部的应用中](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)以及团队管理中心内的 "**管理应用**" 下找到该文件。</span><span class="sxs-lookup"><span data-stu-id="6cefa-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="6cefa-121">控制对组织内的预订的访问</span><span class="sxs-lookup"><span data-stu-id="6cefa-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="6cefa-122">有多种方法可以控制谁有权访问预定应用和应用的特定功能。</span><span class="sxs-lookup"><span data-stu-id="6cefa-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="6cefa-123">若要了解如何在 Microsoft 365 管理中心中打开或关闭 Microsoft 预订，以及如何创建预订应用策略以允许所选用户创建预定日历，请参阅[获取 Microsoft 预订的访问权限](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)。</span><span class="sxs-lookup"><span data-stu-id="6cefa-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="6cefa-124">你还可以了解如何[创建团队应用策略来固定选择用户的预定应用](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6cefa-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="6cefa-125">建议的会议策略设置</span><span class="sxs-lookup"><span data-stu-id="6cefa-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="6cefa-126">若要启用预订的最佳体验，请创建一个 "员工会议策略" 以自动**授予组织中的每个人**。</span><span class="sxs-lookup"><span data-stu-id="6cefa-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="6cefa-127">这将允许教职员工自动加入约会，并为外部与会者启用会议厅体验。</span><span class="sxs-lookup"><span data-stu-id="6cefa-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="6cefa-128">你可以了解有关[自动 admitting 人员加入会议](meeting-policies-in-teams.md#automatically-admit-people)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6cefa-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="6cefa-129">可选的员工批准设置</span><span class="sxs-lookup"><span data-stu-id="6cefa-129">Optional staff approvals setting</span></span>

<span data-ttu-id="6cefa-130">作为额外的隐私设置，你可以选择在计划的计划可用性信息通过预定共享之前以及可以为其预定约会之前，选择需要员工加入。</span><span class="sxs-lookup"><span data-stu-id="6cefa-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="6cefa-131">若要启用此设置，请转到**Microsoft 365 管理中心** \> **设置** \> **设置**，然后选择 "**预定**"。</span><span class="sxs-lookup"><span data-stu-id="6cefa-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="6cefa-132">启用此设置后，员工将收到一封电子邮件，其中要求他们向预定日历批准成员身份。</span><span class="sxs-lookup"><span data-stu-id="6cefa-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="6cefa-133">此功能将在全球范围内逐渐推出给 Microsoft 365 和 Office 365 客户。</span><span class="sxs-lookup"><span data-stu-id="6cefa-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="6cefa-134">如果你的环境中尚未提供所有选项，请稍后再查看。</span><span class="sxs-lookup"><span data-stu-id="6cefa-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="6cefa-135">设置预定邮箱时更改默认域</span><span class="sxs-lookup"><span data-stu-id="6cefa-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="6cefa-136">设置预定邮箱时，将使用 Microsoft 365 或 Office 365 组织的默认电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="6cefa-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="6cefa-137">但是，这可能会在向外部收件人发送会议邀请时出现问题;您的邀请可能被标记为垃圾邮件并移动到收件人的垃圾邮件文件夹，因此收件人可能永远看不到您的邀请。</span><span class="sxs-lookup"><span data-stu-id="6cefa-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="6cefa-138">我们建议您在创建预定邮箱之前更改默认域。</span><span class="sxs-lookup"><span data-stu-id="6cefa-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="6cefa-139">有关如何执行此操作的信息，请参阅[域常见问题解答](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="6cefa-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="6cefa-140">如果你需要在已创建你的预定邮箱后更改默认域，你可以通过 PowerShell 执行此操作：</span><span class="sxs-lookup"><span data-stu-id="6cefa-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="6cefa-141">有关详细信息，请参阅[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)Cmdlet 的 PowerShell 文档。</span><span class="sxs-lookup"><span data-stu-id="6cefa-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="6cefa-142">如果你使用的是 Exchange 混合配置，我们建议你在更改默认域时，在本地 Exchange 和 Exchange Online 之间彻底测试邮件流。</span><span class="sxs-lookup"><span data-stu-id="6cefa-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="6cefa-143">发送反馈</span><span class="sxs-lookup"><span data-stu-id="6cefa-143">Sending feedback</span></span>

<span data-ttu-id="6cefa-144">我们欢迎您提供有关以下内容的反馈：</span><span class="sxs-lookup"><span data-stu-id="6cefa-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="6cefa-145">用户体验或易于使用</span><span class="sxs-lookup"><span data-stu-id="6cefa-145">User experience or ease of use</span></span>
  - <span data-ttu-id="6cefa-146">功能缺口或缺少功能</span><span class="sxs-lookup"><span data-stu-id="6cefa-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="6cefa-147">Bug 或问题</span><span class="sxs-lookup"><span data-stu-id="6cefa-147">Bugs or issues</span></span>
  
<span data-ttu-id="6cefa-148">若要发送反馈，请单击团队左侧导航栏旁边的 "**帮助**" 按钮，然后单击 "报告**所有**问题的**问题**"。</span><span class="sxs-lookup"><span data-stu-id="6cefa-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="6cefa-149">请注意，你正在发送有关 "预定" 反馈的反馈报告的开始处，因此我们可以轻松地确定预订问题。</span><span class="sxs-lookup"><span data-stu-id="6cefa-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6cefa-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="6cefa-150">Related topics</span></span>

[<span data-ttu-id="6cefa-151">最终用户的预定文档</span><span class="sxs-lookup"><span data-stu-id="6cefa-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
