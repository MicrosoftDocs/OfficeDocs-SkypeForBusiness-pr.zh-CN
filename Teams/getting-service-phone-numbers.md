---
title: 获取呼叫套餐的服务电话号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 了解如何为音频会议、自动助理和呼叫队列获取新电话号码和转 (号码) 转接Teams。
ms.openlocfilehash: 34ff296ce94afa4888e8fd4b0ad23c00d0402468
ms.sourcegitcommit: bf350ea47032bd926e75a5433eadce3905e731ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60733303"
---
# <a name="service-phone-numbers-for-calling-plans"></a>呼叫计划的服务电话号码

除了为用户[](./getting-phone-numbers-for-your-users.md)获取电话号码外，还可以获取音频会议 (（用于会议网桥) 、自动助理和呼叫队列 (也称为服务号码) ）的收费或免费电话号码。 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 例如，服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。
  
> [!NOTE]
> 首先必须设置通信信用额度，才能获取免费电话号码。 有关详细信息，请参阅 [为组织设置通信信用额度](./set-up-communications-credits-for-your-organization.md)。
  
有三种方法可获取服务编号：
  
- **使用 Microsoft Teams 管理中心。** 对于一些国家和地区，可以使用管理中心获取Microsoft Teams号码。 请参阅 [获取新服务编号](#get-new-service-numbers)。

- **转网现有的号码。** 可以从当前服务提供商或电话运营商转转现有号码。 如需获取有助于执行此操作的详细信息，请参阅[将电话号码转接到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。  
  
- **使用新号码的请求表单。** 有时 (你的国家/地区或地区) 你将无法使用 Microsoft Teams 管理中心获取新电话号码，或者你需要特定的电话号码或区号。 如果是这样，则需要下载一个表单并将其发回给我们。 有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。
  
> [!NOTE]
> 需要服务号码，以便可以获取特定号码的更高的并发调用容量。 将号码转移给我们时，可以联系 [TNS](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) 服务台，确保要转移的服务号码具有较高的并发呼叫容量。
  
## <a name="get-new-service-numbers"></a>获取新服务号码

若要获取新的服务号码，Teams管理中心：

1. 在左侧导航栏中，**转到"语音**  >  **电话"，** 然后单击"添加 **"。**

2. 输入订单的名称并添加说明。

3. 在"位置和数量"页上，执行以下操作：
    - 在 **"国家/地区"下**，选择一个或多个国家/地区。
    - 在 **"数字类型**"下，选择需要的服务编号类型。
    - 在 **"位置"** 下，选择一个位置。 如果需要创建新位置，请单击"**添加位置"。**
    - 在 **"区号"** 下，选择区号。 
    - 在 **"** 数量"下，输入贵组织需要的数字数，然后单击"下一步"以选择号码。

4. 选择您需要的数字。 你有 10 分钟的时间来选择电话号码并下订单。 如果时间超过 10 分钟，电话号码将返回到号码池。

5. 准备好下订单后，单击"下 **单"。**

## <a name="port-or-transfer-existing-service-numbers"></a>转网或转移现有服务号码

若要将电话号码从当前服务提供商或运营商Teams，可以在管理中心使用Microsoft Teams向导。 按照将电话号码[转移到 Teams。](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

如果移植向导中未列出你的国家/地区，可以手动提交转寄订单[](phone-number-calling-plans/manually-submit-port-order.md)或转到"管理组织的电话号码"，选择[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)你的国家/地区，然后下载授权书 (LOA) 。 必须针对每种类型的服务号码提交单独的转站订单 (例如，使用 LOA 转移的收费和免费) 。 在 LOA 中，必须选择正确的服务编号类型。 请确保指定要转移服务号码 (而不是用户或订阅者号码) ，否则并发呼叫容量可能不足以处理呼叫量。  

> [!NOTE]
> 如果需要获取的电话号码超过此数目， [请联系 TNS 服务台](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)。

## <a name="view-the-phone-numbers-for-your-organization"></a>查看组织的电话号码

在Teams管理中心的左侧导航中，转到"语音电话号码"以查看组织号码，包括位置、号码类型和  >  状态信息。

## <a name="assign-service-phone-numbers"></a>分配服务电话号码

获取服务号码后，将每个号码分配给音频会议网桥。 请参阅 [更改音频会议网桥](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md)上的收费或免费号码。

## <a name="related-topics"></a>相关主题

[电话系统的功能](./here-s-what-you-get-with-phone-system.md)

[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[音频会议和通话套餐的国家/地区可用性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
