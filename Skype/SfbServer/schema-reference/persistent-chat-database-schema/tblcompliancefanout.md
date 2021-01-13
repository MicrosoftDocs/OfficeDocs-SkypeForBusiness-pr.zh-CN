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
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809792"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 包含处理合规性事件的所有服务器。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |事件 ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |服务器标识（与 tblServerIdentity.serverID 表对应）。  <br/> |
   
**注册表项**

|**列**|**说明**|
|:-----|:-----|
|fanoutEventID  <br/> |其查找包含在 tblComplianceData.cmplEventID 表中的外键。  <br/> |
   

