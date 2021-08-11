---
title: Skype for Business Server 2015 中的 ConferenceMessageCount 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每条记录表示一个 IM 会议中的一个用户，并包括该用户发送的消息数。 每个会议都由此表中的多个记录表示;每个用户一条记录。
ms.openlocfilehash: 7e713e6d2eb9f856ee039345a0ab2e920e5ee09778b80201c823b14fbc270009
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289500"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ConferenceMessageCount 表
 
此表中的每条记录表示一个 IM 会议中的一个用户，并包括该用户发送的消息数。 每个会议都由此表中的多个记录表示;每个用户一条记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会议实例的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会议实例的 ID 号。 与 **SessionIdTime 结合使用** 来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |标识此用户的唯一编号，从 Users 表 [引用](users.md)。  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |此用户在此会议期间发送的消息数。  <br/> |
   

