---
title: tblConfig
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一个行中的一些持久聊天服务器不受支持的配置。
ms.openlocfilehash: ddfd8cdc48158a3f4b2776b80c0bf0293ecff71b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846285"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig 包含一个行中的一些持久聊天服务器不受支持的配置。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255)，不为 null  <br/> |包含“池”。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |配置内容。  <br/> |
|configPoolID  <br/> |GUID，不为 null  <br/> |数据库实例的唯一 ID。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|configLabel  <br/> |主键。  <br/> |
   

