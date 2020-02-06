---
title: Skype for Business Server 2015 中的 ConferenceMessageCount 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每条记录表示一个 IM 会议中的一个用户，包括该用户发送的消息数。 每个会议都由该表中的多条记录表示;每个用户一条记录。
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815370"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ConferenceMessageCount 表
 
此表中的每条记录表示一个 IM 会议中的一个用户，包括该用户发送的消息数。 每个会议都由该表中的多条记录表示;每个用户一条记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会议实例的时间。 与**SessionIdSeq**结合使用以唯一标识会议实例。 有关详细信息，请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会议实例的 ID 号。 与**SessionIdTime**结合使用以唯一标识会议实例。 有关详细信息，请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**UserId** <br/> |int  <br/> |外表  <br/> |标识此用户的唯一号码，从 "[用户" 表](users.md)中引用。  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |此用户在此会议期间发送的消息数。  <br/> |
   

