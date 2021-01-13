---
title: 位置策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: 948fb5cb6a5457b512af3fc7d230adf27c304bd2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803952"
---
# <a name="location-policy"></a>位置策略

位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。

位置策略包括全局策略以及可选的一个或多个站点和用户策略：

- **全局策略：** 默认情况下，将创建全局策略。 可以编辑全局策略，但无法将其删除。 如果您尝试删除全局策略，则所有设置将重置为默认值。

- **网站策略 (可选) ：** 可以创建一个或多个站点位置策略，每个策略都适用于特定网站。 站点策略会覆盖全局策略。

- **用户策略 (可选) ：** 可以创建一个或多个用户位置策略，每个策略都适用于特定用户或用户组。 用户策略会覆盖全局策略和站点策略。

> [!NOTE]
> 也可以向网络站点（即子网组）分配位置策略。 分配给网络站点的位置策略优先于所有其他用户策略。 有关使用 cmdlet 向网络站点分配位置策略的详细信息，请参阅在 [Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)中向网络站点添加位置策略。 有关使用 Skype for Business Server 控制面板向网络站点分配位置策略的详细信息，请参阅["配置网络站点"。](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)

“位置策略”页显示一个为组织定义的所有位置策略的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“位置策略”页上执行以下任务：

- 创建新的站点位置策略或用户位置策略

- 更改全局策略或现有站点策略或用户策略

- 删除站点策略或用户策略

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新建** 启动新的站点位置策略或用户位置策略。

- **编辑** 打开所选位置策略进行编辑，选择列表中的所有位置策略，或删除所选站点策略或用户策略。

    > [!NOTE]
    > 对于全局策略，“删除”会将设置重置为默认值。

- **刷新** 刷新位置策略列表。

下表介绍了该页上的各个字段。

- **名称** 标识位置策略。

- **范围** 标识位置策略的范围：全局、站点或用户。

- **E9-1-1** 如果为分配了此位置策略的用户启用了 E9-1-1，则选中。

- **位置** 指定当用户的客户端在 Skype for Business Server 的新位置注册时是否提示用户输入位置信息，以及如果用户在未输入位置信息的情况下消除提示，是否看到免责声明。

- **PSTN 用法** 指定公用电话交换网 (PSTN) 用法，用于确定用于使用此配置文件路由来自客户端的紧急呼叫的语音路由。

- **E9-1-1 号码** 指定为访问紧急服务而拨打的号码。

- **E9-1-1 掩码** 指定用户拨打的号码，然后转换为紧急拨号号码。

有关紧急企业语音功能的详细信息，请参阅规划文档中的 [E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 概述。 有关使用位置策略的详细信息，请参阅操作文档中的[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。


