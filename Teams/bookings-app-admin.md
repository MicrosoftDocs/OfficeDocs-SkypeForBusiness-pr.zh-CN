---
title: 在 Microsoft Teams 中管理 Bookings 应用
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: how-to
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
- m365-frontline
- tier2
- highpri
ms.reviewer: ''
description: 了解如何在 Teams 中为组织中的用户管理 Bookings 应用。
ms.openlocfilehash: 4669b27efb351c375d5d5fd1104843e21c6f5ba9
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131301"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>在 Microsoft Teams 中管理 Bookings 应用

Microsoft Teams 中的 Bookings 应用提供了一种安排亲自和虚拟约会的简单方法。 例如，医疗保健访问、财务咨询、访谈、客户支持和教育办公时间。 若要了解详细信息，请参阅 [Teams 虚拟约会和 Bookings 应用](/microsoft-365/frontline/bookings-virtual-visits)。

计划人员可以从单个体验中管理多个部门和员工日历以及与内部和外部与会者的通信。 虚拟约会通过 Microsoft Teams 会议进行，会议提供强大的视频会议功能。

> [!NOTE]
> 只有调度员需要在 Teams 中安装 Bookings 应用。 进行或参与虚拟约会的员工不需要该应用。 他们只需从其 Outlook 或 Teams 日历或从其预订确认电子邮件中的 Teams 会议链接加入约会。

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>在 Teams 中使用 Bookings 应用的先决条件

* Exchange 邮箱位于 Exchange Online。 不支持本地Exchange Server邮箱。
* Microsoft Bookings适用于组织。
* 用户具有相应的许可证。 支持Office 365 A3、A5、E1、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、F1、F3 和 Business Standard。
* Bookings 应用的所有用户和所有参与会议的员工都具有支持 Teams 会议安排的许可证。
* [软件和浏览器先决条件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams 中 Bookings 可用性

Microsoft Bookings适用于 Teams 的应用在桌面和 Web 上可用。 可以在 [Teams 管理中心的“应用”](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 和 **“管理应用”** 下找到它。

### <a name="control-access-to-bookings-within-your-organization"></a>控制组织内对 Bookings 的访问权限

有几种方式可以控制谁具有对 Bookings 应用和该应用特定功能的访问权限。 你可以使Microsoft Bookings应用可用，或者从Microsoft 365 管理中心禁用它。 或者，可以创建 Bookings 应用策略，以允许选定用户创建 Bookings 日历。 请参阅[获取对Microsoft Bookings的访问权限](/microsoft-365/bookings/get-access)。

还可以 [创建 Teams 应用设置策略，以固定所选用户的 Bookings 应用](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>建议的会议策略设置

若要为 Bookings 启用最佳体验，请创建 Teams 会议策略以自动允许 **组织中的所有人** ，并将策略分配给员工。 该策略允许员工自动加入约会，并为外部与会者启用大厅体验。 请参阅 [如何自动允许人员参加会议](meeting-policies-participants-and-guests.md#automatically-admit-people)。

有关会议策略的详细信息，请参阅[在 Teams 中管理会议策略](meeting-policies-in-teams.md)和 [Teams 中的会议策略和会议过期。](meeting-expiration.md)

## <a name="optional-staff-approvals-setting"></a>可选员工审批策略

在 Bookings 共享其计划可用性信息之前，您可以要求员工选择加入，然后其他人才能与他们安排约会。

若要启用此设置，请转到 **Microsoft 365 管理中心** \> **设置** \> **设置**，然后选择“**预订**”。

启用此设置后，员工将收到一封电子邮件，要求他们批准预订日历的成员身份。  

此功能目前正逐步向全球 Microsoft 365 和 Office 365 客户推出。 如果环境中尚未提供所有选项，请尽快回来查看。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>设置 Bookings 邮箱时更改默认域

设置 Bookings 邮箱时，将使用 Microsoft 365 或 Office 365 组织的默认电子邮件域。 但是，向外部收件人发送会议邀请时，默认域可能会导致问题。 例如，你的邀请可能会被标记为垃圾邮件并移动到收件人的垃圾邮件文件夹，因此收件人可能永远不会看到你的邀请。

建议在创建 Bookings 邮箱之前更改默认域。 请参阅 [域常见问题解答](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365)。

如果需要在创建 Bookings 邮箱后更改默认域，请使用 PowerShell。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

请参阅设置 [邮箱](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet 的 PowerShell 文档。

> [!NOTE]
> 如果使用 Exchange 混合配置，建议在更改默认域时全面测试本地 Exchange 与 Exchange Online 之间的邮件流。

## <a name="send-feedback"></a>发送反馈

我们欢迎您就以下方面提供反馈：

* 用户体验或易用性
* 功能差距或缺失的功能
* bug 或问题
  
若要发送反馈，请选择 Teams 左侧导航栏底部的 **“帮助**”选项，然后选择“报告 **所有****问题的问题**”。 在反馈报告的开头指示你正在发送有关“预订”的反馈，以便我们可以轻松识别 Bookings 问题。

## <a name="related-articles"></a>相关文章

[在浏览器中管理 Teams 虚拟约会的加入体验](/microsoft-365/frontline/browser-join)


  [适用最终用户的 Bookings 文档](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
