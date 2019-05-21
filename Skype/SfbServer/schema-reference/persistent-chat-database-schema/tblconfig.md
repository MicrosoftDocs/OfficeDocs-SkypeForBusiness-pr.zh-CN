---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久聊天服务器不支持的配置, 其中一行。
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295452"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig 包含一些持久聊天服务器不支持的配置, 其中一行。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), not null  <br/> |包含 "pool"。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |配置内容。  <br/> |
|configPoolID  <br/> |GUID, not null  <br/> |数据库实例的唯一 ID。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|configLabel  <br/> |主键。  <br/> |
   

