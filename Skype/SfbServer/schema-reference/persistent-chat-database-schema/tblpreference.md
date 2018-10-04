---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常使用 Lync 2013 之前的客户端。
ms.openlocfilehash: c76c62ec453ab1a152738cb16d76e5c5394a2a98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375941"
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


