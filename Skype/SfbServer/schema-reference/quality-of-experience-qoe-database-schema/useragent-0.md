---
title: UserAgent 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 视图存储有关在数据库中具有记录的会话中涉及的用户代理的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294605"
---
# <a name="useragent-view"></a>UserAgent 视图
 
UserAgent 视图存储有关在数据库中具有记录的会话中涉及的用户代理的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |标识此用户代理的唯一号码。  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |用户代理字符串。  <br/> |
|UAType  <br/> |smallint  <br/> |用户代理的类型。 有关详细信息, 请参阅[UserAgent 表](useragent.md)。 <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |用户代理所属的类别。 例如, 用户代理 Conferencing_Attendant_ 1.0 属于 UACategory CAA。  <br/> |
   

