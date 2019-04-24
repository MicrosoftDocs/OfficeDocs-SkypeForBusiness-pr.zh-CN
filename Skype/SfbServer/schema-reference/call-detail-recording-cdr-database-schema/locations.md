---
title: Locations 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每条记录代表一个位置引用中将紧急呼叫，如 E9-1-1 呼叫。
ms.openlocfilehash: 180a094ef10cc54b4fd65a30adb0909789afa3d6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212999"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Locations 表中的业务服务器 2015 Skype
 
每条记录代表一个位置引用中将紧急呼叫，如 E9-1-1 呼叫。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**位置** <br/> |nvarchar(max)  <br/> ||紧急呼叫的位置。  <br/> |
   

