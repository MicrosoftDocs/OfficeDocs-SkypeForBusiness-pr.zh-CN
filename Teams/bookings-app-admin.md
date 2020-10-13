---
title: Microsoft 团队中的预订应用和虚拟访问
author: msdmaguire
ms.author: dmaguire
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
ms.openlocfilehash: c60993b57233c0c526e1770c1d3d414a73fcc42a
ms.sourcegitcommit: a043bde507a9f6747fdd2063dd085edb3c1d6c3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "48427677"
---
# <a name="bookings-app-and-virtual-visits-in-microsoft-teams"></a>Microsoft 团队中的预订应用和虚拟访问

Microsoft 团队中的 "预定" 应用提供了一种简单的方式来安排人员和虚拟约会，例如医疗保健走访、财务咨询、访谈、客户支持、教育办公时间等。

计划程序可以管理多个部门和员工日历，以及与内部和外部与会者的通信，从单个体验开始。 虚拟约会本身是通过 Microsoft 团队会议举行的，它提供了强健的视频会议功能。

> [!NOTE]
> 只有计划程序需要在团队中安装预定应用。 从事虚拟约会或参与虚拟约会的职员不需要该应用。 他们可以直接从其 Outlook 或团队日历或其预订确认电子邮件中的链接加入约会。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>在团队中使用预定应用的先决条件

- Exchange 邮箱必须位于 Exchange Online 中。 不支持本地 Exchange Server 邮箱。

- 必须为组织启用 Microsoft 预定。

- 用户必须具有相应的许可证。 Office 365 A3、A5、E3 和 E5 以及 Microsoft 365 商业标准、A3、A5、E3 和 E5 均受支持。

- 预定应用和参与会议的所有员工的所有用户都必须拥有支持团队会议计划的许可证。

- 您的系统必须满足所有 [软件和浏览器先决条件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>团队中的预订可用性

适用于团队的 Microsoft 预定应用可在桌面和 web 上使用。 可在 [Microsoft 团队内部的应用中](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 以及团队管理中心内的 " **管理应用** " 下找到该文件。

### <a name="control-access-to-bookings-within-your-organization"></a>控制对组织内的预订的访问

有多种方法可以控制谁有权访问预定应用和应用的特定功能。 若要了解如何在 Microsoft 365 管理中心中打开或关闭 Microsoft 预订，以及如何创建预订应用策略以允许所选用户创建预定日历，请参阅 [获取 Microsoft 预订的访问权限](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)。 你还可以了解如何 [创建团队应用策略来固定选择用户的预定应用](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>建议的会议策略设置

若要启用预订的最佳体验，请创建一个 "员工会议策略" 以自动 **授予组织中的每个人**。 这将允许教职员工自动加入约会，并为外部与会者启用会议厅体验。 你可以了解有关 [自动 admitting 人员加入会议](meeting-policies-in-teams.md#automatically-admit-people)的详细信息。

### <a name="optional-staff-approvals-setting"></a>可选的员工批准设置

作为额外的隐私设置，你可以选择在计划的计划可用性信息通过预定共享之前以及可以为其预定约会之前，选择需要员工加入。  

若要启用此设置，请转到 **Microsoft 365 管理中心** \> **设置** \> **设置**，然后选择 " **预定**"。

启用此设置后，员工将收到一封电子邮件，其中要求他们向预定日历批准成员身份。  

此功能将在全球范围内逐渐推出给 Microsoft 365 和 Office 365 客户。 如果你的环境中尚未提供所有选项，请稍后再查看。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>设置预定邮箱时更改默认域

设置预定邮箱时，将使用 Microsoft 365 或 Office 365 组织的默认电子邮件域。 但是，这可能会在向外部收件人发送会议邀请时出现问题;您的邀请可能被标记为垃圾邮件并移动到收件人的垃圾邮件文件夹，因此收件人可能永远看不到您的邀请。

我们建议您在创建预定邮箱之前更改默认域。 有关如何执行此操作的信息，请参阅 [域常见问题解答](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

如果你需要在已创建你的预定邮箱后更改默认域，你可以通过 PowerShell 执行此操作：

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

有关详细信息，请参阅 [设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) Cmdlet 的 PowerShell 文档。

> [!NOTE]
> 如果你使用的是 Exchange 混合配置，我们建议你在更改默认域时，在本地 Exchange 和 Exchange Online 之间彻底测试邮件流。

## <a name="sending-feedback"></a>发送反馈

我们欢迎您提供有关以下内容的反馈：

  - 用户体验或易于使用
  - 功能缺口或缺少功能
  - Bug 或问题
  
若要发送反馈，请单击团队左侧导航栏旁边的 "**帮助**" 按钮，然后单击 "报告**所有**问题的**问题**"。 请注意，你正在发送有关 "预定" 反馈的反馈报告的开始处，因此我们可以轻松地确定预订问题。

## <a name="related-topics"></a>相关主题

[最终用户的预定文档](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
