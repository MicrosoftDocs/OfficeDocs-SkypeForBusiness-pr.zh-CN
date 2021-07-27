---
title: Teams Contoso 案例研究：紧急呼叫
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
description: Teams公司的语音案例研究：紧急呼叫
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69231adb4588039012cceec1063571ddc201c2bb
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587471"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso 案例研究：紧急呼叫

若要了解紧急呼叫的可用性以及与紧急呼叫相关的术语，请拨打紧急地址、地点、紧急位置和已注册地址 &mdash; &mdash; ，Contoso[](what-are-emergency-locations-addresses-and-call-routing.md)查看管理紧急呼叫和[计划和](configure-dynamic-emergency-calling.md)配置动态紧急呼叫。

在Office 365，呼叫计划用户会自动启用紧急呼叫。 但是，只有美国的呼叫计划用户才能使用动态位置路由紧急呼叫。 

对于直接路由，Contoso 了解到，路由紧急呼叫和合作伙伴连接可能需要其他配置。 管理员必须配置与紧急路由服务提供商 (ERSP)  (美国) 的连接，或者为紧急位置标识号 (ELIN) 应用程序配置会话边界控制器 (SBC) 。

Contoso 在美国和美国以外设有办公室：

- 在美国，Contoso 呼叫计划用户可以使用动态位置路由紧急呼叫。 

- 在美国以外，Contoso 拥有一些使用呼叫计划的站点，以及一些通过直接路由电话系统连接的站点。

## <a name="emergency-calling-use-cases"></a>紧急呼叫用例

确定 Contoso 如何连接到电话后，Contoso 确定了以下紧急呼叫用例： 

- [呼叫美国计划用户](#calling-plan-user-in-the-united-states) 

- [呼叫美国以外的计划用户](#calling-plan-user-outside-of-the-united-states)

- [通过直接路由电话系统用户](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>呼叫美国计划用户  

电话号码何时需要与紧急位置关联有要求。 为了了解这些要求，Contoso 查看了 [调用计划的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 

根据这些要求，Contoso 决定在将号码分配给美国用户时，将位置与电话号码关联。

### <a name="calling-plan-user-outside-of-the-united-states"></a>呼叫美国以外的计划用户 

为了了解电话号码何时需要与紧急位置关联，Contoso 查看了呼叫  [计划的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 Contoso 根据要求决定以下事项：  

-  当向加拿大的用户分配号码时，Contoso 将位置与电话号码关联。 

- 从提供商处获取电话号码时，或者从另一服务提供商或运营商Office 365号码时，Contoso 将分配紧急位置。 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>通过直接路由电话系统用户 

为了针对此用例规划紧急路由，Contoso 查看了 [直接路由的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。 由于直接路由用户接收紧急呼叫的方式与呼叫计划用户不同，Contoso 必须决定如何提供紧急呼叫。 直接路由可以连接到紧急路由服务提供商 (ERSP) 。 直接路由还可以有一个 SBC，其中包含紧急位置标识号 (ELIN) 。   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>紧急路由服务提供商 (ERSP) 注意事项

紧急路由服务提供商 (ERSP) 根据呼叫者的位置自动路由紧急呼叫。  

- 如果将紧急路由服务提供商集成到直接路由部署中，具有动态获取位置的紧急呼叫将自动路由到提供该位置的公共安全应答点 (PSAP) 。 

- 没有动态获取位置的紧急呼叫首先经过筛选，以确定用户的当前位置，然后根据更新的位置将呼叫连接到相应的调度中心。 


#### <a name="elin-considerations"></a>ELIN 注意事项

如果将 SBC ELIN 应用程序集成到直接路由部署中，则需要执行其他配置步骤，将紧急地址与电话号码关联。  

Contoso 决定使用包含紧急位置标识号的会话边界控制器 (ELIN) 应用程序。  

## <a name="security-desk-notification"></a>安全服务台通知

在拨打紧急呼叫时通知安全服务台的能力适用于 Microsoft 呼叫计划和直接电话系统路由。 Contoso 查看了安全服务台通知中的详细信息，确定是否应在其办公室进行配置  

Contoso 决定使用安全服务台通知。

## <a name="configuration"></a>配置 

Contoso 遵循配置动态紧急 [呼叫中的步骤](configure-dynamic-emergency-calling.md) 来： 

- 分配紧急地址 

- 配置网络设置 

- 配置位置信息服务 

- 配置紧急策略 

- 启用用户和网站 

- 测试紧急呼叫 

配置动态紧急呼叫后，Contoso 需要将位置分配给相应的用户。  

- 若要为组织添加、更改或删除紧急位置，Contoso 按照为组织添加、更改或删除紧急位置中的 [步骤操作](add-change-remove-emergency-location-organization.md)

- 为了创建建筑物、楼层和办公室的位置，Contoso 按照添加、更改或删除紧急位置 [中的步骤操作](add-change-remove-emergency-place-organization.md) 。 

- 为了分配紧急位置，Contoso 按照为用户分配或更改紧急 [位置中的步骤操作](assign-change-emergency-location-user.md)。 

 
