---
title: 证书请求（基本）
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: "\"名称和安全 设置\"页提供了一个文本框来定义\"友好名称\"、一个\"私钥\"和\"公钥对的位长度\"下拉列表，以及一个允许您将证书的私钥标记为可导出的复选框。"
ms.openlocfilehash: 445a71c4655a8325de85165f1970b85fc536dff9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764270"
---
# <a name="certificate-request-basic"></a>证书请求（基本）
 
名称和安全性 **设置** 页面提供了一个文本框来定义友好名称、一个私钥和公钥对的位长度的下拉列表，以及一个允许您将证书的私钥标记为可导出的 **复选框**。
  
证书上的友好或简单名称是容易识别的名称，使查看证书的人员更容易识别它。
  
可供选择的私钥和公钥对的位长度为 1024、2048 或 4096。
  
选中" **将证书的** 私钥标记为可导出"复选框将允许导出证书和私钥，并移动到另一台计算机或服务器。 唯一需要这样做的时间是在为 MRAS 中为媒体中继身份验证服务创建边缘 (池) 。
  
> [!CAUTION]
> 为了帮助维护证书和密钥对的安全性，应仅在绝对有必要时选择"将证书的私钥标记为可导出"选项。 
  

