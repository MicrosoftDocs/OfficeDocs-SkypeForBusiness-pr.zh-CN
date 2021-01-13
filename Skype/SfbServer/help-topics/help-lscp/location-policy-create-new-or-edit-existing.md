---
title: 位置策略创建新的或编辑现有的
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
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: 您可以配置位置策略以确定是否启用增强型 9-1-1 (E9-1-1) 、如何使用它，以及如何为用户和联系人使用位置信息。
ms.openlocfilehash: f171d841ec68b3e0b0b4f7c8b9d374ff2261d149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803962"
---
# <a name="location-policy-create-new-or-edit-existing"></a>位置策略：创建新的或编辑现有的

您可以配置位置策略以确定是否启用增强型 9-1-1 (E9-1-1) 、如何使用它，以及如何为用户和联系人使用位置信息。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **范围** 标识要创建或修改的位置策略的范围：全局、站点或用户。

- **名称** 每个位置策略都需要一个名称。 默认情况下会命名全局和站点位置策略，并且无法更改该名称。 对于用户位置策略，请使用用于标识用户或用户组的描述性名称。

    > [!NOTE]
    > 保存位置策略后，无法更改该名称。

- **启用增强型 9-1-1 (E9-1-1)** 选中此复选框，为分配了此位置策略的用户启用 E9-1-1。

- **位置** 指定是否提示用户提供位置信息：

  - **必需** 如果用户的客户端注册到新位置时提示用户输入位置信息，请选择此选项。 用户无需输入位置信息即可消除提示。

  - **不是必需的** 如果未提示用户输入位置信息，请选择此选项。

  - **免责声明** 如果要提示用户输入位置信息，但如果用户拒绝提示而不输入信息，则会看到免责声明消息，请选择此选项。 在用户输入位置信息之前，用户可以完成紧急呼叫，但不能完成其他呼叫。

- **仅对 E9-1-1 使用位置** 如果位置信息仅用于紧急呼叫，请选中此复选框。

- **PSTN 用法** 选择 PSTN (PSTN) 公用电话交换网，该用法将用于确定哪些语音路由将用于路由来自使用此配置文件的客户端的紧急呼叫。 与此用法关联的路由应指向专用于紧急呼叫的 SIP 中继或紧急位置标识号 (ELIN) 网关，该网关将紧急呼叫路由到最近的公共安全应答点 (PSAP) 。 选项为 **内部**、 **本地** 或 **长距离**。

- **E9-1-1 拨号号码** 指定为访问紧急服务而拨打的号码。

- **E9-1-1 拨号掩码** 指定用户拨打的号码，然后转换为紧急拨号号码。 例如，在此字段中输入值 212，以便用户可以拨打 212 来访问紧急服务。 这样，可以拨打备用紧急号码，并且仍可将呼叫联系紧急服务 (例如，如果来自某个国家/地区或地区的用户尝试拨打该国家/地区或地区的号码，而不是当前位于) 中的某个国家/地区的号码。 您可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212;414。 字符串的最大长度为 100 个字符。 每个字符都必须为 0 到 9 的数字。

    > [!IMPORTANT]
    > 请确保拨号掩码与呼叫号码范围中的号码不同，因为呼叫停止路由优先于紧急拨号字符串转换。 To see the Call Park number ranges， click **Voice Features** in the left navigation bar， and then click **Call Park.**

- **通知 URI** 指定进行紧急呼叫时要通知的一个或多个 SIP URI。 例如，键入公司安全办公室的 SIP URI，以在发出紧急呼叫时通过即时消息通知安全人员。 如果呼叫者的位置可用，则通知中会包含该位置。 可以将多个 SIP URI 指定为逗号分隔列表。 例如，"sip：security@litwareinc.com"，"sip：kmyer@litwareinc.com"。 字符串长度必须为 1 到 256 个字符，必须以前缀"sip："开头。 还可以指定通讯组列表。

- **会议 URI** 指定 SIP URI (电话号码，在这种情况下，) 第三方参加紧急呼叫会议。 例如，键入公司安全办公室的电话号码，以便他们在拨打紧急呼叫时收到呼叫。 会议模式 **设置** 确定第三方是否可以参与还是仅收听呼叫。 该字符串的长度必须为 1 到 256 个字符，并且必须以前缀 sip: 开头。

- **会议模式** 如果为会议 **URI 指定了** 值，则此字段设置为下列值之一：

  - **单向** 指定第三方只能侦听呼叫者与 PSAP 接线员之间的呼叫。

  - **双向** 指定第三方可以参与呼叫者与 PSAP 接线员之间的呼叫。

有关紧急企业语音功能的详细信息，请参阅规划文档中的 [E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 概述。 有关使用位置策略的详细信息，请参阅操作文档中的[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。


