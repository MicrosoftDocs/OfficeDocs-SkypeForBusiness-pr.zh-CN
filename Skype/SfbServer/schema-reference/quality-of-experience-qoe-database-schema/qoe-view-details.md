---
title: QoE 查看详细信息
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 视图包括从 QoE SQL 数据库返回数据的最常见方案。 建议视图用于生成自定义报告，而不是直接访问数据库表中。这是因为视图会更容易保持向后兼容与将来的发行版。
ms.openlocfilehash: 72fe0a1cd4bd3319bbb6907a23bda0932b3ef619
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="qoe-view-details"></a>QoE 查看详细信息
 
视图包括从 QoE SQL 数据库返回数据的最常见方案。 建议视图用于生成自定义报告，而不是直接访问数据库表中。这是因为视图会更容易保持向后兼容与将来的发行版。
  
|**视图名称**|**说明**|
|:-----|:-----|
|[AudioStreamDetail 视图](audiostreamdetail.md) <br/> |在数据库中存储有关每个音频流信息。  <br/> |
|[MediaLine 视图](medialine.md) <br/> |在数据库中存储有关每个媒体行的信息。 一个音频会话通常包含音频媒体一行。 一个音频和视频 (A / V) 会话通常包含音频媒体一行和视频媒体一行;但是，会话可能包含两个视频媒体行如果使用电话会议设备，或使用图片库视图。  <br/> |
|[NetworkConfigurationSettings 视图](networkconfigurationsettings.md) <br/> |存储有关网络配置的信息。  <br/> |
|[会话视图](session-0.md) <br/> |存储在数据库中具有记录的会话信息。  <br/> |
|[用户代理视图](useragent-0.md) <br/> |存储在数据库中具有记录的会话中涉及的用户代理信息。  <br/> |
|[VideoStreamDetail 视图](videostreamdetail.md) <br/> |在数据库中存储有关每个视频流的信息。  <br/> |
   

