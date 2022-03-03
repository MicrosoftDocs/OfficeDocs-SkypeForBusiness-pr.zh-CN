---
title: 在应用程序中管理 Bookings Microsoft Teams
author: dmaguire
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 了解如何在应用程序中为Teams管理 Bookings 应用。
ms.openlocfilehash: 692cf8500b47d903986542082c328b4a8be2237d
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2022
ms.locfileid: "63050908"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>在应用程序中管理 Bookings Microsoft Teams

Microsoft Teams 中的 Bookings 应用提供了一种简单的方式来安排个人约会和虚拟约会。 例如，医疗保健访问、财务咨询、面试、客户支持和教育办公时间。 若要了解详情，请参阅使用 Teams [和 Bookings 应用进行虚拟访问](expand-teams-across-your-org/bookings-virtual-visits.md)。

计划程序可以通过单个体验管理多个部门与员工日历，以及与内部和外部与会者的通信。 虚拟约会通过提供强大Microsoft Teams功能的会议进行。

> [!NOTE]
> 只有调度员需要在 Teams 中安装 Bookings 应用。 执行或参与虚拟约会的人员不需要该应用。 他们只需从自己的日历或日历Outlook Teams或预订确认电子邮件Teams会议链接加入约会。

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>在应用程序中使用 Bookings 应用Teams

* Exchange邮箱位于Exchange Online。 不支持Exchange Server本地邮箱。
* Microsoft Bookings 适用于组织。
* 用户具有适当的许可证。 Office 365 A3、A5、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、E5、F1、F3 和业务标准。
* Bookings 应用的所有用户以及参与会议的所有用户都有一个支持Teams安排的许可证。
* [软件和浏览器先决条件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams 中 Bookings 可用性

适用于 Teams 的 Microsoft Bookings 应用在桌面和 Web 上可用。 可在"应用 ["下找到](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)Teams"管理 **中心** 中的应用"Teams下。

### <a name="control-access-to-bookings-within-your-organization"></a>控制组织内对 Bookings 的访问权限

有几种方式可以控制谁具有对 Bookings 应用和该应用特定功能的访问权限。 你可以使 Microsoft Bookings 应用可用，也可以将其从 Microsoft 365 管理中心。 或者，可以创建 Bookings 应用策略以允许选择用户创建 Bookings 日历。 请参阅 [获取 Microsoft Bookings 的访问权限](/microsoft-365/bookings/get-access)。

还可以创建[一个Teams设置策略，为选定用户固定 Bookings 应用](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>建议的会议策略设置

若要为 Bookings 提供最佳体验，请创建Teams会议策略，以自动允许组织中所有人，并将该策略分配给您的员工。 该策略允许员工自动加入约会，并启用外部与会者的大厅体验。 了解如何 [自动允许人员参加会议](meeting-policies-participants-and-guests.md#automatically-admit-people)。

## <a name="optional-staff-approvals-setting"></a>可选员工审批策略

您可以要求员工在 Bookings 共享其日程安排可用性信息之前以及其他人可以安排与他们的约会之前选择加入。

若要启用此设置，请转到"Microsoft 365 管理中心 **设置** \> **设置**\>，**然后选择**"**Bookings"**。

启用此设置后，员工将收到一封电子邮件，要求他们批准预订日历的成员身份。  

此功能目前正逐步向全球 Microsoft 365 和 Office 365 客户推出。 如果环境中尚未提供所有选项，请尽快返回查看。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>设置 Bookings 邮箱时更改默认域

设置 Bookings 邮箱时，将使用 Microsoft 365 或 Office 365 组织的默认电子邮件域。 但是，向外部收件人发送会议邀请时，默认域可能会导致问题。 例如，您的邀请可能标记为垃圾邮件并移动到收件人的垃圾邮件文件夹中，因此收件人可能永远不会看到您的邀请。

建议在创建 Bookings 邮箱之前更改默认域。 请参阅 [域常见问题解答](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

如果在创建 Bookings 邮箱后需要更改默认域，请使用 PowerShell。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

请参阅 PowerShell 文档设置 [邮箱](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet。

> [!NOTE]
> 如果使用混合Exchange配置，我们建议在更改默认域时Exchange Exchange Online本地域之间的邮件流。

## <a name="send-feedback"></a>发送反馈

我们欢迎您就以下方面提供反馈：

* 用户体验或易用性
* 功能差距或缺失的功能
* bug 或问题
  
若要发送反馈，请选择左侧导航栏Teams"帮助"选项，然后选择"报告所有问题 **的问题**"。 在反馈报告的开头指明你正在发送有关"Bookings"的反馈，以便我们可以轻松识别 Bookings 问题。

## <a name="related-articles"></a>相关文章

[管理移动浏览器上Teams虚拟访问的加入体验](expand-teams-across-your-org/mobile-browser-join.md)


  [适用最终用户的 Bookings 文档](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
