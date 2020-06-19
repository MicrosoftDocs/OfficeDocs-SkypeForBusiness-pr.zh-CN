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
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785976"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso 案例研究：紧急电话

要了解紧急呼叫的可用性以及与紧急呼叫 &mdash; 紧急地址、地点、紧急位置和注册地址相关的术语， &mdash; Contoso 已查看[管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)和[计划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

在 Office 365 中，通话计划用户将自动启用以进行紧急呼叫。 但只有美国的通话计划用户才可以使用动态位置路由紧急呼叫。 

对于直接路由，Contoso 发现，需要进行额外的配置来路由紧急呼叫，并且可能需要进行合作伙伴连接。 管理员必须配置与紧急路由服务提供商（ERSP）（美国）的连接，或为紧急位置识别号码（ELIN）应用程序配置会话边界控制器（SBC）。

Contoso 拥有美国和美国境外的办事处：

- 在美国，Contoso 通话计划用户可以使用动态位置路由紧急呼叫。 

- 在美国以外，Contoso 拥有一些使用呼叫计划的网站，以及通过直接路由连接到手机系统的某些网站。

## <a name="emergency-calling-use-cases"></a>紧急呼叫使用案例

确定 Contoso 将如何连接到手机系统后，Contoso 识别出以下紧急呼叫使用案例： 

- [美国的通话计划用户](#calling-plan-user-in-the-united-states) 

- [美国境外的通话计划用户](#calling-plan-user-outside-of-the-united-states)

- [通过直接路由连接到手机系统的用户](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>美国的通话计划用户  

需要与紧急位置相关联的电话号码的要求。 若要了解这些要求，Contoso 检查[了通话计划的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 

根据这些要求，当将号码分配给美国的用户时，Contoso 决定将位置与电话号码相关联。

### <a name="calling-plan-user-outside-of-the-united-states"></a>美国境外的通话计划用户 

若要了解需要与紧急位置相关联的电话号码，Contoso 检查[了通话计划的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 根据要求，Contoso 确定以下事项：  

-  当将号码分配给加拿大的用户时，Contoso 会将该位置与电话号码相关联。 

- 当从 Office 365 获取电话号码时，或者从另一个服务提供商或运营商处转移号码时，Contoso 将分配紧急地点。 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>通过直接路由连接到手机系统的用户 

要为此使用案例规划紧急路由，Contoso 已检查[直接路由的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。 由于直接路由用户没有像呼叫计划用户那样接收紧急呼叫，因此，Contoso 必须决定如何提供紧急电话。 直接路由可以连接到紧急路由服务提供商（ERSP）。 直接路由还可以有一个包含紧急位置识别号（ELIN）的 SBC。   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>紧急路由服务提供商（ERSP）注意事项

紧急路由服务提供商（ERSPs）可以根据呼叫方的位置自动路由紧急电话。  

- 如果将紧急路线服务提供商集成到直接路由部署中，则会将带有动态获取位置的紧急呼叫自动路由到服务该位置的公共安全应答点（PSAP）。 

- 在将呼叫连接到基于更新的位置之前，没有动态获取的位置的紧急电话将首先进行筛选以确定用户的当前位置。 


#### <a name="elin-considerations"></a>ELIN 注意事项

如果 SBC ELIN 应用程序集成到直接路由部署中，则需要执行其他配置步骤以将紧急地址与电话号码相关联。  

Contoso 决定使用包含紧急位置标识号（ELIN）应用程序的会话边框控制器。  

## <a name="security-desk-notification"></a>安全桌面通知

可用于 Microsoft 通话计划和电话系统直接路由，以便在紧急呼叫被置入时通知安全桌面。 Contoso 已查看安全桌面通知中的详细信息，以确定是否应在其办公室配置此信息  

Contoso 决定使用安全桌面通知。

## <a name="configuration"></a>配置 

Contoso 按照[配置动态紧急呼叫](configure-dynamic-emergency-calling.md)的步骤执行以下操作： 

- 分配紧急地址 

- 配置网络设置 

- 配置位置信息服务 

- 配置紧急策略 

- 启用用户和网站 

- 测试紧急电话 

配置动态紧急呼叫后，Contoso 需要将位置分配给相应的用户。  

- 若要为你的组织添加、更改或删除紧急位置，Contoso 按照[添加、更改或删除你的组织的紧急位置](add-change-remove-emergency-location-organization.md)中的步骤进行操作

- 要创建建筑物、楼层和办事处的位置，Contoso 按照[为紧急位置添加、更改或删除位置](add-change-remove-emergency-place-organization.md)中的步骤操作。 

- 要分配紧急位置，Contoso 按照[为用户分配或更改紧急位置](assign-change-emergency-location-user.md)中的步骤操作。 

 