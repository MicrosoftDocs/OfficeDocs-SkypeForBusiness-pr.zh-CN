---
title: Teams语音 Contoso 案例研究：音频会议
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
description: Teams多语言公司语音案例研究：音频会议
appliesto:
- Microsoft Teams
ms.openlocfilehash: f25fa2e81244365d1c0c3dfcacf918f1b35a6fa71d2b619eaaa55c8aa219c310
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335792"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso 案例研究：音频会议

为了了解音频会议是什么、它的成本、可用性及其工作原理，Contoso 在 Office 365 中查看了 &mdash; &mdash; 音频[Office 365。](deploy-audio-conferencing-teams-landing-page.md) 

## <a name="overview"></a>概述 

对于音频会议，Contoso 使用组织内部以及外部已知的电话号码。 由于 Contoso 希望尽可能保留这些号码，因此他们查看了有关向音频会议网桥分配专用和共享电话号码的信息。 

Contoso 根据他们的研究做出以下决策： 

- 只有定期主持音频会议呼叫的一部分用户会收到音频会议许可证。 

- Contoso 将使用专用电话号码并移植其现有号码以用于音频会议。   

由于 Contoso 用户使用 Skype for Business并且所有用户的邮箱都驻留在联机状态，因此许多用户已计划现有会议。 Contoso 阅读使用会议迁移 [服务 (MMS ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)) 了解当 Contoso 将最终用户更改为 TeamsOnly 模式时，会自动更新现有会议。  


## <a name="configuration"></a>配置

电话音频会议关联的号码称为会议内电话系统。 

- 对于使用呼叫计划的位置，为了将现有电话号码从电话运营商移植到 Office 365，Contoso 按照获取服务电话号码[中的步骤操作](getting-service-phone-numbers.md)。

- 为了在技术试点中向最终用户分配音频会议许可证，Contoso 管理员按照管理组织的音频会议设置中的 [步骤操作](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)。 

- 对于业务试点和迁移，Contoso 按照在 中按组成员身份向用户分配许可证中的步骤使用[基于](/azure/active-directory/users-groups-roles/licensing-groups-assign)Azure Active Directory。  

 

