---
title: QoE 视图列表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 视图涉及有关从 QoE SQL 数据库返回数据的最常见方案。 建议使用用于生成自定义报表的视图，而不是直接访问数据库表;这是因为视图更有可能保持与将来版本的向后兼容性。
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834472"
---
# <a name="qoe-view-details"></a>QoE 视图列表
 
视图涉及有关从 QoE SQL 数据库返回数据的最常见方案。 建议使用用于生成自定义报表的视图，而不是直接访问数据库表;这是因为视图更有可能保持与将来版本的向后兼容性。
  
|**视图名称**|**说明**|
|:-----|:-----|
|[AudioStreamDetail 视图](audiostreamdetail.md) <br/> |存储数据库中每个音频流的相关信息。  <br/> |
|[MediaLine 视图](medialine.md) <br/> |存储有关数据库中每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频与视频 (A/V) 会话通常包含一个音频媒体行和一个视频媒体行；但是，如果使用了会议设备或库视图，则会话可能包含两个视频媒体行。  <br/> |
|[NetworkConfigurationSettings 视图](networkconfigurationsettings.md) <br/> |存储有关网络配置的信息。  <br/> |
|[会话视图](session-0.md) <br/> |存储有关数据库中包含记录的会话的信息。  <br/> |
|[UserAgent 视图](useragent-0.md) <br/> |存储有关数据库中包含记录的会话中涉及的用户代理的信息。  <br/> |
|[VideoStreamDetail 视图](videostreamdetail.md) <br/> |存储有关数据库中每个视频流的信息。  <br/> |
   

