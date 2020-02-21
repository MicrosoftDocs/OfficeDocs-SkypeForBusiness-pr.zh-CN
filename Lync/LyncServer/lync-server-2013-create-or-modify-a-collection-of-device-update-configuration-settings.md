---
title: 创建或修改设备更新配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1cba65da0e8c1e01c5cf5666b13b98cc2009baf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="112ca-102">在 Lync Server 2013 中创建或修改设备更新配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="112ca-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="112ca-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="112ca-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="112ca-104">可以使用 Windows PowerShell 和**CsDeviceUpdateConfiguration** cmdlet 创建设备更新配置设置（仅限在网站范围内），并使用**CsDeviceUpdateConfiguration** cmdlet 进行修改。</span><span class="sxs-lookup"><span data-stu-id="112ca-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="112ca-105">这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="112ca-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="112ca-106">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="112ca-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="112ca-107">创建使用默认值的设备更新配置设置</span><span class="sxs-lookup"><span data-stu-id="112ca-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="112ca-108">此命令为 Redmond 站点创建一组新的设备更新配置设置：</span><span class="sxs-lookup"><span data-stu-id="112ca-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="112ca-109">由于前面的命令中未指定强制 Identity 参数之外的任何参数，因此新的配置设置集合将对其所有属性使用默认值。</span><span class="sxs-lookup"><span data-stu-id="112ca-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="112ca-110">创建设备更新配置设置时更改单个属性值</span><span class="sxs-lookup"><span data-stu-id="112ca-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="112ca-111">要创建使用不同属性值的设置，只需包含相应的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="112ca-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="112ca-112">例如，若要创建设备更新配置设置的集合，默认情况下，每隔21天删除一次旧的日志文件，请使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="112ca-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="112ca-113">创建设备更新配置设置时更改多个属性值</span><span class="sxs-lookup"><span data-stu-id="112ca-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="112ca-114">可以通过包含多个参数来修改多个属性值。</span><span class="sxs-lookup"><span data-stu-id="112ca-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="112ca-115">例如，此命令将日志清除间隔设置为21天，日志刷新间隔设置为30分钟：</span><span class="sxs-lookup"><span data-stu-id="112ca-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="112ca-116">有关修改现有设备配置设置的详细信息，请参阅[CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="112ca-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="112ca-117">有关创建配置设置的集合的详细信息，请参阅[CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="112ca-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

