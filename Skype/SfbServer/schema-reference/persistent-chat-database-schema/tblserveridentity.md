---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
ms.openlocfilehash: 65c9106584d6159421964da0329563cd263281ed
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768430"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|serverID  <br/> |int，不为 null  <br/> |服务器 ID。 对应于中央管理存储中的实例 ID。  <br/> |
|serverAddress  <br/> |nvarchar (256)，不为 null  <br/> |使用 Windows Communication Foundation 地址的服务器地址。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |通道服务器更新此行以表明服务器正在运行的最新时间。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|serverID  <br/> |主键。  <br/> |
   

