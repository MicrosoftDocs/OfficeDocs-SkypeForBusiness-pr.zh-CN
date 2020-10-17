---
title: 在 Microsoft Lync Phone Edition 设备上配置服务质量
description: 在 Microsoft Lync Phone Edition 设备上配置服务质量。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0d1e4f10c6b4a550f5da25f8bd2e9fe97606255
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547938"
---
# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="6e643-103">在 Lync Server 2013 中配置 Microsoft Lync Phone Edition 设备上的服务质量</span><span class="sxs-lookup"><span data-stu-id="6e643-103">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e643-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6e643-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6e643-105">虽然默认情况下不为 Iphone 等设备启用服务质量 (QoS) ，但默认情况下为运行 Lync Phone Edition 的设备启用了 QoS。</span><span class="sxs-lookup"><span data-stu-id="6e643-105">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="6e643-106"> (这些设备通常称为 UC 或统一通信电话。 ) 若要验证这一点，请在 Lync Server 命令行管理程序中运行以下 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="6e643-106">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="6e643-107">如果尚未对 UC 电话配置设置进行任何更改，则将会得到看起来如下所示的信息：</span><span class="sxs-lookup"><span data-stu-id="6e643-107">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="6e643-108">针对服务质量，只有其中一个属性很重要：VoiceDiffServTag。</span><span class="sxs-lookup"><span data-stu-id="6e643-108">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="6e643-109">VoiceDiffServTag 表示分配给来自 Lync Phone Edition 设备的语音流量 emanating 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="6e643-109">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6e643-110">Lync Server 2013 不再支持 Voice8021p 参数。</span><span class="sxs-lookup"><span data-stu-id="6e643-110">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="6e643-111">参数仍然有效，以与 Microsoft Lync Server 2010 保持向后兼容;但是，它对在 Lync Server 2013 中使用的设备没有影响。</span><span class="sxs-lookup"><span data-stu-id="6e643-111">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="6e643-112">在大多数网络中，使用 VoiceDiffServTag 40 标记 Lync Phone Edition 数据包不会导致出现任何问题。</span><span class="sxs-lookup"><span data-stu-id="6e643-112">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="6e643-113">但是，40 并不是通常用于音频流量的值；音频流量几乎始终用 DSCP 代码 46 进行标记。</span><span class="sxs-lookup"><span data-stu-id="6e643-113">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="6e643-114">为了在整个网络中保持一致性，您可能想要将 UC 电话的 VoiceDiffServTag 属性更改为 46。</span><span class="sxs-lookup"><span data-stu-id="6e643-114">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="6e643-115">若要执行此操作，可以使用 Windows PowerShell 或 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="6e643-115">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="6e643-116">若要使用 Windows PowerShell 修改 VoiceDiffServTag 值，请在 Lync Server 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6e643-116">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="6e643-p106">上述命令会修改 UC 电话配置设置的全局集合。但请注意，也可以将 UC 电话设置分配给站点范围。要修改站点范围的 UC 电话配置设置，您必须指定站点 Identity。例如：</span><span class="sxs-lookup"><span data-stu-id="6e643-p106">The preceding command modifies the global collection of UC phone configuration settings. Note, however, that UC phone settings can also be assigned to the site scope. To modify UC phone configuration settings at the site scope, you must specify the site Identity. For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="6e643-121">您也可以使用以下命令同时修改所有 UC 电话配置设置：</span><span class="sxs-lookup"><span data-stu-id="6e643-121">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="6e643-122">如果您更愿意使用 Lync Server 控制面板进行此更改，请启动 "控制面板"，然后完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="6e643-122">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="6e643-123">单击“客户端”\*\*\*\*，然后单击“设备配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6e643-123">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="6e643-124">在“设备配置”\*\*\*\* 选项卡上，双击要修改的设置集合（例如，“全局”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="6e643-124">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="6e643-125">在“编辑设备配置”\*\*\*\* 对话框中，将“语音服务质量 (QoS)”\*\*\*\* 框的值设置为 **46**，然后单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6e643-125">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="6e643-126">如果您拥有多个集合，则需要针对每个 UC 电话设置集合重复此过程。</span><span class="sxs-lookup"><span data-stu-id="6e643-126">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="6e643-127">Lync Server 控制面板将不允许同时修改多个设置集合。</span><span class="sxs-lookup"><span data-stu-id="6e643-127">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="6e643-p108">如果您所拥有的设备并不是基于您组织中的 Windows 操作系统（如 iPhone），则更改 VoiceDiffServTag 设置不会对这些设备造成影响。如果您想要更改这些设备上的 DSCP 值，则需要参考管理手册，以了解每种设备类型。</span><span class="sxs-lookup"><span data-stu-id="6e643-p108">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting. If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

