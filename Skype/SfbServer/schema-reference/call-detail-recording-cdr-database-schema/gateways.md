---
title: Skype for Business Server 2015 中的 Gateways 表
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Gateways 表是一个支持表。 每条记录都存储有关在公用电话交换网中涉及的一个网关的信息 (数据库中具有记录的 PSTN) PSTN 呼叫。
ms.openlocfilehash: 62bbe3ab802736a50d1fb049a3585cba286ee7ec16907335aa831ab49259b0fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349664"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 Gateways 表
 
Gateways 表是一个支持表。 每条记录都存储有关在公用电话交换网中涉及的一个网关的信息 (数据库中具有记录的 PSTN) PSTN 呼叫。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |主  <br/> |标识此网关的唯一编号。  <br/> |
|**网关** <br/> |nvarchar (256)   <br/> | <br/> |网关名称。  <br/> |
   

