---
title: Dialog 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 对话框表是支持表;每条记录表示一个会话初始协议 (SIP) 对话框。
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294955"
---
# <a name="dialog-table"></a>Dialog 表
 
对话框表是支持表;每条记录表示一个会话初始协议 (SIP) 对话框。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |优质 (QoE) agent 接收来自呼叫方或被叫方的第一个报告的时间。 与 SessionSeq 结合使用以唯一标识会话。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |序列号, 以便在具有相同的 ConferenceDateTime 时区分会话。  <br/> |
|**DialogID** <br/> |varchar (256)  <br/> ||全局唯一的对话框 ID。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |食指  <br/> |对话框 ID 的校验和。  <br/> |
   

