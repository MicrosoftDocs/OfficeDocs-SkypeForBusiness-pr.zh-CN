---
title: 使用Microsoft Teams 电话系统套餐电话号码设置呼叫
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 了解如何使用呼叫Microsoft Teams 电话系统为组织中用户和服务设置呼叫计划电话号码。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19d2b165e85620b0fb9e9e8242adacc4c07f2c53
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053251"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>步骤 2：设置Teams 电话系统电话号码

在组织中设置用户或自动助理之前，需要获取其电话号码。 有几种不同类型的电话号码，但以下是需要在此步骤中添加的两种类型的号码：

- **服务编号** 这些号码用于自动助理、音频会议和呼叫队列。 它们可以是收费或免费号码，可以同时处理大量呼叫。 公司电话号码需要是服务号码，因为稍后的步骤会将其分配给自动助理。
- **订阅者号码** 这些号码用于普通用户，以便他们可以拨打和接听电话。

> [!IMPORTANT]
> 即使想使用现有电话号码，也需要创建临时电话号码并将其分配给公司的主电话线和用户。 在稍后的步骤中，你可以将这些临时号码替换为现有电话号码。

> [!NOTE]
> 新电话号码可能需要几个小时才能在 Teams。

## <a name="set-up-a-service-number"></a>设置服务号码

现在设置的服务号码将用于公司主电话号码的后一步。

1. 打开 Microsoft Teams 管理中心，使用全局管理员用户登录 (该帐户通常是用于注册帐户Microsoft 365) 。
2. 在左侧导航栏中，转到"<a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**语音** > **电话号码**</a>"，然后单击"添加 **"**。
3. 输入订单的名称并添加说明。
4. 在"位置和数量"页上，执行以下操作：
    1. 在 **"国家/地区"** 下，选择一个或多个国家/地区。
    2. 在 **"数字类型**"下，选择以下选项之一：

        - **自动助理 (收费)** 常规非免费电话号码。 长距离费用将收取给呼叫方。
        - **自动助理 (免费)** 使用免费电话 (美国和加拿大) 或免费电话 () 电话号码。 长距离费用由公司收取。 在选择此选项之前，需要购买通信信用额度。 有关详细信息，请参阅需要购买哪些商品才能获得适用于中小型企业的语音 [功能？](whats-business-voice.md)。

    3. 在" **数量"** 下， **选择"1"**。
        > [!NOTE]
        > 如果 **收到消息"** 没有足够的许可证来请求更多此类号码，请确保已使用呼叫计划Teams 电话许可证购买。 有关详细信息，请参阅需要购买哪些商品才能获得适用于中小型企业的语音 [功能？](whats-business-voice.md)。
    4. 选择 **"位置**"或"区号"，具体取决于是想要使用位置的城市搜索电话号码，还是想要搜索特定区号中的号码。
    5. 如果选择"位置 **"**：

        1. 在"设置紧急位置"步骤中键入紧急地址所在的城市 [](set-up-emergency-locations.md)，或者如果需要为另一个办公室或家庭办公室创建新位置，请单击"添加位置 **"**。
        2. 在 **"区号**"下，选择区号，然后选择"下 **一步"** 以保留号码。

    6. 如果选择"**区号"**，请键入要搜索的区号，然后选择"下一步"以保留号码。

5. 选择您需要的号码。 你有 10 分钟的时间来选择电话号码并下订单。 如果时间超过 10 分钟，电话号码将返回到号码池。
6. 准备好下订单后，单击"下 **单**"，然后单击"完成 **"**

## <a name="set-up-phone-numbers-for-your-users"></a>为用户设置电话号码

1. 打开Microsoft Teams管理中心，使用全局管理员用户登录。这通常是用于注册帐户的帐户Microsoft 365。
2. 在左侧导航栏中，转到"<a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**语音** > **电话号码**</a>"，然后单击"添加 **"**。
3. 输入订单的名称并添加说明。
4. 在"位置和数量"页上，执行以下操作：

    1. 在 **"国家/地区"** 下，选择一个或多个国家/地区。
    2. 在 **"号码类型"** 下，选择" **(订阅)**"。
    3. 在 **"** 数量"下，输入组织需要的数字数。
    4. 选择 **"位置**"或"区号"，具体取决于是想要使用位置的城市搜索电话号码，还是想要搜索特定区号中的号码。
    5. 如果选择"位置 **"**：

        1. 在"设置紧急位置"步骤中键入紧急地址所在的城市 [](set-up-emergency-locations.md)，或者如果需要为另一个办公室或家庭办公室创建新位置，请单击"添加位置 **"**。
        2. 在 **"区号**"下，选择区号，然后选择"下 **一步"** 以保留号码。

    6. 如果选择"**区号"**，请键入要搜索的区号，然后选择"下一步"以保留号码。
5. 选择您需要的数字。 你有 10 分钟的时间来选择电话号码并下订单。 如果时间超过 10 分钟，电话号码将返回到号码池。
6. 准备好下订单后，单击"下单 **"，然后单击**"完成 **"**。

> [!div class="nextstepaction"]
> [下一步：向用户Teams许可证](set-up-licenses.md)
