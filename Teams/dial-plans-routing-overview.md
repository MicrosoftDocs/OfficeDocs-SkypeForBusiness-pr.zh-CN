---
title: 拨号计划和路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
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
description: 在Microsoft Teams中拨号计划和路由
ms.openlocfilehash: 1d99b5edef1cf6c4440a218097933e4ff5843f1d
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686710"
---
# <a name="overview"></a>概述

本部分中的文章介绍Microsoft Teams中的拨号计划和呼叫路由。 

- [什么是拨号计划](what-are-dial-plans.md)
- [创建并管理拨号计划](create-and-manage-dial-plans.md)
- [将调用路由到未分配的 numbes](routing-calls-to-unassigned-numbers.md)

本部分中的文章适用于连接到公共交换电话网络的所有选项 (PSTN) ：呼叫计划、运营商连接和直接路由。 有关所有 PSTN 连接选项的详细信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。

如果选择呼叫计划或运营商连接，大多数呼叫路由由 Microsoft 或提供商处理。 但是，直接路由需要其他步骤来配置呼叫路由。 

对于直接路由，必须通过指定语音路由并向用户分配语音路由策略来配置呼叫路由。 可以在中继级别配置号码转换的拨号计划，以确保与会话边框控制器 (SBC) 互操作性。 有关详细信息，请参阅 [为直接路由配置语音路由](direct-routing-voice-routing.md)、 [管理语音路由策略](manage-voice-routing-policies.md) 和 [翻译电话号码](direct-routing-translate-numbers.md)。

请注意，可以将直接路由联机语音路由策略分配给呼叫计划并运营商连接用户。 例如，你可能需要执行此操作，以使用户能够直接拨入呼叫中心。 可以设置到呼叫中心的直接路由中继。

例如，如果用户具有呼叫计划许可证，则该用户的传出呼叫会自动通过 Microsoft 呼叫计划 PSTN 基础结构路由。 如果配置直接路由联机语音路由策略并将其分配给用户，则会检查用户的传出呼叫，以确定拨号号码是否与联机语音路由策略中定义的数字模式匹配。 如果存在匹配项，则通过直接路由中继路由调用。 如果没有匹配项，则通过呼叫计划 PSTN 基础结构路由调用。

有关详细信息，请参阅 [直接路由语音路由策略注意事项](direct-routing-voice-routing.md#voice-routing-policy-considerations)。



