---
title: CDR 视图列表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 可通过视图轻松访问有关用于从 CDR 数据库返回数据的最常见方案的信息。 建议您使用视图来生成自定义报告，而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与将来版本的向后兼容性。
ms.openlocfilehash: 24effb3b8c90721550ac813342965142f0e29875
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626474"
---
# <a name="list-of-cdr-views"></a>CDR 视图列表
 
可通过视图轻松访问有关用于从 CDR 数据库返回数据的最常见方案的信息。 建议您使用视图来生成自定义报告，而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与将来版本的向后兼容性。
  
|**视图名称**|**说明**|
|:-----|:-----|
|[ClientVersions 视图](clientversions-0.md) <br/> |返回通信会话中使用的客户端软件/设备的相关信息。  <br/> |
|[ConferenceMessageCount 视图](conferencemessagecount-0.md) <br/> |返回会议中的用户发送的消息数的相关信息。  <br/> |
|[会议视图](conferences-0.md) <br/> |返回会议信息，包括开始时间、结束时间和会议组织者。  <br/> |
|[ConferenceSessionDetails 视图](conferencesessiondetails.md) <br/> |返回所有会议会话的会话详细信息，包括开始和结束时间、用户 ID、响应代码和诊断 ID。  <br/> |
|[ConferenceUris 视图](conferenceuris-0.md) <br/> |返回会议中使用的会议 URI 的相关信息  <br/> |
|[ErrorReport 视图](errorreport-0.md) <br/> |返回会话期间发生的错误的相关信息。  <br/> |
|[FileTransfers 视图](filetransfers.md) <br/> |返回文件传输会话的相关信息，包括文件名以及是接受、拒绝还是取消传输。  <br/> |
|[FocusJoinsAndLeaves 视图](focusjoinsandleaves-0.md) <br/> |返回有关会议加入和离开活动的信息。  <br/> |
|[McuJoinsAndLeaves 视图](mcujoinsandleaves-0.md) <br/> |返回有关会议加入和离开活动的组合信息（每个会议加入与相应的会议离开配对）。  <br/> |
|[Mcus 视图](mcus-0.md) <br/> |返回有关会议服务器的信息。  <br/> |
|[媒体视图](media-0.md) <br/> |返回有关对等通信会话中使用的媒体类型的信息。  <br/> |
|[ProgressReport 视图](progressreport-0.md) <br/> |返回有关已完成会话的信息。  <br/> |
|[注册视图](registration-0.md) <br/> |返回有关在 Skype for Business Server 2015 中注册的信息。  <br/> |
|[SessionDetails 视图](sessiondetails-0.md) <br/> |返回有关对等会话的信息，包括 VoIP-VoIP 电话呼叫、双方 IM 会话或其他对等通信会话。  <br/> |
|[用户视图](user.md) <br/> |返回参与通信会话的用户的相关信息。  <br/> |
|[VoIPDetails 视图](voipdetails.md) <br/> |返回至少包括一个 VoIP (Voice over IO) 用户的对等会话的相关信息。  <br/> |
   

