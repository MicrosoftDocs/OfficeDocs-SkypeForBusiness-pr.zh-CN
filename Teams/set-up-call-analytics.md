---
title: 为 Microsoft 团队设置呼叫分析
ms.author: lolaj
author: LolaJacobsen
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
description: 设置每用户呼叫分析以识别和解决 Microsoft 团队通话质量问题。
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085308"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>为 Microsoft 团队设置呼叫分析

作为 Microsoft 团队管理员，你可以使用每用户调用分析来解决团队呼叫**单个用户**的质量和连接问题。 若要充分利用呼叫分析，请设置以下内容：
  
- 将专用支持角色分配给人员（如帮助台代理），让他们可以查看用户的呼叫分析。 这些支持角色无法访问团队管理中心的其余部分。 
    
- 通过上载 tsv 或 .csv 数据文件，将生成、网站和租户信息添加到每用户调用分析。
    
当您准备好开始使用每用户呼叫分析时，请参阅[使用每用户呼叫分析来解决较差的通话质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>向支持部门和帮助台人员提供权限

作为团队管理员，您拥有对所有用户的 "调用分析" 信息的完全访问权限。 我们创建了一些专用的 Azure Active Directory 角色，你可以将其分配给支持人员和帮助台代理，以便他们也可以访问每个用户的呼叫分析（无需访问团队管理中心的其他人员中心）。 将**团队通信支持专家**角色分配给应该具有受限视图的每用户调用分析的用户（第1层支持）。 将**团队通信支持工程师**角色分配给需要对每用户调用分析具有完全访问权限的用户（第2层支持）。 这两个角色都有权访问团队管理中心的其余部分。

若要了解每个角色的用途，请阅读[每个团队支持角色执行哪些操作](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)？

有关团队管理员角色的详细信息，请参阅[使用团队管理员角色管理团队](using-admin-roles.md)。 若要了解如何在 Azure Active Directory 中分配管理员角色，请参阅[在 Azure Active directory 中查看和分配角色](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

若要了解如何在 Azure Active Directory 中分配管理角色，请参阅[在 Azure Active directory 中查看和分配角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>上载 tsv 或 .csv 文件以添加建筑物、网站和租户信息

你可以通过上载 .csv 或 tsv 文件，将生成、网站和租户信息添加到每用户调用分析。 有了所有这些信息，呼叫分析可以将 IP 地址映射到物理位置。 管理员和帮助台工程师可以使用此信息来帮助发现通话问题的趋势。 例如，为什么同一建筑物中的用户有类似的通话质量问题？ 

如果你是团队或 Skype for business 管理员，则可以使用现有租户并通过 "团队" 或 "Skype for business 呼叫质量" 仪表板（CQD）构建数据文件。 首先，从 CQD 下载文件，然后将其上传到 "调用分析"。 

- 若要下载现有数据文件，请转到**Microsoft 团队管理中心**  >  **呼叫质量仪表板**"  >  **立即上载**"。 在 "**我的上载**" 列表中，单击所需文件旁边的 "**下载**"。 

- 若要上传新文件，请转到 " **Microsoft 团队管理中心**  >  "**位置**，然后选择 "**上载位置数据**" 或 "**替换位置数据**"。
  
如果要从头开始创建 tsv 或 .csv 文件，请参阅[上载租户和生成数据](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>相关主题

[使用每用户呼叫分析解决较差的通话质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
