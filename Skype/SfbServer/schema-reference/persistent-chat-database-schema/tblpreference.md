---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。
ms.openlocfilehash: 698976f3f98b939578787a0f8a2c0aeb8167888ad09ea20a09d0d7e4d83e900c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315428"
---
# <a name="tblpreference"></a>tblPreference

tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。

**Columns**


| **列**            | **类型**                        | **说明**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255)，不为 null  <br/> | 带如下格式的标签： \<user sip uri\>                   |
| prefSeqID  <br/>      | int，不为 null  <br/>            | 出于版本 (，每个标签) 一个数字。  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | 编码的内容。  <br/>                                         |
| lastModifiedBy  <br/> | int，不为 null  <br/>            | 更新首选项的主体的 ID。  <br/>         |

**键**

|**列**|**说明**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |主键。  <br/> |


