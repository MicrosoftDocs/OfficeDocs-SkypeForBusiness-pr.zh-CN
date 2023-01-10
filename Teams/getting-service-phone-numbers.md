---
title: 获取通话套餐的服务电话号码
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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 了解如何获取新的电话号码和转网或转移音频会议、自动助理和呼叫队列的现有号码， (Teams 服务号码) 。
ms.openlocfilehash: f72e24db204a53680a3f82469a7a77ca81943d8f
ms.sourcegitcommit: 1398c778e46b0d81c9710cd70d3818a2b7af995a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2023
ms.locfileid: "69749048"
---
# <a name="service-phone-numbers-for-calling-plans"></a>通话套餐的服务电话号码

除了 [为用户获取电话号码](./getting-phone-numbers-for-your-users.md)外，还可以获取收费或免费电话号码，例如音频会议 (用于会议网桥) 、自动助理和呼叫队列 (也称为服务号码) 。 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 例如，一个服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。
  
> [!NOTE]
> 必须先设置通信点数，然后才能获取免费号码。 若要了解详细信息，请参阅 [为组织设置通信额度](./set-up-communications-credits-for-your-organization.md)。
  
有三种方法可以获取服务编号：
  
- **使用 Microsoft Teams 管理中心。** 对于某些国家和地区，可以使用 Microsoft Teams 管理中心获取服务编号。 请参阅 [获取新的服务编号](#get-new-service-numbers)。

- **转网现有的号码。** 可以从当前服务提供商或电话运营商转网或转移现有号码。 有关详细信息，请参阅 [将电话号码转移到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [管理组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。  
  
- **使用新号码的请求表单。** 有时无法使用 Microsoft Teams 管理中心获取新电话号码，或者需要特定的电话号码或区号。 如果是这样，你需要下载表单并将其寄回给我们。 有关详细信息，请参阅[为你的组织管理电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。
  
> [!NOTE]
> 需要服务号码，以便为特定号码获取更高的并发呼叫容量。 将号码转接给我们时，可以 [联系 TNS 服务台](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) ，以确保要转移的服务号码具有较高的并发呼叫容量。
  
## <a name="get-new-service-numbers"></a>获取新服务号码

若要获取新的服务编号，请在 Teams 管理中心中：

1. 在左侧导航中，转到 **“语音** > **电话号码**”，然后选择“ **添加**”。

2. 输入订单的名称并添加说明。

3. 在 **“位置和数量** ”页上，完成以下步骤：
    - 在“ **国家或地区**”下，选择国家或地区。
    - 在 **“编号类型**”下，选择所需的服务号码类型。
    - 在“ **位置**”下，选择一个位置。 如果需要创建新位置，请选择“ **添加位置**”。
    - 在“ **区号**”下，选择一个区号。 
    - 在 **“数量**”下，输入组织所需的号码，然后选择“ **下一步** ”以选择号码。

4. 选择所需的数字。 你有 10 分钟的时间选择电话号码并下订单。 如果花费的时间超过 10 分钟，电话号码将返回到号码池。

5. 准备好下订单后，选择“ **下订单**”。

## <a name="port-or-transfer-existing-service-numbers"></a>转网或转移现有服务号码

若要将电话号码从当前服务提供商或运营商转移到 Teams，可以使用 Microsoft Teams 管理中心中的移植向导。 按照将 [电话号码转移到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 中的步骤操作。

如果移植向导出现问题，可以 [手动提交转网订单](phone-number-calling-plans/manually-submit-port-order.md) 或转到 [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，选择国家或地区，然后下载授权书 (LOA) 。 对于每种类型的服务号码，必须提交单独的转网订单， (例如，收费与免费) 将使用 LOA 转移。 在 LOA 中，必须选择正确的服务编号类型。 请确保指定 (传输服务号码，而不是) 的用户或订阅者号码，否则并发呼叫容量可能不足以处理呼叫量。  

> [!NOTE]
> 可以在 Microsoft Teams 管理中心购买额外的电话号码。 对于特殊情况，例如大量端口 (1000 多个) 、复杂端口，或者如果需要帮助， [请联系 TNS 服务台](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)。

## <a name="view-the-phone-numbers-for-your-organization"></a>查看组织的电话号码

在 Teams 管理中心的左侧导航中，转到 **“语音** > **电话号码** ”，查看组织的号码，包括位置、号码类型和状态信息。

## <a name="assign-service-phone-numbers"></a>分配服务电话号码

获取服务号码后，将每个号码分配给音频会议网桥。 请参阅 [更改音频会议网桥上的收费或免费号码](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

## <a name="related-articles"></a>相关文章

[电话系统的功能](./here-s-what-you-get-with-phone-system.md)

[转接电话号码常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[音频会议和通话套餐的国家/地区可用性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
