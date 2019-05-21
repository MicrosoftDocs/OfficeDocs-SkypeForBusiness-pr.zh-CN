---
title: Skype for Business Server 2015 中的 "位置" 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每条记录代表紧急呼叫中的一个位置引用, 如 E9-1-1 通话。
ms.openlocfilehash: 28054419187b8f23348396f52ec147b06eee2136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296117"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 "位置" 表
 
每条记录代表紧急呼叫中的一个位置引用, 如 E9-1-1 通话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**位置** <br/> |nvarchar (max)  <br/> ||紧急电话的位置。  <br/> |
   

