---
title: Skype for Business Server 2015 中的位置表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每条记录均表示紧急呼叫（例如 E9-1-1 呼叫）中的一个位置引用。
ms.openlocfilehash: 7a14e44e5514944c69f751e21ed055a9ab1fa114
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746548"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的位置表
 
每条记录均表示紧急呼叫（例如 E9-1-1 呼叫）中的一个位置引用。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会话请求的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**位置** <br/> |nvarchar (max)   <br/> ||紧急呼叫的位置。  <br/> |
   

