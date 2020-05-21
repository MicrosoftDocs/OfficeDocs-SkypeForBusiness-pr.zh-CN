---
title: Teams 会议中的演示者和参与者功能
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解 Teams 会议中的演示者和参与者功能。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 11c5858532ade4fd4ed00f7c8f6d1d0c94baeb2d
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321731"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Teams 会议中的演示者和参与者功能
======================================================

Microsoft Teams 会议支持多种参与者类型。 参与者可以根据自己在组织内部或外部的角色访问各种会议功能。

可用的会议功能有：

- 聊天（包括照片和贴纸）
- 会议记录
- 白板
- 录制
- 文件
- 安排会议（仅适用于会议）

本文介绍了这些参与者功能以及他们对会议功能的访问权限。

## <a name="presenters-and-organizers"></a>演示者和组织者

演示者和组织者包括以下内容：

- 来自我的组织的演示者
- 来自其他组织的演示者 - 包括匿名和外部参与者。 演示者由组织者指定，且需要具有来自组织者的个人邀请。

演示者和组织者可访问会议或直播活动中的所有功能。

## <a name="participants"></a>参与者

有多种类型的会议参与者：

- [租户内参与者](#in-tenant-participant)
- [来宾参与者](#guest-participant)
- [外部（联合）参与者](#external-federated-participant)
- [匿名参与者](#anonymous-participant)

### <a name="in-tenant-participant"></a>租户内参与者

租户内参与者为组织内部人员，并且具有租户凭据。 有关此类参与者的详细信息，请参阅[安全性与 Microsoft Teams](teams-security-guide.md#participant-types)。

|会议  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **功能**        | 会议前 | 会议中 | 会议后 |
| 聊天 | 是 | 是 | 是 |
| 会议记录 | 是 | 是 |是 |
| 白板 | 是 | 是 |是 |
| 录制 | 不适用 |是 | 是 |
| 文件 | 是 | 是 | 是 |
| 安排会议 | 是 | 不适用 | 不适用 |
|||||||

### <a name="guest-participant"></a>来宾参与者

来宾参与者是来自另一个组织的人员，该人员受邀基于 Azure Active Directory B2B 平台访问 Teams 或贵组织租户中的其他资源。 来宾用户可受邀加入常规会议和频道会议。 有关来宾参与者的详细信息，请参阅[来宾体验介绍](guest-experience.md#comparison-of-team-member-and-guest-capabilities)。

| 会议 |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **功能**        | 会议前 | 会议中 | 会议后 |
| 聊天 | 是 | 是 | 是 |
| 会议记录 | 是 | 是 | 是 |
| 白板 | 否 | 否 |否 |
| 录制 | 不适用 |否 | 否 |
| 文件 | 是 | 是 | 是 |
| 安排会议 | 否 | 不适用 | 不适用 |
|||||||

### <a name="external-federated-participant"></a>外部（联合）参与者

外部参与者是另一个组织中使用 Teams 的人员，该人员受邀加入会议，但无权访问贵组织中的其他共享资源。 外部用户参与者会出现在会议名单中，且其显示名称与他们在自己组织中的标识名称相同。 有关外部参与者的详细信息，请参阅[与其他组织的用户通信](communicate-with-users-from-other-organizations.md#external-access)。

| 会议（仅可作为来宾添加到团队） ||
|-|-|-|
| **功能** |||
| 聊天 | 不适用 |
| 会议记录 | 不适用 |  
| 白板 | 不适用 |
| 录制 | 不适用 |  
| 文件 | 不适用 |
| 安排会议 | 不适用 |
|||

### <a name="anonymous-participant"></a>匿名参与者

匿名参与者与外部用户类似，但其身份未被投映到会议中。 在加入时，他们将手动输入一个昵称。 有关匿名参与者的详细信息，请参阅[安全性与 Microsoft Teams](teams-security-guide.md#participant-types)。

| 会议  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **功能**        | 会议前 | 会议中 | 会议后 |
| 聊天 | 不适用 | 否 | 不适用 |
| 会议记录 | 不适用 | 否 | 不适用 |
| 白板 | 不适用 | 否 | 不适用 |
| 录制 | 不适用 | 否 | 不适用 |
| 文件 | 不适用 | 否 | 不适用 |
| 安排会议 | 不适用 | 不适用 | 不适用 |
|||||||

## <a name="related-topics"></a>相关主题

[安全性与 Microsoft Teams](teams-security-guide.md)

[Teams 中的来宾访问](guest-access.md)
