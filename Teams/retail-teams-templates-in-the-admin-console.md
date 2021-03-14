---
title: 在管理中心使用 Teams 零售模板
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用 Teams 模板通过管理中心提供预定义的设置、频道和预安装的应用，从而创建针对零售商需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662637"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>在管理中心使用 Teams 零售模板

Teams 模板提供预定义的设置、频道和预安装的应用模板，让你能够快速轻松地创建团队。

Teams 模板具有预先构建的围绕零售商需求设计的团队结构定义。 可使用 Teams 模板快速创建适用于零售商的团队类型，并在整个组织中部署它们。 你还可以扩展 Teams 模板，以创建根据特定组织需求量身定制的团队。

在本文中，我们将介绍各个 Teams 模板并建议如何使用它们。

如果你负责在整个零售组织中规划、部署和管理多个团队，则本文非常适合你。 假设你已在贵组织内部署 Teams 服务。 如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](How-to-roll-out-teams.md)。

若要了解有关常规团队模板的详细信息，请参阅[开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="organize-a-store"></a>组织商店

将你的零售员工汇集到一个中心体验中，以管理任务、共享文档和解决客户问题。 整合其他应用程序，以简化轮班开始和结束流程。

| 基本模板类型 |baseTemplateId | 此基本模板包含的属性 |
| ------------------|-- |----------------------------------------------------- |
|组织商店|`retailStore`|频道： <ul><li>常规<li>换班</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>经理协作

经理协作模板非常适合用于创建一个团队，供一组经理跨商店/地区进行协作等。例如，如果你的组织跨越多个地区，则可以为加利福尼亚地区创建一个经理协作团队，并包括该地区的所有商店经理以及该地区的区域经理。

| 基本模板类型| baseTemplateId | 此基本模板包含的属性 |
| ------------------|- |----------------------------------------------------- |
|零售 - 经理协作|`retailManagerCollaboration` |频道： <ul><li>常规<li>运营</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
||||
