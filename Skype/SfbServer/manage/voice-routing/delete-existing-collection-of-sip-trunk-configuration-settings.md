---
title: 删除 Skype for Business Server 中的 SIP 中继配置设置的现有集合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。 '
ms.openlocfilehash: c24633e598efe8f5bd9f62e7e46651045d24b71b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120894"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="cc24b-103">删除 Skype for Business Server 中的 SIP 中继配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="cc24b-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="cc24b-p101">SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：</span><span class="sxs-lookup"><span data-stu-id="cc24b-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="cc24b-106">是否应对中继启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="cc24b-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="cc24b-107">发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="cc24b-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="cc24b-108">每个中继上是否需要安全实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="cc24b-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="cc24b-109">安装 Skype for Business Server 时，将创建 SIP 中继配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="cc24b-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="cc24b-110">此全局集合设置无法删除。</span><span class="sxs-lookup"><span data-stu-id="cc24b-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="cc24b-111">但是，您可以使用 Skype for Business ServerControl 面板或 [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 将全局集合中的属性"重置"为默认值。</span><span class="sxs-lookup"><span data-stu-id="cc24b-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="cc24b-112">例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。</span><span class="sxs-lookup"><span data-stu-id="cc24b-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="cc24b-p103">管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="cc24b-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="cc24b-p104">如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。</span><span class="sxs-lookup"><span data-stu-id="cc24b-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="cc24b-117">如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。</span><span class="sxs-lookup"><span data-stu-id="cc24b-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="cc24b-118">**使用 Skype for Business Server 控制面板删除中继配置设置**</span><span class="sxs-lookup"><span data-stu-id="cc24b-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="cc24b-119">在 Skype for Business Server 控制面板中，单击 **"语音路由"，** 然后单击"**中继配置"。**</span><span class="sxs-lookup"><span data-stu-id="cc24b-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="cc24b-120">在 **"Trunk 配置"** 选项卡上，选择要删除的 SIP 中继配置设置的集合，单击"编辑"，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="cc24b-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="cc24b-121">若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。</span><span class="sxs-lookup"><span data-stu-id="cc24b-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="cc24b-p106">集合的“状态”属性将更新为“未提交”。若要提交更改和删除集合，请单击“提交”，然后单击“全部提交”。</span><span class="sxs-lookup"><span data-stu-id="cc24b-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="cc24b-124">在“未提交的语音配置设置”对话框中，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="cc24b-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="cc24b-125">在 **"Skype for Business Server 控制面板**"对话框中，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="cc24b-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="cc24b-126">If you change your mind and decide not to delete the collection， click **Commit**， and then click **Cancel All Uncommitted Changes**.</span><span class="sxs-lookup"><span data-stu-id="cc24b-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="cc24b-127">当出现 **"Skype for Business Server 控制面板**"对话框时，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="cc24b-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cc24b-128">使用 cmdlet 删除中继Windows PowerShell设置</span><span class="sxs-lookup"><span data-stu-id="cc24b-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="cc24b-129">可以通过使用 Windows PowerShell **和 Remove-CsTrunkConfiguration** cmdlet 删除中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="cc24b-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="cc24b-130">可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cc24b-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="cc24b-131">**删除指定的设置集合**</span><span class="sxs-lookup"><span data-stu-id="cc24b-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="cc24b-132">以下命令将删除应用于 Redmond 站点的中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="cc24b-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="cc24b-133">**删除应用于网站范围的所有集合**</span><span class="sxs-lookup"><span data-stu-id="cc24b-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="cc24b-134">以下命令将删除应用于服务作用域的所有中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="cc24b-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="cc24b-135">**删除启用了媒体旁路的所有集合**</span><span class="sxs-lookup"><span data-stu-id="cc24b-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="cc24b-136">以下命令将删除启用了媒体旁路的所有中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="cc24b-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="cc24b-137">有关详细信息，请参阅 [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="cc24b-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>