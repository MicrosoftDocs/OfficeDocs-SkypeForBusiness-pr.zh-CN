---
title: tblConfig
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久的聊天服务器不支持的配置，在一行中。
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig 包含一些持久的聊天服务器不支持的配置，在一行中。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255) 不为空  <br/> |包含"池。  <br/> |
|configContent  <br/> |nvarchar （最大）  <br/> |配置内容。  <br/> |
|configPoolID  <br/> |GUID，不为空  <br/> |数据库实例的唯一 ID。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|configLabel  <br/> |为主键。  <br/> |
   

