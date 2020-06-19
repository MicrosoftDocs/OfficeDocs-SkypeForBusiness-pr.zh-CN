---
title: 团队语音 Contoso 个案研究
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
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785957"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 个案研究：自动助理和呼叫队列

Contoso 通过其本地 Skype for Business 部署熟悉自动助理和呼叫队列。 若要了解如何设置云自动助理，他们审阅[了什么是云自动助理？](what-are-phone-system-auto-attendants.md)和[小型企业版示例-设置自动助理教程](tutorial-org-aa.yml)。 若要了解可用于设置呼叫队列的选项，Contoso 已审阅 "[创建云呼叫队列](create-a-phone-system-call-queue.md)"。  

## <a name="requirements-depending-on-site-type"></a>根据网站类型的要求

根据网站类型，Contoso 有以下需要：

- 网站类型 A：传统旧电话系统 

  网站类型将与接待员相关联的电话号码保留为其自动助理的编号。 其中每个站点的关键部门都有自己的通话队列，它们将路由到团队成员。 有一种网站混合使用手机系统和通话计划的直接路由和电话系统。  

- 网站类型 B： Skype for Business 企业语音 

  网站类型 B 拥有迁移到团队所需的自动助理和呼叫队列。 Contoso 需要保留与自动助理相关联的电话号码。 Contoso 通过通话计划将大部分这些站点移动到电话系统。 但是，在通话计划不可用的几个位置中，Contoso 将这些网站移动到直接路由配置。  

- 网站类型 C： Skype for Business 企业语音 & 传统旧式电话系统 

  网站类型 C 具有驻留在传统旧式电话系统中的现有自动助理。 此网站的决策和配置与网站类型 A 相同。   

- 对于所有网站类型，Contoso 询问以下问题：

  - 问：我们将使用新号码还是现有号码？ 
    A： Contoso 决定使用现有电话号码分配给自动助理的服务帐户。 

  - 问：自动助理是否可以用来接受拨入电话？ 
    A： Contoso 决定设置营业时间，并在营业时间已重定向到 "时间超过" 自动助理后收到呼叫。  

  - 问：如何将呼叫路由到呼叫队列中的成员：助理、串行或循环路由？ 
    A： Contoso 决定使用助理路由， 

  - 问：如何确定用户何时应该或不应该进行呼叫？ 
    A： Contoso 决定使用呼叫处理选项确定代理是否可用：基于状态的路由。 


## <a name="configuration"></a>配置

设置自动助理和呼叫队列的步骤包括 "[管理资源帐户](manage-resource-accounts.md)" 中列出的以下内容： 

1. 获取服务号码。 

2. 获取免费电话系统-虚拟用户许可证或付费电话系统许可证，以便与资源帐户或电话系统许可证配合使用。

3. 创建资源帐户。 需要使用自动助理或呼叫队列才能拥有关联的资源帐户。 

4. 为资源帐户分配电话系统或电话系统-虚拟用户许可证。 有关详细信息，请参阅[Microsoft 365 Phone 系统-虚拟用户许可证](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)。

5. 将服务电话号码分配给您为其分配了许可证的资源帐户。 

6. 创建电话系统呼叫队列或自动助理 

7. 将资源帐户与呼叫队列或自动助理链接。 


### <a name="sites-with-phone-system-with-direct-routing"></a>带有直接路由的手机系统的站点 

Contoso 必须将本地运营商提供的电话号码设置为 Office 365 中的服务号码。 

- 若要通过直接路由设置可用的电话号码，Contoso 按照 "[管理资源帐户](manage-resource-accounts.md)" 中的说明进行操作。 由于 Office 365 不知道本地电话号码，Contoso 使用 PowerShell 完成设置。   

- 若要配置云自动助理，Contoso 按照[设置云自动助理](create-a-phone-system-auto-attendant.md)中概述的步骤进行操作。 

- 若要设置云呼叫队列，Contoso 按照[创建云呼叫队列](create-a-phone-system-call-queue.md)中概述的步骤进行操作。  


### <a name="sites-with-phone-system-with-calling-plan"></a>带有呼叫计划的带有电话系统的站点

Contoso 必须将用于 Skype for Business 企业语音自动助理的电话号码移植到 Office 365 电话系统。 这允许将同一号码分配为作为自动助理使用的服务号码。 

- 若要移植电话号码，Contoso 按照[向团队转移电话号码](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)的说明进行操作，并在[管理您的组织的电话号码](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)时获得其他指导。

- 若要配置云自动助理，Contoso 按照[设置云自动助理](create-a-phone-system-auto-attendant.md)中概述的步骤进行操作。

-  若要设置云呼叫队列，Contoso 按照[创建云呼叫队列](create-a-phone-system-call-queue.md)中概述的步骤进行操作。  

 