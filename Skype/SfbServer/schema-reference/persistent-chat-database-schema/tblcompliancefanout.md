---
title: tblComplianceFanout
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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含处理合规性事件的所有服务器。
ms.openlocfilehash: 81ee29e5b25080f841ab578214694f563c7cc6b14fe791b1c6b26dc5ea741859
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351931"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 包含处理合规性事件的所有服务器。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |事件 ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |服务器标识（与 tblServerIdentity.serverID 表对应）。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|fanoutEventID  <br/> |其查找包含在 tblComplianceData.cmplEventID 表中的外键。  <br/> |
   

