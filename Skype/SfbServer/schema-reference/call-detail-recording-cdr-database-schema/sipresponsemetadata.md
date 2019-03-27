---
title: SIPResponseMetaData 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 响应代码的分类和定义的每个代码的列表。 这些代码以响应事件影响 SIP 设备生成和 SIP 通信会话;例如，SIP 设备发出请求，但服务器拒绝接受该请求时，将生成 403 的响应代码。
ms.openlocfilehash: 7b60ffff90434c341fcf15fb75ddc93ac9f26201
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878208"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData 表
 
SIPResponseMetaDataTable 包含 SIP 响应代码的分类和定义的每个代码的列表。 这些代码以响应事件影响 SIP 设备生成和 SIP 通信会话;例如，SIP 设备发出请求，但服务器拒绝接受该请求时，将生成 403 的响应代码。
  
此表中引入 Skype 的业务服务器 2015年。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |表示 SIP 响应代码的数值。  <br/> |
|**类** <br/> |int  <br/> || 常规分类的响应代码。 分类包括： <br/>  1-信息响应 <br/>  2-成功响应 <br/>  3-重定向响应 <br/>  4-客户端失败响应 <br/>  5 – 服务器失败响应 <br/>  6-全局失败响应 <br/> |
|**说明** <br/> |nvarchar(256)  <br/> ||SIP 响应代码的描述。 例如，响应代码 181 具有以下描述：  <br/> 呼叫转接  <br/> |
   

