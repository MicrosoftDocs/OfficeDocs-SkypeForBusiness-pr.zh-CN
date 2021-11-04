---
title: tblPreference
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。
ms.openlocfilehash: 24de89ff74da66023aeac696c7f3ae91fb9b98b1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768442"
---
# <a name="tblpreference"></a>tblPreference

tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。

**列**


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


