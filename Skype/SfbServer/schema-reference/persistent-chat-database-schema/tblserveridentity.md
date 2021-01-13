---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831492"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|serverID  <br/> |int，不为 null  <br/> |服务器 ID。 对应于中央管理存储中的实例 ID。  <br/> |
|serverAddress  <br/> |nvarchar (256)，不为 null  <br/> |使用 Windows Communication Foundation 地址的服务器地址。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |通道服务器更新此行以表明服务器正在运行的最新时间。  <br/> |
   
**注册表项**

|**列**|**说明**|
|:-----|:-----|
|serverID  <br/> |主键。  <br/> |
   

