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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 了解如何在应用程序中为组织Teams Bookings 应用。
ms.openlocfilehash: 42e7c4741104f417f7e24a0e6441acb57cac203a
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973050"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>在应用程序中管理 Bookings Microsoft Teams

Microsoft Teams 中的 Bookings 应用提供了简便的方法来安排面对面的和虚拟的约会，如医疗访问、财务咨询、面试、客户支持、教育办公时间等。 若要了解详情，请参阅使用[Teams 和 Bookings](expand-teams-across-your-org/bookings-virtual-visits.md)应用进行虚拟访问。

调度程序可以从一次体验中管理多个部门和员工日历，以及与内部和外部与会者的通信。 虚拟约会本身通过会议Microsoft Teams，这提供了强大的桌面功能。

> [!NOTE]
> 只有调度员需要在 Teams 中安装 Bookings 应用。 执行或参与虚拟约会的人员不需要该应用。 他们只需从自己的日历或日历Outlook Teams，或者从Teams确认电子邮件中的会议链接加入约会。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>在 Teams 中使用 Bookings 应用的先决条件

- Exchange 邮箱必须在 Exchange Online 中。 不支持Exchange Server本地邮箱。

- 必须为组织启用 Microsoft Bookings。

- 用户必须具有相应的许可证。 Office 365 A3、A5、E3、E5、F1、F3、Microsoft 365 A3、A5、E3 和 E5、Business Standard。

- Bookings 应用的所有用户以及参与会议的所有用户都必须具有支持Teams安排的许可证。

- 系统必须满足所有[软件和浏览器先决条件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams 中 Bookings 可用性

适用于 Teams 的 Microsoft Bookings 应用在桌面和 Web 上可用。 可在"[应用"下](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)找到Teams"管理 **中心中的** 应用"Teams下。

### <a name="control-access-to-bookings-within-your-organization"></a>控制组织内对 Bookings 的访问权限

有几种方式可以控制谁具有对 Bookings 应用和该应用特定功能的访问权限。

若要了解如何在 Microsoft 365 管理中心 中打开或关闭 Microsoft Bookings，以及如何创建 Bookings 应用策略以允许所选用户创建 Bookings 日历，请参阅获取[Microsoft Bookings 的访问权限](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)。

还可以创建[一个Teams设置策略，为选定](teams-app-setup-policies.md)用户固定 Bookings 应用。

## <a name="recommended-meeting-policy-settings"></a>建议的会议策略设置

若要为 Bookings 提供最佳体验，请创建Teams会议策略以自动允许组织中所有人，并将该策略分配给你的员工。 这样，员工可以自动加入约会，为外部与会者启用大厅体验。 详细了解如何 [自动允许人员参加会议](meeting-policies-participants-and-guests.md#automatically-admit-people)。

## <a name="optional-staff-approvals-setting"></a>可选员工审批策略

作为额外的隐私设置，可以选择要求员工在通过 Bookings 共享其日程可用性信息之前，以及可以预定其参加某一约会之前选择加入。  

若要启用此设置，请转到"Microsoft 365 管理中心设置设置"， \>  \> 然后选择 **"Bookings"。**

启用此设置后，员工将收到一封电子邮件，要求他们批准预订日历的成员身份。  

此功能目前正逐步向全球 Microsoft 365 和 Office 365 客户推出。 如果环境中尚未提供所有选项，请尽快返回查看。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>设置 Bookings 邮箱时更改默认域

设置 Bookings 邮箱时，将使用 Microsoft 365 或 Office 365 组织的默认电子邮件域。 但是，此设置在项外部收件人发送会议邀请时可能导致问题；你的邀请可能标记为垃圾邮件并移动到收件人的垃圾邮件文件夹，因此收件人可能根本未看到你的邀请。

建议在创建 Bookings 邮箱之前更改默认域。 有关如何执行此操作的信息，请参阅 [域常见问题解答](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

如果在已创建 Bookings 邮箱后需要更改默认域，请通过 PowerShell 更改：

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

有关详细信息，请参阅 PowerShell 文档以了解 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet。

> [!NOTE]
> 如果使用混合Exchange，我们建议在更改默认域时Exchange Exchange Online本地域之间的邮件流。

## <a name="sending-feedback"></a>发送反馈

我们欢迎您就以下方面提供反馈：

  - 用户体验或易用性
  - 功能差距或缺失的功能
  - bug 或问题
  
若要发送反馈，请选择左侧导航栏Teams附近的"帮助"按钮，然后选择"报告所有问题 **的问题**"。  在反馈报告的开头指明你正在发送有关"Bookings"的反馈，以便我们可以轻松识别 Bookings 问题。

## <a name="related-articles"></a>相关文章

[管理在移动浏览器中Teams虚拟访问的加入体验](expand-teams-across-your-org/mobile-browser-join.md)


  [适用最终用户的 Bookings 文档](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
