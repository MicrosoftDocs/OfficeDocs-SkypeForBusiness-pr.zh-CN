---
title: 位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: cb28dd60793da6681f2a8db71cf40ce8a5eda6fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293471"
---
# <a name="location-policy"></a>位置策略

位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。

位置策略包括全局策略以及可选的一个或多个站点和用户策略：

- **全球政策:** 默认情况下会创建全局策略。 可以编辑全局策略，但无法将其删除。 如果您尝试删除全局策略，则所有设置将重置为默认值。

- **网站策略 (可选):** 你可以创建一个或多个网站位置策略, 每个网站位置策略都适用于特定网站。 站点策略会覆盖全局策略。

- **用户策略 (可选):** 你可以创建一个或多个用户位置策略, 每个都适用于特定用户或用户组。 用户策略会覆盖全局策略和站点策略。

> [!NOTE]
> 也可以向网络站点（即子网组）分配位置策略。 分配给网络站点的位置策略优先于所有其他用户策略。 有关使用 cmdlet 将位置策略分配给网络网站的详细信息, 请参阅[在 Skype for Business Server 2015 中将位置策略添加到网络网站](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)。 有关使用 "Skype for Business 服务器" 控制面板将位置策略分配给网络网站的详细信息, 请参阅[配置网络站点](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)。

“**位置策略**”页显示一个为组织定义的所有位置策略的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**位置策略**”页上执行以下任务：

- 创建新的站点位置策略或用户位置策略

- 更改全局策略或现有站点策略或用户策略

- 删除站点策略或用户策略

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新**启动新的网站位置策略或用户位置策略。

- **编辑**打开所选的位置策略以对其进行编辑, 选择列表中的所有位置策略, 或删除所选网站策略或用户策略。

    > [!NOTE]
    > 对于全局策略，“**删除**”会将设置重置为默认值。

- **刷新**刷新位置策略的列表。

下表介绍了该页上的各个字段。

- **名称**标识位置策略。

- **范围**标识位置策略的范围: 全局、网站或用户。

- **E9-1-1**已检查用户分配了此位置策略的 E9-1-1。

- **位置**指定当用户在新位置向 Skype for business 服务器注册时, 是否提示用户输入位置信息, 以及他们是否可以在不输入位置信息的情况下发现该提示时看到免责声明。

- **PSTN 使用**指定用于确定用于从使用此配置文件的客户端路由紧急呼叫的语音路线的公共交换电话网络 (PSTN) 使用。

- **E9-1-1-1 号**指定为达到紧急服务而拨打的号码。

- **E9-1-1 掩码**指定用户拨出的号码, 然后将其转换为 "紧急电话拨号码"。

有关企业语音紧急服务功能和功能的详细信息, 请参阅规划文档中的[E9 概述 1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 。 有关使用位置策略的详细信息，请参阅操作文档中的[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。


