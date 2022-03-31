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
description: 分步指南，详细说明如何在 Microsoft 365 中为组织Teams 电话系统设置Microsoft 365。
ms.openlocfilehash: 6b56c68e7316c78c7c1881d6e9d6ca39b13823b1
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556293"
---
# <a name="set-up-phone-system-in-your-organization"></a>在组织中设置电话系统

本文提供有关设置 电话系统 的内容的路线图-Microsoft 在云中启用呼叫控制和专用分支 Exchange (PBX) 功能Microsoft 365技术。 每个步骤结束时，会提供指向更多详细信息的链接。 

阅读本文之前，请确保已阅读什么是电话系统，下面[](what-is-phone-system-in-office-365.md)介绍了通过本文[电话系统](here-s-what-you-get-with-phone-system.md)。 后两篇文章介绍了电话系统和功能。    

本文介绍以下步骤： 

- [步骤 1：购买并分配电话系统许可证](#step-1-buy-and-assign-a-phone-system-license)  
- [步骤 2：选择 PSTN 连接选项](#step-2-choose-a-pstn-connectivity-option) 
- [步骤 3：获取用户的电话号码](#step-3-get-phone-numbers-for-your-users)
- [步骤 4：获取服务的电话号码](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [步骤 5：如果要设置呼叫队列](#step-5-if-you-want-to-set-up-a-call-queue) 
- [步骤 6：如果要设置自动助理](#step-6-if-you-want-to-set-up-an-auto-attendant) 
- [步骤 7：为免费电话号码设置通信信用额度](#step-7-set-up-communications-credits-for-toll-free-numbers)
 

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>步骤 1：购买并分配电话系统许可证

若要将电话系统许可证分配给单个用户，步骤与分配许可证Microsoft 365相同。 也可以批量向多个用户分配许可证。 有关可用许可证电话系统以及如何获取和分配许可证 [，请参阅Teams](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing)附加许可证和分配Microsoft Teams[许可证](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)。

## <a name="step-2-choose-a-pstn-connectivity-option"></a>第 2 步 选择 PSTN 连接选项 
 
为了让您的用户能够拨打和接听外部呼叫，您需要将呼叫电话系统 PSTN 呼叫 (电话) 。 Microsoft 提供了多个用于连接到 PSTN 的选项，包括： 

- 调用计划。 以 Microsoft 作为 PSTN 运营商的全云解决方案。 

- 运营商连接。 如果你的现有运营商参与 Microsoft 运营商连接计划，他们可以管理 PSTN 呼叫和会话边界控制器 (SDC) 你。 

- 直接路由。 通过将 SDC 连接到其他 SDC，使用自己的 PSTN 电话系统。 

有关所有连接选项的详细信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。   

## <a name="step-3-get-phone-numbers-for-your-users"></a>步骤 3：获取用户的电话号码

在将组织中用户设置为拨打和接听电话之前，必须获取其电话号码。

若要了解如何管理用户的电话号码，请参阅以下文章。 如何管理用户号码取决于你选择的 PSTN 连接选项。   

- [为组织管理电话号码](manage-phone-numbers-landing-page.md) - 提供电话号码类型的概述，其中提供了特定文章的链接，这些文章根据 PSTN 连接选项获取和管理号码。 描述两种类型的 [用户电话号码](manage-phone-numbers-landing-page.md#user-telephone-numbers)。 
 
- [为用户分配](assign-change-or-remove-a-phone-number-for-a-user.md) 、更改或删除电话号码 - 介绍如何分配和管理已获取的电话号码。 
 
- [可以获取的电话号码](how-many-phone-numbers-can-you-get.md) 数 - 描述可以获取的电话号码数，具体取决于你购买和分配的电话号码类型和许可证类型。 


## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>步骤 4：获取呼叫队列 (服务的电话号码，自动助理) 

除了为用户获取电话号码外，还可以获取自动助理和呼叫队列等服务的收费或免费电话号码。 服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。   

可以从 Microsoft 获取许可中包含的服务编号。 如果你通过直接路由运营商连接 PSTN 连接，可以使用自己的运营商或运营商提供的服务号码。 

有关详细信息，请参阅：

- [为组织管理电话号码](manage-phone-numbers-landing-page.md) - 提供电话号码类型的概述，其中提供了特定文章的链接，这些文章根据 PSTN 连接选项获取和管理号码。  
介绍 [许可](manage-phone-numbers-landing-page.md#service-telephone-numbers) 中包含的 Microsoft 提供的服务电话号码。 有关由用户或直接路由运营商连接服务号码的信息，请与提供商联系。 

- [可以获取的电话号码](how-many-phone-numbers-can-you-get.md) 数 - 描述可以获取的电话号码数，具体取决于你购买和分配的电话号码类型和许可证类型。 

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>步骤 5：如果要设置呼叫队列

呼叫队列包括当有人呼叫贵组织的电话号码时使用的问候语、自动保持呼叫的能力，以及搜索下一个可用的呼叫代理以处理呼叫的能力。 你可以为组织创建单个或多个呼叫队列。 

有关呼叫队列详细信息，请参阅 [创建呼叫队列](create-a-phone-system-call-queue.md)。

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>步骤 6：如果要设置自动助理

自动助理允许呼叫进入组织的人导航菜单系统，以将其转到正确的部门、呼叫队列、人员或接线员。  

有关设置自动助理的信息，请参阅 [设置自动助理](create-a-phone-system-auto-attendant.md)。

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>步骤 7：为免费号码设置通信信用额度

如果要将免费电话号码与 Microsoft Teams，则需要设置通信信用额度。 免费呼叫按分钟计费，需要正通信信用额度余额。 

通信信用额度是添加免费号码的便捷方式，如下所示： 

- 使用语音应用的服务号码，例如自动助理或呼叫队列。 

- 在拥有国内呼叫计划订阅或超出国内和国际呼叫计划订阅中包含的套餐时拨打任何国际电话号码。 

- 用完每月分钟数分配后拨出并按分钟支付。 

有关详细信息，请参阅 [通信信用额度是什么？](what-are-communications-credits.md) 和 [为组织设置通信信用额度](set-up-communications-credits-for-your-organization.md)。
  

## <a name="related-topics"></a>相关主题

- [什么是电话系统？](what-is-phone-system-in-office-365.md)

- [电话系统的功能](here-s-what-you-get-with-phone-system.md)

- [管理组织的电话号码](manage-phone-numbers-landing-page.md)


    
  
 
