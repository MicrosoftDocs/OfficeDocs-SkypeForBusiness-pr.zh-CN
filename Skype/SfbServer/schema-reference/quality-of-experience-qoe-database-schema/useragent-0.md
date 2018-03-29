---
title: 用户代理视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: 用户代理视图存储在数据库中具有记录的会话中涉及的用户代理信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 8df1d45ed1272a886a440aded79a9c4e04c1bae8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-view"></a>用户代理视图
 
用户代理视图存储在数据库中具有记录的会话中涉及的用户代理信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |标识此用户代理的唯一编号。  <br/> |
|用户代理  <br/> |nvarchar(256)  <br/> |用户代理字符串。  <br/> |
|UAType  <br/> |smallint  <br/> |用户代理的类型。 [用户代理表](useragent.md)的更多详细信息，请参阅。 <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |用户代理所属的类别。 例如，Conferencing_Attendant_1.0 的用户代理都属于 UACategory CAA。  <br/> |
   

