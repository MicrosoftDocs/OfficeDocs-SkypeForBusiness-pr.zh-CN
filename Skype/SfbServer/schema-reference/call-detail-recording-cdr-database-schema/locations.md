---
title: Locations 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每条记录代表一个位置引用中将紧急呼叫，如 E9-1-1 呼叫。
ms.openlocfilehash: 389aa56dfaf6d8b732692909ff3375a992b504b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930239"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Locations 表中的业务服务器 2015 Skype
 
每条记录代表一个位置引用中将紧急呼叫，如 E9-1-1 呼叫。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**位置** <br/> |nvarchar(max)  <br/> ||紧急呼叫的位置。  <br/> |
   

