---
title: Teams 语音 Contoso 案例研究：自动助理和呼叫队列
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
description: 多国公司 Teams 语音案例研究：自动助理和呼叫队列
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50d1ee2d384b200aeab6eefd6ca2de623015b6f2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615838"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 案例研究：自动助理和呼叫队列

Contoso 熟悉其本地Skype for Business部署中的自动助理和呼叫队列。 为了了解如何设置云自动助理和呼叫队列，他们查看了 [Teams 自动助理和呼叫队列的计划](plan-auto-attendant-call-queue.md)。

## <a name="requirements-depending-on-site-type"></a>根据网站类型的要求

根据网站类型，Contoso 有以下需求：

- 站点类型 A：传统的旧式电话系统 

  网站类型 A 需要保留与其自动助理的号码相同的与接待员关联的电话号码。 每个站点的关键部门都有自己的呼叫队列，这些队列将路由到团队成员。 有混合的网站，使用电话系统与直接路由和电话系统与呼叫计划。  

- 站点类型 B：Skype for Business 企业语音 

  站点类型 B 具有迁移到 Teams 所需的现有自动助理和呼叫队列。 Contoso 需要保留与自动助理关联的电话号码。 Contoso 使用通话套餐将大部分网站移动到电话系统。 但是，在通话套餐不可用的少数位置，Contoso 将这些站点移动到直接路由配置。  

- 站点类型 C：Skype for Business 企业语音 &传统传统电话系统 

  站点类型 C 具有驻留在传统传统电话系统中的现有自动助理。 此站点的决策和配置与站点类型 A 相同。   

- 对于所有网站类型，Contoso 都提出了以下问题：

  - 问：我们会使用新的数字还是现有数字？ 
    答：Contoso 决定使用现有电话号码分配给自动助理的服务帐户。 

  - 问：自动助理何时可以接受传入呼叫？ 
    答：Contoso 决定设置营业时间，并在工作时间重定向到“下班后”自动助理后接听电话。  

  - 问：如何将呼叫路由到呼叫队列中的成员：助理、串行或轮循机制路由？ 
    答：Contoso 决定使用助理路由， 

  - 问：如何确定用户何时应或不应接听呼叫？ 
    答：Contoso 决定使用调用处理选项来确定代理是否可用：基于状态的路由。 

## <a name="configuration"></a>配置

设置自动助理和呼叫队列的步骤包括“[管理资源帐户](manage-resource-accounts.md)”中概述的以下步骤：

1. 获取服务编号。

2. 获取免费 **Microsoft Teams 电话资源帐户** 许可证或付费电话系统许可证，以便与资源帐户或电话系统许可证一起使用。

3. 创建资源帐户。 需要自动助理或调用队列才能拥有关联的资源帐户。

4. 将 **Teams 电话标准版** 或 **Microsoft Teams 电话资源帐户** 许可证分配给资源帐户。 有关详细信息，请参阅[Microsoft Teams 电话资源帐户许可证](./teams-add-on-licensing/virtual-user.md)。

5. 向分配许可证的资源帐户分配服务电话号码。

6. 创建电话系统呼叫队列或自动助理。

7. 将资源帐户与呼叫队列或自动助理链接。

### <a name="sites-with-phone-system-with-direct-routing"></a>具有直接路由的电话系统网站

Contoso 必须将本地运营商提供的电话号码设置为Office 365中的服务号码。

- 为了设置通过直接路由提供的电话号码，Contoso 遵循了“ [管理资源帐户](manage-resource-accounts.md)”中的说明。 由于Office 365不知道本地电话号码，Contoso 使用 PowerShell 完成设置。   

- 为了配置云自动助理，Contoso 遵循了“[设置云自动助理](create-a-phone-system-auto-attendant.md)”中所述的步骤。 

- 为了设置云呼叫队列，Contoso 遵循了“ [创建云呼叫队列”](create-a-phone-system-call-queue.md)中所述的步骤。  


### <a name="sites-with-phone-system-with-calling-plan"></a>具有电话系统和呼叫计划的网站

Contoso 必须将用于Skype for Business 企业语音自动助理的电话号码移植到Office 365 电话系统。 这允许将相同的数字分配为用作自动助理的服务编号。 

- 为了移植电话号码，Contoso 遵循了 [将电话号码传输到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 中的说明，并获得了组织 [管理电话号码](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)的其他指导。

- 为了配置云自动助理，Contoso 遵循了“[设置云自动助理](create-a-phone-system-auto-attendant.md)”中所述的步骤。

-  为了设置云呼叫队列，Contoso 遵循了“ [创建云呼叫队列”](create-a-phone-system-call-queue.md)中所述的步骤。  

