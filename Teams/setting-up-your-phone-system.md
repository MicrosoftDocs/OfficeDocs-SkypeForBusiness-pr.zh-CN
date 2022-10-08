---
title: 在组织中设置电话系统
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: 分步指南，详细介绍如何在 Microsoft 365 中为组织设置 Teams 电话系统。
ms.openlocfilehash: beb82fd78fa58a4a3339dc1b7a5f54ceb5117479
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999537"
---
# <a name="set-up-phone-system-in-your-organization"></a>在组织中设置电话系统

本文提供了有关设置电话系统的内容的路线图 --Microsoft 在 Microsoft 365 云中启用呼叫控制和专用分支交换 (PBX) 功能的技术。 每个步骤末尾都有指向更详细信息的链接。

在阅读本文之前，请确保已阅读了 [“什么是电话系统](what-is-phone-system-in-office-365.md) ”和“ [电话系统](here-s-what-you-get-with-phone-system.md)”功能。 后两篇文章介绍了电话系统的要求和功能。

本文介绍以下步骤：

- [步骤 1：购买和分配电话系统许可证](#step-1-buy-and-assign-a-phone-system-license)
- [步骤 2：选择 PSTN 连接选项](#step-2-choose-a-pstn-connectivity-option)
- [步骤 3：获取用户的电话号码](#step-3-get-phone-numbers-for-your-users)
- [步骤 4：获取服务的电话号码](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [步骤 5：如果要设置呼叫队列](#step-5-if-you-want-to-set-up-a-call-queue)
- [步骤 6：如果要设置自动助理](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [步骤 7：为免费号码设置通信额度](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>步骤 1：购买和分配电话系统许可证

若要将电话系统许可证分配给单个用户，步骤与分配 Microsoft 365 许可证相同。 还可以批量向多个用户分配许可证。 有关可用电话系统许可证以及如何获取和分配许可证的详细信息，请参阅 [Teams 加载项许可证](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) 和 [分配 Microsoft Teams 加载项许可证](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)。

## <a name="step-2-choose-a-pstn-connectivity-option"></a>第 2 步 选择 PSTN 连接选项

若要使用户能够拨打和接收外部呼叫，需要将电话系统连接到公共交换电话网络 (PSTN) 。 Microsoft 提供了多个用于连接到 PSTN 的选项，包括：

- 调用计划。 以 Microsoft 为 PSTN 运营商的全云解决方案。

- 运算符连接。 如果现有运营商参与 Microsoft Operator Connect 计划，他们可以管理 PSTN 调用和会话边界控制器 (SBC) 。

- 直接路由。 通过将 SBC 连接到电话系统来使用自己的 PSTN 运营商。

有关所有连接选项的详细信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步骤 3：获取用户的电话号码

在组织中设置用户以拨打和接听电话之前，必须为他们获取电话号码。

有关如何为用户管理电话号码的信息，请参阅以下文章。 如何管理用户的数字取决于所选的 PSTN 连接选项。

- [管理组织的电话号码](manage-phone-numbers-landing-page.md) – 提供电话号码类型的概述，其中包含特定文章的链接，用于获取和管理号码，具体取决于 PSTN 连接选项。
介绍两种类型的 [用户电话号码](manage-phone-numbers-landing-page.md#user-telephone-numbers)。

- [为用户分配、更改或删除电话号码](assign-change-or-remove-a-phone-number-for-a-user.md) – 介绍如何分配和管理已获取的电话号码。

- [可以获取多少个电话号码](how-many-phone-numbers-can-you-get.md) – 描述可以获取多少个电话号码，具体取决于你购买和分配的电话号码类型和许可证类型。

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>步骤 4：获取服务的电话号码 (呼叫队列、自动助理) 

除了为用户获取电话号码外，还可以获取自动助理和呼叫队列等服务的收费或免费电话号码。 服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。

可以从 Microsoft 获取许可中包含的服务号码。 如果通过运算符连接或直接路由建立 PSTN 连接，则可以使用自己的运营商或运营商提供的服务号码。

有关详细信息，请参阅：

- [管理组织的电话号码](manage-phone-numbers-landing-page.md) – 提供电话号码类型的概述，其中包含特定文章的链接，用于获取和管理号码，具体取决于 PSTN 连接选项。
介绍许可中包含的 Microsoft 提供的 [服务电话号码](manage-phone-numbers-landing-page.md#service-telephone-numbers) 。 有关操作员连接或直接路由提供的服务号码的信息，请联系提供商。

- [可以获取多少个电话号码](how-many-phone-numbers-can-you-get.md) – 描述可以获取多少个电话号码，具体取决于你购买和分配的电话号码类型和许可证类型。

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>步骤 5：如果要设置呼叫队列

呼叫队列包括当有人为你的组织拨打电话号码时使用的问候语、自动将呼叫暂缓的功能，以及搜索下一个可用呼叫代理以处理呼叫的能力。 可以为组织创建单个或多个呼叫队列。

有关呼叫队列的详细信息，请参阅 [“创建呼叫队列](create-a-phone-system-call-queue.md)”。

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>步骤 6：如果要设置自动助理

自动助理允许呼叫你的组织的人导航菜单系统，让他们到达正确的部门、呼叫队列、人员或操作员。

有关设置自动助理的信息，请参阅 [设置自动助理](create-a-phone-system-auto-attendant.md)。

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>步骤 7：为免费号码设置通信额度

如果要在 Microsoft Teams 中使用免费号码，则需要设置通信额度。 免费呼叫每分钟计费，需要一个正通信额度余额。

通信额度是添加免费号码的便捷方式，如下所示：

- 使用语音应用的服务号码，例如自动助理或呼叫队列。

- 如果拥有国内通话套餐订阅或国内和国际通话套餐订阅中包含的号码，请拨打任何国际电话号码。

- 用尽每月的分钟分配后，按分钟拨号并支付费用。

- 如果有即用即付呼叫计划，则为所有传出呼叫拨打电话并按分钟付费。

有关详细信息，请参阅 [什么是通信信用额度？](what-are-communications-credits.md) 并为 [组织设置通信额度](set-up-communications-credits-for-your-organization.md)。

## <a name="related-articles"></a>相关文章

- [什么是电话系统？](what-is-phone-system-in-office-365.md)

- [电话系统的功能](here-s-what-you-get-with-phone-system.md)

- [管理组织的电话号码](manage-phone-numbers-landing-page.md)
