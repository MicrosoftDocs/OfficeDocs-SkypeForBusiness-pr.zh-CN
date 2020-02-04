---
title: Lync Server 2013：提前请求证书（可选）
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
ms.openlocfilehash: 7ee4598f35bb607a9262bfeb7931e2c88e27920c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="b80f3-102">为 Lync Server 2013 提前请求证书（可选）</span><span class="sxs-lookup"><span data-stu-id="b80f3-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b80f3-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b80f3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b80f3-104">所有运行 Lync Server 2013 的内部服务器都需要证书，包括每个企业版前端服务器、标准版服务器、Director、Edge 服务器和独立中介服务器。</span><span class="sxs-lookup"><span data-stu-id="b80f3-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="b80f3-105">虽然建议内部服务器使用内部企业证书颁发机构（CA），但您也可以使用公共 CA。</span><span class="sxs-lookup"><span data-stu-id="b80f3-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="b80f3-106">有关证书要求和公用 CA 使用的详细信息，请参阅规划文档中的[Lync Server 2013 内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="b80f3-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="b80f3-107">Lync Server 2013 安装程序包括证书向导，该向导有助于在部署期间请求、分配和安装证书的任务。</span><span class="sxs-lookup"><span data-stu-id="b80f3-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="b80f3-108">如果要在安装服务器之前请求证书（例如，为了在服务器的实际部署期间节省时间），可以通过使用安装了 Lync Server 2013 管理工具的计算机或使用证书请求来执行此操作。在您的组织中定义的过程，只要您确保证书是可导出的并包含所有必需的主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="b80f3-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="b80f3-109">预先申请证书是可选的。</span><span class="sxs-lookup"><span data-stu-id="b80f3-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="b80f3-110">如果不提前请求，则必须将其作为需要证书的每台服务器的设置的一部分进行请求。</span><span class="sxs-lookup"><span data-stu-id="b80f3-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="b80f3-111">此部署文档提供使用证书向导作为安装过程的一部分请求证书的过程，如 "在 lync server [2013 中配置服务器的证书](lync-server-2013-configure-certificates-for-servers.md)" 中所述，在[lync server 2013 中配置 Director 的证书](lync-server-2013-configure-certificates-for-the-director.md)，并在此部署文档的[Lync Server 2013 部分中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="b80f3-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="b80f3-112">如果提前申请证书，则必须根据需要在这些分区中修改证书部署过程，以便导入和分配证书，而不是在部署时请求证书。</span><span class="sxs-lookup"><span data-stu-id="b80f3-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b80f3-113">Lync Server 2013 包括对从运行 Windows Vista、Windows Server&nbsp;2008、windows server&nbsp;2008&nbsp;R2 和 Windows 7 操作系统以及 Lync Phone Edition 的客户端的连接的 SHA-256 证书的支持。</span><span class="sxs-lookup"><span data-stu-id="b80f3-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="b80f3-114">若要支持使用 SHA-256 的外部访问，外部证书由使用 SHA-256 的公共 CA 颁发。</span><span class="sxs-lookup"><span data-stu-id="b80f3-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

