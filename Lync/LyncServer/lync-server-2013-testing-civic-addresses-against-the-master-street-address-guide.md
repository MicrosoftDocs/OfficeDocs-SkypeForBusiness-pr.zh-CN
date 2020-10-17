---
title: 对照主街道地址指南测试市政地址
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
ms.openlocfilehash: 2d03647df3752860c114a16967a3bea5271a89d4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527809"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="29cec-102">在 Lync Server 2013 中对照主街道地址指南测试市政地址</span><span class="sxs-lookup"><span data-stu-id="29cec-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29cec-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="29cec-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29cec-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="29cec-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="29cec-105">每天</span><span class="sxs-lookup"><span data-stu-id="29cec-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cec-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="29cec-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="29cec-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29cec-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cec-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="29cec-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="29cec-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="29cec-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="29cec-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsRegistration cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="29cec-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="29cec-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="29cec-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="29cec-112">说明</span><span class="sxs-lookup"><span data-stu-id="29cec-112">Description</span></span>

<span data-ttu-id="29cec-113">Test-CsLisCivicAddress cmdlet 用于验证添加到您的位置信息服务 (.LIS) 数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="29cec-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="29cec-114">该 cmdlet 的工作原理是将位置与主街道地址指南 (MSAG) （属于 E9-1-1）网络路由提供程序的位置进行比较。</span><span class="sxs-lookup"><span data-stu-id="29cec-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="29cec-115">如果没有网络路由提供程序或无法访问提供程序，则测试将失败。</span><span class="sxs-lookup"><span data-stu-id="29cec-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="29cec-116">如果向命令中添加可选开关参数 UpdateValidationStatus，则对于每个通过测试的地址，相应的 MSAGValid 数据库属性都将设置为 True。</span><span class="sxs-lookup"><span data-stu-id="29cec-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="29cec-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="29cec-117">Running the test</span></span>

<span data-ttu-id="29cec-118">Test-CsLisCivicAddress cmdlet 可用于测试各个地址或测试多个地址。</span><span class="sxs-lookup"><span data-stu-id="29cec-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="29cec-119">例如，以下命令将测试位于 Redmond，WA 中的单个地址：</span><span class="sxs-lookup"><span data-stu-id="29cec-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="29cec-120">通过比较，此命令将测试您的 IIS 数据库中当前的所有地址：</span><span class="sxs-lookup"><span data-stu-id="29cec-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="29cec-121">有关详细信息，请参阅 [CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="29cec-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="29cec-122">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="29cec-122">Determining success or failure</span></span>

<span data-ttu-id="29cec-123">Test-CsLisCivicAddress 将报告提供的地址的返回成功或失败。</span><span class="sxs-lookup"><span data-stu-id="29cec-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="29cec-124">如果找不到地址，或者无法联系服务提供商，则地址测试将失败。</span><span class="sxs-lookup"><span data-stu-id="29cec-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="29cec-125">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="29cec-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="29cec-126">下面是 Test-CsLisCivicAddress 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="29cec-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="29cec-127">IIS 服务提供商可能不可用。</span><span class="sxs-lookup"><span data-stu-id="29cec-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="29cec-128">您可以通过运行 Get-CsLisConfiguration cmdlet 来检索您的 .LIS 服务提供程序的 URL：</span><span class="sxs-lookup"><span data-stu-id="29cec-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="29cec-129">然后，可以 ping 该 URL 以验证服务提供程序是否可用。</span><span class="sxs-lookup"><span data-stu-id="29cec-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

