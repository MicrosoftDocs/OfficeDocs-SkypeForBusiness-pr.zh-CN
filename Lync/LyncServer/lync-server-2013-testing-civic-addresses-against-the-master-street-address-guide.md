---
title: 根据主街道地址指南测试市政地址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d6aa1443dc2e062aa099237d9b25f2b33e32b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="ba23d-102">根据 Lync Server 2013 中的主要街道地址指南测试市政地址</span><span class="sxs-lookup"><span data-stu-id="ba23d-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba23d-103">_**主题上次修改时间：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ba23d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba23d-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="ba23d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ba23d-105">每天</span><span class="sxs-lookup"><span data-stu-id="ba23d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba23d-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="ba23d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ba23d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba23d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba23d-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="ba23d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ba23d-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="ba23d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ba23d-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsRegistration cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ba23d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="ba23d-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ba23d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ba23d-112">说明</span><span class="sxs-lookup"><span data-stu-id="ba23d-112">Description</span></span>

<span data-ttu-id="ba23d-113">CsLisCivicAddress cmdlet 用于验证添加到您的位置信息服务（.LIS）数据库中的位置。</span><span class="sxs-lookup"><span data-stu-id="ba23d-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="ba23d-114">该 cmdlet 的工作原理是将位置与属于 E9 网络路由提供商的主街道地址指南（MSAG）中找到的位置进行比较。</span><span class="sxs-lookup"><span data-stu-id="ba23d-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="ba23d-115">如果你没有网络路由提供程序或无法访问提供程序，则你的测试将失败。</span><span class="sxs-lookup"><span data-stu-id="ba23d-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="ba23d-116">如果将可选的开关参数 UpdateValidationStatus 添加到命令，则每个传递测试的地址都将为其设置相应的 MSAGValid 数据库属性。</span><span class="sxs-lookup"><span data-stu-id="ba23d-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ba23d-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="ba23d-117">Running the test</span></span>

<span data-ttu-id="ba23d-118">CsLisCivicAddress cmdlet 可用于测试各个地址或测试多个地址。</span><span class="sxs-lookup"><span data-stu-id="ba23d-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="ba23d-119">例如，此命令测试位于 Redmond、WA 中的单个地址：</span><span class="sxs-lookup"><span data-stu-id="ba23d-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="ba23d-120">通过比较，此命令将测试 IIS 数据库中当前的所有地址：</span><span class="sxs-lookup"><span data-stu-id="ba23d-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="ba23d-121">有关详细信息，请参阅[CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="ba23d-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ba23d-122">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="ba23d-122">Determining success or failure</span></span>

<span data-ttu-id="ba23d-123">CsLisCivicAddress 将报告提供的地址的成功或失败。</span><span class="sxs-lookup"><span data-stu-id="ba23d-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="ba23d-124">如果找不到地址或无法联系服务提供商，则地址测试将失败。</span><span class="sxs-lookup"><span data-stu-id="ba23d-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ba23d-125">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="ba23d-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="ba23d-126">下面是测试 CsLisCivicAddress 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="ba23d-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="ba23d-127">.LIS 服务提供商可能不可用。</span><span class="sxs-lookup"><span data-stu-id="ba23d-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="ba23d-128">你可以通过运行 CsLisConfiguration cmdlet 来检索 IIS 的服务提供商的 URL：</span><span class="sxs-lookup"><span data-stu-id="ba23d-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="ba23d-129">然后，你可以 ping 该 URL 以验证服务提供程序是否可用。</span><span class="sxs-lookup"><span data-stu-id="ba23d-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

