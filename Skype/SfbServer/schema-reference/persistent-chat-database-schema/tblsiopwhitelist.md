---
title: tblSiopWhiteList
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
ms.localizationpriority: medium
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可与节点关联的注册外接程序的列表。
ms.openlocfilehash: 78cc98f584f20d3a08e9ed750ed9ac406f7e5780
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613822"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList 是可与节点关联的注册外接程序的列表。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID，不为 null  <br/> |外接程序的 GUID。  <br/> |
|siopName  <br/> |nvarchar (50)，不为 null  <br/> |外接程序的显示名称。  <br/> |
|siopUrl  <br/> |nvarchar (255)，不为 null  <br/> |外接程序的 URL。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|siopID  <br/> |主键。  <br/> |
   

