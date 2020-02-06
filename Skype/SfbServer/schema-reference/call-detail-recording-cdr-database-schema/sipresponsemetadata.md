---
title: SIPResponseMetaData 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 响应代码列表以及每个代码的分类和定义。 系统会生成这些代码，以响应影响 SIP 设备和 SIP 通信会话的事件;例如，在 SIP 设备发出请求时，将生成响应代码403，但服务器拒绝接受该请求。
ms.openlocfilehash: 2c302793dc9f9c53d445d231a261bf43a0c385df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814890"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData 表
 
SIPResponseMetaDataTable 包含 SIP 响应代码列表以及每个代码的分类和定义。 系统会生成这些代码，以响应影响 SIP 设备和 SIP 通信会话的事件;例如，在 SIP 设备发出请求时，将生成响应代码403，但服务器拒绝接受该请求。
  
此表是在 Skype for Business Server 2015 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |表示 SIP 响应代码的数值。  <br/> |
|**种类** <br/> |int  <br/> || 响应代码的常规分类。 分类包括： <br/>  1-信息答复 <br/>  2-成功的答复 <br/>  3-重定向答复 <br/>  4-客户端故障响应 <br/>  5--服务器故障响应 <br/>  6-全球故障响应 <br/> |
|**说明** <br/> |nvarchar(256)  <br/> ||SIP 响应代码的说明。 例如，响应代码181具有以下说明：  <br/> 正在转发呼叫  <br/> |
   

