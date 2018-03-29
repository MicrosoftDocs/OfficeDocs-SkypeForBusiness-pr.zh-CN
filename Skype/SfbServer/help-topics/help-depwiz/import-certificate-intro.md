---
title: 导入证书 （简介）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: 导入证书，您必须提供的证书文件的路径。 在选择证书文件文本框中，您可以键入完整路径和文件名，或单击浏览按钮，导航到的路径位置和文件名 （通常.p7b、.pfx 或.cer 文件）。
ms.openlocfilehash: f83f42bbd8515ae20510d8253b560a93070e9ed6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="import-certificate-intro"></a><span data-ttu-id="7dbd7-104">导入证书 （简介）</span><span class="sxs-lookup"><span data-stu-id="7dbd7-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="7dbd7-105">导入证书，您必须提供的证书文件的路径。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-105">To import a certificate, you must provide a path to the certificate file.</span></span> <span data-ttu-id="7dbd7-106">在**选择证书文件**文本框中，您可以键入完整路径和文件名，或单击**浏览**按钮，导航到的路径位置和文件名 （通常.p7b、.pfx 或.cer 文件）。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-106">In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="7dbd7-107">如果证书包含私钥，请选择**证书文件包含证书的专用密钥**。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="7dbd7-108">选中此复选框后，将启用**密码**文本输入。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="7dbd7-109">如果您有与它相关联的私钥的证书，密码通常放置在私钥创建证书时。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="7dbd7-110">您输入的密码允许证书的专用密钥和私钥导入到证书存储区。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="7dbd7-111">当您提供了信息的证书的文件路径，和私钥密码 （可选） 如果需要，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7dbd7-112">如果您不知道的私钥的密码，则导入将失败。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

