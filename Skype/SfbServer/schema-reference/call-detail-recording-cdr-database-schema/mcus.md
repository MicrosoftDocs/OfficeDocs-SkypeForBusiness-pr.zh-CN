---
title: Skype for Business Server 2015 中的 Mcus 表
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 表是一个支持表。 每条记录都存储有关一个会议服务的信息。 其中包括 IM 会议服务和电话会议服务 (这些服务在前端服务器) 以及 Web 会议服务和 A/V 会议服务上作为进程运行。
ms.openlocfilehash: abbbe20d6b247b23f0042dcc3bf552dd4a1362f1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846305"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 Mcus 表
 
Mcus 表是一个支持表。 每条记录都存储有关一个会议服务的信息。 其中包括 IM 会议服务和电话会议服务 (这些服务在前端服务器) 以及 Web 会议服务和 A/V 会议服务上作为进程运行。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |主  <br/> |标识此会议服务器的唯一编号。  <br/> |
|**McuUri** <br/> |nvarchar (450)   <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Foreign <br/> |会议服务器类型，例如 conf：chat (，) conf：audio-video。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
   

