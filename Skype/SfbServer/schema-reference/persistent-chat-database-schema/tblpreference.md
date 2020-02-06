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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814550"
---
# <a name="tblpreference"></a>tblPreference

tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。

**多**


| **列**            | **类型**                        | **说明**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar （255），not null  <br/> | 标签，格式如下： \<用户 sip uri\>                   |
| prefSeqID  <br/>      | int，not null  <br/>            | 用于进行版本控制的序列号（每个标签）。  <br/> |
| prefContent  <br/>    | nvarchar （max）  <br/>           | 编码内容。  <br/>                                         |
| lastModifiedBy  <br/> | int，not null  <br/>            | 已更新首选项的主体的 ID。  <br/>         |

**Key**

|**列**|**说明**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |主键。  <br/> |


