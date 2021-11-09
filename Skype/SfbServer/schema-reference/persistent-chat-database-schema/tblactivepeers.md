---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间当前对等连接。
ms.openlocfilehash: 980364d2483d4418177d5eaeceeb9a7ec884871d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852856"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers 包含聊天服务之间当前对等连接。
  
**列**

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
   

