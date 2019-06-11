---
title: 'Lync Server 2013: 查看证书报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>在 Lync Server 2013 中查看证书报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

"证书" 报告包含建议的 Lync Server 2013 部署中所需的所有证书。 适用于所输入的主题名称和主题备用名称的规划工具帐户。 未经编辑的默认文本可能会给负责请求和颁发证书的团队带来挑战。 证书信息还包含通常可以从何处颁发证书的信息。 如果基础结构中没有内部公钥基础结构 (PKI)，则可以通过公共证书提供商请求所有证书。 该报告中的“扩展密钥用法 (EKU)”和“分配给”字段非常有助于理解每个证书应有的用途和应处的位置。

![证书管理员报告](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "证书管理员报告")

仔细阅读并确保了解部署中每个证书的用法和用途。 如果对证书用途有疑问，请确定是何种服务器或服务在与何种对象通信。 Lync Server 2013 中的证书用于两个主要用途:

  - 相互传输层安全性 (MTLS) – 参与通信的每台计算机均需向另一台计算机出示证明其身份的证书，这称为服务器身份验证。所有计算机相互信任彼此的身份后，通信才会开始。

  - 加密 – 加密（安全套接字层 (SSL) 和传输层安全性 (TLS)）是帮助保护通信安全、确保隐私以及创建受信任通信与协作系统的重要途径。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中查看管理员报告](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

