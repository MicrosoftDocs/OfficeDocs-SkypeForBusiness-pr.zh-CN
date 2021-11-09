---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含用于文件传输的临时令牌。
ms.openlocfilehash: 73958e48814a27e5871b2a0af73d77a55531e49b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831776"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken 包含用于文件传输的临时令牌。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50)，不为 null  <br/> |唯一令牌（一个 GUID）。  <br/> |
|fileTokenUserID  <br/> |int，不为 null  <br/> |要传输文件的主体的 ID。  <br/> |
|fileTokenChannelID  <br/> |GUID，不为 null  <br/> |聊天室节点的 GUID。  <br/> |
|fileTokenExpireDate  <br/> |datetime，不为 null  <br/> |过期时间。除非固定，令牌的有效期为 30 分钟（请参阅此列中以下说明）。  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar (256)   <br/> |已传输文件的 URL（用于合规性服务）。  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar (256)   <br/> |已传输文件的缩略图的 URL（用于合规性服务）。  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |实际文件传输操作的时间戳（用于合规性服务）。  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |如果上载，则为 True；如果下载，则为 False（用于合规性服务）。  <br/> |
|fileTokenCompliancePinned  <br/> |bit，不为 null  <br/> |如果令牌是固定的，则为 True。 它用于将令牌保留到表中，直到合规性服务有机会从表中检索相关字段。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|fileToken  <br/> |主键。  <br/> |
|fileTokenChannelID  <br/> |其查找包含在 tblNode.nodeGuid 表中的外键。  <br/> |
   

