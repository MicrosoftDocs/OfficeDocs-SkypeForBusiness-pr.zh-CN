---
title: Skype for Business Server 2015 中的网关表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: 网关表是支持表。 每条记录存储有关一个网关的信息, 这些信息涉及到数据库中有记录的公共交换电话网络 (PSTN) 呼叫。
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296180"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的网关表
 
网关表是支持表。 每条记录存储有关一个网关的信息, 这些信息涉及到数据库中有记录的公共交换电话网络 (PSTN) 呼叫。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |标识此网关的唯一号码。  <br/> |
|**网关** <br/> |nvarchar(256)  <br/> | <br/> |网关名称。  <br/> |
   

