---
title: 证书列表
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: 若要分配证书，请从本地证书存储中选择证书。 单击“下一步”继续。
ms.openlocfilehash: 3b8f18c84bbd0b7efba201430255f057556268cf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235155"
---
# <a name="certificate-list"></a><span data-ttu-id="7b9c0-104">证书列表</span><span class="sxs-lookup"><span data-stu-id="7b9c0-104">Certificate List</span></span>
 
<span data-ttu-id="7b9c0-p102">若要分配证书，请从本地证书存储中选择证书。单击“**下一步**”继续。</span><span class="sxs-lookup"><span data-stu-id="7b9c0-p102">To assign a certificate, select a certificate from the local certificate store. Click **Next** to continue.</span></span>
  
<span data-ttu-id="7b9c0-p103">“**从本地证书存储中选择证书**”窗格中可供选择的证书是有效证书，可分配到您需要的证书用途。可通过单击“**查看证书详细信息**”按钮确认选择的证书是否正确。在“**详细信息**”选项卡上，可以查看证书上配置的使用者名称和使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="7b9c0-p103">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need. You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button. On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7b9c0-p104">选择窗格中可能不会列出任何证书。如果出现这种情况，通常原因是目标服务器上没有安装受信任根证书或中间证书颁发机构证书，以验证证书并维护证书创建的到证书颁发机构的信任链。要解决此问题，可请求并导入证书链，通常包括根证书颁发机构 (CA) 证书和任何中间 CA 证书以及颁发 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="7b9c0-p104">It is possible that no certificate will be listed in the selection pane. When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority. To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  

