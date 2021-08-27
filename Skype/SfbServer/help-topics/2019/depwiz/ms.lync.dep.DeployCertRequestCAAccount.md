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
ms.localizationpriority: medium
ms.assetid: 6251322d-ac36-4760-b467-bcd543af22aa
ROBOTS: NOINDEX, NOFOLLOW
description: 为了提交请求，证书颁发机构 (CA) 可能需要与当前登录的用户身份不同的凭据。
ms.openlocfilehash: 494ca750bf0ac6ba505f04c8c4ee594272c10670
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588934"
---
# <a name="certificate-request-certificate-authority-account"></a>证书请求（证书颁发机构帐户）
 
为了提交请求，证书颁发机构 (CA) 可能需要与当前登录的用户身份不同的凭据。 若要允许以其他用户身份请求证书，请选中"指定证书颁发机构的备用凭据"复选框，然后键入可以请求证书的用户的用户名或 \  域用户名。 在“密码”文本框中，键入指定用户的密码。 然后，用户名和密码将作为证书请求过程的一部分发送到联机 CA，但并不包含在实际证书请求中。
  

