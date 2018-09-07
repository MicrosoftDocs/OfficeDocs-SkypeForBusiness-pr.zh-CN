---
title: 针对 Who 配置权限
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 在 Microsoft Teams 中部署云语音功能实践指导
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc8fe9a21cdfa4d1df0bf3f11631d103a13fe94b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860212"
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

有关如何管理 Microsoft Graph 权限范围的详细信息，请参阅[权限范围](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes)。
 
有关 Microsoft Graph 权限的详细信息，请参阅 [Microsoft Graph 权限参考](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)。