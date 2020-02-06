---
title: 导入证书（简介）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: 若要导入证书，必须提供证书文件的路径。 在 "选择证书文件" 文本框中，你可以键入完整路径和文件名，或单击 "浏览" 按钮并导航到路径位置和文件名（通常为. p7b、.pfx 或 .cer 文件）。
ms.openlocfilehash: 63420dad20e5174cb41f9fc00d63a1f7c25763a2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823666"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="61437-104">导入证书（简介）</span><span class="sxs-lookup"><span data-stu-id="61437-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="61437-105">若要导入证书，必须提供证书文件的路径。</span><span class="sxs-lookup"><span data-stu-id="61437-105">To import a certificate, you must provide a path to the certificate file.</span></span> <span data-ttu-id="61437-106">在 "**选择证书文件**" 文本框中，你可以键入完整路径和文件名，或单击 "**浏览**" 按钮并导航到路径位置和文件名（通常为. p7b、.pfx 或 .cer 文件）。</span><span class="sxs-lookup"><span data-stu-id="61437-106">In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="61437-107">如果证书包含私钥，请选中 "**证书文件包含证书的专用密钥**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="61437-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="61437-108">选中此复选框后，将启用**密码**文本输入。</span><span class="sxs-lookup"><span data-stu-id="61437-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="61437-109">如果你有一个与私钥相关联的证书，则在创建证书时，通常会在私钥上放置一个密码。</span><span class="sxs-lookup"><span data-stu-id="61437-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="61437-110">输入私钥的密码，以允许证书和私钥导入到证书存储。</span><span class="sxs-lookup"><span data-stu-id="61437-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="61437-111">如果您提供了证书文件路径的信息，并且有必要输入私钥密码，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="61437-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="61437-112">如果不知道私钥的密码，导入将失败。</span><span class="sxs-lookup"><span data-stu-id="61437-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

