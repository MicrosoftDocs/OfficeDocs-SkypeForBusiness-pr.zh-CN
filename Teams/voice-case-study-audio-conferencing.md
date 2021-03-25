---
title: Teams 语音 Contoso 案例研究
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
description: 针对多语言公司的 Teams 语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121300"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso 案例研究：音频会议

为了了解音频会议是什么、它的成本、可用性及其工作原理 &mdash; &mdash; ，Contoso 查看了 Office [365](deploy-audio-conferencing-teams-landing-page.md)中的音频会议。 

## <a name="overview"></a>概述 

对于音频会议，Contoso 使用组织内部以及外部已知的电话号码。 由于 Contoso 希望尽可能保留这些号码，因此他们查看了有关向音频会议网桥分配专用和共享电话号码的信息。 

Contoso 根据他们的研究做出以下决策： 

- 只有定期主持音频会议呼叫的一部分用户会收到音频会议许可证。 

- Contoso 将使用专用电话号码并移植其现有号码以用于音频会议。   

由于 Contoso 用户使用的是 Skype for Business，并且所有用户的邮箱都位于联机状态，因此许多用户已安排了现有会议。 Contoso 阅读使用会议迁移 [服务 (MMS ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)) 了解当 Contoso 将最终用户更改为 TeamsOnly 模式时，会自动更新现有会议。  


## <a name="configuration"></a>配置

与音频会议关联的电话号码称为电话系统内的服务号码。 

- 对于使用呼叫计划的位置，为了将现有电话号码从电话运营商移植到 Office 365，Contoso 按照获取服务电话号码 [中的步骤操作](getting-service-phone-numbers.md)。

- 为了在技术试点中向最终用户分配音频会议许可证，Contoso 管理员按照管理组织的音频会议设置中的 [步骤操作](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)。 

- 对于业务试点和迁移，Contoso 遵循 [在 Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)中按组成员身份向用户分配许可证中的步骤，使用基于组的许可。  

 

