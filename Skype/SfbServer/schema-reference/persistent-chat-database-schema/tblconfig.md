---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含不支持某些持久聊天服务器的配置，在一行中。
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930020"
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
   

