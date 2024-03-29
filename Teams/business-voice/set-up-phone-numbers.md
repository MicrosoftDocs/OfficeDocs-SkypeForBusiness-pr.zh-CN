---
title: 使用呼叫计划电话号码设置Microsoft Teams 电话系统
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何为组织中的用户和服务设置Microsoft Teams 电话系统通话套餐电话号码。
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
- M365initiative-voice
- highpri
ms.openlocfilehash: 9e8da251893cfb26ecee02cab4562ffa8675164b
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584513"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>步骤 2：设置 Teams 电话系统电话号码

在组织中设置用户或自动助理之前，需要为他们获取电话号码。 有几种不同类型的电话号码，但下面是需要在此步骤中添加的两种类型的号码：

- **服务编号** 这些数字用于自动助理、音频会议和呼叫队列。 它们可以是收费号码或免费号码，可以同时处理大量呼叫。 你的公司电话号码需要是一个服务号码，因为它将在后续步骤中分配给自动助理。
- **订阅服务器号码** 这些号码用于普通用户，以便他们能够拨打和接听电话。

> [!IMPORTANT]
> 即使要使用现有电话号码，也需要创建临时电话号码并将其分配给公司的主电话线和用户。 在后续步骤中，你将能够将这些临时号码替换为现有的电话号码。

> [!NOTE]
> 新电话号码可能需要几个小时才能在 Teams 中使用。

## <a name="set-up-a-service-number"></a>设置服务编号

现在设置的服务号码将在后续步骤中用于公司的主要电话号码。

1. 打开 Microsoft Teams 管理中心，并使用全局管理员用户登录 (这通常是用于注册 Microsoft 365) 的帐户。
2. 在左侧导航栏中，转到 <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**“语音** > **电话号码**</a>”，然后单击 **“添加**”。
3. 输入订单的名称并添加说明。
4. 在“位置和数量”页上，执行以下操作：
    1. 在 **“国家或地区**”下，选择一个国家或地区。
    2. 在 **“数字”类型** 下，选择以下选项之一：

        - **自动助理 (收费)** 常规、非免费电话号码。 向呼叫者收取长途费用。
        - **自动助理 (免费)** 免费 (美国和加拿大) 或免费电话 (英国) 电话号码。 长途费用会向公司收费。 在选择此选项之前，需要购买通信额度。 有关详细信息，请参阅需要[购买哪些内容来获取中小型企业的语音功能？](whats-business-voice.md)

    3. 在 **“数量**”下，选择 **1**。
        > [!NOTE]
        > 如果收到消息， **你没有足够的许可证来请求更多此类号码**，请确保已购买具有通话套餐捆绑包许可证的 Teams 电话。 有关详细信息，请参阅需要[购买哪些内容来获取中小型企业的语音功能？](whats-business-voice.md)
    4. 选择 **位置** 或 **区域代码**，具体取决于是要使用位置的城市搜索电话号码，还是要在特定区域代码中搜索号码。
    5. 如果选择 **“位置”**：

        1. 在 [“设置紧急位置](set-up-emergency-locations.md) ”步骤中键入紧急地址所在的城市，或者如果需要为其他办公室或家庭办公室创建新位置，请单击 **“添加位置**”。
        2. 在 **“区域代码**”下，选择一个区域代码，然后选择 **“下一步** ”以保留你的号码。

    6. 如果选择 **“区域代码**”，请键入要搜索的区域代码，然后选择 **“下一步** ”以保留号码。

5. 选择所需的号码。 有 10 分钟的时间选择电话号码并下订单。 如果花费超过 10 分钟，电话号码将返回到号码池。
6. 准备好下订单后，单击 **“放置”订单**，然后 **完成**

## <a name="set-up-phone-numbers-for-your-users"></a>为用户设置电话号码

1. 打开 Microsoft Teams 管理中心，并与全局管理员用户一起登录。这通常是用于注册 Microsoft 365 的帐户。
2. 在左侧导航栏中，转到 <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**“语音** > **电话号码**</a>”，然后单击 **“添加**”。
3. 输入订单的名称并添加说明。
4. 在“位置和数量”页上，执行以下操作：

    1. 在 **“国家或地区**”下，选择一个国家或地区。
    2. 在 **“数字”类型** 下，选择 **“用户 (订阅服务器)**”。
    3. 在 **“数量**”下，输入所需的组织数量。
    4. 选择 **位置** 或 **区域代码**，具体取决于是要使用位置的城市搜索电话号码，还是要在特定区域代码中搜索号码。
    5. 如果选择 **“位置”**：

        1. 在 [“设置紧急位置](set-up-emergency-locations.md) ”步骤中键入紧急地址所在的城市，或者如果需要为其他办公室或家庭办公室创建新位置，请单击 **“添加位置**”。
        2. 在 **“区域代码**”下，选择一个区域代码，然后选择 **“下一步** ”以保留你的号码。

    6. 如果选择 **“区域代码**”，请键入要搜索的区域代码，然后选择 **“下一步** ”以保留号码。
5. 选择所需的数字。 有 10 分钟的时间选择电话号码并下订单。 如果花费超过 10 分钟，电话号码将返回到号码池。
6. 准备好下订单后，单击 **“放置”订单**，然后 **完成**。

> [!div class="nextstepaction"]
> [下一步：向 Teams 用户分配许可证](set-up-licenses.md)
