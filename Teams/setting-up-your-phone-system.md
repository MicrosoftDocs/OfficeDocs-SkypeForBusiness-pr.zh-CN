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
description: 分步指南详细介绍了如何在 Microsoft 365 中为组织设置 Teams 电话系统。
ms.openlocfilehash: 974cabac0d02f30d9371114e0f6886fdbc9f9389
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343172"
---
# <a name="set-up-phone-system-in-your-organization"></a>在组织中设置电话系统

本文提供了设置电话系统的内容路线图-Microsoft的技术用于在 Microsoft 365 云中启用呼叫控制和专用分支 Exchange (PBX) 功能。 每个步骤末尾提供了指向更多详细信息的链接。

在阅读本文之前，请确保已阅读 [什么是电话系统](what-is-phone-system-in-office-365.md) 以及电话 [系统功能](here-s-what-you-get-with-phone-system.md)。 后两篇文章介绍了电话系统的要求和功能。

本文介绍以下步骤：

- [步骤 1：购买和分配电话系统许可证](#step-1-buy-and-assign-a-phone-system-license)
- [步骤 2：选择 PSTN 连接选项](#step-2-choose-a-pstn-connectivity-option)
- [步骤 3：获取用户的电话号码](#step-3-get-phone-numbers-for-your-users)
- [步骤 4：获取服务的电话号码](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [步骤 5：如果要设置呼叫队列](#step-5-if-you-want-to-set-up-a-call-queue)
- [步骤 6：如果要设置自动助理](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [步骤 7：为免费号码设置通信信用额度](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>步骤 1：购买和分配电话系统许可证

若要将电话系统许可证分配给单个用户，步骤与分配 Microsoft 365 许可证相同。 还可以批量向多个用户分配许可证。 有关可用的电话系统许可证以及如何获取和分配许可证的详细信息，请参阅 [Teams 附加许可证](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing)和[分配Microsoft Teams 附加许可证](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)。

## <a name="step-2-choose-a-pstn-connectivity-option"></a>第 2 步 选择 PSTN 连接选项

若要使用户能够拨打和接听外部呼叫，需要将电话系统连接到公用电话交换网 (PSTN) 。 Microsoft提供了多个用于连接到 PSTN 的选项，包括：

- 通话套餐。 Microsoft作为 PSTN 运营商的全云解决方案。

- 操作员连接。 如果现有运营商参与Microsoft操作员连接计划，他们可以为你管理 PSTN 呼叫和会话边界控制器 (SBC) 。

- Teams Phone Mobile。 如果你的现有运营商参与Microsoft Teams 电话移动版计划，他们可以管理服务，以便在 Teams 中使用启用了 SIM 的移动电话号码。

- 直接路由。 通过将 SBC 连接到电话系统，使用自己的 PSTN 运营商。

有关所有连接选项的详细信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步骤 3：获取用户的电话号码

必须先获取用户的电话号码，然后才能将组织中的用户设置为拨打和接听电话。

有关如何管理用户的电话号码的信息，请参阅以下文章。 管理用户号码的方式取决于所选的 PSTN 连接选项。

- [管理组织的电话号码](manage-phone-numbers-landing-page.md) - 提供电话号码类型的概述，并提供指向特定文章的链接，这些文章用于获取和管理号码，具体取决于 PSTN 连接选项。
描述两种类型的 [用户电话号码](manage-phone-numbers-landing-page.md#user-telephone-numbers)。

- [为用户分配、更改或删除电话号码](assign-change-or-remove-a-phone-number-for-a-user.md) – 描述如何分配和管理已获取的电话号码。

- [你可以获得多少个电话号码](how-many-phone-numbers-can-you-get.md) - 描述你可以获取多少个电话号码，具体取决于你购买和分配的电话号码类型和许可证类型。

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>步骤 4：获取呼叫队列、自动助理)  (服务的电话号码

除了为用户获取电话号码外，还可以获取自动助理和呼叫队列等服务的收费或免费电话号码。 服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。

可以从许可中包含的Microsoft获取服务编号。 如果通过运营商连接或直接路由建立 PSTN 连接，则可以使用自己的运营商或运营商提供的服务号。

有关详细信息，请参阅：

- [管理组织的电话号码](manage-phone-numbers-landing-page.md) - 提供电话号码类型的概述，并提供指向特定文章的链接，这些文章用于获取和管理号码，具体取决于 PSTN 连接选项。
介绍许可中包含的Microsoft提供的服务[电话号码](manage-phone-numbers-landing-page.md#service-telephone-numbers)。 有关操作员连接或直接路由提供的服务号码的信息，请联系提供商。

- [你可以获得多少个电话号码](how-many-phone-numbers-can-you-get.md) - 描述你可以获取多少个电话号码，具体取决于你购买和分配的电话号码类型和许可证类型。

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>步骤 5：如果要设置呼叫队列

呼叫队列包括有人呼叫组织的电话号码时使用的问候语、自动将呼叫置于保留状态的功能，以及搜索下一个可用呼叫代理来处理呼叫的功能。 可以为组织创建一个或多个呼叫队列。

有关呼叫队列的详细信息，请参阅 [创建呼叫队列](create-a-phone-system-call-queue.md)。

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>步骤 6：如果要设置自动助理

自动助理允许呼叫组织的人员在菜单系统中导航，以便他们找到正确的部门、呼叫队列、人员或操作员。

有关设置自动助理的信息，请参阅 [设置自动助理](create-a-phone-system-auto-attendant.md)。

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>步骤 7：为免费号码设置通信额度

如果要将免费号码与 Microsoft Teams 配合使用，则需要设置通信点数。 免费呼叫按分钟计费，需要通信积分余额为正数。

通信额度是添加免费号码的便捷方式，如下所示：

- 使用语音应用的服务号码，例如自动助理或呼叫队列。

- 当你拥有国内通话套餐订阅或超出国内和国际通话套餐订阅中包含的范围时拨打任何国际电话号码。

- 在用完每月每分钟分配后拨出并按分钟付费。

- 如果你有即用即付通话套餐，则为所有传出呼叫拨出并按分钟付费。

有关详细信息，请参阅 [什么是通信额度？](what-are-communications-credits.md) 和 [为组织设置通信额度](set-up-communications-credits-for-your-organization.md)。

## <a name="related-articles"></a>相关文章

- [什么是电话系统？](what-is-phone-system-in-office-365.md)

- [电话系统的功能](here-s-what-you-get-with-phone-system.md)

- [管理组织的电话号码](manage-phone-numbers-landing-page.md)
