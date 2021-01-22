---
title: Teams 语音 Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 针对多语言公司的 Teams 语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918728"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 案例研究：自动助理和呼叫队列

Contoso 熟悉其本地 Skype for Business 部署中的自动助理和呼叫队列。 为了了解如何设置云自动助理和呼叫队列，他们查看了 Teams 自动助理和 [呼叫队列的计划](plan-auto-attendant-call-queue.md)。

## <a name="requirements-depending-on-site-type"></a>要求，具体取决于网站类型

根据站点类型，Contoso 具有以下需求：

- 站点类型 A：传统传统电话系统 

  网站类型 A 需要保留与其自动助理号码相同的与接待员关联的电话号码。 每个网站的关键部门都有自己的呼叫队列，这些队列将路由到团队成员。 将电话系统与直接路由和电话系统与呼叫计划一起使用的站点混合在一起。  

- 站点类型 B：Skype for Business 企业语音 

  网站类型 B 有现有的自动助理和需要迁移到 Teams 的呼叫队列。 Contoso 需要保留与自动助理相关联的电话号码。 Contoso 将大多数此类网站移动到具有通话套餐的电话系统。 但是，在呼叫计划不可用的少数位置，Contoso 将这些站点移到了直接路由配置。  

- 站点类型 C：Skype for Business 企业语音 &传统传统电话系统 

  站点类型 C 具有驻留在传统旧电话系统中的现有自动助理。 此站点的决策和配置与站点类型 A 相同。   

- 对于所有网站类型，Contoso 询问了以下问题：

  - 问：我们将使用新号码还是现有号码？ 
    答：Contoso 决定使用现有电话号码分配给自动助理的服务帐户。 

  - 问：何时可以使用自动助理接受传入呼叫？ 
    答：Contoso 决定设置营业时间，将营业时间后收到的呼叫重定向到"非工作时间"自动助理。  

  - 问：如何将呼叫路由到呼叫队列中的成员：助理、串行或轮循机制路由？ 
    答：Contoso 决定使用 Attendant 路由， 

  - 问：我们如何确定用户何时应或不应进行呼叫？ 
    答：Contoso 决定使用呼叫处理选项来确定代理是否可用：基于状态的路由。 


## <a name="configuration"></a>配置

设置自动助理和呼叫队列的步骤包括管理资源帐户 [中概述的以下内容](manage-resource-accounts.md)： 

1. 获取服务编号。 

2. 获取免费电话系统 - 虚拟用户许可证或付费电话系统许可证，以用于资源帐户或电话系统许可证。

3. 创建资源帐户。 需要自动助理或呼叫队列才能拥有关联的资源帐户。 

4. 将电话系统或电话系统 - 虚拟用户许可证分配给资源帐户。 有关详细信息，请参阅 [Microsoft 365 手机系统 - 虚拟用户许可证](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)。

5. 将服务电话号码分配给分配给资源帐户的许可证。 

6. 创建电话系统呼叫队列或自动助理 

7. 将资源帐户与呼叫队列或自动助理关联。 


### <a name="sites-with-phone-system-with-direct-routing"></a>使用电话系统进行直接路由的网站 

Contoso 必须设置本地运营商提供的电话号码作为 Office 365 中的服务号码。 

- 为了设置通过直接路由提供的电话号码，Contoso 按照"管理资源帐户" [中的说明进行操作](manage-resource-accounts.md)。 由于 Office 365 不知道本地电话号码，Contoso 使用 PowerShell 完成设置。   

- 为了配置云自动助理，Contoso 遵循了"设置云自动助理 ["中概述的步骤](create-a-phone-system-auto-attendant.md)。 

- 为了设置云呼叫队列，Contoso 遵循了"创建云呼叫队列 ["中概述的步骤](create-a-phone-system-call-queue.md)。  


### <a name="sites-with-phone-system-with-calling-plan"></a>具有电话系统和呼叫计划的网站

Contoso 必须将 Skype for Business 使用的电话号码企业语音自动助理移植到 Office 365 电话系统。 这允许将同一号码分配为服务号码，以用作自动助理。 

- 为了转转电话号码，Contoso 按照"将电话号码转移到 [Teams"](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 中的说明，在"为组织管理电话号码"上获得了 [其他指导](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。

- 为了配置云自动助理，Contoso 遵循了"设置云自动助理 ["中概述的步骤](create-a-phone-system-auto-attendant.md)。

-  为了设置云呼叫队列，Contoso 遵循了"创建云呼叫队列 ["中概述的步骤](create-a-phone-system-call-queue.md)。  

 