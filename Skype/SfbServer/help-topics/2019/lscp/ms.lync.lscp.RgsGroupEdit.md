---
title: 响应组创建新的或编辑现有的代理组
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: 代理组定义可应答针对响应组（称为代理）的呼叫的人员以及应用于组中所有代理的设置。
ms.openlocfilehash: 944cd48745a2524ccfcd795d9edc60e806859301
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118961"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>响应组：创建新的或编辑现有的代理组

代理组定义可应答针对响应组（称为代理）的呼叫的人员以及应用于组中所有代理的设置。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称** 每个代理组都需要唯一的名称。 使用标识组函数的描述性名称。 例如，技术支持。

- **说明** 此字段是可选的。 使用它提供有关组的其他详细信息。

- **参与策略** 指定代理登录到响应组的方式：

  - 选择 **"** 非正式"指定组中代理无需登录和注销。非正式代理在登录时自动登录。 默认设置为“非正式”。

  - 选择 **"** 正式"指定组中代理必须登录和注销。选择此选项后，代理将单击客户端中的菜单项以打开浏览器并显示用于登录和退出的网页控制台。

- **警报时间 (秒)** 指定在将呼叫提供给下一个可用代理之前拨打代理的秒数。 该值必须至少为 10 秒且小于 180 秒。 默认值为 20 秒。

- **路由方法** 选择用于确定代理接收呼叫的顺序的方法：

  - 选择“最长空闲时间”可将新呼叫优先路由至空闲（处于“空闲”或“非活动”的状态）时间最长的代理。

  - 选择“并行”可将新呼叫同时路由至所有空闲的代理。呼叫将发往第一个接受该呼叫的代理。

  - 选择“循环”可将新呼叫轮流路由至每个代理。

  - 选择“串行”将新呼叫始终按照“代理”列表中代理的排列顺序路由至代理。

  - 选择 **"** 助理"可同时向已登录的所有代理和响应组应用程序提供新呼叫，无论其当前状态如何。 配置为代理的助理和客户端用户可以查看所有正在等待的呼叫，并可以按任意顺序应答等待中的呼叫。 呼叫将发送给第一个接受该呼叫的代理，其他助理和用户不会再看到该呼叫。

- **代理** 通过下列方法之一选择作为响应组代理的用户：

  - 选择 **"使用现有电子邮件通讯组列表** "以使用 Exchange 通讯组列表。 在“通讯组列表地址”中键入该通讯组列表的电子邮件地址。

    > [!NOTE]
    > 只能为每个代理组选择一个通讯组列表。如果通讯组列表包括嵌套的通讯组列表，则该嵌套的通讯组列表将不会被包括在代理组中。

    > [!NOTE]
    > 通讯组列表中代理排列的顺序将影响代理接收呼叫以进行循环和串行路由的顺序。

    > [!NOTE]
    > 响应组管理员或用户可能会看到隐藏成员身份或隐藏列表。 有关详细信息，请参阅[Create or modify an agent group in Skype for Business。](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)

  - 选择“定义自定义代理组”可选择您要分配为响应组代理的用户。单击“选择”可将代理添加到列表中。单击“删除”可从列表中删除所选代理。

    向上和向下箭头可在代理列表中向上和向下移动所选代理。列表中代理的排列顺序将影响代理接收呼叫以进行循环和串行路由的顺序。

有关响应组特性和功能的详细信息，请参阅规划文档中的 Plan [for the Response Group application in Skype for Business Server。](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) 有关使用代理组的详细信息，请参阅操作文档中的[Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups)。