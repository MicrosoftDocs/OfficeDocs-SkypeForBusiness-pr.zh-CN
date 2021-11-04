---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含处理合规性事件的所有服务器。
ms.openlocfilehash: 6c0ae5a9b00945494c125511e1206f4177432703
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765070"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 包含处理合规性事件的所有服务器。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |事件 ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |服务器标识（与 tblServerIdentity.serverID 表对应）。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|fanoutEventID  <br/> |其查找包含在 tblComplianceData.cmplEventID 表中的外键。  <br/> |
   

