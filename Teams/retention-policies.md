---
title: Microsoft Teams 中的保留策略
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
description: 了解如何保留策略以及如何管理这些团队中。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3c253569f642a8833d9bfad6677fe1a17624447
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640975"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft Teams 中的保留策略

团队对话是永久性的且保留默认情况下不限次数。 保留策略的引入，管理员可以在工作组聊天和频道邮件安全 & 合规性中心中配置保留策略 （保留和删除）。 这有助于组织保留特定时间段法规遵从性 （即保留策略） 的数据，或者如果认为是责任特定的一段时间后删除的数据 （即，删除策略）。 团队保留策略确保删除数据时，它从删除所有团队服务上的永久数据存储位置。 

若要管理团队保留策略，使用的设置和 cmdlet 在 Office 365 安全性 & 下**数据管理**的合规性中心 > **保留**。

支持团队保留策略： 
    
- 保留： 指定的持续时间保持团队数据并不执行任何操作
- 保留和然后删除： 团队数据保留在指定时间段，然后删除
- 删除： 指定的时间后删除团队数据

尚不支持团队保留策略：

- 高级的保留策略不适用于团队聊天和团队通道消息位置
- 少于 30 天的持续时间

管理员可以设置团队专用聊天 （1:1 或一对多聊天） 和团队通道消息的独立的保留策略。 在许多情况下，组织考虑为多个比通道消息，通常是与项目相关的更多对话责任的私人聊天数据。 设置安全 & 合规性中心**数据调控**这些策略 > **保留**。 打开**团队通道消息**和**团队聊天**，然后定义 （还如下图中所示） 这些位置的保留策略。 

当您打开**团队通道消息**时，您可以指定此策略将应用于哪个团队。 例如，团队 X、 Y、 和 Z，管理员可以 1 年后删除策略设置 （通过单独选择这些团队），并将 3 年删除策略应用于工作组的其余部分。 

您可以通过选择特定用户并应用唯一的保留策略的**团队聊天**执行相同的操作。 

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Retention-Policies.png)


> [!IMPORTANT]
> 团队通道消息位置和团队聊天位置仅地址存储在 Exchange Online 邮箱 （用户和组邮箱） 的团队对话。 从所有相关的存储位置，即邮箱、 基底和聊天服务中删除邮件。 
> 
> 若要管理保留策略的工作组文件，存储在 OneDrive for Business 和 SharePoint，使用它们的保留策略。

按照设计，为团队文件删除策略配置通过 SharePoint Online 和 OneDrive 业务位置。 因此，很可能策略无法删除之前删除这些消息获取团队聊天或通道邮件中引用的文件。 在这种情况下，该文件将仍显示在工作组邮件中，但如果您单击该文件，将出现"找不到文件"错误 （此种可能还出现不存在的策略，如果有人手动删除文件从 SharePoint Online 或 OneDrive for Business）。

有关为 Office 365 配置保留策略的详细信息，请阅读[的保留策略的概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。
 
