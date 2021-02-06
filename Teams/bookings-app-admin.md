---
title: 使用 Microsoft Teams 和 Bookings 应用进行虚拟访问
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 使用 Bookings 应用进行 Microsoft Teams 和虚拟访问
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125745"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="c5bfe-103">使用 Microsoft Teams 和 Bookings 应用进行虚拟访问</span><span class="sxs-lookup"><span data-stu-id="c5bfe-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="c5bfe-104">Microsoft Teams 中的 Bookings 应用提供了一种简单的方式来安排个人约会和虚拟约会，例如医疗保健访问、财务咨询、面试、客户支持、教育办公时间等。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="c5bfe-105">计划程序可以通过单个体验管理多个部门日历和教职员工日历，以及与内部和外部与会者的通信。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="c5bfe-106">虚拟约会本身通过 Microsoft Teams 会议进行，这提供了强大的空间功能。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="c5bfe-107">只有计划人员需要在 Teams 中安装 Bookings 应用。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="c5bfe-108">执行或参与虚拟约会的人员不需要该应用。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="c5bfe-109">他们只需从 Outlook 或 Teams 日历或预订确认电子邮件中的链接加入约会。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="c5bfe-110">在 Teams 中使用 Bookings 应用的先决条件</span><span class="sxs-lookup"><span data-stu-id="c5bfe-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="c5bfe-111">Exchange 邮箱必须在 Exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="c5bfe-112">不支持Exchange Server本地邮箱。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="c5bfe-113">必须为组织启用 Microsoft Bookings。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="c5bfe-114">用户必须具有适当的许可证。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-114">Users must have an appropriate license.</span></span> <span data-ttu-id="c5bfe-115">支持 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商业标准版、A3、A5、E3 和 E5。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="c5bfe-116">Bookings 应用的所有用户以及参与会议的所有用户都必须拥有支持 Teams 会议安排的许可证。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="c5bfe-117">系统必须满足所有 [软件和浏览器先决条件](hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="c5bfe-118">Teams 中 Bookings 的可用性</span><span class="sxs-lookup"><span data-stu-id="c5bfe-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="c5bfe-119">适用于 Teams 的 Microsoft Bookings 应用在桌面和 Web 上可用。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="c5bfe-120">可在 Microsoft Teams 中的"应用" [下和"](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 在 Teams 管理中心 **内** 管理应用"下找到它。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="c5bfe-121">控制对组织中 Bookings 的访问</span><span class="sxs-lookup"><span data-stu-id="c5bfe-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="c5bfe-122">有几种方法可控制谁有权访问 Bookings 应用以及应用的特定功能。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="c5bfe-123">若要了解如何在 Microsoft 365 管理中心中打开或关闭 Microsoft Bookings，以及如何创建 Bookings 应用策略以允许所选用户创建 Bookings 日历，请参阅"获取 [Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)的访问权限"。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="c5bfe-124">还可以了解如何创建 Teams [应用策略，为选定用户固定 Bookings 应用](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="c5bfe-125">建议的会议策略设置</span><span class="sxs-lookup"><span data-stu-id="c5bfe-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="c5bfe-126">若要为 Bookings 提供最佳体验，请创建教职员工会议策略以自动允许 **组织中所有人。**</span><span class="sxs-lookup"><span data-stu-id="c5bfe-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="c5bfe-127">这将允许员工自动加入约会，并启用外部与会者的大厅体验。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="c5bfe-128">你可以了解有关自动 [允许人员参加会议的更多信息](meeting-policies-in-teams.md#automatically-admit-people)。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="c5bfe-129">可选的教职员工审批设置</span><span class="sxs-lookup"><span data-stu-id="c5bfe-129">Optional staff approvals setting</span></span>

<span data-ttu-id="c5bfe-130">作为额外的隐私设置，你可以选择要求员工在通过 Bookings 共享其日程安排可用性信息之前以及预订约会之前选择加入。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="c5bfe-131">若要启用此设置，请转到 **Microsoft 365 管理** 中心"设置 \>  \> **设置**"，然后选择 **"预订"。**</span><span class="sxs-lookup"><span data-stu-id="c5bfe-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="c5bfe-132">启用此设置后，教职员工将收到一封电子邮件，要求他们批准预订日历的成员身份。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="c5bfe-133">此功能正在全球逐渐向 Microsoft 365 和 Office 365 客户推出。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="c5bfe-134">如果环境中尚未提供所有选项，请尽快返回查看。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="c5bfe-135">在设置 Bookings 邮箱时更改默认域</span><span class="sxs-lookup"><span data-stu-id="c5bfe-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="c5bfe-136">设置 Bookings 邮箱时，使用 Microsoft 365 或 Office 365 组织的默认电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="c5bfe-137">但是，这可能会导致向外部收件人发送会议邀请时出现问题;你的邀请可能标记为垃圾邮件并移动到收件人的垃圾邮件文件夹中，因此收件人可能永远不会看到你的邀请。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="c5bfe-138">建议在创建 Bookings 邮箱之前更改默认域。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="c5bfe-139">有关此操作的信息，请参阅域 [常见问题解答](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="c5bfe-140">如果创建 Bookings 邮箱后需要更改默认域，可以使用 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="c5bfe-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="c5bfe-141">有关详细信息，请参阅 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet 的 PowerShell 文档。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="c5bfe-142">如果你使用的是 Exchange 混合配置，我们建议你在本地 Exchange 和 Exchange Online 之间彻底测试邮件流，同时更改默认域。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="c5bfe-143">发送反馈</span><span class="sxs-lookup"><span data-stu-id="c5bfe-143">Sending feedback</span></span>

<span data-ttu-id="c5bfe-144">欢迎提供反馈：</span><span class="sxs-lookup"><span data-stu-id="c5bfe-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="c5bfe-145">用户体验或易用性</span><span class="sxs-lookup"><span data-stu-id="c5bfe-145">User experience or ease of use</span></span>
  - <span data-ttu-id="c5bfe-146">功能差距或功能缺失</span><span class="sxs-lookup"><span data-stu-id="c5bfe-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="c5bfe-147">Bug 或问题</span><span class="sxs-lookup"><span data-stu-id="c5bfe-147">Bugs or issues</span></span>
  
<span data-ttu-id="c5bfe-148">若要发送反馈，请单击Teams 左侧导航栏底部附近的"帮助"按钮，然后单击"报告 **所有问题\*\*\*\*的问题**"。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="c5bfe-149">请注意，在反馈报告的开头，您发送有关"Bookings"的反馈，以便我们可以轻松识别 Bookings 问题。</span><span class="sxs-lookup"><span data-stu-id="c5bfe-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c5bfe-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="c5bfe-150">Related topics</span></span>

[<span data-ttu-id="c5bfe-151">最终用户的 Bookings 文档</span><span class="sxs-lookup"><span data-stu-id="c5bfe-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
