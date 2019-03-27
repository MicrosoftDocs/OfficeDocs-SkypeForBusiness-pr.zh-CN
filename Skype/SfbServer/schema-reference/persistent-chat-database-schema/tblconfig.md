---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含不支持某些持久聊天服务器的配置，在一行中。
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898935"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig 包含不支持某些持久聊天服务器的配置，在一行中。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255)，不为 null  <br/> |包含"池。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |配置内容。  <br/> |
|configPoolID  <br/> |GUID，不为 null  <br/> |数据库实例的唯一 ID。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|configLabel  <br/> |主键。  <br/> |
   

