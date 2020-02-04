---
title: Lync Server 2013：验证地址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="26d13-102">在 Lync Server 2013 中验证地址</span><span class="sxs-lookup"><span data-stu-id="26d13-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d13-103">_**主题上次修改时间：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="26d13-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="26d13-104">在发布位置数据库之前，必须根据你的 SIP 主干或公共交换电话网络（PSTN） E9 服务提供商维护的主要街道地址指南（MSAG）验证新位置。</span><span class="sxs-lookup"><span data-stu-id="26d13-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="26d13-105">有关 SIP 中继 E9 服务提供商的详细信息，请参阅[为 Lync Server 2013 选择 E9 服务提供商](lync-server-2013-choosing-an-e9-1-1-service-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="26d13-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="26d13-106">有关验证地址的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="26d13-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="26d13-107">**CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="26d13-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="26d13-108">**Set-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="26d13-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="26d13-109">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="26d13-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="26d13-110">**CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="26d13-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="26d13-111">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="26d13-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="26d13-112">验证位于位置数据库中的地址</span><span class="sxs-lookup"><span data-stu-id="26d13-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="26d13-113">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="26d13-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="26d13-114">运行以下 cmdlet 配置紧急服务提供商连接。</span><span class="sxs-lookup"><span data-stu-id="26d13-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="26d13-115">运行以下 cmdlet 验证位置数据库中的地址。</span><span class="sxs-lookup"><span data-stu-id="26d13-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="26d13-116">还可以使用 **Test-CsLisCivicAddress** cmdlet 验证单个地址。</span><span class="sxs-lookup"><span data-stu-id="26d13-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

