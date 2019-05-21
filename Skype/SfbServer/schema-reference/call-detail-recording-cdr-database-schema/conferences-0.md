---
title: 会议视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: "\"会议\" 视图存储有关会议的信息。 此视图已在 Microsoft Lync Server 2013 中引入。"
ms.openlocfilehash: 2e49a60be1651c34fb874c62bbee8c993eb00983
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296460"
---
# <a name="conferences-view"></a>会议视图
 
"会议" 视图存储有关会议的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |会议的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |会议 URI 的类型。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**ConfInstance** <br/> |标识符  <br/> |用于定期会议。 定期会议的每个实例都具有相同的 ConferenceUri, 但具有不同的 ConfInstance。  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |会议的开始时间。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |会议的结束时间。  <br/> |
|**OrganizerUri** <br/> |nvarchar (450)  <br/> |组织会议的用户的 URI。  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |组织会议的用户的 URI 类型。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |组织会议的用户的租户。 有关详细信息, 请参阅[租户表](tenants.md)。 <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |托管会议的池的完全限定的域名。  <br/> |
|**旗** <br/> |smallint  <br/> |包含会议属性的位掩码。 可能的值：  <br/> 0X01-合成事务  <br/> |
   

