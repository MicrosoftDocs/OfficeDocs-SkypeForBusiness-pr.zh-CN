---
title: tblFileToken
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含临时标记用于文件传输的目的。
ms.openlocfilehash: 86047611c21301543a12486fa1c15bb15fde4c65
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken 包含临时标记用于文件传输的目的。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50) 不为空  <br/> |唯一的标记 (GUID)。  <br/> |
|fileTokenUserID  <br/> |int，不为空  <br/> |将文件传送的承担者的 ID。  <br/> |
|fileTokenChannelID  <br/> |GUID，不为空  <br/> |聊天室节点的 GUID。  <br/> |
|fileTokenExpireDate  <br/> |日期时间不为空  <br/> |到期时间。 （令牌过期，30 分钟后，除非固定 （请参阅以下说明此列中的）。  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |（用于法规遵从性服务） 传输的文件的 URL。  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |（用于法规遵从性服务） 传输的文件的缩略图的 URL。  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |实际的文件传输操作 （用于法规遵从性服务） 的时间戳。  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True 传;假如果下载 （用于法规遵从性服务）。  <br/> |
|fileTokenCompliancePinned  <br/> |位，不为空  <br/> |如果令牌被固定，则为 true。 它用来标记保留的表中，直到法规遵从性服务有机会从中检索的相关字段。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|fileToken  <br/> |为主键。  <br/> |
|fileTokenChannelID  <br/> |TblNode.nodeGuid 表中查找与外键。  <br/> |
   

