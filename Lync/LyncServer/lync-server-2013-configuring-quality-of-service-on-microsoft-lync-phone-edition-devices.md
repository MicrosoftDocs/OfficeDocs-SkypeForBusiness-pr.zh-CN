---
title: 在 Microsoft Lync Phone Edition 设备上配置服务质量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="71c6d-102">在 Lync Server 2013 中配置 Microsoft Lync Phone Edition 设备上的服务质量</span><span class="sxs-lookup"><span data-stu-id="71c6d-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71c6d-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="71c6d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="71c6d-104">虽然默认情况下不为 Iphone 等设备启用服务质量 (QoS), 但对于运行 Lync Phone Edition 的设备, 默认情况下启用 QoS。</span><span class="sxs-lookup"><span data-stu-id="71c6d-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="71c6d-105">(这些设备通常称为 UC 或统一通信电话。)若要验证此内容, 请从 Lync Server 命令行管理程序中运行以下 Windows PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="71c6d-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="71c6d-106">如果您未对 UC 手机配置设置进行任何更改, 则您将获得如下所示的信息:</span><span class="sxs-lookup"><span data-stu-id="71c6d-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="71c6d-107">对于服务质量目的, 仅关注以下属性之一: VoiceDiffServTag。</span><span class="sxs-lookup"><span data-stu-id="71c6d-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="71c6d-108">VoiceDiffServTag 表示分配给 Lync Phone Edition 设备的语音流量 emanating 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="71c6d-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="71c6d-109">Lync Server 2013 不再支持 Voice8021p 参数。</span><span class="sxs-lookup"><span data-stu-id="71c6d-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="71c6d-110">该参数仍然有效, 可向后兼容 Microsoft Lync Server 2010;但是, 它对使用 Lync Server 2013 的设备不起作用。</span><span class="sxs-lookup"><span data-stu-id="71c6d-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="71c6d-111">在大多数网络中, 使用40的 VoiceDiffServTag 标记 Lync Phone Edition 数据包不会导致任何问题。</span><span class="sxs-lookup"><span data-stu-id="71c6d-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="71c6d-112">但是, 40 不是通常用于音频流量的值;相反, 音频流量几乎始终标有 DSCP 代码46。</span><span class="sxs-lookup"><span data-stu-id="71c6d-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="71c6d-113">为了保持整个网络的一致性, 您可能希望将您的 UC 手机的 VoiceDiffServTag 属性更改为46。</span><span class="sxs-lookup"><span data-stu-id="71c6d-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="71c6d-114">若要执行此操作, 您可以使用 Windows PowerShell 或 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="71c6d-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="71c6d-115">若要使用 Windows PowerShell 修改 VoiceDiffServTag 值, 请从 Lync Server 命令行管理程序中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="71c6d-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="71c6d-116">上面的命令修改 UC 手机配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="71c6d-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="71c6d-117">但是请注意, UC 电话设置也可以分配给网站范围。</span><span class="sxs-lookup"><span data-stu-id="71c6d-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="71c6d-118">若要在网站范围内修改 UC 手机配置设置, 必须指定网站标识。</span><span class="sxs-lookup"><span data-stu-id="71c6d-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="71c6d-119">例如：</span><span class="sxs-lookup"><span data-stu-id="71c6d-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="71c6d-120">您也可以使用以下命令同时修改您的所有 UC 手机配置设置:</span><span class="sxs-lookup"><span data-stu-id="71c6d-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="71c6d-121">如果您希望使用 Lync Server "控制面板" 进行此更改, 请启动 "控制面板", 然后完成以下过程:</span><span class="sxs-lookup"><span data-stu-id="71c6d-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="71c6d-122">单击 "**客户端**", 然后单击 "**设备配置**"。</span><span class="sxs-lookup"><span data-stu-id="71c6d-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="71c6d-123">在 "**设备配置**" 选项卡上, 双击要修改的设置集合 (例如, "**全局**")。</span><span class="sxs-lookup"><span data-stu-id="71c6d-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="71c6d-124">在 "**编辑设备配置**" 对话框中, 将 "**语音服务质量 (QoS)** " 框的值设置为**46** , 然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="71c6d-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="71c6d-125">如果你有多个集合, 你将需要为每个 UC 电话设置集合重复此过程。</span><span class="sxs-lookup"><span data-stu-id="71c6d-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="71c6d-126">Lync Server "控制面板" 将不允许同时修改多个设置集合。</span><span class="sxs-lookup"><span data-stu-id="71c6d-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="71c6d-127">如果你的设备不是基于你组织中的 Windows 操作系统 (如 Iphone), 这些设备将不会受到更改 VoiceDiffServTag 设置的影响。</span><span class="sxs-lookup"><span data-stu-id="71c6d-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="71c6d-128">如果你想要在这些设备上更改 DSCP 值, 你需要参考每个设备类型的管理手册。</span><span class="sxs-lookup"><span data-stu-id="71c6d-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

