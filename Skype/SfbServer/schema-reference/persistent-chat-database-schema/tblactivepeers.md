---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间当前对等连接。
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929873"
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
   

