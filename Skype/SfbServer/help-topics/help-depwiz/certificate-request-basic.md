---
title: 证书请求（基本）
ms.reviewer: ''
ms.author: v-cichur
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
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: "\"名称和安全设置\"页提供了用于定义友好名称的文本框、私钥和公钥对的位长度的下拉列表，以及允许您将证书的私钥标记为可导出的复选框。"
ms.openlocfilehash: f0d0339a483056276d400654f897b898b002cf03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805342"
---
# <a name="certificate-request-basic"></a>证书请求（基本）
 
"名称和安全设置"页提供了一个文本框来定义友好名称、私钥和公钥对的 **位** 长度的下拉列表，以及一个允许您将证书的私钥标记为可导出的 **复选框**。
  
证书上的友好或简单名称是容易识别的名称，使查看证书的人员更容易识别它。
  
可供选择的私钥和公钥对的位长度为 1024、2048 或 4096。
  
选中"将证书的私钥标记为可导出"复选框将允许导出证书和私钥，并移动到其他计算机或服务器。 唯一需要这样做的时间是在为 MRAS 服务中的媒体中继身份验证服务创建边缘 (池) 。
  
> [!CAUTION]
> 为了帮助维护证书和密钥对的安全性，应仅在绝对有必要时选择将证书的私钥标记为可导出选项。 
  

