---
title: 在Microsoft Teams中管理Bookings应用
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
description: 了解如何为组织中的用户管理Teams中的Bookings应用。
ms.openlocfilehash: aab7ce7a4813d851574f9a5796f5ce21d44774ff
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853063"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>在Microsoft Teams中管理Bookings应用

Microsoft Teams中的Bookings应用提供了一种安排亲自约会和虚拟约会的简单方法。 例如，医疗保健访问、财务咨询、面试、客户支持和教育办公时间。 若要了解详细信息，请参阅[包含Teams和Bookings应用的虚拟约会](expand-teams-across-your-org/bookings-virtual-visits.md)。

计划程序可以从单个体验中管理多个部门和员工日历以及与内部和外部与会者的通信。 虚拟约会通过提供强大视频会议功能的Microsoft Teams会议进行。

> [!NOTE]
> 只有调度员需要在 Teams 中安装 Bookings 应用。 执行或参与虚拟约会的工作人员不需要该应用。 他们只需从Outlook或Teams日历或预订确认电子邮件中的Teams会议链接加入约会。

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>在Teams中使用Bookings应用的先决条件

* Exchange邮箱位于Exchange Online中。 不支持本地Exchange Server邮箱。
* Microsoft Bookings可用于组织。
* 用户具有适当的许可证。 Office 365 A3、A5、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、E5、F1、F3 和 Business Standard 受支持。
* Bookings应用的所有用户以及所有参加会议的工作人员都有支持Teams会议安排的许可证。
* [软件和浏览器先决条件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams 中 Bookings 可用性

桌面和 Web 上提供了适用于Teams的Microsoft Bookings应用。 可以在 [Teams中的“应用](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)”和“**管理** 应用”下的Teams管理中心中找到它。

### <a name="control-access-to-bookings-within-your-organization"></a>控制组织内对 Bookings 的访问权限

有几种方式可以控制谁具有对 Bookings 应用和该应用特定功能的访问权限。 可以使Microsoft Bookings应用可用，或将其从Microsoft 365 管理中心中禁用。 或者，可以创建Bookings应用策略，以允许选择用户创建Bookings日历。 请参阅[获取对Microsoft Bookings的访问权限](/microsoft-365/bookings/get-access)。

还可以[创建Teams应用设置策略，以便为选择用户固定Bookings应用](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>建议的会议策略设置

若要为Bookings启用最佳体验，请创建Teams会议策略，自动允许 **组织中的所有人**，并将策略分配给员工。 该策略允许员工自动加入约会，并为外部与会者启用大厅体验。 了解 [如何自动允许用户参加会议](meeting-policies-participants-and-guests.md#automatically-admit-people)。

## <a name="optional-staff-approvals-setting"></a>可选员工审批策略

你可以要求员工在Bookings共享其计划可用性信息之前选择加入，然后其他人才能与他们安排约会。

若要启用此设置，请转到 **Microsoft 365 管理中心设置** \>  \> **设置**，然后选择 **Bookings**。

启用此设置后，员工会收到一封电子邮件，其中要求他们批准预订日历的成员身份。  

此功能目前正逐步向全球 Microsoft 365 和 Office 365 客户推出。 如果环境中尚不可用所有选项，请尽快返回。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>设置Bookings邮箱时更改默认域

设置 Bookings 邮箱时，将使用 Microsoft 365 或 Office 365 组织的默认电子邮件域。 但是，默认域可能会在向外部收件人发送会议邀请时导致问题。 例如，您的邀请可能会标记为垃圾邮件并移动到收件人的垃圾邮件文件夹，因此收件人可能永远看不到您的邀请。

建议在创建Bookings邮箱之前更改默认域。 请参阅 [域常见问题解答](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

如果在创建Bookings邮箱后需要更改默认域，请使用 PowerShell。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

请参阅 PowerShell 文档以 [设置邮箱](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet。

> [!NOTE]
> 如果使用的是Exchange混合配置，建议在更改默认域时彻底测试本地Exchange和Exchange Online之间的邮件流。

## <a name="send-feedback"></a>发送反馈

我们欢迎您就以下方面提供反馈：

* 用户体验或易用性
* 功能差距或缺失的功能
* bug 或问题
  
若要发送反馈，请选择左侧导航栏Teams底部的 **“帮助**”选项，然后选择 **“报告所有问题的问题**”。 在反馈报告的开头指示你正在发送有关“Bookings”的反馈，以便我们可以轻松识别Bookings问题。

## <a name="related-articles"></a>相关文章

[管理浏览器上Teams虚拟约会的联接体验](expand-teams-across-your-org/browser-join.md)


  [适用最终用户的 Bookings 文档](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
