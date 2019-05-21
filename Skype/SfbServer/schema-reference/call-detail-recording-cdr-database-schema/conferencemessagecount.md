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
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每条记录表示一个 IM 会议中的一个用户, 包括该用户发送的消息数。 每个会议都由该表中的多条记录表示;每个用户一条记录。
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296453"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ConferenceMessageCount 表
 
此表中的每条记录表示一个 IM 会议中的一个用户, 包括该用户发送的消息数。 每个会议都由该表中的多条记录表示;每个用户一条记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会议实例的时间。 与**SessionIdSeq**结合使用以唯一标识会议实例。 有关详细信息, 请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会议实例的 ID 号。 与**SessionIdTime**结合使用以唯一标识会议实例。 有关详细信息, 请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**UserId** <br/> |int  <br/> |外表  <br/> |标识此用户的唯一号码, 从 "[用户" 表](users.md)中引用。  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |此用户在此会议期间发送的消息数。  <br/> |
   

