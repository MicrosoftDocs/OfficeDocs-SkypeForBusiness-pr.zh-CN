---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常使用 Lync 2013 之前的客户端。
ms.openlocfilehash: 1c8b098d308802428dcb314d2163b9e32863b547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929915"
---
# <a name="tblpreference"></a>tblPreference

tblPreference 包含用户的客户端首选项。 这通常使用 Lync 2013 之前的客户端。

**列**


| **列**            | **类型**                        | **说明**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255)，不为 null  <br/> | 如标签格式：\<用户 sip uri\>                   |
| prefSeqID  <br/>      | int，不为 null  <br/>            | 序列号 （每标签） 用于版本控制。  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | 编码的内容。  <br/>                                         |
| lastModifiedBy  <br/> | int，不为 null  <br/>            | 更新首选项的主体的 ID。  <br/>         |

**关键字**

|**列**|**说明**|
|:-----|:-----|
|\<prefLabel prefSeqID\>  <br/> |主键。  <br/> |


