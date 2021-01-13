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
# <a name="certificate-request-certificate-authority-account"></a><span data-ttu-id="d02ac-103">证书请求（证书颁发机构帐户）</span><span class="sxs-lookup"><span data-stu-id="d02ac-103">Certificate Request (Certificate Authority Account)</span></span>
 
<span data-ttu-id="d02ac-104">为了提交请求，证书颁发机构 (CA) 可能需要与当前登录的用户身份不同的凭据。</span><span class="sxs-lookup"><span data-stu-id="d02ac-104">To submit a request, your certification authority (CA) may require credentials other than the ones for the user that you are currently logged in as.</span></span> <span data-ttu-id="d02ac-105">若要以其他用户身份允许证书请求，请选中"为证书颁发机构指定备用凭据"复选框，然后键入可以请求证书的用户的用户名或 \  域用户名。</span><span class="sxs-lookup"><span data-stu-id="d02ac-105">To allow a certificate request as a different user, select the check box **Specify alternate credentials for the certification authority**, and then type the user name or  _domain_\ _username_ for a user who can request the certificate.</span></span> <span data-ttu-id="d02ac-106">在“密码”文本框中，键入指定用户的密码。</span><span class="sxs-lookup"><span data-stu-id="d02ac-106">In the **Password** text box, type the password for the user that you specified.</span></span> <span data-ttu-id="d02ac-107">然后，用户名和密码将作为证书请求过程的一部分发送到联机 CA，但并不包含在实际证书请求中。</span><span class="sxs-lookup"><span data-stu-id="d02ac-107">The user name and password are then sent as part of the certificate request process, but not in the actual certificate request, to an online CA.</span></span>
  

