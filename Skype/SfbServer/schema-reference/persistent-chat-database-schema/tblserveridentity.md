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
ms.openlocfilehash: 092331f275ef76372ad1bd2d2462acb9eb7848eea263d59c2276d7a4b6a83779
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303655"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|serverID  <br/> |int，不为 null  <br/> |服务器 ID。 对应于中央管理存储中的实例 ID。  <br/> |
|serverAddress  <br/> |nvarchar (256)，不为 null  <br/> |使用 Windows Communication Foundation 地址的服务器地址。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |通道服务器更新此行以表明服务器正在运行的最新时间。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|serverID  <br/> |主键。  <br/> |
   

