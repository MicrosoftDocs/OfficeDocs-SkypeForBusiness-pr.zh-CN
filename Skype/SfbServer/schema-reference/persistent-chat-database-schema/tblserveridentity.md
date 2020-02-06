---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812270"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|serverID  <br/> |int，not null  <br/> |服务器 ID。 对应于中央管理存储中的实例 ID。  <br/> |
|serverAddress  <br/> |nvarchar （256），not null  <br/> |使用 Windows Communication Foundation 地址的服务器地址。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |频道服务器更新此行以提供它正在运行的证据的最新时间。  <br/> |
   
**Key**

|**列**|**说明**|
|:-----|:-----|
|serverID  <br/> |主键。  <br/> |
   

