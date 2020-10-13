---
title: 在管理中心中使用团队零售模板
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
description: 了解如何使用团队模板，通过使用管理中心提供预定义的设置、信道和预安装应用来创建专为零售需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40e21687aa3d14b0cb9d51d4ba5f856eada3c538
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424562"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>在管理中心中使用团队零售模板

[!INCLUDE [preview-feature](includes/preview-feature.md)]

团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。

团队模板具有围绕零售商需求设计的团队结构的预建定义。 你可以使用团队模板快速创建适用于零售商的团队类型，并在组织中部署这些团队。 您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。

在本文中，我们将介绍每个团队模板以及我们建议如何使用它们。

本文适用于您负责在您的零售组织中规划、部署和管理多个团队的情况。 我们假定你的组织中已部署团队服务。 如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。

若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="organize-a-store"></a>组织商店

将零售员工集中在一个中心体验中，以管理任务、共享文档和解决客户问题。 集成其他应用程序以简化班次开始 & 结束过程。

| 基本模板类型 |baseTemplateId | 此基本模板附带的属性 |
| ------------------|-- |----------------------------------------------------- |
|组织商店| `retailStore`|信道 <ul><li>常规<li>切换切换</li><li>培训</li></ul> 识别 <ul><li>源自</li></ul>|
||||

## <a name="manager-collaboration"></a>经理协作

经理协作模板非常适合为一组经理创建团队，以便在商店/地区等协作。例如，如果您的组织拥有区域，则可以为加利福尼亚地区创建经理协作团队，并包括该地区的所有商店经理以及该地区的地区经理。

| 基本模板类型| baseTemplateId | 此基本模板附带的属性 |
| ------------------|- |----------------------------------------------------- |
|零售经理协作|`retailManagerCollaboration` |信道 <ul><li>常规<li>运营</li><li>培训</li></ul> 识别 <ul><li>源自</li></ul>|
||||
