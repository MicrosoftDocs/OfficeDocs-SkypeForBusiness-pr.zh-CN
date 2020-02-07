---
title: Microsoft Teams 中的保留策略
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: 了解如何保留策略以及如何在团队中管理它们。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6adaee32648a6ec522098d90fd3c90ff161ef00e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838192"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft Teams 中的保留策略

默认情况下，团队对话保持不变并永久保留。 随着保留策略的推出，管理员可以在安全 & 合规性中心中配置保留策略（保留和删除），以便团队聊天和频道消息。 这有助于组织在特定时间段内保留数据以实现合规性（即保留策略）或删除数据（即删除策略）（如果在特定时间段后被视为负债）。 团队保留策略可确保在你删除数据时，团队服务上的所有永久数据存储位置都将删除该数据。

> [!NOTE]
> 我们尚不支持保留专用频道消息的配置。 支持在专用频道中共享的文件的保留。

若要管理团队保留策略，请在 "**信息管理** > **保留**" 下的 Office 365 安全 & 合规中心中使用设置和 cmdlet。

团队保留策略支持： 
    
- 保留：保留指定工期的工作组数据，然后不执行任何操作
- 保留并删除：将团队数据保留指定工期，然后删除
- 删除：在指定工期后删除团队数据

团队保留策略尚不支持：

- 高级保留策略不适用于团队聊天和团队频道消息位置

管理员可以为团队私人聊天（1:1 或1：许多聊天）和团队频道消息设置单独的保留策略。 在许多情况下，组织将专用聊天数据视为比频道消息更多的责任，这通常是更多与项目相关的对话。 在安全 & 合规性中心（**信息管理** > **保留**）中设置这些策略。 打开**团队频道消息**和**团队聊天**，然后定义这些位置的保留策略（也显示在下图中）。 

当您打开**团队频道消息**时，您可以指定将应用此策略的团队。 例如，对于团队 X、Y 和 Z，管理员可以将删除策略设置为1年（通过单独选择这些团队），并向团队的其余成员应用3年删除策略。 

你可以通过选择特定用户并应用唯一的保留策略来为**团队聊天**执行相同操作。 

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Retention-Policies.png)


> [!IMPORTANT]
> 团队频道消息位置和团队聊天位置仅解决存储在 Exchange Online 邮箱（用户和组邮箱）中的团队对话。 将从所有相关存储位置（即邮箱、基底和聊天服务）中删除这些消息。 
> 
> 若要管理团队文件（存储在 OneDrive for Business 和 SharePoint 中）的保留策略，请使用其保留策略。

根据设计，团队文件的删除策略是通过 SharePoint Online 和 OneDrive for Business 位置配置的。 因此，策略可能会删除团队聊天或频道消息中引用的文件，然后再删除这些邮件。 在这种情况下，文件仍将显示在 "团队" 消息中，但如果你单击该文件，你将收到 "找不到文件" 错误（如果有人手动删除 SharePoint Online 或 OneDrive for business 中的文件，也可能会发生此错误）。

有关配置 Office 365 的保留策略的详细信息，请阅读[保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。
 
