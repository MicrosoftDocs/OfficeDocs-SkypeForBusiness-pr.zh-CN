---
title: 响应组创建新的或编辑现有代理组
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: 代理组定义可应答针对响应组（称为代理）的呼叫的人员以及应用于组中所有代理的设置。
ms.openlocfilehash: 19ff8272e70ef56dfb92b537422fddefe0e69842
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819182"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>响应组：创建新的或编辑现有的代理组

代理组定义可应答针对响应组（称为代理）的呼叫的人员以及应用于组中所有代理的设置。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称** 每个代理组都需要唯一的名称。 使用标识组函数的描述性名称。 例如，技术支持。

- **说明** 此字段是可选的。 使用它提供有关组的其他详细信息。

- **参与策略** 指定代理登录到响应组的方式：

  - 选择 **"** 非正式"可指定组中代理无需登录和注销。非正式代理在登录时自动登录。 默认设置为“非正式”。

  - 选择 **"** 正式"可指定组中代理必须登录和注销。选择此选项后，代理将单击客户端中的菜单项以打开浏览器并显示用于登录和退出的网页控制台。

- **警报时间 (秒)** 指定在向下一个可用代理提供呼叫之前拨打代理电话的秒数。 该值必须至少为 10 秒且小于 180 秒。 默认值为 20 秒。

- **路由方法** 选择用于确定代理接收呼叫的顺序的方法：

  - 选择“最长空闲时间”可将新呼叫优先路由至空闲（处于“空闲”或“非活动”的状态）时间最长的代理。

  - 选择“并行”可将新呼叫同时路由至所有空闲的代理。呼叫将发往第一个接受该呼叫的代理。

  - 选择“循环”可将新呼叫轮流路由至每个代理。

  - 选择“串行”将新呼叫始终按照“代理”列表中代理的排列顺序路由至代理。

  - 选择 **"** 助理"可同时向已登录的所有代理和响应组应用程序提供新呼叫，无论其当前状态如何。 配置为代理的助理和客户端用户可以查看所有正在等待的呼叫，并可以按任意顺序应答等待的呼叫。 呼叫将发送给第一个接受该呼叫的代理，其他助理和用户不再看到该呼叫。

- **代理** 通过下列方法之一选择作为响应组代理的用户：

  - 选择 **"使用现有电子邮件通讯组列表** "以使用 Exchange 通讯组列表。 在“通讯组列表地址”中键入该通讯组列表的电子邮件地址。

    > [!NOTE]
    > 只能为每个代理组选择一个通讯组列表。如果通讯组列表包括嵌套的通讯组列表，则该嵌套的通讯组列表将不会被包括在代理组中。

    > [!NOTE]
    > 通讯组列表中代理排列的顺序将影响代理接收呼叫以进行循环和串行路由的顺序。

    > [!NOTE]
    > 响应组管理员或用户可能会看到隐藏的成员资格或隐藏列表。 有关详细信息，请参阅 [在 Skype for Business 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)中创建或修改代理组。

  - 选择“定义自定义代理组”可选择您要分配为响应组代理的用户。单击“选择”可将代理添加到列表中。单击“删除”可从列表中删除所选代理。

    向上和向下箭头可在代理列表中向上和向下移动所选代理。列表中代理的排列顺序将影响代理接收呼叫以进行循环和串行路由的顺序。

有关响应组特性和功能的详细信息，请参阅规划文档中 [的"规划 Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) 中的响应组应用程序"。 有关使用代理组的详细信息，请参阅操作文档中的[Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)。


