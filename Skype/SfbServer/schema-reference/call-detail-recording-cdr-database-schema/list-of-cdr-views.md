---
title: CDR 视图列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 视图提供了一种简单的方法来访问有关用于从 CDR 数据库返回数据的最常见方案的信息。 建议使用视图生成自定义报表, 而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与未来版本的向后兼容性。
ms.openlocfilehash: e1a7926108c2e27ecc69c5717867b9c18f8b47ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296138"
---
# <a name="list-of-cdr-views"></a>CDR 视图列表
 
视图提供了一种简单的方法来访问有关用于从 CDR 数据库返回数据的最常见方案的信息。 建议使用视图生成自定义报表, 而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与未来版本的向后兼容性。
  
|**视图名称**|**说明**|
|:-----|:-----|
|[ClientVersions 视图](clientversions-0.md) <br/> |返回有关在通信会话中使用的客户端软件/设备的信息。  <br/> |
|[ConferenceMessageCount 视图](conferencemessagecount-0.md) <br/> |返回有关会议中用户发送的邮件数的信息。  <br/> |
|[会议视图](conferences-0.md) <br/> |返回会议信息, 包括 "开始时间"、"结束时间" 和 "会议组织者"。  <br/> |
|[ConferenceSessionDetails 视图](conferencesessiondetails.md) <br/> |返回所有会议会话的会话详细信息, 包括开始和结束时间、用户 Id、响应代码和诊断 Id。  <br/> |
|[ConferenceUris 视图](conferenceuris-0.md) <br/> |返回有关会议中使用的会议 Uri 的信息  <br/> |
|[ErrorReport 视图](errorreport-0.md) <br/> |返回有关会话期间发生的错误的信息。  <br/> |
|[FileTransfers 视图](filetransfers.md) <br/> |返回有关文件传输会话的信息, 包括文件名以及是否接受、拒绝或取消传输。  <br/> |
|[FocusJoinsAndLeaves 视图](focusjoinsandleaves-0.md) <br/> |返回有关会议加入和退出活动的信息。  <br/> |
|[McuJoinsAndLeaves 视图](mcujoinsandleaves-0.md) <br/> |返回有关会议加入和退出活动的组合信息 (每个会议联接与相应的会议休假配对)。  <br/> |
|[Mcus 视图](mcus-0.md) <br/> |返回有关会议服务器的信息。  <br/> |
|[媒体视图](media-0.md) <br/> |返回有关对等通信会话中使用的媒体类型的信息。  <br/> |
|[ProgressReport 视图](progressreport-0.md) <br/> |返回有关已完成会话的信息。  <br/> |
|[注册视图](registration-0.md) <br/> |返回有关 Skype for business Server 2015 的注册信息。  <br/> |
|[SessionDetails 视图](sessiondetails-0.md) <br/> |返回有关对等会话的信息, 包括 VoIP-VoIP 电话呼叫、两方 IM 会话或其他对等通信会话。  <br/> |
|[用户视图](user.md) <br/> |返回有关参与通信会话的用户的信息。  <br/> |
|[VoIPDetails 视图](voipdetails.md) <br/> |返回至少涉及一个 VoIP (通过 IO 的语音) 用户的对等会话的信息。  <br/> |
   

