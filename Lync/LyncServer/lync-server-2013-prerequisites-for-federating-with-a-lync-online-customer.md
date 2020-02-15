---
title: Lync Server 2013：与 Lync Online 客户联合的先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ad28107f31bf2593952ae8356ac2c9af2b4bc6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="1cf3a-102">在 Lync Server 2013 中与 Lync Online 客户进行联盟的先决条件</span><span class="sxs-lookup"><span data-stu-id="1cf3a-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cf3a-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1cf3a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1cf3a-104">若要与 Lync Online 2010 客户联合，您应已在您的组织中完成了 Lync Server 2013 的初始部署和配置。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="1cf3a-105">其中包括：</span><span class="sxs-lookup"><span data-stu-id="1cf3a-105">This includes the following:</span></span>

  - <span data-ttu-id="1cf3a-106">在您的组织中部署至少一个 Standard Edition server 或一个 Enterprise Edition 前端池。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="1cf3a-107">有关部署内部服务器的详细信息，请参阅部署文档中的[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="1cf3a-108">为 Lync Server 2013 启用内部用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="1cf3a-109">有关详细信息，请参阅部署文档或操作文档中的[禁用或重新启用 Lync Server 2013 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="1cf3a-110">至少部署一台边缘服务器以及支持外部用户访问所需的其他组件。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="1cf3a-111">有关详细信息，请参阅部署文档中的[管理对 Lync Server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="1cf3a-112">在您的组织中启用联盟支持并配置适当的方法来控制联合域进行的访问。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="1cf3a-113">有关详细信息，请参阅操作文档中的在 lync server [2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)和[管理您的2013组织的 SIP 联合提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="1cf3a-114">为您的组织中的用户启用外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="1cf3a-115">有关详细信息，请参阅在 Lync Server 2013 和部署文档或操作文档中[为启用 Lync 的用户分配外部用户访问策略](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf3a-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

