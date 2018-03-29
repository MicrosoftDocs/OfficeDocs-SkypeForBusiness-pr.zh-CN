---
title: 在业务服务器 2015年的 Skype 的 ConferenceMessageCount 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每个记录表示一个用户在一个 IM 会议，包括由该用户发送的邮件数。 每个会议表示的多个记录表;每个用户的的一个记录。
ms.openlocfilehash: 6b9dfcf0743c03e69726bb501cc7a4a961bf5df8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 ConferenceMessageCount 表
 
此表中的每个记录表示一个用户在一个 IM 会议，包括由该用户发送的邮件数。 每个会议表示的多个记录表;每个用户的的一个记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主键和外  <br/> |会议实例的时间。 与**SessionIdSeq**配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |若要标识的会议实例的 ID 号。 与**SessionIdTime**配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**用户 Id** <br/> |int  <br/> |外  <br/> |标识该用户，从[用户表](users.md)中引用的唯一编号。  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |这次会议过程中由该用户发送的消息数。  <br/> |
   

