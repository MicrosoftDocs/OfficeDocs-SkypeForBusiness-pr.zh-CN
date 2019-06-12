---
title: Microsoft Teams 的限制和规范
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/10/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: karuanag
description: 了解适用于 Microsoft 团队的限制、规范和其他要求。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30e3a9de6a832753b8480733528a0db44f4f143b
ms.sourcegitcommit: 5895afd0d5752a6ea1ace68d613f86c68eae8bdb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857403"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams 的限制和规范

本文介绍适用于团队的一些限制、规范和其他要求。

## <a name="teams-and-channels"></a>团队和频道 

|功能    | 最大限制 |
|-----------|---------------|
|用户可以创建的团队数 | 受250对象限制的限制&sup1;         |
|团队中的成员数 | 5,000       |
|租户中允许的组织范围内的团队数 | 5     |
|[组织范围团队](create-an-org-wide-team.md)中的成员数 | 5,000       |
|全局管理员可以创建的团队数        |  500000   |
|Office 365 租户可以拥有的团队数    | 500000&sup2;     |
|每个团队的频道数    | 200 (包括删除的频道) &sup3;         |

&sup1;Azure Active Directory 中的任何目录对象都将计入此限制。 全局管理员不受此限制限制, 与使用[应用程序权限](https://docs.microsoft.com/graph/permissions-reference)调用 Microsoft Graph 的应用一样。

&sup2;此限制包括已存档的团队。

&sup3; 删除的频道可以在30天内恢复。 在30天内, 已删除的频道将继续按每个团队限额的200频道计入。 30天后, 删除的频道及其内容将被永久删除, 频道不再按每个团队的每个团队限额的200频道计数。

## <a name="meetings-and-calls"></a>会议和通话 

|功能     | 最大限制 |
|------------|---------------|
|会议中的人员数  | 250    |

## <a name="storage"></a>Storage

Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。 对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。

如果你的租户中未启用 SharePoint Online, Microsoft 团队用户将无法始终共享团队中的文件。 私人聊天中的用户也无法共享文件, 因为 OneDrive for business (绑定到 SharePoint 许可证) 是该功能所必需的。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。 (有关详细信息, 请参阅[SharePoint Online 和 OneDrive For Business 如何与 Microsoft 团队交互](sharepoint-onedrive-interact.md)。)

由于团队运行于 SharePoint Online 后端进行文件共享, 因此 SharePoint 限制适用于团队中的 "文件" 部分。 下面是 SharePoint Online 适用的存储空间限制。

|功能                 |Office 365 商业协作版  |Office 365 商业高级版   |Office 365 企业版 E1  |Office 365 企业版 E3  |Office 365 企业版 E5  |Office 365 企业版 F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Storage                 |每个组织 1 TB 加上购买的每个许可证 10 GB  |每个组织 1 TB 加上购买的每个许可证 10 GB  |每个组织 1 TB 加上购买的每个许可证 10 GB   |每个组织 1 TB 加上购买的每个许可证 10 GB |每个组织 1 TB 加上购买的每个许可证 10 GB  |每个组织 1 TB           |
|团队文件的存储空间 |每个网站集或组最多 25 TB |每个网站集或组最多 25 TB |每个网站集或组最多 25 TB |每个网站集或组最多 25 TB |每个网站集或组最多 25 TB |每个网站集或组最多 25 TB |
|文件上载限制 (每个文件)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

频道由为团队创建的 SharePoint Online 网站集内的文件夹提供支持, 因此频道内的文件选项卡共享其所属团队的存储限制。

有关详细信息, 请参阅[SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。

## <a name="messaging"></a>消息

参与 Microsoft 团队中的聊天列表的对话的用户必须具有 Exchange Online (基于云的) 邮箱, 管理员才能搜索聊天对话。 这是因为属于聊天列表的对话存储在聊天参与者的基于云的邮箱中。 如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。 例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与属于 Microsoft Teams 中聊天列表的对话。 但是，在这种情况下，由于用户没有基于云的邮箱，这些对话中的内容不可搜索，也不可置于保留状态。 (有关详细信息, 请参阅[Exchange 和 Microsoft 团队如何交互](exchange-teams-interact.md)。)

Microsoft 团队聊天功能适用于 Microsoft Exchange 后端, 因此你可以将 Exchange 邮件限制应用于 Microsoft 团队内的聊天功能。 如果用户想要向团队中的频道发送电子邮件, 他们将使用频道电子邮件地址。 一旦电子邮件是频道的一部分, 任何人都可以回复它以启动对话。 下面是向频道发送电子邮件的一些适用限制。 

|功能  | 最大限制  |
|---------|---------|
|私人聊天中的用户数  | 100    |
|邮件大小&dagger;  |25 KB   |
|文件附件数&Dagger;  |10     |
|内联图像的数量&Dagger; |50   |

&dagger;如果邮件超过此限制, 将生成预览消息, 要求用户从提供的链接查看/下载原始电子邮件。

&Dagger;如果附件或图像的数量超过此限制, 将不会处理邮件, 并且会将 NDR 电子邮件发送回发送错误的发件人。

> [!NOTE]
> 邮件大小、文件附件和嵌入式图像限制在所有 Office 365 许可证中的大小相同。

有关详细信息, 请参阅[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。

## <a name="browsers"></a>上级

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>操作系统

有关操作系统要求的信息, 请参阅[获取 Microsoft 团队客户端](get-clients.md)。
