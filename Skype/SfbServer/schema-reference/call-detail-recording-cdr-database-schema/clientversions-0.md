---
title: ClientVersions 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储有关各种客户端类型和已参与记录数据库中的会话的版本信息。 在视图中的每条记录代表一个客户端版本。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: cc4024a7e2644a177eb6962c8fdc7078fd6b397d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901520"
---
# <a name="clientversions-view"></a>ClientVersions 视图
 
ClientVersions 视图存储有关各种客户端类型和已参与记录数据库中的会话的版本信息。 在视图中的每条记录代表一个客户端版本。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
> [!NOTE]
> 可能有多个记录的某些列。 
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |标识此客户端类型和版本的唯一编号。  <br/> |
|**版本** <br/> |nvarchar(256)  <br/> |代表用户代理。  <br/> |
|**客户端类型** <br/> |int  <br/> |客户端类型。  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |客户端所属的类别。 例如，客户端 Conferencing_Attendant_1.0 所属 ClientCategory CAA。  <br/> |
   

