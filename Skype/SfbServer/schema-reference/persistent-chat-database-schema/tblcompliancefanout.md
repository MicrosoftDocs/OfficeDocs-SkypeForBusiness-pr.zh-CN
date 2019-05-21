---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含处理合规性事件的所有服务器。
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295501"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 包含处理合规性事件的所有服务器。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |事件 ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |服务器标识 (对应于 tblServerIdentity 表)。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|fanoutEventID  <br/> |TblComplianceData 表中的 lookup 的外键。  <br/> |
   

