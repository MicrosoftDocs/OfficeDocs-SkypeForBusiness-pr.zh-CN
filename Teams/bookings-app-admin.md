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
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>使用 Microsoft Teams 和 Bookings 应用进行虚拟访问

Microsoft Teams 中的 Bookings 应用提供了一种简单的方式来安排个人约会和虚拟约会，例如医疗保健访问、财务咨询、面试、客户支持、教育办公时间等。

计划程序可以通过单个体验管理多个部门日历和教职员工日历，以及与内部和外部与会者的通信。 虚拟约会本身通过 Microsoft Teams 会议进行，这提供了强大的空间功能。

> [!NOTE]
> 只有计划人员需要在 Teams 中安装 Bookings 应用。 执行或参与虚拟约会的人员不需要该应用。 他们只需从 Outlook 或 Teams 日历或预订确认电子邮件中的链接加入约会。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>在 Teams 中使用 Bookings 应用的先决条件

- Exchange 邮箱必须在 Exchange Online 中。 不支持Exchange Server本地邮箱。

- 必须为组织启用 Microsoft Bookings。

- 用户必须具有适当的许可证。 支持 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商业标准版、A3、A5、E3 和 E5。

- Bookings 应用的所有用户以及参与会议的所有用户都必须拥有支持 Teams 会议安排的许可证。

- 系统必须满足所有 [软件和浏览器先决条件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams 中 Bookings 的可用性

适用于 Teams 的 Microsoft Bookings 应用在桌面和 Web 上可用。 可在 Microsoft Teams 中的"应用" [下和"](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 在 Teams 管理中心 **内** 管理应用"下找到它。

### <a name="control-access-to-bookings-within-your-organization"></a>控制对组织中 Bookings 的访问

有几种方法可控制谁有权访问 Bookings 应用以及应用的特定功能。 若要了解如何在 Microsoft 365 管理中心中打开或关闭 Microsoft Bookings，以及如何创建 Bookings 应用策略以允许所选用户创建 Bookings 日历，请参阅"获取 [Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)的访问权限"。 还可以了解如何创建 Teams [应用策略，为选定用户固定 Bookings 应用](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>建议的会议策略设置

若要为 Bookings 提供最佳体验，请创建教职员工会议策略以自动允许 **组织中所有人。** 这将允许员工自动加入约会，并启用外部与会者的大厅体验。 你可以了解有关自动 [允许人员参加会议的更多信息](meeting-policies-in-teams.md#automatically-admit-people)。

### <a name="optional-staff-approvals-setting"></a>可选的教职员工审批设置

作为额外的隐私设置，你可以选择要求员工在通过 Bookings 共享其日程安排可用性信息之前以及预订约会之前选择加入。  

若要启用此设置，请转到 **Microsoft 365 管理** 中心"设置 \>  \> **设置**"，然后选择 **"预订"。**

启用此设置后，教职员工将收到一封电子邮件，要求他们批准预订日历的成员身份。  

此功能正在全球逐渐向 Microsoft 365 和 Office 365 客户推出。 如果环境中尚未提供所有选项，请尽快返回查看。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>在设置 Bookings 邮箱时更改默认域

设置 Bookings 邮箱时，使用 Microsoft 365 或 Office 365 组织的默认电子邮件域。 但是，这可能会导致向外部收件人发送会议邀请时出现问题;你的邀请可能标记为垃圾邮件并移动到收件人的垃圾邮件文件夹中，因此收件人可能永远不会看到你的邀请。

建议在创建 Bookings 邮箱之前更改默认域。 有关此操作的信息，请参阅域 [常见问题解答](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

如果创建 Bookings 邮箱后需要更改默认域，可以使用 PowerShell：

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

有关详细信息，请参阅 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet 的 PowerShell 文档。

> [!NOTE]
> 如果你使用的是 Exchange 混合配置，我们建议你在本地 Exchange 和 Exchange Online 之间彻底测试邮件流，同时更改默认域。

## <a name="sending-feedback"></a>发送反馈

欢迎提供反馈：

  - 用户体验或易用性
  - 功能差距或功能缺失
  - Bug 或问题
  
若要发送反馈，请单击Teams 左侧导航栏底部附近的"帮助"按钮，然后单击"报告 **所有问题****的问题**"。 请注意，在反馈报告的开头，您发送有关"Bookings"的反馈，以便我们可以轻松识别 Bookings 问题。

## <a name="related-topics"></a>相关主题

[最终用户的 Bookings 文档](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
