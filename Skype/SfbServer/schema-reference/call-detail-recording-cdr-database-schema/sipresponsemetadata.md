---
title: SIPResponseMetaData 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 响应代码的分类和定义的每个这些代码的列表。 这些代码以响应事件影响 SIP 设备生成和 SIP 通信会话;例如，对 SIP 设备发出请求，而服务器拒绝接受请求时生成响应代码 403。
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData 表
 
SIPResponseMetaDataTable 包含 SIP 响应代码的分类和定义的每个这些代码的列表。 这些代码以响应事件影响 SIP 设备生成和 SIP 通信会话;例如，对 SIP 设备发出请求，而服务器拒绝接受请求时生成响应代码 403。
  
为业务服务器 2015年在 Skype 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |数字值，表示 SIP 响应代码。  <br/> |
|**类** <br/> |int  <br/> || 响应代码的的一般分类。 类别包括： <br/>  1-信息的响应 <br/>  2-成功的响应 <br/>  3-重定向响应 <br/>  4-客户端故障响应 <br/>  5-服务器故障响应 <br/>  6-全局失败响应 <br/> |
|**说明** <br/> |nvarchar(256)  <br/> ||SIP 响应代码的描述。 例如，响应代码 181 有以下说明：  <br/> 呼叫已转发  <br/> |
   

