---
title: 为 Microsoft Teams 设置呼叫分析
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 设置每用户呼叫分析，以识别和排查 Microsoft Teams 呼叫质量问题。
ms.openlocfilehash: bcfe39ccdd9a1a751b49cdc8d0f433e3707635e3
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789937"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>为 Microsoft Teams 设置呼叫分析

作为 Microsoft Teams 管理员，可以使用每用户呼叫分析来排查 Teams 呼叫质量和 **单个用户** 的连接问题。 若要充分利用调用分析，请设置以下各项：
  
- 为人员（如支持人员代理）分配专用支持角色，让他们查看用户的呼叫分析。 这些支持角色无法访问 Teams 管理中心的其余部分。 
    
- 通过上传 .tsv 或 .csv 数据文件，将生成、站点和租户信息添加到每个用户的呼叫分析。
    
准备好开始使用每用户呼叫分析时，请阅读 [“使用每用户呼叫分析”来排查通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>授予支持人员和支持人员的权限

作为 Teams 管理员，你完全有权为所有用户调用分析信息。 我们创建了一些专门的 Azure Active Directory 角色，你可以将其分配给支持人员和支持人员代理，以便他们还可以访问每用户呼叫分析 (而无需访问 Teams 管理中心) 的其他成员。 将 **Teams 通信支持专家** 角色分配给用户，这些用户对每用户呼叫分析的视图应该有限， (第 1 层支持) 。 将 **Teams 通信支持工程师** 角色分配给需要完全访问每用户呼叫分析 (第 2 层支持) 的用户。 这两个角色都无权访问 Teams 管理中心的其余部分。

若要了解每个角色的作用，请阅读 [每个 Teams 支持角色的作用](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)？

有关 Teams 管理员角色的详细信息，请参阅 [使用 Teams 管理员角色来管理 Teams](using-admin-roles.md)。 若要了解如何在 Azure Active Directory 中分配管理员角色，请参 [阅 Azure Active Directory 中的查看和分配角色](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

若要了解如何在 Azure Active Directory 中分配管理角色，请 [参阅 Azure Active Directory 中的查看和分配角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>上传 .tsv 或 .csv 文件以添加建筑物、站点和租户信息

可以通过上传.csv或 .tsv 文件，将生成、站点和租户信息添加到每个用户的呼叫分析。 使用所有这些信息，调用分析可以将 IP 地址映射到物理位置。 管理员和支持人员代理可以使用此信息来帮助发现呼叫问题的趋势。 例如，为什么同一建筑中的用户遇到类似的呼叫质量问题？ 

如果你是 Teams 或Skype for Business管理员，则可以使用现有租户并从 Teams 或 Skype for Business 调用质量仪表板 (CQD) 生成数据文件。 首先，从 CQD 下载文件，然后上传该文件以调用分析。 

- 若要下载现有数据文件，请转到 **Microsoft Teams 管理中心** > **Analytics &立即报告** > **通话质量仪表板** > **上传**。 在 **“我的上传** ”列表中，单击所需文件旁边的 **“下载** ”。 

- 若要上传新文件，请参阅 [“添加和更新报告标签](/microsoftteams/learn-more-about-site-upload)”。
  
如果要从头开始创建 .tsv 或 .csv 文件，请参阅 [上传租户和生成数据](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>相关主题

[使用每用户呼叫分析来排查通话质量差的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
