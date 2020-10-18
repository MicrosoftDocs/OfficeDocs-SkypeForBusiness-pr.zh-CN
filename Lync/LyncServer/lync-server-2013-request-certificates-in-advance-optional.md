---
title: 'Lync Server 2013：提前请求证书 (可选) '
description: Lync Server 2013：提前请求证书 (可选) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92ac9b68012487d07f25f08649689611117202
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579028"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="bad0d-103"> (Lync Server 2013 的可选) 提前请求证书</span><span class="sxs-lookup"><span data-stu-id="bad0d-103">Request certificates in advance (optional) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bad0d-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bad0d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bad0d-105">所有运行 Lync Server 2013 的内部服务器都需要证书，包括每个 Enterprise Edition 前端服务器、Standard Edition server、Director、Edge 服务器和独立中介服务器。</span><span class="sxs-lookup"><span data-stu-id="bad0d-105">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="bad0d-106">虽然建议对内部服务器使用内部企业证书颁发机构 (CA)，但您也可以使用公共 CA。</span><span class="sxs-lookup"><span data-stu-id="bad0d-106">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="bad0d-107">有关证书要求和公用 CA 使用的详细信息，请参阅规划文档中的 [Lync Server 2013 中的内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md) 。</span><span class="sxs-lookup"><span data-stu-id="bad0d-107">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="bad0d-108">Lync Server 2013 安装程序包括证书向导，该向导可促进在部署过程中请求、分配和安装证书的任务。</span><span class="sxs-lookup"><span data-stu-id="bad0d-108">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="bad0d-109">如果要在安装服务器之前请求证书 (例如，为了在服务器的实际部署) 中节省时间，您可以通过使用安装了 Lync Server 2013 管理工具的计算机或使用组织中定义的证书请求过程来执行此操作，前提是确保证书是可导出的并包含所有必需的主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="bad0d-109">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="bad0d-110">提前请求证书是可选的。</span><span class="sxs-lookup"><span data-stu-id="bad0d-110">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="bad0d-111">如果你未提前请求，则必须将其作为需要证书的每个服务器的安装程序的一部分进行请求。</span><span class="sxs-lookup"><span data-stu-id="bad0d-111">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="bad0d-112">此部署文档提供了使用证书向导作为安装过程的一部分请求证书的过程，如在 lync server [2013 中配置服务器的证书](lync-server-2013-configure-certificates-for-servers.md)、 [在 lync server 2013 中为控制器配置证书](lync-server-2013-configure-certificates-for-the-director.md)以及在此部署文档的 [Lync Server 2013 部分中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md) 中所述。</span><span class="sxs-lookup"><span data-stu-id="bad0d-112">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="bad0d-113">如果提前请求证书，则必须适当修改上述各节中的证书部署过程，以导入和分配证书，而不是在部署时请求证书。</span><span class="sxs-lookup"><span data-stu-id="bad0d-113">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bad0d-114">Lync Server 2013 支持从运行 Windows Vista、Windows Server &nbsp; 2008、Windows server 2008 R2 和 Windows 7 操作系统的客户端连接到 SHA-256 证书， &nbsp; &nbsp; 以及 lync Phone Edition。</span><span class="sxs-lookup"><span data-stu-id="bad0d-114">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="bad0d-115">要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。</span><span class="sxs-lookup"><span data-stu-id="bad0d-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

