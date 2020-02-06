---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含用于文件传输目的的临时令牌。
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814590"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken 包含用于文件传输目的的临时令牌。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar （50），not null  <br/> |唯一标记（GUID）。  <br/> |
|fileTokenUserID  <br/> |int，not null  <br/> |传输文件的主体的 ID。  <br/> |
|fileTokenChannelID  <br/> |GUID，not null  <br/> |聊天室节点的 GUID。  <br/> |
|fileTokenExpireDate  <br/> |datetime，not null  <br/> |过期时间。 （令牌将在30分钟后到期，除非已固定（请参阅本专栏中的以下说明）。  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |已传送文件的 URL （用于合规性服务使用）。  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |传输文件的缩略图的 URL （适用于合规性服务使用）。  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |实际文件传输操作的时间戳（用于合规性服务使用）。  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |如果上载，则为 True;如果下载（适用于合规性服务使用），则为 False。  <br/> |
|fileTokenCompliancePinned  <br/> |位，not null  <br/> |如果标记已固定，则为 True。 它用于在表中保留令牌，直到合规性服务有机会从中检索相关字段。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|fileToken  <br/> |主键。  <br/> |
|fileTokenChannelID  <br/> |TblNode 表中的 lookup 的外键。  <br/> |
   

