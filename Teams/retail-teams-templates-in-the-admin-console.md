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
description: 了解如何通过使用管理中心提供预定义的设置、频道和预安装的应用，使用 Teams 模板创建专为零售商需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662637"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>在管理中心使用 Teams 零售模板

Teams 模板提供预定义的设置、频道和预安装应用模板，让你快速轻松地创建团队。

Teams 模板具有围绕零售商需求设计的团队结构的预构建定义。 可以使用 Teams 模板快速创建适用于零售商的团队类型，并在整个组织中部署它们。 还可以扩展 Teams 模板，创建根据特定组织需求定制的团队。

本文将介绍每个 Teams 模板，以及我们建议如何使用它们。

如果你负责规划、部署和管理整个零售组织的多个团队，本文适合你。 我们假设你已在组织中部署了 Teams 服务。 如果尚未推出 Teams，请首先阅读"如何推出[Microsoft Teams"。](How-to-roll-out-teams.md)

若要了解有关团队模板的一般信息，请参阅 [Teams 模板入门](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="organize-a-store"></a>组织商店

将零售员工汇集在一个中心体验中，以管理任务、共享文档和解决客户问题。 集成其他应用程序，以简化&流程。

| 基本模板类型 |baseTemplateId | 此基本模板提供的属性 |
| ------------------|-- |----------------------------------------------------- |
|组织商店|`retailStore`|频道： <ul><li>常规<li>Shift 切换</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>管理器协作

管理器协作模板非常适合为一组经理创建团队，以跨商店/区域等进行协作。例如，如果您的组织有区域，您可以为加利福尼亚州创建经理协作团队，并包括该区域的所有商店经理，以及该区域的区域经理。

| 基本模板类型| baseTemplateId | 此基本模板提供的属性 |
| ------------------|- |----------------------------------------------------- |
|零售 - 管理器协作|`retailManagerCollaboration` |频道： <ul><li>常规<li>运营</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
||||
