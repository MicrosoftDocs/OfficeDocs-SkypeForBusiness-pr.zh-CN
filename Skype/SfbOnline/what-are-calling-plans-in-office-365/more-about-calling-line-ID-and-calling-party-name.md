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
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 了解您需要添加获得授权的人员可以时使用新的本地号码端口订单向导的帐户进行更改的原因。
ms.openlocfilehash: 846abfd5b6973a02ad1a7388b45a79ec709695a0
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23865274"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>更多关于呼叫线路 ID 和主叫方名称的信息

来电显示，如通常被认为，实际上包括两个面向用户的识别部分的信息：
    - 电话号码 （通常称为为 CLID 或调用行 ID） 
    - 调用方名称 （通常称作 CNAM） 的长度最多包含 15 个字符。 

在发出呼叫时，CLID （电话号码） 路由至的目标运营商 （也称为终止运营商）。 用于呼叫的 CNAM 信息可能也可能不会路由调用，这取决于如何国家/地区已实现 CNAM （如果有）。 使用呼叫 CNAM 传递的可靠性而异的国家/地区和其处理呼叫，或者作为中介的运营商和/或终止运营商。 

只要终止运营商必须支持 CLID = CNAM 功能以及提供的这两个值的最新记录，则 CLID = CNAM 传输是终止运营商的责任。 Microsoft 能够可靠地提供 CLID 值，当发起呼叫，但这些值可能不会保持不变后通过中间的运营商或终止运营商。 遗憾的是，在事件 CLID 值更改、 省略或中间或终止运营商被截断，Microsoft 具有更正公共电话网络中的此类问题的小为没有解决方法。

在 CNAM 不一致情况可能是由刷新 CNAM 信息，如美国的大小写中所示的权威数据库中的中间或终止运营商的延迟导致的。 国家/地区其中没有为 CNAM 权威数据库，各个运营商实践也会导致调用原封不动到达 CNAM 信息的问题。 Microsoft 当前不支持发起 CNAM 信息在美国之外的国家/地区。"

## <a name="related-topics"></a>相关主题


