---
title: 更多关于呼叫线路 ID 和主叫方名称的信息
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: 了解在使用 "新的本地号码" 外接程序时，为什么需要添加可对帐户进行更改的授权人员。
ms.openlocfilehash: a687bc1aca8a47b349415d4a0cc2dc9f61f81884
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708798"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>更多关于呼叫线路 ID 和主叫方名称的信息

CallerID （通常称为），实际上包含两个面向用户的可识别信息片段：
    - 电话号码（通常称为 CLID 或呼叫行 ID） 
    - 呼叫方名称（通常称为 CNAM），最多可以有15个字符的长度。 

进行呼叫时，CLID （电话号码）将路由到目的地的运营商（也称为终止载波）。 呼叫的 CNAM 信息可能与呼叫路由，也可能不会与通话路由，具体取决于国家的实现 CNAM （如果有）。 与通话的 CNAM 传递的可靠性因作为中间和/或终止运营商处理呼叫的国家和运营商而异。 

CLID & CNAM 传输是终止载波的责任，因为终止运营商必须支持 CLID & CNAM 功能以及为两个值提供最新的记录。 在发起呼叫时 Microsoft 可靠地提供 CLID 值，但这些值在通过中间运营商或终止运营商传递后可能不会保持不变。 遗憾的是，在 CLID 值发生更改时，由中间或终止载波省略或截断，Microsoft 几乎不能在 recourse 公共电话网络中解决这些问题。

CNAM 中的不一致可能由中间或终止运营商刷新权威数据库中的 CNAM 信息引起的，如美国的情况。 在没有 CNAM 权威数据库的国家/地区，单个运营商的做法也可能会导致与呼叫一起送达 tact 的 CNAM 信息出现问题。 Microsoft 目前不支持除美国之外的其他国家/地区的原始 CNAM 信息。 "

## <a name="related-topics"></a>相关主题


