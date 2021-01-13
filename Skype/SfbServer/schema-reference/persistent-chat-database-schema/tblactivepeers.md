---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间当前对等连接。
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812932"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers 包含聊天服务之间当前对等连接。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int，不为 null  <br/> |发布条目的服务器的 ID。  <br/> |
|aplPeerID  <br/> |int，不为 null  <br/> |发布服务器连接到的对等方的 ID。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |主键。  <br/> |
|aplServerID  <br/> |其查找包含在 tblServerIdentity.serverID 表中的外键。  <br/> |
|aplPeerID  <br/> |其查找包含在 tblServerIdentity.serverID 表中的外键。  <br/> |
   

