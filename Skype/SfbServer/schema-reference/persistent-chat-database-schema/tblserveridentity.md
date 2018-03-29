---
title: tblServerIdentity
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|serverID  <br/> |int，不为空  <br/> |服务器 id。 从中央管理存储对应的实例 ID。  <br/> |
|serverAddress  <br/> |nvarchar (256) 不为空  <br/> |使用窗口通信基础地址的服务器地址。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |最晚的时间通道服务器更新该行，以便使它运行的证据。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|serverID  <br/> |为主键。  <br/> |
   

