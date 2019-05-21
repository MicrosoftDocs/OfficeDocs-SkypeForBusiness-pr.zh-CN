---
title: 在 Skype for Business Server 中删除 SIP 中继配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。 '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274931"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e3d49-103">在 Skype for Business Server 中删除 SIP 中继配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="e3d49-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="e3d49-104">SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。</span><span class="sxs-lookup"><span data-stu-id="e3d49-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="e3d49-105">这些设置可执行如下所指定内容的操作：</span><span class="sxs-lookup"><span data-stu-id="e3d49-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="e3d49-106">是否在中继上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="e3d49-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="e3d49-107">发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="e3d49-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="e3d49-108">每个主干上是否需要安全的实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="e3d49-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="e3d49-109">安装 Skype for Business 服务器时, 将为你创建一个全局 SIP 中继配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="e3d49-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e3d49-110">此全局集合设置无法删除。</span><span class="sxs-lookup"><span data-stu-id="e3d49-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="e3d49-111">但是, 你可以使用 Skype for Business ServerControl 面板或[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 将全局集合中的属性 "重置" 为其默认值。</span><span class="sxs-lookup"><span data-stu-id="e3d49-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="e3d49-112">例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。</span><span class="sxs-lookup"><span data-stu-id="e3d49-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="e3d49-p103">管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="e3d49-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="e3d49-p104">如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。</span><span class="sxs-lookup"><span data-stu-id="e3d49-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="e3d49-117">如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。</span><span class="sxs-lookup"><span data-stu-id="e3d49-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="e3d49-118">**通过 Skype for Business 服务器控制面板删除中继配置设置**</span><span class="sxs-lookup"><span data-stu-id="e3d49-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="e3d49-119">在 "Skype for Business 服务器" 控制面板中, 单击 "**语音路由**", 然后单击 "**中继配置**"。</span><span class="sxs-lookup"><span data-stu-id="e3d49-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="e3d49-120">在 "**中继配置**" 选项卡上, 选择要删除的 SIP 中继配置设置的集合, 单击 "**编辑**", 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e3d49-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="e3d49-121">若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。</span><span class="sxs-lookup"><span data-stu-id="e3d49-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="e3d49-p106">集合的“状态”\*\*\*\* 属性将更新为“未提交”\*\*\*\*。若要提交更改和删除集合，请单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e3d49-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="e3d49-124">在“未提交的语音配置设置”\*\*\*\* 对话框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e3d49-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="e3d49-125">在 " **Skype For Business 服务器控制面板**" 对话框中, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e3d49-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="e3d49-126">如果你改变主意并决定不删除集合, 请单击 "**提交**", 然后单击 "**取消所有未提交的更改**"。</span><span class="sxs-lookup"><span data-stu-id="e3d49-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="e3d49-127">当出现 " **Skype For Business 服务器控制面板**" 对话框时, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e3d49-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e3d49-128">使用 Windows PowerShell cmdlet 删除中继配置设置</span><span class="sxs-lookup"><span data-stu-id="e3d49-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="e3d49-129">你可以使用 Windows PowerShell 和**new-cstrunkconfiguration** cmdlet 删除中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="e3d49-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="e3d49-130">你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e3d49-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="e3d49-131">**删除指定的设置集合**</span><span class="sxs-lookup"><span data-stu-id="e3d49-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="e3d49-132">以下命令将删除应用于 Redmond 站点的中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="e3d49-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="e3d49-133">**删除适用于站点范围的所有集合**</span><span class="sxs-lookup"><span data-stu-id="e3d49-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="e3d49-134">以下命令将删除应用于服务作用域的所有中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="e3d49-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="e3d49-135">**删除启用了媒体旁路的所有集合**</span><span class="sxs-lookup"><span data-stu-id="e3d49-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="e3d49-136">以下命令将删除启用了媒体旁路的所有中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="e3d49-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="e3d49-137">有关详细信息, 请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e3d49-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
