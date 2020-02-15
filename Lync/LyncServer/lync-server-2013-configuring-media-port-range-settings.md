---
title: Lync Server 2013：配置媒体端口范围设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cfde603ace9036ba547ffb0a7ee80c1963ae6cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="9526e-102">在 Lync Server 2013 中配置媒体端口范围设置</span><span class="sxs-lookup"><span data-stu-id="9526e-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9526e-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9526e-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9526e-104">媒体端口范围设置可显著影响客户端性能，应对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="9526e-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="9526e-105">您可以使用 Lync Server 命令行管理程序配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="9526e-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="9526e-106">媒体端口范围设置</span><span class="sxs-lookup"><span data-stu-id="9526e-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9526e-107">设置</span><span class="sxs-lookup"><span data-stu-id="9526e-107">Setting</span></span></th>
<th><span data-ttu-id="9526e-108">说明</span><span class="sxs-lookup"><span data-stu-id="9526e-108">Description</span></span></th>
<th><span data-ttu-id="9526e-109">Lync Server 命令行管理程序 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9526e-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="9526e-110">Cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="9526e-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9526e-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="9526e-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="9526e-p102">指定服务器发送的端口范围是否应由客户端用于媒体和信号。与子值 MinMediaPort 和 MaxMediaPort 结合使用。</span><span class="sxs-lookup"><span data-stu-id="9526e-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="9526e-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="9526e-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="9526e-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="9526e-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9526e-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="9526e-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="9526e-p103">指定用于媒体的起始端口号。与 MaxMediaPort 一起指定端口范围。建议的最小范围为 40 个端口。</span><span class="sxs-lookup"><span data-stu-id="9526e-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="9526e-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="9526e-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="9526e-121">ClientMediaPort（代表用于客户端媒体的起始端口号）</span><span class="sxs-lookup"><span data-stu-id="9526e-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9526e-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="9526e-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="9526e-p104">指定用于媒体的最高端口号。与 MinMediaPort 一起指定端口范围。建议的最小范围为 40 个端口。</span><span class="sxs-lookup"><span data-stu-id="9526e-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="9526e-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="9526e-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="9526e-127">ClientMediaPortRange（指示可用于客户端媒体的端口总数；默认值为 40）</span><span class="sxs-lookup"><span data-stu-id="9526e-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="9526e-128">配置媒体端口范围设置</span><span class="sxs-lookup"><span data-stu-id="9526e-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="9526e-129">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9526e-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9526e-130">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9526e-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="9526e-131">此 cmdlet 返回会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="9526e-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="9526e-132">使用要更改的参数和值运行以下 cmdlet （有关此 cmdlet 的参数的详细信息，请参阅 Lync Server 命令行管理程序文档）：</span><span class="sxs-lookup"><span data-stu-id="9526e-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9526e-133">可为特定站点创建其他会议配置设置集。</span><span class="sxs-lookup"><span data-stu-id="9526e-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="9526e-134">使用具有站点标识的 <STRONG>New-CsConferencingConfiguration</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9526e-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="9526e-135">在为站点创建新的会议配置设置时，站点设置优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="9526e-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="9526e-136">有关详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="9526e-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

