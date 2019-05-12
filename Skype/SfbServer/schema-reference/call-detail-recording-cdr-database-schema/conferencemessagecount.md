---
title: ConferenceMessageCount 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每条记录代表一个 IM 会议中的一个用户，并包含该用户发送的消息数。 此表; 中的多个记录由表示每个会议每个用户的的一个记录。
ms.openlocfilehash: f45de53333b23368351c8c5330b474cd3260192b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901427"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>ConferenceMessageCount 表中的业务服务器 2015 Skype
 
此表中的每条记录代表一个 IM 会议中的一个用户，并包含该用户发送的消息数。 此表; 中的多个记录由表示每个会议每个用户的的一个记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会议实例的时间。 与**SessionIdSeq**结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |若要确定会议实例的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**用户 Id** <br/> |int  <br/> |外  <br/> |标识此用户从[Users table](users.md)引用的唯一编号。  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |在此会议期间发送的此用户的消息数。  <br/> |
   

