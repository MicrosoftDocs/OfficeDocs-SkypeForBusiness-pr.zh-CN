---
title: tblActivePeers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间当前对等连接。
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884165"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers 包含聊天服务之间当前对等连接。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int，不为 null  <br/> |发布条目的服务器的 ID。  <br/> |
|aplPeerID  <br/> |int，不为 null  <br/> |发布服务器连接到的对等方的 ID。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<aplServerID aplPeerID\>  <br/> |主键。  <br/> |
|aplServerID  <br/> |包含在 tblServerIdentity.serverID 表中查找的外键。  <br/> |
|aplPeerID  <br/> |包含在 tblServerIdentity.serverID 表中查找的外键。  <br/> |
   

