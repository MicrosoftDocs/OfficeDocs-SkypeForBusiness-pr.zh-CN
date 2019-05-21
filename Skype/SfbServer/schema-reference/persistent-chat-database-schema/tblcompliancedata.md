---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含尚未由合规性适配器处理的合规性事件。
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295508"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData 包含尚未由合规性适配器处理的合规性事件。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, not null  <br/> |事件 ID。  <br/> |
|entryDate  <br/> |smalldatetime, not null  <br/> |插入时间 (对于 cmplType = 9, 将来可能会是很远), 因为在该情况下, 条目只是占位符。  <br/> |
|cmplType  <br/> |int, not null  <br/> | 合规性事件的类型: <br/>  1: 聊天 <br/>  2: Backchat <br/>  3: 文件下载 <br/>  4: 文件上载 <br/>  9: 临时文件传输 <br/>  10: 删除聊天 (带替换) <br/>  11: 聊天清除 <br/> |
|cmplTime  <br/> |bigint, not null  <br/> |事件的时间戳。  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), not null  <br/> |通道统一资源标识符 (URI)。  <br/> |
|cmplChatID  <br/> |bigint  <br/> |聊天 ID (对应于 tblChat 表)。  <br/> |
|cmplUserID  <br/> |int, not null  <br/> |海报的主体 ID (对应于 tblPrincipal 表)。  <br/> |
|cmplUserUri  <br/> |nvarchar (255), not null  <br/> |用户 URI。  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |邮件 (编码取决于 cmplType)。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|cmplEventID  <br/> |主键。  <br/> |
   

