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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久聊天服务器不支持的配置，其中一行。
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814620"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig 包含一些持久聊天服务器不支持的配置，其中一行。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar （255），not null  <br/> |包含 "pool"。  <br/> |
|configContent  <br/> |nvarchar （max）  <br/> |配置内容。  <br/> |
|configPoolID  <br/> |GUID，not null  <br/> |数据库实例的唯一 ID。  <br/> |
   
**Key**

|**列**|**说明**|
|:-----|:-----|
|configLabel  <br/> |主键。  <br/> |
   

