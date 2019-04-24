---
title: Dialog 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog 表是一个支持表;每条记录代表一个会话初始协议 (SIP) 对话。
ms.openlocfilehash: 017da65154d12c89aeed63ea59269639d23b2129
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212570"
---
# <a name="dialog-table"></a>Dialog 表
 
Dialog 表是一个支持表;每条记录代表一个会话初始协议 (SIP) 对话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |卓越质量 (QoE) 代理时接收从呼叫者或被叫方的第一个报告时间。 与 SessionSeq 结合使用，来唯一地标识会话。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |区分会话拥有相同的 ConferenceDateTime 时的序列号。  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||全局唯一的对话 ID。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |索引  <br/> |对话框 ID 的校验和。  <br/> |
   

