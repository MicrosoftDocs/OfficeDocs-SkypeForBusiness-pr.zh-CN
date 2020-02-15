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
ms.openlocfilehash: 75eeabe640c9d66c897d59f4e06bb485a482ed04
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="d5dd1-102">在 Lync Server 2013 中验证地址</span><span class="sxs-lookup"><span data-stu-id="d5dd1-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5dd1-103">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="d5dd1-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="d5dd1-104">在发布位置数据库之前，必须根据您的 SIP 中继或公用电话交换网（PSTN） E9-1-1 服务提供商维护的主街道地址指南（MSAG）验证新位置。</span><span class="sxs-lookup"><span data-stu-id="d5dd1-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="d5dd1-105">有关 SIP 中继 E9-1-1 服务提供商的详细信息，请参阅[为 Lync Server 2013 选择 E9-1-1 服务提供商](lync-server-2013-choosing-an-e9-1-1-service-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d5dd1-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="d5dd1-106">有关验证地址的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d5dd1-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="d5dd1-107">**CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="d5dd1-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="d5dd1-108">**CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="d5dd1-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="d5dd1-109">**CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="d5dd1-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="d5dd1-110">**CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="d5dd1-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="d5dd1-111">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="d5dd1-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="d5dd1-112">验证位于位置数据库中的地址</span><span class="sxs-lookup"><span data-stu-id="d5dd1-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="d5dd1-113">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5dd1-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d5dd1-114">运行以下 cmdlet 以配置紧急服务提供程序连接。</span><span class="sxs-lookup"><span data-stu-id="d5dd1-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="d5dd1-115">运行以下 cmdlet 以验证位置数据库中的地址。</span><span class="sxs-lookup"><span data-stu-id="d5dd1-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="d5dd1-116">您还可以使用**CsLisCivicAddress** cmdlet 来验证各个地址。</span><span class="sxs-lookup"><span data-stu-id="d5dd1-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

