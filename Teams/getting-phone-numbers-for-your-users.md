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
description: '了解如何获取新号码、转网或转移现有号码Teams以及如何向用户显示更改。 '
ms.openlocfilehash: 368a9d2c699fa631ff98b343d6c2f9562efc62e1
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729621"
---
# <a name="getting-phone-numbers-for-your-users"></a>为用户获取电话号码

在将组织中用户设置为拨打和接听电话之前，必须获取其电话号码。
  
有三种方法可获取用户编号：

- **使用Microsoft Teams管理中心。** 对于一些国家和地区，可以使用管理中心获取Microsoft Teams号码。 请参阅 [为用户获取新电话号码](#get-new-phone-numbers-for-your-users)。

- **转网现有的号码。** 可以从当前服务提供商或电话运营商转转现有号码。 如需获取有助于执行此操作的详细信息，请参阅[将电话号码转接到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。  
  
- **使用新号码的请求表单。** 有时 (你的国家/地区) 你将无法使用 Microsoft Teams 管理中心获取新电话号码，或者你需要特定的电话号码或区号。 有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。
  
> [!NOTE]
> 如果在为组织设置电话号码时需要帮助，请联系支持联系人，了解商业产品 [- 管理员帮助](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)。
  
## <a name="get-new-phone-numbers-for-your-users"></a>为用户获取新电话号码

![一个图标，显示Microsoft Teams徽标。](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

必须是 Teams 服务管理员才能管理这些策略。 请参阅 [Teams 管理员角色管理 Teams](./using-admin-roles.md) ，了解管理员角色和权限。

1. 转到"Microsoft Teams管理中心"。
2. 在左侧导航栏中，**转到"语音**  >  **电话"，** 然后单击"添加 **"。**
3. 输入订单的名称并添加说明。
4. 在"位置和数量"页上，执行以下操作：
    1. 在 **"国家/地区"下**，选择一个或多个国家/地区。
    2. 在 **"数字类型"** 下，选择" (**订阅) "。**
    3. 在 **"位置"** 下，选择一个位置。 如果需要创建新位置，请单击"**添加位置"。**
    4. 在 **"区号"** 下，选择区号。
    5. 在 **"** 数量"下，输入贵组织需要的数字数，然后单击"下一步"以选择号码。
5. 选择您需要的数字。 你有 10 分钟的时间来选择电话号码并下订单。 如果时间超过 10 分钟，电话号码将返回到号码池。
6. 准备好下订单后，单击"下 **单"。**

    > [!IMPORTANT]
    > 用户 （订户） 的电话号码数等于 **国内通话套餐** 和/或 **国内和国际通话套餐** 的许可证已分配乘以 1.1、 加上 10 个其他电话号码的总数。 例如，如果您总共有 50 个国内通话套餐和/或国内和国际通话套餐的用户，您可以获取 **65** 个电话号码 **(50 x 1.1 + 10)**。 有关详细信息，请参阅[可以获取多少个电话号码？。](./how-many-phone-numbers-can-you-get.md) 如果需要获取的电话号码超过此数目，请联系支持联系人，了解商业产品 [- 管理员帮助](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)。
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移
  
- 如果你的用户需要的电话号码数少于 999 个，请使用管理中心Microsoft Teams向导。 按照将电话号码[转移到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)中的步骤。 如果移植向导中未列出你的国家/地区，可以手动提交转寄订单[](phone-number-calling-plans/manually-submit-port-order.md)，或参阅管理组织的电话号码以下载[](/microsoftteams/manage-phone-numbers-for-your-organization)正确的授权书 (LOA) 。

- 如果需要转网超过 999 个电话号码，可以手动提交[](phone-number-calling-plans/manually-submit-port-order.md)转网订单或参阅管理组织的电话号码[](/microsoftteams/manage-phone-numbers-for-your-organization)以下载正确的授权书 (LOA) 并将其发送到[PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)服务台以转移所有号码。

## <a name="view-the-phone-numbers-for-your-organization"></a>查看组织的电话号码

![一个图标，显示Microsoft Teams徽标。](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

在管理中心的左侧导航中，转到"语音电话号码"以查看组织号码，包括位置、号码类型和  >  状态信息。
  
## <a name="assign-phone-numbers-to-users"></a>向用户分配电话号码

获得电话号码后，你需要为每个用户分配一个号码。 有关详细信息 [，请参阅为用户分配、更改或删除](./assign-change-or-remove-a-phone-number-for-a-user.md) 电话号码。

> [!NOTE]
> 如果需要获取的电话号码超过此数目，请联系支持联系人，了解商业产品 [- 管理员帮助](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)。

## <a name="related-topics"></a>相关主题

[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)