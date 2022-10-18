---
title: 将电话号码传输到 Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
- highpri
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何使用移植向导将电话号码从当前服务提供商传输到 Microsoft Teams。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4dd814f81bb7c48c331ebaa1178f8f3069f7b156
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584163"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>将电话号码传输到 Microsoft Teams

使用 Microsoft Teams 管理中心中的移植向导将电话号码从当前服务提供商传输到 Teams。 将电话号码移植到 Teams 后，Microsoft 将成为你的服务提供商，并将向你收取这些电话号码的费用。

在开始之前，我们建议你查看[什么是端口订单](port-order-overview.md)中的信息？ 如果你有电话拨入式会议网桥的服务号码、自动助理或其他服务号码、免费电话号码，或者有超过 999 个用户 (订阅者) 需要传输到 Teams 的电话号码，请参阅 [“管理电话号码”，供组织](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 下载正确的表单并将其发送给我们。

  > [!NOTE]
  > 我们处理仅在美国个工作日而不是公共假日或周末传输电话号码的端口订单。
  > 免费电话号码的移植可用性可能因国家/地区而异。 若要查找我们的详细信息，请参阅您的国家或地区特定文档，以查看对移植服务的可用支持。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>创建端口订单并将电话号码传输到 Teams

> [!NOTE]
> **目前，可以使用此向导获取英国、美国和加拿大的电话号码**。 若要获取其他国家和地区的电话号码，可以 [手动提交端口订单](manually-submit-port-order.md)。 若要获取手动提交端口订单所需的表单，请在 [组织管理电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)的下拉列表中选择你的国家或地区。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音** > **电话号码**。 单击 **“数字**”，然后单击 **“端口** ”以启动移植向导。
2. 查看 **“入门** ”页上的信息，然后在准备就绪后，单击 **“下一步**”。
3. 在 **“选择位置和数字类型** ”页上，指定以下内容，然后单击 **“下一步**”

    - **国家或地区**：获取数字的国家或地区。
    - **电话号码类型**：号码类型，例如地理号码或免费电话号码。
    - **分配给的数字**：分配给的数字。 例如，用户、会议或语音功能。

4. 在 **“添加帐户信息** ”页上，完成以下操作，然后单击 **“下一步**”。

    > [!IMPORTANT]
    > 此页上显示的信息由国家/地区和数字类型决定。 每个国家和地区对端口号所需的信息有不同的规定。 此页上显示的内容可能与此处所述的内容不同。

    - **订单详细信息**： 
        - **订单名称**：订单名称
        - **通知电子邮件**：Email地址以接收订单通知。 如果输入多个电子邮件地址，请使用分号分隔每个地址。
        - **转移日期**：由当前服务提供商颁发的传输日期。
    - **电话号码详细信息**
        - **端口类型**：是执行全端口传输所有号码，还是使用部分端口传输部分号码。
    - **请求详细信息的人员**  
        - 请求转移的人员的组织名称和联系人详细信息。
    - **当前提供商的详细信息**
        - **(BTN) 计费电话号码**：E.164 格式的 BTN，需要加号才能将号码放在前面。 例如，对于北美数字，请使用 +1XXXYYYZZZZ 格式。
        - 其他详细信息，包括当前服务提供商的名称、帐户号和服务地址。
            
5. 在 **“添加号码** ”页上，单击 **“选择文件**”，浏览到并选择包含要传输的电话号码的 CSV 文件，然后单击 **“下一步**”。  

    > [!NOTE]
    > CSV 文件必须只有一列标题名为 PhoneNumber。 每个电话号码必须位于单独的行上，并且只能是数字或 E.164 格式。

6. 在 **“完成订单** ”页上，单击 **“上传签名授权书** ”，上传已签名授权书 (LOA) 的扫描副本。

    如果尚未下载并签名 LOA，请执行以下操作：
    
    1. 单击 **“下载模板** ”，下载所在国家或地区的 LOA。 
    2. 打印 LOA。
    3. 由有权对帐户进行更改的人员签名 LOA。
    4. 扫描已签名的 LOA，然后单击 **“上传签名授权书** ”上传。

    > [!NOTE]
    > 上传 LOA 后，提交订单。 仅上传 LOA 是不够的。 还必须提交要处理的订单。

7. 查看订单详细信息，然后单击“ **提交**”。


## <a name="what-happens-next"></a>下一步会发生什么？

当我们收到你的端口订单时，你将收到一封电子邮件来验证你的请求。 你的请求每天都会被检查和更新，你将在电子邮件中收到其进度和状态的通知。 如果端口请求被丢失的运营商拒绝，请联系 [TNS 服务台](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)。

若要查看端口订单的状态，请在 Microsoft Teams 管理中心的左侧导航中转到“ **语音** > **端口订单**>”，然后单击 **“订单历史记录**”。 状态 **列中** 列出了每个端口订单状态。 若要了解详细信息，请参阅 [端口订单的状态如何？](port-order-status.md)


## <a name="reporting-telephone-number-issues"></a>报告电话号码问题？
如果在端口完成后的前 24-48 小时内发现移植号码存在任何问题， [请联系 TNS 服务台](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)。 对于超过 48 小时的任何问题，请联系Microsoft 支持部门团队。

## <a name="related-topics"></a>相关主题

- [什么是转网订单？](port-order-overview.md)
- [用于通话套餐的不同类型的电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
