---
title: 为用户获取电话号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
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
- Calling Plans
description: 了解如何获取 Teams 的新号码、端口号码或传输现有号码，以及如何向用户显示更改。
ms.openlocfilehash: 18dd5a84110dc25721d9f8c027dffe861d29cbd1
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682541"
---
# <a name="getting-phone-numbers-for-your-users"></a>为用户获取电话号码

在组织中设置用户以拨打和接听电话之前，必须为他们获取电话号码。
  
可通过三种方式获取用户编号：

- **使用 Microsoft Teams 管理中心。** 对于某些国家和地区，可以使用 Microsoft Teams 管理中心为用户获取号码。 请参阅 [获取用户的新电话号码](#get-new-phone-numbers-for-your-users)。

- **转网现有的号码。** 可以从当前服务提供商或电话运营商移植或传输现有号码。 如需获取有助于执行此操作的详细信息，请参阅[将电话号码转接到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。  
  
- **使用新号码的请求表单。** 有时 (取决于你的国家或地区) 你将无法使用 Microsoft Teams 管理员中心获取新电话号码，或者需要特定的电话号码或区号。 有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。
  
> [!NOTE]
> 如果需要帮助为组织设置电话号码，请[联系企业产品支持联系人 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)。
## <a name="get-new-phone-numbers-for-your-users"></a>为用户获取新电话号码

 **使用 Microsoft Teams 管理中心**

必须是 Teams 服务管理员才能管理这些策略。 请参阅 [Teams 管理员角色管理 Teams](./using-admin-roles.md) ，了解管理员角色和权限。

1. 转到 Microsoft Teams 管理员中心。

2. 在左侧导航栏中，转到 **“语音** > **电话号码**”，然后单击 **“添加**”。

3. 输入订单的名称并添加说明。

4. 在“位置和数量”页上，执行以下操作：
    1. 在 **“国家或地区**”下，选择一个国家或地区。
    2. 在 **“数字”类型** 下，选择 **“用户 (订阅服务器)**”。
    3. 在 **“位置”** 下，选择一个位置。 如果需要创建新位置，请单击 **“添加位置**”。
    4. 在 **“区域代码**”下，选择一个区域代码。
    5. 在 **“数量**”下，输入组织所需的数字数，然后单击 **“下一步** ”选择数字。

5. 选择所需的数字。 有 10 分钟的时间选择电话号码并下订单。 如果花费超过 10 分钟，电话号码将返回到号码池。

6. 准备好下订单后，单击 **“放置”订单**。

    > [!IMPORTANT]
    > 用户 (订户) 的电话号码数等于你分配的 **国内通话套餐****和国际通话套餐** 许可证总数乘以 1.1，外加 10 个额外的电话号码。 例如，如果你有 50 个用户与国内通话计划和/或国际通话计划，你可以获取 **65** 个电话号码 **(50 x 1.1 + 10)**。 有关详细信息，请参阅[可以获取多少电话号码？](./how-many-phone-numbers-can-you-get.md) 如果需要获得比这更多的电话号码，请[联系企业产品支持联系人 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)。
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移
  
- 如果用户需要 999 个或更少的电话号码，请在 Microsoft Teams 管理员中心使用移植向导。 按照将 [电话号码传输到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 中的步骤进行操作。 如果你的国家或地区未在移植向导中列出，则可以 [手动提交端口订单](phone-number-calling-plans/manually-submit-port-order.md) 或查看 [组织管理电话号码](/microsoftteams/manage-phone-numbers-for-your-organization) ，以便下载正确的授权书 (LOA) 。

- 如果需要移植超过 999 个电话号码，可以 [手动提交端口订单](phone-number-calling-plans/manually-submit-port-order.md) 或查看 [组织管理电话号码](/microsoftteams/manage-phone-numbers-for-your-organization) ，以便下载正确的授权书 (LOA) ，然后将其发送到 [TNS 服务台](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) 以传输所有号码。

## <a name="view-the-phone-numbers-for-your-organization"></a>查看组织的电话号码

 **使用 Microsoft Teams 管理中心**

在管理中心的左侧导航中，转到 **语音** > **电话号码** 以查看组织的号码，包括位置、号码类型和状态信息。
  
## <a name="assign-phone-numbers-to-users"></a>向用户分配电话号码

获取电话号码后，需要为每个用户分配一个号码。 有关详细信息，请参阅 [分配、更改或删除用户的电话号码](./assign-change-or-remove-a-phone-number-for-a-user.md) 。

> [!NOTE]
> 如果需要获得比这更多的电话号码，请[联系企业产品支持联系人 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)。

## <a name="related-topics"></a>相关主题

[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
