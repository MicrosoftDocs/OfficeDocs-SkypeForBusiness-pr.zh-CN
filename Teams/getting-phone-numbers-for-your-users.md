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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 了解如何获取 Teams 的新号码、移植或转移现有号码，以及如何向用户显示更改。
ms.openlocfilehash: d92d48f95e620767148d3917a78d1e72c87f0645
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835485"
---
# <a name="getting-phone-numbers-for-your-users"></a>为用户获取电话号码

必须先获取用户的电话号码，然后才能将组织中的用户设置为拨打和接听电话。
  
有三种方法可以获取用户号码：

- **使用 Microsoft Teams 管理中心。** 对于某些国家和地区，可以使用 Microsoft Teams 管理中心为用户获取号码。 请参阅 [获取用户的新电话号码](#get-new-phone-numbers-for-your-users)。

- **转网现有的号码。** 可以从当前服务提供商或电话运营商转网或转移现有号码。 有关详细信息，请参阅 [将电话号码转移到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [管理组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。  
  
- **使用新号码的请求表单。** 有时 (取决于你的国家或地区) 你无法使用 Microsoft Teams 管理中心获取新的电话号码，或者需要特定的电话号码或区号。 有关详细信息，请参阅[为你的组织管理电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。
  
> [!NOTE]
> 如果需要有关为组织设置电话号码的帮助，[请联系商业产品支持联系人 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)。

## <a name="get-new-phone-numbers-for-your-users"></a>为用户获取新电话号码

**使用 Microsoft Teams 管理中心**

必须是 Teams 服务管理员才能管理这些策略。 请参阅 [Teams 管理员角色管理 Teams](./using-admin-roles.md) ，了解管理员角色和权限。

1. 登录到 [Microsoft Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)。

2. 在左侧导航中，转到 **“语音** > **电话号码**”，然后选择“ **添加**”。

3. 输入订单的名称并添加说明。

4. 在“位置和数量”页上，执行以下操作：
    1. 在“ **国家或地区**”下，选择国家或地区。
    2. 在 **“编号类型**”下，选择“ **用户 (订阅者)**”。
    3. 在“ **位置**”下，选择一个位置。 如果需要创建新位置，请选择“ **添加位置**”。
    4. 在“ **区号**”下，选择一个区号。
    5. 在 **“数量**”下，输入组织所需的号码数，然后选择“ **下一步** ”以选择号码。

5. 选择所需的数字。 你有 10 分钟的时间选择电话号码并下订单。 如果花费的时间超过 10 分钟，电话号码将返回到号码池。

6. 准备好下订单后，选择“ **下订单**”。

    > [!IMPORTANT]
    > ) 用户 (订阅者的电话号码数等于你分配的 **国内通话套餐****和国际通话套餐** 许可证总数乘以 1.1，加上 10 个附加电话号码。 例如，如果总共有 50 个用户使用国内通话套餐和/或国际通话套餐，则可以 **(50 x 1.1 + 10)** 获取 **65** 个电话号码。 请注意，如果你有即用即付通话套餐，则每个分配的许可证只能获取 1 个电话号码。
    >
    > 有关详细信息，请参阅 [可以获取多少个电话号码？](./how-many-phone-numbers-can-you-get.md)。 如果需要获取超过此号码的电话号码，[请联系商业产品支持联系人 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)。
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移
  
- 如果需要为用户提供 999 或更少的电话号码，请使用 Microsoft Teams 管理中心中的移植向导。 按照将 [电话号码转移到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 中的步骤操作。 如果需要此过程的帮助，可以 [手动提交转网订单](phone-number-calling-plans/manually-submit-port-order.md) 或参阅 [管理组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization) ，以下载正确的授权书 (LOA) 。

- 如果需要移植超过 999 个电话号码，可以 [手动提交转网订单](phone-number-calling-plans/manually-submit-port-order.md) 或参阅 [管理组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization) ，以下载正确的授权书 (LOA) 。 填写并签署 LOA 文档，然后联系你区域的 [TNS 服务台](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) 。

> [!NOTE]
> 有关用于移植/转移现有电话号码的 LOA 和其他文档要求的详细信息，请参阅 [管理通话套餐的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。
>
>若要为用户移植/转移 999 或更少的电话号码，请将已完成且已签名的 LOA 上传到 Microsoft Teams 管理中心以供进一步处理。 
>
> 若要移植/转移超过 999 个电话号码，或者如果在 Microsoft Teams 管理中心的移植过程中遇到问题，可以 [手动将转网订单提交](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) 到你区域的 TNS 服务台。

## <a name="view-the-phone-numbers-for-your-organization"></a>查看组织的电话号码

**使用 Microsoft Teams 管理中心**

在管理中心的左侧导航中，转到 **“语音** > **电话号码** ”以查看组织的号码，包括位置、号码类型和状态信息。
  
## <a name="assign-phone-numbers-to-users"></a>向用户分配电话号码

获取电话号码后，需要为每个用户分配一个号码。 有关详细信息，请参阅 [为用户分配、更改或删除电话号码](./assign-change-or-remove-a-phone-number-for-a-user.md)。

此视频演示了向用户分配电话号码的步骤。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE54mbS?autoplay=false]

## <a name="related-articles"></a>相关文章

[转接电话号码常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
