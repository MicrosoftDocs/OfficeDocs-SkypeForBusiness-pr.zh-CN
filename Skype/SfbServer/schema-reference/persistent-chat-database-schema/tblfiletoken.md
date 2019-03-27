---
title: tblFileToken
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含用于文件传输的临时令牌。
ms.openlocfilehash: 46553a4b8752e2a95691dc2042a2632845166fc7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881296"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken 包含用于文件传输的临时令牌。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50)，不为 null  <br/> |唯一的令牌 (GUID)。  <br/> |
|fileTokenUserID  <br/> |int，不为 null  <br/> |要传输文件的主体的 ID。  <br/> |
|fileTokenChannelID  <br/> |GUID，不为 null  <br/> |聊天室节点的 GUID。  <br/> |
|fileTokenExpireDate  <br/> |datetime，不为 null  <br/> |过期时间。 （令牌过期后 30 分钟，除非固定 （请参阅此列中的以下说明）。  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |已传输文件 （用于合规性服务） 的 URL。  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |已传输文件 （用于合规性服务） 的缩略图的 URL。  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |（用于合规性服务） 的实际文件传输操作的时间戳。  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True 如果上载;则为 false （用于合规性服务） 下载。  <br/> |
|fileTokenCompliancePinned  <br/> |bit，不为 null  <br/> |如果固定令牌，则为 true。 它用于保留标记的表中，直到合规性服务有机会从中检索相关字段。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|fileToken  <br/> |主键。  <br/> |
|fileTokenChannelID  <br/> |包含在 tblNode.nodeGuid 表中查找的外键。  <br/> |
   

