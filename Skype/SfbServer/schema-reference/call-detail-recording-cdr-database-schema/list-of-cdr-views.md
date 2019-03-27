---
title: CDR 视图列表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 视图提供轻松访问有关用于从 CDR 数据库返回数据的最常见方案的信息。 建议用于生成自定义报告，而不是使用实际 CDR 数据库表; 使用视图这是因为更容易保持向后兼容性将来版本的数据库视图。
ms.openlocfilehash: 7767a80069201e5ec07ea68d4bdef3a6a5977e4d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876857"
---
# <a name="list-of-cdr-views"></a>CDR 视图列表
 
视图提供轻松访问有关用于从 CDR 数据库返回数据的最常见方案的信息。 建议用于生成自定义报告，而不是使用实际 CDR 数据库表; 使用视图这是因为更容易保持向后兼容性将来版本的数据库视图。
  
|**视图名称**|**说明**|
|:-----|:-----|
|[ClientVersions 视图](clientversions-0.md) <br/> |返回有关客户端的信息的通信会话中使用的软件/设备。  <br/> |
|[ConferenceMessageCount 视图](conferencemessagecount-0.md) <br/> |返回有关会议中的用户发送的消息数的信息。  <br/> |
|[会议视图](conferences-0.md) <br/> |返回会议信息，包括开始时间、 结束时间和会议组织者。  <br/> |
|[ConferenceSessionDetails 视图](conferencesessiondetails.md) <br/> |所有会议会话，包括开始和结束时间、 用户 Id、 响应代码和诊断 Id 都返回会话详细信息。  <br/> |
|[ConferenceUris 视图](conferenceuris-0.md) <br/> |在会议中返回有关会议使用 Uri 的信息  <br/> |
|[ErrorReport 视图](errorreport-0.md) <br/> |返回会话期间发生的错误有关的信息。  <br/> |
|[FileTransfers 视图](filetransfers.md) <br/> |返回文件传输会话，包括文件名和是否被接受转接，有关的信息拒绝还是取消。  <br/> |
|[FocusJoinsAndLeaves 视图](focusjoinsandleaves-0.md) <br/> |返回有关会议加入和离开活动。  <br/> |
|[McuJoinsAndLeaves 视图](mcujoinsandleaves-0.md) <br/> |返回组合信息会议加入和离开的活动 （每个会议加入与相应的会议离开配对）。  <br/> |
|[Mcus 视图](mcus-0.md) <br/> |返回有关会议服务器的信息。  <br/> |
|[媒体视图](media-0.md) <br/> |返回的对等通信会话中使用的媒体类型的信息。  <br/> |
|[ProgressReport 视图](progressreport-0.md) <br/> |返回有关已完成会话的信息。  <br/> |
|[注册视图](registration-0.md) <br/> |返回有关与 Skype 的注册业务服务器 2015年的信息。  <br/> |
|[SessionDetails 视图](sessiondetails-0.md) <br/> |返回有关对等会话，包括 Voip-voip 电话呼叫、 双方 IM 会话或其他对等通信会话的信息。  <br/> |
|[用户视图](user.md) <br/> |返回有关已参与通信会话的用户信息。  <br/> |
|[VoIPDetails 视图](voipdetails.md) <br/> |返回涉及至少一个 VoIP (Voice over IO) 用户的对等会话的信息。  <br/> |
   

