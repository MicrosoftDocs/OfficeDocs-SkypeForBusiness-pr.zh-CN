---
title: tblSiopWhiteList
ms.reviewer: ''
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可与节点关联的注册外接程序的列表。
ms.openlocfilehash: 43277bec50baa3224d52aa247e20d417104b16e6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398588"
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
   

