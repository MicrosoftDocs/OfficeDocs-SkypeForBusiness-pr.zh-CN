---
title: 限制和规格的 Microsoft 团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: karuanag
description: 了解这些限制、 规格和适用于 Microsoft 团队的其他要求。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd62d8ea24de4ce790609b710b78c7d6977821d7
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "25436693"
---
<a name="limits-and-specifications-for-microsoft-teams"></a>限制和规格的 Microsoft 团队
=============================================

本文介绍一些限制、 规格和适用于 Microsoft 团队的其他要求。 

<a name="teams-and-channels"></a>团队和频道 
------------------

|功能    | 最大限制 |
|-----------|---------------|
|用户可创建的团队数量 | 受到 250 对象限制和 sup1;         |
|团队中的成员数 | 2500       |
|组织范围团队中的成员数 | 1,000 个       |
|全局管理员可以创建的团队数量        | 500,000 个   |
|Office 365 租户可以具有的团队数量    | 500,000 个     |
|每个工作组的通道数    | 200         |

& sup1;Azure Active Directory 中的任何目录对象计算达到此限制。

<a name="meetings-and-calls"></a>会议和呼叫 
------------------

|功能     | 最大限制 |
|------------|---------------|
|在会议中的人员数量  | 250    |
|私人聊天中的人数  | 50    |

<a name="storage"></a>存储
-------

Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。 对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。

如果您没有 SharePoint Online 租户中启用，Microsoft 团队用户始终不能共享团队中的文件。 此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。 （有关详细信息，请参阅[如何 SharePoint Online 和 OneDrive for Business 交互的 Microsoft 团队](sharepoint-onedrive-interact.md)。）

工作组在文件共享的 SharePoint Online 后端上运行，因为 SharePoint 限制应用于工作组中文件部分。 以下是 SharePoint Online 的适用的存储限制。

|功能                 |Office 365 商业协作版  |Office 365 商业高级版   |Office 365 企业版 E1  |Office 365 企业版 E3  |Office 365 企业版 E5  |Office 365 企业版 F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|存储                 |1 TB 每个组织以及每个许可证购买 10 GB  |1 TB 每个组织以及每个许可证购买 10 GB  |1 TB 每个组织以及每个许可证购买 10 GB   |1 TB 每个组织以及每个许可证购买 10 GB |1 TB 每个组织以及每个许可证购买 10 GB  |每个组织的 1 TB           |
|团队文件存储 |最多 25 TB 每个网站集或组 |最多 25 TB 每个网站集或组 |最多 25 TB 每个网站集或组 |最多 25 TB 每个网站集或组 |最多 25 TB 每个网站集或组 |最多 25 TB 每个网站集或组 |
|文件上载限制       |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

团队中的每个文件选项卡上 SharePoint Online 的后端，运行，因此以上的存储限制适用于团队中每个通道。

有关详细信息，请参阅[SharePoint Online 的限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。

<a name="messaging"></a>消息
---------

参与对话的一部分的 Microsoft 团队中的聊天列表中的用户必须拥有管理员可以搜索聊天 Exchange Online （基于云的） 邮箱。 这是因为属于聊天列表的对话存储在聊天参与者的基于云的邮箱中。 如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。 例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与属于 Microsoft Teams 中聊天列表的对话。 但是，在这种情况下，由于用户没有基于云的邮箱，这些对话中的内容不可搜索，也不可置于保留状态。 （有关详细信息，请参阅[如何 Exchange 和 Microsoft 团队进行交互](exchange-teams-interact.md)。）

Microsoft 团队聊天函数处理 Microsoft Exchange 后端，以便您可以将应用 Exchange 邮件限制内的 Microsoft 团队的聊天功能。 如果用户希望电子邮件发送给团队中的通道，他们使用的通道电子邮件地址。 一旦电子邮件通道的一部分，任何人都可以对其开始对话进行答复。 下面是一些到通道发送电子邮件的适用限制。 

|功能  |Office 365 企业版 E1  |Office 365 企业版 E3  |Office 365 企业版 E5  |Office 365 企业版 F1  |
|---------|---------|---------|---------|---------|
|邮件大小限制&dagger;  |25 KB   |25 KB   |25 KB   |25 KB   |
|文件附件限制&Dagger;  |20     |20     |20     |20    |
|内嵌图像限制&Dagger; |50   |50   |50   |50   |

&dagger;如果邮件超过此限制，生成预览消息，并要求用户要查看/下载原始电子邮件从提供的链接。

&Dagger;如果附件或图像的数目超过此限制，将不会处理邮件和 NDR 电子邮件将发送回发件人通知他们的错误。

有关详细信息，请参阅[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。

<a name="browsers"></a> 浏览器 
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a>操作系统
-----------------

有关操作系统要求的信息，请参阅[获取 Microsoft 团队的客户端](get-clients.md)。


