---
title: 对话框表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog 表是一个支持表；每条记录代表一个会话初始协议 (SIP) 对话。
ms.openlocfilehash: bccc053855ae88bc453aeef27d13732166cc6760
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765040"
---
# <a name="dialog-table"></a>对话框表
 
Dialog 表是一个支持表；每条记录代表一个会话初始协议 (SIP) 对话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |用户体验质量 (QoE) 代理从呼叫者或被叫方接收第一个报告的时间。与 SessionSeq 结合使用来唯一地标识会话。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |当会话具有相同的 ConferenceDateTime 时区分会话的序号。  <br/> |
|**DialogID** <br/> |varchar (256)   <br/> ||全局唯一的对话 ID。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |对话 ID 的校验和。  <br/> |
   

