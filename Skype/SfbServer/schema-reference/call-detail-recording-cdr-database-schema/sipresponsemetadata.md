---
title: SIPResponseMetaData 表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 响应代码的列表以及每种代码的分类和定义。在响应影响 SIP 设备和 SIP 通信会话的事件时生成这些代码；例如，当某个 SIP 设备发出请求，但服务器拒绝服从该请求时，将生成响应代码 403。
ms.openlocfilehash: acf2c3166628af3a4633e98713ca25a5ae703ff6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863389"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData 表
 
SIPResponseMetaDataTable 包含 SIP 响应代码的列表以及每种代码的分类和定义。在响应影响 SIP 设备和 SIP 通信会话的事件时生成这些代码；例如，当某个 SIP 设备发出请求，但服务器拒绝服从该请求时，将生成响应代码 403。
  
此表是在 2015 年 Skype for Business Server引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |主  <br/> |表示 SIP 响应代码的数字值。  <br/> |
|**类** <br/> |int  <br/> || 响应代码的常规分类。分类包括： <br/>  1 - 信息性响应 <br/>  2 - 成功响应 <br/>  3 - 重定向响应 <br/>  4 - 客户端故障响应 <br/>  5 -- 服务器故障响应 <br/>  6 - 全局故障响应 <br/> |
|**说明** <br/> |nvarchar (256)   <br/> ||SIP 响应代码的说明。例如，响应代码 181 的说明如下：  <br/> Call Is Being Forwarded  <br/> |
   

