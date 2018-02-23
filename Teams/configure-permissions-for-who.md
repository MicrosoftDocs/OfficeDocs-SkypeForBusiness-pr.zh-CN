---
title: "针对 Who 配置权限"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "在 Microsoft Teams 中部署云语音功能实践指导"
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5afb795e98accc1e441572d5fc56da16cb4d75
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
<a name="configure-permissions-for-who"></a>针对 Who 配置权限
=============================

用户可以结合使用 Who 应用与 Microsoft Teams 来帮助他们根据其处理的内容及其共事的人员提出问题并在组织中查找任何人。

为了确保用户可以充分利用 Who，你必须在 Microsoft Graph 中启用以下成员权限。

- Calendars.Read

- Calendars.Read.Shared

- Mail.Read

- MailboxSettings.ReadWrite

- People.Read

- People.Read.All

- Sites.Read.All

- User.Read.All

有关如何管理 Microsoft Graph 权限范围的详细信息，请参阅[权限范围](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes)。
 
有关 Microsoft Graph 权限的详细信息，请参阅 [Microsoft Graph 权限参考](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference)。