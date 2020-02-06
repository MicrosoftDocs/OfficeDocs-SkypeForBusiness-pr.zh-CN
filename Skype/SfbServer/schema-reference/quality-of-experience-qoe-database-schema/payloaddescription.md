---
title: PayloadDescription 表
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
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 表是支持表。 每条记录表示一个编解码器，用于音频或视频会话。
ms.openlocfilehash: 3a5719d7fbfe23eb8c1457565a36df0a02617fde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807490"
---
# <a name="payloaddescription-table"></a>PayloadDescription 表
 
PayloadDescription 表是支持表。 每条记录表示一个编解码器，用于音频或视频会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |标识编解码器的唯一号码。  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |唯一  <br/> |编解码器名称。  <br/> |
   

