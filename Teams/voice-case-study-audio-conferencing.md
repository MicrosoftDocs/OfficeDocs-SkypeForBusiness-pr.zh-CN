---
title: 团队语音 Contoso 个案研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785983"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso 案例研究：音频会议

若要了解音频会议的 &mdash; 内容、it 成本、可用性和工作原理， &mdash; Contoso[在 Office 365 中查看音频会议](deploy-audio-conferencing-teams-landing-page.md)。 

## <a name="overview"></a>概述 

对于音频会议，Contoso 使用了组织内部和外部的电话号码。 由于 Contoso 希望在可能的情况下保留这些号码，他们已查看有关将专用电话号码和共享电话号码分配给音频会议桥的信息。 

根据其研究，Contoso 做出以下决策： 

- 只有定期托管音频会议呼叫的一段人口才会收到音频会议许可证。 

- Contoso 将使用专用电话号码，并将其现有号码与音频会议配合使用。   

由于 Contoso 用户使用 Skype for Business，并且所有用户的邮箱处于联机状态，因此许多用户已安排了现有会议。 Contoso[使用会议迁移服务（MMS）](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)进行阅读，了解当用户将最终用户更改为 TeamsOnly 模式时，将自动为 Contoso 更新现有会议。  


## <a name="configuration"></a>配置

与音频会议关联的电话号码称为电话系统中的服务号码。 

- 对于使用呼叫计划的位置，要将其电话运营商的现有电话号码移植到 Office 365，Contoso 按照[获取服务电话号码](getting-service-phone-numbers.md)中的步骤进行操作。

- 要将音频会议许可证分配给技术试验中的最终用户，Contoso 管理员按照[管理您的组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)中的步骤操作。 

- 对于商业试点和迁移，Contoso 使用基于组的许可，方法是按照在[Azure Active Directory 中按组成员身份将许可证分配给用户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)的步骤进行操作。  

 

 