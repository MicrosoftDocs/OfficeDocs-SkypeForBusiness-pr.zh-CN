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
ms.openlocfilehash: ab3e5f1d15b32e866a0a8a99f54ce8a1b3d81a42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830342"
---
# <a name="certificate-request-certificate-authority-account"></a>证书请求（证书颁发机构帐户）
 
为了提交请求，证书颁发机构 (CA) 可能需要与当前登录的用户身份不同的凭据。 若要以其他用户身份允许证书请求，请选中"为证书颁发机构指定备用凭据"复选框，然后键入可以请求证书的用户的用户名或 \  域用户名。 在“密码”文本框中，键入指定用户的密码。 然后，用户名和密码将作为证书请求过程的一部分发送到联机 CA，但并不包含在实际证书请求中。
  

