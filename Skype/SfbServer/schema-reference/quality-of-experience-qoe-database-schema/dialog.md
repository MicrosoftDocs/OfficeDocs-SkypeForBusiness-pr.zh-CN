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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 对话框表是支持表;每条记录表示一个会话初始协议（SIP）对话框。
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809530"
---
# <a name="dialog-table"></a>Dialog 表
 
对话框表是支持表;每条记录表示一个会话初始协议（SIP）对话框。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |优质（QoE） agent 接收来自呼叫方或被叫方的第一个报告的时间。 与 SessionSeq 结合使用以唯一标识会话。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |序列号，以便在具有相同的 ConferenceDateTime 时区分会话。  <br/> |
|**DialogID** <br/> |varchar （256）  <br/> ||全局唯一的对话框 ID。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |食指  <br/> |对话框 ID 的校验和。  <br/> |
   

