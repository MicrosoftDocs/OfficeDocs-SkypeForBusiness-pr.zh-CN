---
title: UserAgent 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 视图存储有关数据库中包含记录的会话中涉及的用户代理的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: c63873f219f5d741925339f52f949be55fc64411
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875002"
---
# <a name="useragent-view"></a>UserAgent 视图
 
UserAgent 视图存储有关数据库中包含记录的会话中涉及的用户代理的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |标识此用户代理的唯一编号。  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |用户代理字符串。  <br/> |
|UAType  <br/> |smallint  <br/> |用户代理的类型。 请参阅[UserAgent 表](useragent.md)的详细信息。 <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |用户代理所属的类别。 例如，用户代理 Conferencing_Attendant_1.0 所属 UACategory CAA。  <br/> |
   

