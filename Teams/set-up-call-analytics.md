---
title: 为事件设置Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
description: 设置每用户呼叫分析，以识别并排查Microsoft Teams质量问题。
ms.openlocfilehash: be93a24f7d18e5b347c6375622ca47c3bdaeae26
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556473"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>为事件设置Microsoft Teams

作为Microsoft Teams管理员，可以使用每个用户的呼叫分析来排查Teams用户的呼叫质量和 **连接问题**。 若要充分利用呼叫分析，请设置以下各项：
  
- 向人员（例如支持人员代理）分配专门的支持角色，让他们查看用户的呼叫分析。 这些支持角色无法访问管理中心Teams角色。 
    
- 通过上传 .tsv 或 .csv数据文件，将建筑物、站点和租户信息添加到每个用户的调用分析。
    
准备好开始使用按用户的呼叫分析时，请阅读使用按用户的呼叫分析来排查 [通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>授予支持和支持人员的权限

作为Teams管理员，你可以完全访问所有用户的呼叫分析信息。 我们创建了一些可分配给支持人员和支持人员代理的专用 Azure Active Directory 角色，以便他们还可以访问每个用户的呼叫分析 (而无需访问 Teams 管理中心) 的其余部分。 将 **Teams通信支持专家** 角色分配给应具有按用户呼叫分析有限视图的用户， (第 1 层支持) 。 将 **Teams通信支持工程师** 角色分配给需要完全访问每用户呼叫分析的用户， (第 2 层支持) 。 两个角色都无法访问管理中心Teams的其余部分。

若要了解每个角色的作用，请阅读每个角色Teams[角色的作用](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)？

有关管理员角色Teams，请参阅使用 Teams [管理员角色管理Teams](using-admin-roles.md)。 若要了解如何在任务中分配管理员Azure Active Directory，请参阅[在 Azure Active Directory 中查看和分配Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

若要了解如何在任务中分配管理Azure Active Directory，请参阅[在 Azure Active Directory 中查看和分配Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Upload .tsv 或 .csv 文件以添加建筑物、站点和租户信息

可以通过上传 .csv 或 .tsv 文件，将建筑物、站点和租户信息添加到每个用户的调用分析。 使用所有这些信息，调用分析可以将 IP 地址映射到物理位置。 管理员和技术支持代理可以使用此信息来帮助发现呼叫问题的趋势。 例如，为什么同一大楼中的用户遇到类似的呼叫质量问题？ 

如果你是管理员或Teams Skype for Business，可以使用现有租户和从 Teams 生成数据文件，或者Skype for Business CQD 仪表板 (生成) 。 首先，从 CQD 下载文件，然后上传它以调用分析。 

- 若要下载现有数据文件，请转到管理Microsoft Teams **Analytics** >  &**"** >  > 设置质量仪表板 **Upload。** 在"**我的上传"列表中****，单击文件** 旁边的"下载"。 

- 若要上传新文件，请参阅 [添加和更新报告标签](/microsoftteams/learn-more-about-site-upload)。
  
如果要从头开始创建 .tsv 或 .csv 文件，请参阅Upload[租户和建筑物数据](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>相关主题

[使用每个用户的呼叫分析来排查通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
