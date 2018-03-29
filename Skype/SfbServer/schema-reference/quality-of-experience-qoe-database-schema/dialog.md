---
title: Dialog 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 对话框表是支持表;每个记录都表示一个会话启动协议 (SIP) 对话框。
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a>Dialog 表
 
对话框表是支持表;每个记录都表示一个会话启动协议 (SIP) 对话框。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |当卓越质量 (QoE) 代理程序从调用方或被调用方接收的第一个报告的时间。 与 SessionSeq 配合使用，以唯一标识会话。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |若要区分的会话时它们具有相同的 ConferenceDateTime 的序列号。  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||这是全局唯一的对话框 ID。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |索引  <br/> |校验和的对话框 id。  <br/> |
   

