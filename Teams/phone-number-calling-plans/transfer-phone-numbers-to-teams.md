---
title: 将电话号码转移到 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用移植向导将电话号码从当前服务提供商转移到 Microsoft Teams。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52dd8a2a1dcbc14930695efd52141ce3b1842458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812962"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>将电话号码转移到 Microsoft Teams

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

使用 Microsoft Teams 管理中心中的移植向导将电话号码从当前服务提供商转移到 Teams。 将电话号码移植到 Teams 后，Microsoft 将成为服务提供商，并针对这些电话号码计费。

在启动之前，建议查看"什么是移植 [订单"中的信息？](port-order-overview.md) 如果你有电话拨入式会议网桥的服务号码、自动助理或其他服务号码、免费电话号码，或者你需要将超过 999 个用户 (订阅者) 电话号码转移到 Teams，请参阅"管理贵组织的电话号码"以下载正确的表单并将其发送给[](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)我们。

  > [!NOTE]
  > 我们仅在美国营业日（而不是公共假日或周末）处理转口订单以转移电话号码。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>创建转货订单，将电话号码转移到 Teams

> [!NOTE]
> **目前，可以使用此向导** 获取英国、美国和加拿大的电话号码。 若要获取其他国家/地区的电话号码，可以 [手动提交移植订单](manually-submit-port-order.md)。 若要获取需要手动提交移植订单的表单，请在"管理组织的电话号码"的下拉列表中选择 [你的国家/地区](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"语音**  >  **电话号码"。** 单击 **"** 数字"，然后单击 **"端口** "以启动移植向导。
2. 查看"**开始"页上** 的信息，然后在准备就绪后单击"下一 **步"。**
3. 在"**选择位置和编号类型**"页上，指定以下内容，并单击"下一 **步"：**

    - **国家/地区**：获取号码的一个或多个国家/地区。
    - **电话号码类型**：号码类型，例如地理号码或免费电话号码。
    - **分配给的数字**：要分配给哪些数字。 例如，用户、会议或语音功能。

4. 在"**添加帐户信息**"页上，完成以下操作，并单击"下一 **步"。**

    > [!IMPORTANT]
    > 此页面上显示的信息由国家/地区或号码类型决定。 每个国家/地区对端口号所需信息有不同的法规。 在此页上看到的内容可能不同于此处所述的内容。

    - **订单详细信息**： 
        - **订单名称**：订单名称
        - **通知电子邮件**：用于接收订单通知的电子邮件地址。 如果输入多个电子邮件地址，请用分号分隔每个电子邮件地址。
        - **转移日期**：当前服务提供商发布的转让日期。
    - **电话号码详细信息**
        - **端口类型**：无论是执行完整转网来转移所有号码，还是进行部分转网以转移部分号码。
    - **请求详细信息的人**  
        - 你的组织名称和请求转移的人的联系人详细信息。
    - **当前提供商的详细信息**
        - **付费电话号码 (BTN) ：** 采用 E.164 格式的 BTN，需要加号以在号码前加号。 例如，对于北美数字，请使用 +1XXXYYYZZZZ 格式。
        - 其他详细信息，包括当前服务提供商的名称、帐号和服务地址。
            
5. 在"**添加号码**"页上，单击"选择文件"，浏览到并选择要转移的电话号码的 CSV 文件，然后单击"下一 **步"。**  

    > [!NOTE]
    > CSV 文件必须只有一列，其标头名为 PhoneNumber。 每个电话号码必须位于单独的行中，只能是数字或 E.164 格式。

6. 在"**完成订单"** 页上，单击"上传已签名的授权书"，上传已签名授权书的扫描副本 (LOA) 。

    如果尚未下载和签名 LOA，请执行下列操作：
    
    1. 单击 **"下载模板** "，下载适用于你的国家/地区或地区的 LOA。 
    2. 打印 LOA。
    3. 由有权更改帐户的人员签署 LOA。
    4. 扫描签名的 LOA，并单击" **上传签名** 的授权书"以上传它。

    > [!NOTE]
    > 上传 LOA 后，提交订单。 仅上传 LOA 是不够的。 还必须提交订单才能进行处理。

7. 查看订单详细信息，然后单击"提交 **"。**


## <a name="what-happens-next"></a>下一步会发生什么？

当我们收到你的移植订单时，你将收到一封验证你的请求的电子邮件。 每日检查和更新你的请求，你将在电子邮件中收到其进度和状态通知。 如果你的移植请求被丢失的运营商拒绝，请联系 [PSTN 服务台](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

若要查看转台订单的状态，请在 Microsoft Teams 管理中心的左侧导航栏中，转到"语音转>订单，然后单击"订单  >  **历史记录"。** 每个端口订单状态都列在"状态 **"** 列中。 若要了解有关详细信息， [请参阅移植订单的状态是什么？](port-order-status.md)

## <a name="related-topics"></a>相关主题

- [什么是转网订单？](port-order-overview.md)
- [用于通话套餐的不同类型的电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
