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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: '了解如何为团队获取新的、移植或转移现有号码，以及如何向用户显示所做的更改。 '
ms.openlocfilehash: f2028a4d7b49560ff426d83241da8f1f7c3243d3
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030458"
---
# <a name="getting-phone-numbers-for-your-users"></a>为用户获取电话号码

在您可以将组织中的用户设置为拨打和接收电话呼叫之前，您必须为他们获取电话号码。
  
有三种方法可以获取用户号码：

- **使用 Microsoft 团队管理中心。** 对于某些国家和地区，你可以使用 Microsoft 团队管理中心为你的用户获取数字。 请参阅 [为您的用户获取新电话号码](#get-new-phone-numbers-for-your-users)。

- **转网现有的号码。** 您可以从当前服务提供商或电话运营商处移植或转移现有号码。 如需获取有助于执行此操作的详细信息，请参阅[将电话号码转接到 Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。  
  
- **使用新号码的请求表单。** 有时 (取决于您所在的国家或地区) 你无法使用 Microsoft 团队管理中心获取新电话号码，或者你将需要特定的电话号码或区号。 有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。
  
> [!NOTE]
> 如果您需要帮助为您的组织设置电话号码，请 [联系支持人员联系以获取商业产品-管理员帮助 (https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online 。
  
## <a name="get-new-phone-numbers-for-your-users"></a>为用户获取新电话号码

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

您必须是团队服务管理员才能进行这些更改。 请参阅 [使用团队管理员角色管理团队](https://docs.microsoft.com/microsoftteams/using-admin-roles) ，了解如何获取管理员角色和权限。

1. 转到 Microsoft 团队管理中心。
2. 在左侧导航中，转到 " **语音**  >  **电话号码** "，然后单击 " **添加** "。
3. 输入订单的名称并添加说明。
4. 在 "位置和数量" 页面上，执行下列操作：
    1. 在 " **国家或地区** " 下，选择一个国家或地区。
    2. 在 " **号码类型** " 下，选择 " **用户 (订阅者")** 。
    3. 在 " **位置** " 下，选择一个位置。 如果需要创建新位置，请单击 " **添加位置** "。
    4. 在 " **区域代码** " 下，选择区号。
    5. 在 " **数量** " 下，输入您的组织所需的号码数，然后单击 " **下一步** " 以选择您的号码。
5. 选择所需的数字。 您有10分钟的时间来选择您的电话号码并放置您的订单。 如果您的时间超过10分钟，电话号码将返回到号码池。
6. 准备好下订单后，单击 " **下订单** "。

    > [!IMPORTANT]
    > 用户 （订户） 的电话号码数等于 **国内通话套餐** 和/或 **国内和国际通话套餐** 的许可证已分配乘以 1.1、 加上 10 个其他电话号码的总数。 例如，如果您总共有 50 个国内通话套餐和/或国内和国际通话套餐的用户，您可以获取 **65** 个电话号码 **(50 x 1.1 + 10)** 。 有关详细信息，请参阅 [您可以获取多少个电话号码？](/microsoftteams/how-many-phone-numbers-can-you-get)。 如果您需要获得比这更多的电话号码，请 [联系支持人员联系以获取商业产品-管理员帮助](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)。
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移
  
- 如果你需要999或更少的用户电话号码，请使用 Microsoft 团队管理中心中的移植向导。 按照将 [电话号码转移到团队](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)中的步骤进行操作。 如果您的国家或地区未在 "移植向导" 中列出，您可以 [手动提交一个端口订单](phone-number-calling-plans/manually-submit-port-order.md) ，或参阅 [管理您的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization) 以下载正确的授权 (LOA) 。

- 如果您需要使用超过999的电话号码，您可以 [手动提交一个端口订单](phone-number-calling-plans/manually-submit-port-order.md) ，或参阅 [管理您的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization) 以下载正确的授权 (LOA) ，然后将其发送到 [PSTN 服务桌面](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) ，以获取您的所有已转移号码。

## <a name="view-the-phone-numbers-for-your-organization"></a>查看您的组织的电话号码

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

在管理中心的左侧导航中，转到 " **语音**  >  **电话号码** " 以查看您的组织的号码，包括位置、号码类型和状态信息。
  
## <a name="assign-phone-numbers-to-users"></a>向用户分配电话号码

获得您的电话号码后，您需要为每个用户分配一个号码。 有关详细信息，请参阅 [为用户分配、更改或删除电话号码](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) 。

> [!NOTE]
> 如果您需要获得比这更多的电话号码，请 [联系支持人员联系以获取商业产品-管理员帮助](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)。

## <a name="related-topics"></a>相关主题

[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
