---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间的当前点对点连接。
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814710"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers 包含聊天服务之间的当前点对点连接。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int，not null  <br/> |已发布条目的服务器的 ID。  <br/> |
|aplPeerID  <br/> |int，not null  <br/> |过帐服务器连接到的对等的 ID。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |主键。  <br/> |
|aplServerID  <br/> |TblServerIdentity 表中的 lookup 的外键。  <br/> |
|aplPeerID  <br/> |TblServerIdentity 表中的 lookup 的外键。  <br/> |
   

