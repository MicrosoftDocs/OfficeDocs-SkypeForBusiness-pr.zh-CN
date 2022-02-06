---
title: ClientVersions 视图
ms.reviewer: null
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储已参与数据库中记录的会话的各种客户端类型和版本的相关信息。 视图中的每条记录都代表一个客户端版本。 此视图在 Microsoft Lync Server 2013 中引入。
---

# <a name="clientversions-view"></a>ClientVersions 视图
 
ClientVersions 视图存储已参与数据库中记录的会话的各种客户端类型和版本的相关信息。 视图中的每条记录都代表一个客户端版本。 此视图在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> 某些列可能有多条记录。 
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |标识此客户端类型和版本的唯一编号。  <br/> |
|**版本** <br/> |nvarchar (256)   <br/> |代表用户代理。  <br/> |
|**ClientType** <br/> |int  <br/> |客户端类型。  <br/> |
|**ClientCategory** <br/> |nvarchar (64)   <br/> |客户端所属的类别。例如，客户端 Conferencing_Attendant_1.0 属于 ClientCategory CAA。  <br/> |
   

