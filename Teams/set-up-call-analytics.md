---
title: 为 Microsoft Teams 设置呼叫分析
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 为 设置按用户通话分析，以识别和排查 Microsoft Teams 通话质量问题。
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117130"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>为 Microsoft Teams 设置呼叫分析

作为 Microsoft Teams 管理员，可以使用按用户的呼叫分析来排查单个用户的 Teams 通话质量和 **连接问题**。 若要充分利用呼叫分析，请设置以下各项：
  
- 向人员（例如支持人员代理）分配专门的支持角色，让他们查看用户的呼叫分析。 这些支持角色无法访问 Teams 管理中心的其余部分。 
    
- 通过上传 .tsv 或 .csv 数据文件，将建筑物、站点和租户信息添加到每个用户的调用分析。
    
当你准备开始使用按用户的呼叫分析时，请阅读使用每用户呼叫分析来 [排查通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>授予支持和支持人员的权限

作为 Teams 管理员，你可以完全访问所有用户的呼叫分析信息。 我们创建了一些专门的 Azure Active Directory 角色，你可以将其分配给支持人员和支持人员代理，以便他们还可以访问每个用户的呼叫分析 (而无需访问 Teams 管理中心) 的其余部分。 将 **Teams 通信支持专家** 角色分配给应具有按用户呼叫分析的有限视图的用户， (第 1 层支持) 。 将 **Teams 通信支持工程师** 角色分配给需要完全访问每用户呼叫分析的用户 (第 2 层支持) 。 两个角色都无法访问 Teams 管理中心的其余部分。

若要了解每个角色的作用，请阅读 [每个 Teams 支持角色的作用](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)是什么？

有关 Teams 管理员角色的信息，请参阅[使用 Teams 管理员角色管理 Teams。](using-admin-roles.md) 若要了解如何在 Azure Active Directory 中分配管理员角色，请参阅在 [Azure Active Directory 中查看和分配角色](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

若要了解如何在 Azure Active Directory 中分配管理角色，请参阅在 [Azure Active Directory 中查看和分配角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>上传 .tsv 或 .csv 文件以添加建筑物、站点和租户信息

可以通过上传 .csv 或 .tsv 文件，将建筑物、站点和租户信息添加到每个用户的调用分析。 使用所有这些信息，调用分析可以将 IP 地址映射到物理位置。 管理员和技术支持代理可以使用此信息来帮助发现呼叫问题的趋势。 例如，为什么同一大楼中的用户遇到类似的呼叫质量问题？ 

如果你是 Teams 或 Skype for Business 管理员，可以使用现有租户，然后从 Teams 或 Skype for Business 呼叫质量仪表板 (CQD) 。 首先，从 CQD 下载文件，然后上传它以调用分析。 

- 若要下载现有数据文件，请转到 Microsoft **Teams** 管理中心"立即  >  **调用质量仪表板**  >  **上传"。** 在"**我的上传"列表中****，单击文件** 旁边的"下载"。 

- 若要上传新文件，请转到 **Microsoft Teams 管理** 中心  >  **"** 位置"，然后选择"**上传位置** 数据"或"**替换位置数据"。**
  
如果要从头开始创建 .tsv 或 .csv 文件，请参阅 [上传租户和生成数据](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>相关主题

[使用每个用户的呼叫分析来排查通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)