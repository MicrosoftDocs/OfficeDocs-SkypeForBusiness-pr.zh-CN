---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间的当前对等连接。
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers 包含聊天服务之间的当前对等连接。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int，不为空  <br/> |过帐此项的服务器的 ID。  <br/> |
|aplPeerID  <br/> |int，不为空  <br/> |连接到发布服务器的对等方的 ID。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<aplServerID aplPeerID\>  <br/> |为主键。  <br/> |
|aplServerID  <br/> |TblServerIdentity.serverID 表中查找与外键。  <br/> |
|aplPeerID  <br/> |TblServerIdentity.serverID 表中查找与外键。  <br/> |
   

