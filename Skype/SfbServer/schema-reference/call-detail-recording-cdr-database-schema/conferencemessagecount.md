---
title: ConferenceMessageCount 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每条记录代表一个 IM 会议中的一个用户，并包含该用户发送的消息数。 此表; 中的多个记录由表示每个会议每个用户的的一个记录。
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874355"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>ConferenceMessageCount 表中的业务服务器 2015 Skype
 
此表中的每条记录代表一个 IM 会议中的一个用户，并包含该用户发送的消息数。 此表; 中的多个记录由表示每个会议每个用户的的一个记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会议实例的时间。 与**SessionIdSeq**结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |若要确定会议实例的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**用户 Id** <br/> |int  <br/> |外  <br/> |标识此用户从[Users table](users.md)引用的唯一编号。  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |在此会议期间发送的此用户的消息数。  <br/> |
   

