---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295340"
---
# <a name="tblpreference"></a>tblPreference

tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。

**多**


| **列**            | **类型**                        | **说明**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), not null  <br/> | 标签, 格式如下: \<用户 sip uri\>                   |
| prefSeqID  <br/>      | int, not null  <br/>            | 用于进行版本控制的序列号 (每个标签)。  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | 编码内容。  <br/>                                         |
| lastModifiedBy  <br/> | int, not null  <br/>            | 已更新首选项的主体的 ID。  <br/>         |

**关键字**

|**列**|**说明**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |主键。  <br/> |


