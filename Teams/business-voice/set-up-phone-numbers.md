---
title: 设置Microsoft 365 商务语音电话号码
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 了解如何为Microsoft 365 商务语音和服务设置电话号码。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129997"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a>步骤 2：设置业务语音电话号码

在组织中设置用户或自动助理之前，需要获取其电话号码。 有几种不同类型的电话号码，但以下是需要在此步骤中添加的两种类型的号码：

- **服务编号** 这些号码用于自动助理、音频会议和呼叫队列。 它们可以是收费或免费号码，可以同时处理大量呼叫。 公司电话号码需要是服务号码，因为稍后的步骤会将其分配给自动助理。
- **订阅者号码** 这些号码用于普通用户，以便他们可以拨打和接听电话。

> [!IMPORTANT]
> 即使想使用现有电话号码，也需要创建临时电话号码并将其分配给公司的主电话线和用户。 在稍后的步骤中，你可以将这些临时号码替换为现有电话号码。

> [!NOTE]
> 新电话号码可能需要几个小时才能在 Teams。

## <a name="set-up-a-service-number"></a>设置服务号码

现在设置的服务号码将用于公司主电话号码的后一步。

1. 转到"Microsoft Teams管理中心"。
2. 在左侧导航栏中，转到"语音  >  **电话"，** 然后单击"添加 **"。**
3. 输入订单的名称并添加说明。
4. 在"位置和数量"页上，执行以下操作：
    1. 在 **"国家/地区"下**，选择一个或多个国家/地区。
    2. 在 **"数字类型**"下，选择以下选项之一：

        - **自动助理 (收费)** 常规非免费电话号码。 长距离费用将收取给呼叫方。
        - **自动助理 (免费)** 使用免费电话号码 (美国和加拿大) 免费电话 () 电话号码。 长距离费用由公司收取。 在选择此选项之前，需要购买通信信用额度。 有关详细信息，请参阅我需要购买哪些产品以[使用Microsoft 365 商务语音？。](what-to-buy.md)

    3. 在 **"数量"** 下，选择 **"1"。**
        > [!NOTE]
        > 如果 **收到消息"** 没有足够的许可证来请求更多此类号码"，请确保已购买商业语音许可证。 有关详细信息，请参阅我需要购买哪些产品以[使用Microsoft 365 商务语音？。](what-to-buy.md)
    4. 在 **"** 位置"下，键入在"设置紧急位置"步骤中创建 [的位置](set-up-emergency-locations.md) 的名称。
    5. 在 **"区号"** 下，选择区号，然后单击"下一步"以选择你的号码
5. 选择您需要的号码。 你有 10 分钟的时间来选择电话号码并下订单。 如果时间超过 10 分钟，电话号码将返回到号码池。
6. 准备好下单后，单击"下 **单"，** 然后单击"完成 **"**

## <a name="set-up-phone-numbers-for-your-users"></a>为用户设置电话号码

1. 转到"Microsoft Teams管理中心"。
2. 在左侧导航栏中，转到"语音  >  **电话"，** 然后单击"添加 **"。**
3. 输入订单的名称并添加说明。
4. 在"位置和数量"页上，执行以下操作：

    1. 在 **"国家/地区"下**，选择一个或多个国家/地区。
    2. 在 **"数字类型"** 下，选择" (**订阅) "**。
    3. 在 **"** 数量"下，输入希望组织使用的数字数。
    4. 在 **"位置"** 下，选择一个位置。 可以选择在"设置紧急位置"步骤中添加的紧急 [](set-up-emergency-locations.md)位置，或者如果需要为另一个办公室或家庭办公室创建新位置，请单击"**添加位置"。**
    5. 在 **"区号**"下，选择区号，然后单击 **"下一** 步"以选择你的号码。
5. 选择您需要的数字。 你有 10 分钟的时间来选择电话号码并下订单。 如果时间超过 10 分钟，电话号码将返回到号码池。
6. 准备好下订单后，单击"下 **单**"，然后单击"完成 **"。**

> [!div class="nextstepaction"]
> [下一步：向用户Teams许可证](set-up-licenses.md)
