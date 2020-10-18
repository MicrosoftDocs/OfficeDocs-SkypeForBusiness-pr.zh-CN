---
title: Lync Server 2013：查看证书报告
description: Lync Server 2013：查看 "证书" 报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2133e2f70c78217788d84251c2035a9115bc3283
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578458"
---
# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="a90aa-103">在 Lync Server 2013 中查看证书报告</span><span class="sxs-lookup"><span data-stu-id="a90aa-103">Reviewing the Certificates Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a90aa-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a90aa-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a90aa-105">证书报告包含建议的 Lync Server 2013 部署中所需的所有证书。</span><span class="sxs-lookup"><span data-stu-id="a90aa-105">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="a90aa-106">规划工具适用于所输入的主题名称和使用者替代名称的帐户。</span><span class="sxs-lookup"><span data-stu-id="a90aa-106">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="a90aa-107">保留未编辑的默认文本可能代表负责请求和颁发证书的团队的潜在挑战。</span><span class="sxs-lookup"><span data-stu-id="a90aa-107">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="a90aa-108">证书信息还包含通常可以从何处颁发证书的信息。</span><span class="sxs-lookup"><span data-stu-id="a90aa-108">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="a90aa-109">如果基础结构中没有内部公钥基础结构 (PKI)，则可以通过公共证书提供商请求所有证书。</span><span class="sxs-lookup"><span data-stu-id="a90aa-109">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="a90aa-110">该报告中的“扩展密钥用法 (EKU)”和“分配给”字段非常有助于理解每个证书应有的用途和应处的位置。</span><span class="sxs-lookup"><span data-stu-id="a90aa-110">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="a90aa-111">![证书管理报告](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "证书管理报告")</span><span class="sxs-lookup"><span data-stu-id="a90aa-111">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="a90aa-112">仔细查看并确保了解部署中每个证书的用途和用途。</span><span class="sxs-lookup"><span data-stu-id="a90aa-112">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="a90aa-113">如果有关于证书用途的问题，请确定哪个服务器或服务正在与其通信。</span><span class="sxs-lookup"><span data-stu-id="a90aa-113">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="a90aa-114">Lync Server 2013 中的证书用于两个主要用途：</span><span class="sxs-lookup"><span data-stu-id="a90aa-114">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="a90aa-115">相互传输层安全性 (MTLS) –通信中涉及的计算机都提供了向另一台计算机证明身份的证书。</span><span class="sxs-lookup"><span data-stu-id="a90aa-115">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="a90aa-116">这称为 "服务器身份验证"。</span><span class="sxs-lookup"><span data-stu-id="a90aa-116">This is known as server authentication.</span></span> <span data-ttu-id="a90aa-117">只有在每台计算机信任另一台计算机的身份后，才能开始通信。</span><span class="sxs-lookup"><span data-stu-id="a90aa-117">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="a90aa-118">加密 – 加密（安全套接字层 (SSL) 和传输层安全性 (TLS)）是帮助保护通信安全、确保隐私以及创建受信任通信与协作系统的重要途径。</span><span class="sxs-lookup"><span data-stu-id="a90aa-118">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a90aa-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a90aa-119">See Also</span></span>


[<span data-ttu-id="a90aa-120">在 Lync Server 2013 中查看管理员报告</span><span class="sxs-lookup"><span data-stu-id="a90aa-120">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

