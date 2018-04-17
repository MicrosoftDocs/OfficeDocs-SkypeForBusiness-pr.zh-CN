---
title: 限制和 Microsoft 小组的规范
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/09/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: 了解有关限制、 规范和其他适用于 Microsoft 小组的要求。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff28cb59dabbf3d9d43dbde00cba73541280b39
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
<a name="limits-and-specifications-for-microsoft-teams"></a>限制和 Microsoft 小组的规范
=============================================

本文介绍了一些限制、 规范和其他适用于 Microsoft 小组的要求。 

<a name="teams-and-channels"></a>团队和频道 
------------------

|功能    | 最大限制 |
|-----------|---------------|
|用户可创建的团队数量 | 250         |
|在一个团队中的成员数 | 2500       |
|团队可以创建全局管理员数量        | 无限制   |
|Office 365 租户可以有的团队数量    | 500000     |
|每组的通道数    | 200         |

<a name="meetings-and-calls"></a>会议和电话 
------------------

|功能     | 最大限制 |
|------------|---------------|
|许多人在会议中  | 80    |
|许多人在私人聊天  | 20    |

<a name="storage"></a>存储
-------

Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。 对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。

如果您未安装 SharePoint Online 在您的组织中启用，Microsoft 小组用户始终无法共享团队中的文件。 此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。 （有关详细信息，请参阅[如何 SharePoint Online 和业务的 OneDrive 与 Microsoft 小组进行交互](sharepoint-onedrive-interact.md)。

因为在文件共享的 SharePoint Online 端上运行团队，SharePoint 限制到小组内的文件部分。 这里是 SharePoint Online 的适用的存储限制。

|功能                 |Office 365 商业协作版  |Office 365 商业高级版   |Office 365 企业版 E1  |Office 365 企业版 E3  |Office 365 企业版 E5  |Office 365 企业版 F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|存储                 |每个组织的 1 TB 加上 0.5 GB 每个购买的许可证  |每个组织的 1 TB 加上 0.5 GB 每个购买的许可证  |每个组织的 1 TB 加上 0.5 GB 每个购买的许可证   |每个组织的 1 TB 加上 0.5 GB 每个购买的许可证 |每个组织的 1 TB 加上 0.5 GB 每个购买的许可证  |每个组织的 1 TB           |
|工作组文件的存储 |每个站点集合或组达 25 TB |每个站点集合或组达 25 TB |每个站点集合或组达 25 TB |每个站点集合或组达 25 TB |每个站点集合或组达 25 TB |每个站点集合或组达 25 TB |
|文件上载限制       |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

在团队中的每个文件选项卡上运行 SharePoint Online 的后端，因此上述存储限制适用于在一个团队中的每个通道。

有关详细信息，请参阅[SharePoint Online 的限制](https://support.office.com/en-us/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。

<a name="messaging"></a>消息
---------

参与对话的聊天列表中 Microsoft 小组的一部分的用户必须具有管理员搜索聊天 Exchange Online （云） 邮箱。 这是因为属于聊天列表的对话存储在聊天参与者的基于云的邮箱中。 如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。 例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与属于 Microsoft Teams 中聊天列表的对话。 但是，在这种情况下，由于用户没有基于云的邮箱，这些对话中的内容不可搜索，也不可置于保留状态。 （有关详细信息，请参阅[如何交换和 Microsoft 小组进行交互](exchange-teams-interact.md)。

Microsoft 小组聊天函数处理 Microsoft Exchange 后端，因此您可以应用 Exchange 邮件传递到 Microsoft 小组内的聊天功能的限制。 如果用户希望在电子邮件发送给团队中的通道，使用通道电子邮件地址。 后一封电子邮件是一个通道的一部分，任何人都可以回复它开始对话。 下面是一些适用到通道发送电子邮件的限制。 

|功能  |Office 365 企业版 E1  |Office 365 企业版 E3  |Office 365 企业版 E5  |Office 365 企业版 F1  |
|---------|---------|---------|---------|---------|
|邮件大小限制&dagger;  |25 KB   |25 KB   |25 KB   |25 KB   |
|文件附件限制&Dagger;  |20     |20     |20     |20    |
|内联图像限制&Dagger; |50   |50   |50   |50   |

&dagger;如果邮件超过该限额，生成预览消息，询问用户要查看/下载原始电子邮件中提供的链接。

&Dagger;如果附件或图像的数量超过此限制，将不会处理该邮件和 NDR 邮件将被发送回发件人通知他们的错误。

有关详细信息，请参阅[Exchange Online 的限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。

<a name="browsers"></a>浏览器 
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a>操作系统
-----------------

有关操作系统要求的详细说明，请参阅[获取有关 Microsoft 小组的客户机](get-clients.md)。


