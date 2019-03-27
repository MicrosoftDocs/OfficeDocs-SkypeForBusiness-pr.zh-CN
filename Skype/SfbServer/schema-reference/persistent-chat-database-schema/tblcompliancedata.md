---
title: tblComplianceData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含具有合规性适配器尚未处理的合规性事件。
ms.openlocfilehash: e617f7821fcf026f279f333d45f526a1322509a1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885819"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData 包含具有合规性适配器尚未处理的合规性事件。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint，不为 null  <br/> |事件 id。  <br/> |
|entryDate  <br/> |smalldatetime，不为 null  <br/> |插入时间 (可能遥远将来对于 cmplType = 9，因为该条目在此情况下是只是一个占位符)。  <br/> |
|cmplType  <br/> |int，不为 null  <br/> | 合规性事件的类型： <br/>  1： 聊天 <br/>  2： 聊天记录 <br/>  3： 文件下载 <br/>  4： 文件上载 <br/>  9： 临时文件传输 <br/>  10： 删除聊天 （通过替换） <br/>  11： 清除聊天 <br/> |
|cmplTime  <br/> |bigint，不为 null  <br/> |该事件的时间戳。  <br/> |
|cmplChannelUri  <br/> |nvarchar (255)，不为 null  <br/> |通道统一资源标识符 (URI)。  <br/> |
|cmplChatID  <br/> |bigint  <br/> |聊天 ID （与 tblChat.chatId 表对应）。  <br/> |
|cmplUserID  <br/> |int，不为 null  <br/> |（与 tblPrincipal.prinID 表对应） 的海报的主体 ID。  <br/> |
|cmplUserUri  <br/> |nvarchar (255)，不为 null  <br/> |用户 URI。  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |消息 （编码取决于 cmplType）。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|cmplEventID  <br/> |主键。  <br/> |
   

