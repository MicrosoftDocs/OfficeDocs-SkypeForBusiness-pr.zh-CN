---
title: tblComplianceData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含有尚未处理法规遵从性在适配器的法规遵从性事件。
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData 包含有尚未处理法规遵从性在适配器的法规遵从性事件。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint，不为空  <br/> |事件 id。  <br/> |
|entryDate  <br/> |短格式不为空  <br/> |插入时 (可能是到目前为止在将来为 cmplType = 9，因为在这种情况下对应的项是只是一个占位符)。  <br/> |
|cmplType  <br/> |int，不为空  <br/> | 法规遵从性事件类型： <br/>  1： 聊天 <br/>  2: backchat <br/>  3： 文件下载 <br/>  4： 文件上载 <br/>  9： 临时文件传输 <br/>  10： 聊天 （替换） 的删除 <br/>  11： 聊天清除 <br/> |
|cmplTime  <br/> |bigint，不为空  <br/> |该事件的时间戳。  <br/> |
|cmplChannelUri  <br/> |nvarchar (255) 不为空  <br/> |统一资源标识符 (URI) 的通道。  <br/> |
|cmplChatID  <br/> |bigint  <br/> |聊天 （对应于 tblChat.chatId 表） 的 ID。  <br/> |
|cmplUserID  <br/> |int，不为空  <br/> |（对应于 tblPrincipal.prinID 表） 的海报的主体 ID。  <br/> |
|cmplUserUri  <br/> |nvarchar (255) 不为空  <br/> |用户的 URI。  <br/> |
|cmplMessage  <br/> |nvarchar （最大）  <br/> |消息 （编码取决于 cmplType）。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|cmplEventID  <br/> |为主键。  <br/> |
   

