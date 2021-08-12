---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含合规适配器尚未处理的合规事件。
ms.openlocfilehash: 70929cd85499fb015489054d11e11d492fe00e145e7da32dbf7477deb5e7c60d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284462"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData 包含合规适配器尚未处理的合规事件。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint，不为 null  <br/> |事件 ID。  <br/> |
|entryDate  <br/> |smalldatetime，不为 null  <br/> |插入时间（将来对于 cmplType=9，可能比较遥远，因为该条目在那种情况下只是一个占位符）。  <br/> |
|cmplType  <br/> |int，不为 null  <br/> | 合规事件的类型： <br/>  1：聊天 <br/>  2：聊天记录 <br/>  3：文件下载 <br/>  4：文件上载 <br/>  9：临时文件传输 <br/>  10：删除聊天（通过替换） <br/>  11：清除聊天 <br/> |
|cmplTime  <br/> |bigint，不为 null  <br/> |事件的时间戳。  <br/> |
|cmplChannelUri  <br/> |nvarchar (255)，不为 null  <br/> |通道统一资源标识符 (URI)。  <br/> |
|cmplChatID  <br/> |bigint  <br/> |聊天 ID（与 tblChat.chatId 表对应）。  <br/> |
|cmplUserID  <br/> |int，不为 null  <br/> |发布人的主体 ID（与 tblPrincipal.prinID 表对应）。  <br/> |
|cmplUserUri  <br/> |nvarchar (255)，不为 null  <br/> |用户 URI。  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |消息（编码方式取决于 cmplType）。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|cmplEventID  <br/> |主键。  <br/> |
   

