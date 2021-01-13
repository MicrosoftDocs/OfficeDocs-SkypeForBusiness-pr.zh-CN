---
title: UserAgent 视图
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 视图会存储有关在数据库中含有记录的会话中所涉及的用户代理的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800012"
---
# <a name="useragent-view"></a>UserAgent 视图
 
UserAgent 视图会存储有关在数据库中含有记录的会话中所涉及的用户代理的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**Details**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |标识此用户代理的唯一编号。  <br/> |
|UserAgent  <br/> |nvarchar (256)   <br/> |用户代理字符串。  <br/> |
|UAType  <br/> |smallint  <br/> |用户代理的类型。 有关详细信息， [请参阅 UserAgent](useragent.md) 表。 <br/> |
|UACategory  <br/> |nvarchar (64)   <br/> |用户代理所属的类别。例如，用户代理 Conferencing_Attendant_1.0 属于 UACategory CAA。  <br/> |
   

