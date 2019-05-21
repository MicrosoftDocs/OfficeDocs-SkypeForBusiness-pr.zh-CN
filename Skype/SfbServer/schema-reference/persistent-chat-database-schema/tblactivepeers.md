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
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间的当前点对点连接。
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295543"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers 包含聊天服务之间的当前点对点连接。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, not null  <br/> |已发布条目的服务器的 ID。  <br/> |
|aplPeerID  <br/> |int, not null  <br/> |过帐服务器连接到的对等的 ID。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |主键。  <br/> |
|aplServerID  <br/> |TblServerIdentity 表中的 lookup 的外键。  <br/> |
|aplPeerID  <br/> |TblServerIdentity 表中的 lookup 的外键。  <br/> |
   

