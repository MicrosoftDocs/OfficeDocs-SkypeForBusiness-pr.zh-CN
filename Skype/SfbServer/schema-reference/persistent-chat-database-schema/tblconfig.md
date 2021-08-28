---
title: tblConfig
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 8cf1fc53087d3fc786ac47e848a21dbd2a8f5549
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595304"
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
   

