---
title: 证书请求（基本）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: "\"名称和安全设置\" 页面提供一个文本框，用于定义友好名称、用于私钥和公钥对的位长的下拉列表，以及使你能够将证书的专用密钥标记为可导出的复选框。"
ms.openlocfilehash: 26315f24dd14989bd2832d6f28e591a7ae38cc64
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796763"
---
# <a name="certificate-request-basic"></a>证书请求（基本）
 
"**名称和安全设置**" 页面提供一个文本框，用于定义**友好名称**、用于私钥和公钥对的**位长**的下拉列表，以及使你能够将**证书的专用密钥标记为可导出**的复选框。
  
证书上的友好或简单名称是容易识别的名称，使查看证书的人员更容易识别它。
  
可供选择的私钥和公钥对的位长度为 1024、2048 或 4096。
  
选中 "将**证书的私钥标记**为可导出" 复选框后，即可导出证书和私钥并将其移动到另一台计算机或服务器。 只有在为媒体中继身份验证服务 (MRAS) 创建边缘服务器池时，才需要选中此项。
  
> [!CAUTION]
> 若要帮助维护证书和密钥对的安全性，应选中 "将证书的私钥标记为可导出" 选项（仅当绝对必要时）。 
  

