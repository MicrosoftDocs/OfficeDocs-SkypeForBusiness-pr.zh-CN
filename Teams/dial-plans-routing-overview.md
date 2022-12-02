---
title: Microsoft Teams 拨号计划和路由
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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Microsoft Teams 中的拨号计划和路由
ms.openlocfilehash: b45fd9ec15ae6a9bb8f342096711b58512aead43
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242466"
---
# <a name="microsoft-teams-dial-plans-and-routing"></a>Microsoft Teams 拨号计划和路由

本部分中的文章介绍了 Microsoft Teams 中的拨号计划和呼叫路由。 

- [什么是拨号计划](what-are-dial-plans.md)
- [创建并管理拨号计划](create-and-manage-dial-plans.md)
- [将调用路由到未分配的 numbes](routing-calls-to-unassigned-numbers.md)

本部分中的文章适用于连接到公用电话交换网 (PSTN) 的所有选项：通话套餐、运营商连接、Teams 电话移动和直接路由。 有关所有 PSTN 连接选项的详细信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。

如果选择“通话套餐”、“运营商连接”或“Teams 电话移动”，则大多数呼叫路由由Microsoft或提供商处理。 但是，直接路由需要其他步骤来配置呼叫路由。 

对于直接路由，必须通过指定语音路由并向用户分配语音路由策略来配置呼叫路由。 可以在中继级别配置号码转换的拨号计划，以确保与会话边界控制器 (SBC) 的互操作性。 有关详细信息，请参阅 [配置直接路由的语音路由](direct-routing-voice-routing.md)、 [管理语音路由策略](manage-voice-routing-policies.md) 和 [翻译电话号码](direct-routing-translate-numbers.md)。

请注意，可以将直接路由联机语音路由策略分配给通话套餐和运营商连接用户。 例如，你可能希望执行此操作，使用户能够直接拨入呼叫中心。 可以设置到呼叫中心的直接路由中继。

例如，如果用户具有通话套餐许可证，该用户的传出呼叫将通过Microsoft呼叫计划 PSTN 基础结构自动路由。 如果配置直接路由联机语音路由策略并将其分配给用户，则会检查用户的传出呼叫，以确定拨出号码是否与联机语音路由策略中定义的号码模式匹配。 如果有匹配项，则通过直接路由中继路由呼叫。 如果没有匹配项，则通过呼叫计划 PSTN 基础结构路由呼叫。

有关详细信息，请参阅 [直接路由语音路由策略注意事项](direct-routing-voice-routing.md#voice-routing-policy-considerations)。



