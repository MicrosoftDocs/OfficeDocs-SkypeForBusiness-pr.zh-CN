---
title: UserAgent 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 视图会存储有关在数据库中含有记录的会话中所涉及的用户代理的信息。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 22dcd5e127e123e027448ccddaa79007cfdbfe8d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420815"
---
# <a name="useragent-view"></a>UserAgent 视图
 
UserAgent 视图会存储有关在数据库中含有记录的会话中所涉及的用户代理的信息。 此视图在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |标识此用户代理的唯一编号。  <br/> |
|UserAgent  <br/> |nvarchar (256)   <br/> |用户代理字符串。  <br/> |
|UAType  <br/> |smallint  <br/> |用户代理的类型。 有关详细信息， [请参阅 UserAgent](useragent.md) 表。 <br/> |
|UACategory  <br/> |nvarchar (64)   <br/> |用户代理所属的类别。例如，用户代理 Conferencing_Attendant_1.0 属于 UACategory CAA。  <br/> |
   

