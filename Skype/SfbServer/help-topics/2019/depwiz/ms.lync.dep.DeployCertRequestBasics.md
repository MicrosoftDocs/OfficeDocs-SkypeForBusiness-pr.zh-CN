---
title: 证书请求（基本）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: "\"名称和安全性 设置\"页提供了一个文本框来定义友好名称、一个私钥和公钥对的位长度下拉列表，以及一个允许您将证书的私钥标记为可导出的复选框。"
ms.openlocfilehash: 051c883525582559756a4c3ec3b03e921314e9ef
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591876"
---
# <a name="certificate-request-basic"></a>证书请求（基本）
 
"名称和安全性 **设置"** 页提供了一个文本框来定义"友好名称"、一个"私钥"和"公钥对的位长度"下拉列表，以及一个允许您将证书的私钥标记为可导出的 **复选框**。 
  
证书上的友好或简单名称是容易识别的名称，使查看证书的人员更容易识别它。
  
可供选择的私钥和公钥对的位长度为 1024、2048 或 4096。
  
选中" **将证书的** 私钥标记为可导出"复选框将允许导出证书和私钥，并移动到另一台计算机或服务器。 唯一需要这样做的时间是，为 MRAS (媒体中继身份验证服务创建边缘) 。
  
> [!CAUTION]
> 为了帮助维护证书和密钥对的安全性，应仅在绝对有必要时选择"将证书的私钥标记为可导出"选项。 
  

