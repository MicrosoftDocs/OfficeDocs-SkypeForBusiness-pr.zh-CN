---
title: Lync Server 2013：与 Lync Online 客户进行联盟的先决条件
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
ms.openlocfilehash: 337189476cf7c2767b359086014944715afbd623
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="037a6-102">在 Lync Server 2013 中与 Lync Online 客户进行联盟的先决条件</span><span class="sxs-lookup"><span data-stu-id="037a6-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="037a6-103">_**主题上次修改时间：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="037a6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="037a6-104">若要与 Lync Online 2010 客户联盟，你应该已经完成了你的组织中 Lync Server 2013 的初始部署和配置。</span><span class="sxs-lookup"><span data-stu-id="037a6-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="037a6-105">这包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="037a6-105">This includes the following:</span></span>

  - <span data-ttu-id="037a6-106">在您的组织中部署至少一个标准版服务器或一个企业版前端池。</span><span class="sxs-lookup"><span data-stu-id="037a6-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="037a6-107">有关部署内部服务器的详细信息，请参阅部署文档中的 "[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) "。</span><span class="sxs-lookup"><span data-stu-id="037a6-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="037a6-108">为 Lync Server 2013 启用内部用户帐户。</span><span class="sxs-lookup"><span data-stu-id="037a6-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="037a6-109">有关详细信息，请参阅在部署文档或操作文档中[禁用或重新启用 Lync Server 2013 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="037a6-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="037a6-110">至少部署一个 Edge 服务器和支持外部用户访问所需的其他组件。</span><span class="sxs-lookup"><span data-stu-id="037a6-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="037a6-111">有关详细信息，请参阅在部署文档中[管理 Lync Server 2013 的联合身份验证和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="037a6-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="037a6-112">在你的组织中启用联合身份验证支持并配置适当的方法来控制联盟域的访问。</span><span class="sxs-lookup"><span data-stu-id="037a6-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="037a6-113">有关详细信息，请参阅在 lync server [2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)和在操作文档的[lync Server 2013 中管理组织的 SIP 联合提供商](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="037a6-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="037a6-114">为你的组织中的用户启用外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="037a6-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="037a6-115">有关详细信息，请参阅在 Lync Server 2013 和部署文档或操作文档[中将外部用户访问策略分配给启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="037a6-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

