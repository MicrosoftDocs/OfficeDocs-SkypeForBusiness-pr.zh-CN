---
title: tblComplianceFanout
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含处理法规遵从性事件中的所有服务器。
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 包含处理法规遵从性事件中的所有服务器。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |事件 id。  <br/> |
|fanoutServerID  <br/> |int  <br/> |服务器标识 （对应于 tblServerIdentity.serverID 表）。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|fanoutEventID  <br/> |TblComplianceData.cmplEventID 表中查找与外键。  <br/> |
   

