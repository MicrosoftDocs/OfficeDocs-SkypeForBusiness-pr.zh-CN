---
title: "Microsoft Teams 的 Office 365 相关性"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Microsoft Teams 依赖 Office 365 组、SharePoint Online 和 OneDrive for Business。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a>Microsoft Teams 的 Office 365 相关性
===========================================

Microsoft Teams 依赖 Office 365 组存储团队的成员身份和其他属性，例如，团队数据分类设置。 Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。 

Teams 还依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。 此外，Teams 还依赖 Office 365 组存储团队的成员身份和其他属性，例如，团队数据分类设置。 来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。
  
    
    
为了实现完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置选择**“开启”**：
  
    
    

- 在 SharePoint Online 中：**仅允许与已在目录中的外部用户共享**
    
    有关详细信息，请参阅[为你的 SharePoint Online 环境管理外部共享](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)。
    
  
- 在 Office 365 组中：**允许组所有者将组织外部的人员添加到组**
    
    有关详细信息，请参阅[控制对 Microsoft Teams 的来宾访问](#controlguest)。
  

你可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置。 有关更多详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。