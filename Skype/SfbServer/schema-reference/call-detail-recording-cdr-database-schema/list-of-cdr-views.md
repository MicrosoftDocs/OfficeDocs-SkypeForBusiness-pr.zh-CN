---
title: CDR 视图的列表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 视图，可以方便地访问信息用于从 CDR 数据库返回数据的最常见方案。 建议使用视图，以便生成自定义报表，而不是使用实际的 CDR 数据库表;这是因为数据库视图会更容易保持向后兼容与将来的发行版。
ms.openlocfilehash: d0ccf227af5bf205acd57660ca9cc51ba27e103e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-cdr-views"></a>CDR 视图的列表
 
视图，可以方便地访问信息用于从 CDR 数据库返回数据的最常见方案。 建议使用视图，以便生成自定义报表，而不是使用实际的 CDR 数据库表;这是因为数据库视图会更容易保持向后兼容与将来的发行版。
  
|**视图名称**|**说明**|
|:-----|:-----|
|[ClientVersions 视图](clientversions-0.md) <br/> |返回有关客户端信息通信会话中使用的软件/设备。  <br/> |
|[ConferenceMessageCount 视图](conferencemessagecount-0.md) <br/> |返回有关在会议中的用户发送的邮件数。  <br/> |
|[查看会议](conferences-0.md) <br/> |返回会议信息，包括开始时间、 结束时间和会议组织者。  <br/> |
|[ConferenceSessionDetails 视图](conferencesessiondetails.md) <br/> |对于所有会议会话，包括开始和结束时间、 用户 Id、 响应代码和诊断的 Id 返回会话的详细信息。  <br/> |
|[ConferenceUris 视图](conferenceuris-0.md) <br/> |在会议中返回 Uri 使用的会议有关的信息  <br/> |
|[ErrorReport 视图](errorreport-0.md) <br/> |返回有关在会话期间发生的错误的信息。  <br/> |
|[FileTransfers 视图](filetransfers.md) <br/> |返回有关文件传输会话，包括的文件的名称和传输是否已被接受的拒绝，或者取消。  <br/> |
|[FocusJoinsAndLeaves 视图](focusjoinsandleaves-0.md) <br/> |返回有关大会的信息联接和休假活动。  <br/> |
|[McuJoinsAndLeaves 视图](mcujoinsandleaves-0.md) <br/> |返回组合参加会议有关的信息，并将的活动 （每个参加会议配合相应的会议保留）。  <br/> |
|[Mcu 视图](mcus-0.md) <br/> |返回会议服务器有关的信息。  <br/> |
|[媒体视图](media-0.md) <br/> |返回信息的对等通信会话中使用的媒体类型。  <br/> |
|[ProgressReport 视图](progressreport-0.md) <br/> |返回有关已完成的会话的信息。  <br/> |
|[注册视图](registration-0.md) <br/> |返回与 Skype 的注册有关的业务服务器 2015年的信息。  <br/> |
|[SessionDetails 视图](sessiondetails-0.md) <br/> |返回有关对等会话，包括 VoIP VoIP 电话联络、 两方的 IM 会话或其他对等通信会话的信息。  <br/> |
|[用户视图](user.md) <br/> |返回有关参加通信会话的用户的信息。  <br/> |
|[VoIPDetails 视图](voipdetails.md) <br/> |返回用于对等会话涉及至少一个 VoIP （IO 配音） 用户的信息。  <br/> |
   

