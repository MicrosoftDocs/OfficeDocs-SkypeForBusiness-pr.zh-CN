---
title: 证书请求（证书颁发机构帐户）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCAAccount
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6251322d-ac36-4760-b467-bcd543af22aa
ROBOTS: NOINDEX, NOFOLLOW
description: 为了提交请求，证书颁发机构 (CA) 可能需要与当前登录的用户身份不同的凭据。
ms.openlocfilehash: f10871788dc70ee015db6243603d6b66aad593bcd1750a5ad694f7c9f4b85d33
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281175"
---
# <a name="certificate-request-certificate-authority-account"></a>证书请求（证书颁发机构帐户）
 
为了提交请求，证书颁发机构 (CA) 可能需要与当前登录的用户身份不同的凭据。 若要允许以其他用户身份请求证书，请选中"指定证书颁发机构的备用凭据"复选框，然后键入可以请求证书的用户的用户名或 \  域用户名。 在“密码”文本框中，键入指定用户的密码。 然后，用户名和密码将作为证书请求过程的一部分发送到联机 CA，但并不包含在实际证书请求中。
  

