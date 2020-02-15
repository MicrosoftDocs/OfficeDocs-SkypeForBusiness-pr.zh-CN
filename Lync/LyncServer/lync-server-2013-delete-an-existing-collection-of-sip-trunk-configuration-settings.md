---
title: 删除现有的 SIP 中继配置设置集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac74d42a8f85ceaa0a3ba41dfbd3e07f6b677f5f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8589c-102">删除 Lync Server 2013 中现有的 SIP 中继配置设置集合</span><span class="sxs-lookup"><span data-stu-id="8589c-102">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8589c-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="8589c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="8589c-p101">SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：</span><span class="sxs-lookup"><span data-stu-id="8589c-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="8589c-106">是否应对中继启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="8589c-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="8589c-107">发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="8589c-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="8589c-108">每个中继上是否需要安全实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="8589c-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="8589c-109">安装 Microsoft Lync Server 2013 时，将为您创建一个全局 SIP 中继配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="8589c-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="8589c-110">此全局集合设置无法删除。</span><span class="sxs-lookup"><span data-stu-id="8589c-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="8589c-111">但是，可以使用 Lync Server 控制面板或[remove-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet 将全局集合中的属性 "重置" 为其默认值。</span><span class="sxs-lookup"><span data-stu-id="8589c-111">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="8589c-112">例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。</span><span class="sxs-lookup"><span data-stu-id="8589c-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="8589c-p103">管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="8589c-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="8589c-p104">如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。</span><span class="sxs-lookup"><span data-stu-id="8589c-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="8589c-117">如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。</span><span class="sxs-lookup"><span data-stu-id="8589c-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="8589c-118">使用 Lync Server 控制面板删除中继配置设置</span><span class="sxs-lookup"><span data-stu-id="8589c-118">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8589c-119">在 "Lync Server 控制面板" 中，单击 "**语音路由**"，然后单击 "**中继配置**"。</span><span class="sxs-lookup"><span data-stu-id="8589c-119">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="8589c-p105">在“Trunk 配置”\*\*\*\* 选项卡上，选择要删除的 SIP 中继配置设置的集合，单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。</span><span class="sxs-lookup"><span data-stu-id="8589c-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="8589c-p106">集合的“状态”\*\*\*\* 属性将更新为“未提交”\*\*\*\*。若要提交更改和删除集合，请单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8589c-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="8589c-124">在“未提交的语音配置设置”\*\*\*\* 对话框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8589c-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="8589c-125">在“Microsoft Lync Server 2013 控制面板”\*\*\*\* 对话框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8589c-125">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="8589c-p107">如果您改变了想法并决定不删除集合，请单击“提交”\*\*\*\*，然后单击“取消所有未提交的更改”\*\*\*\*。当出现“Microsoft Lync Server 2013 控制面板”\*\*\*\* 对话框时，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8589c-p107">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8589c-128">使用 Windows PowerShell Cmdlet 删除中继配置设置</span><span class="sxs-lookup"><span data-stu-id="8589c-128">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8589c-129">您可以使用 Windows PowerShell 和**remove-cstrunkconfiguration** cmdlet 删除中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="8589c-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="8589c-130">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8589c-130">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8589c-131">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="8589c-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="8589c-132">删除指定的设置集合</span><span class="sxs-lookup"><span data-stu-id="8589c-132">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="8589c-133">以下命令将删除应用于 Redmond 站点的中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="8589c-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="8589c-134">删除应用到站点范围的所有集合</span><span class="sxs-lookup"><span data-stu-id="8589c-134">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="8589c-135">以下命令将删除应用于服务作用域的所有中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="8589c-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="8589c-136">删除启用了媒体旁路的所有集合</span><span class="sxs-lookup"><span data-stu-id="8589c-136">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="8589c-137">以下命令将删除启用了媒体旁路的所有中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="8589c-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="8589c-138">有关详细信息，请参阅[remove-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="8589c-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

