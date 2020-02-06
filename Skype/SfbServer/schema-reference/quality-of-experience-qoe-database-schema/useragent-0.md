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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 视图存储有关在数据库中具有记录的会话中涉及的用户代理的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805080"
---
# <a name="useragent-view"></a>UserAgent 视图
 
UserAgent 视图存储有关在数据库中具有记录的会话中涉及的用户代理的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |标识此用户代理的唯一号码。  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |用户代理字符串。  <br/> |
|UAType  <br/> |smallint  <br/> |用户代理的类型。 有关详细信息，请参阅[UserAgent 表](useragent.md)。 <br/> |
|UACategory  <br/> |nvarchar （64）  <br/> |用户代理所属的类别。 例如，Conferencing_Attendant_1 .0 的用户代理属于 UACategory CAA。  <br/> |
   

