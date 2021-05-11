---
title: 更多关于呼叫线路 ID 和主叫方名称的信息
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: 了解呼叫线路 ID 和呼叫方名称。
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308311"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>更多关于呼叫线路 ID 和主叫方名称的信息

CallerID 包含两条面向用户的信息：

- 电话号码 (称为 CLID 或呼叫线路 ID) 。

- 调用方 (通常称为 CNAM) 。 

进行呼叫时，CLID (电话号码) 路由到目的地的运营商 (也称为终止运营商) 。 调用的 CNAM 信息可能会路由，也可能不能与调用一起路由，因为此信息取决于国家/地区实现 CNAM (（如果) ）。 通过呼叫进行 CNAM 传送的可靠性因处理呼叫的国家/地区或运营商（作为中介或终止性运营商）而异。 

CLID & CNAM 传输是终止运营商的责任。 终止运营商必须支持 CLID & CNAM 功能，并为这两个值提供最新记录。 Microsoft 在发起调用时可靠地提供 CLID 值，但这些值在通过中间运营商或终止运营商后可能不会保持不变。 如果 CLID 值被中介或终止运营商更改、省略或截断，Microsoft 几乎无法解决公共电话网络中此类问题。

当中间或终止性运营商延迟刷新权威数据库中的 CNAM 信息时（如美国的情况）时，CNAM 中的不一致可能引起。 在没有 CNAM 权威数据库的国家/地区，各个运营商的做法也可能导致 CNAM 信息在呼叫中保持不变。 Microsoft 目前不支持美国外的国家/地区提供原始 CNAM 信息。

## <a name="related-topics"></a>相关主题


