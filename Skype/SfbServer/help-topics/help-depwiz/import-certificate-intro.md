---
title: 导入证书（简介）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 要导入证书，必须提供证书文件的路径。 在“选择证书文件”文本框中，可以键入完整路径和文件名，也可以单击“浏览”按钮并导航到相应的路径位置和文件名（通常为 .p7b、.pfx 或 .cer 文件）。
ms.openlocfilehash: 2ca89291376c488426001e1ff42c4925da58a3e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827282"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="d15b8-104">导入证书（简介）</span><span class="sxs-lookup"><span data-stu-id="d15b8-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="d15b8-p102">要导入证书，必须提供证书文件的路径。在 **“选择证书文件”** 文本框中，可以键入完整路径和文件名，也可以单击 **“浏览”** 按钮并导航到相应的路径位置和文件名（通常为 .p7b、.pfx 或 .cer 文件）。</span><span class="sxs-lookup"><span data-stu-id="d15b8-p102">To import a certificate, you must provide a path to the certificate file. In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="d15b8-107">如果证书包含私钥，则选中复选框"证书文件 **"包含证书的私钥**。</span><span class="sxs-lookup"><span data-stu-id="d15b8-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="d15b8-108">选中此复选框后，会启用 **“密码”** 文本输入。</span><span class="sxs-lookup"><span data-stu-id="d15b8-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="d15b8-109">如果证书具有关联的私钥，则在创建该证书时，通常会针对私钥设置密码。</span><span class="sxs-lookup"><span data-stu-id="d15b8-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="d15b8-110">输入私钥的密码以允许将证书和私钥导入证书存储。</span><span class="sxs-lookup"><span data-stu-id="d15b8-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="d15b8-111">提供证书文件路径信息并根据需要提供私钥密码后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d15b8-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d15b8-112">如果不知道私钥的密码，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="d15b8-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

