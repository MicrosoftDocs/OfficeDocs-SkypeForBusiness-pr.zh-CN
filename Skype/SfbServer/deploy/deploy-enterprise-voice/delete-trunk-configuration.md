---
title: 在 Skype for Business Server 2015 中删除现有 SIP 中继配置设置的集合
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 摘要： 了解如何使用适用于业务 Server Control Panel Skype 删除中继配置设置的集合。
ms.openlocfilehash: 64831efe35880b3e211543c80d9ba00939128354
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="180c3-103">在 Skype for Business Server 2015 中删除现有 SIP 中继配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="180c3-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="180c3-104">**摘要：**了解如何使用适用于业务 Server Control Panel Skype 删除中继配置设置的集合。</span><span class="sxs-lookup"><span data-stu-id="180c3-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="180c3-p101">SIP 中继配置设置可定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置可执行如下所指定内容的操作：</span><span class="sxs-lookup"><span data-stu-id="180c3-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="180c3-107">是否在中继上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="180c3-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="180c3-108">发送实时传输控制协议 (RTCP) 数据包所依据的条件。</span><span class="sxs-lookup"><span data-stu-id="180c3-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="180c3-109">在每个中继上是否需要安全实时传输协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="180c3-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="180c3-110">在安装 Skype 业务服务器时，会为您创建 SIP 中继配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="180c3-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="180c3-111">此全局集合设置无法删除。</span><span class="sxs-lookup"><span data-stu-id="180c3-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="180c3-112">但是，您可以使用业务 Server Control Panel 或[Remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet Skype 为其默认值"重置"中的全局集合的属性。</span><span class="sxs-lookup"><span data-stu-id="180c3-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="180c3-113">例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。</span><span class="sxs-lookup"><span data-stu-id="180c3-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="180c3-p103">管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="180c3-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="180c3-p104">如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。</span><span class="sxs-lookup"><span data-stu-id="180c3-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="180c3-118">如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。</span><span class="sxs-lookup"><span data-stu-id="180c3-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="180c3-119">删除与 Skype 的中继配置设置的业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="180c3-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="180c3-120">在业务 Server Control Panel 的 Skype，单击**语音路由**，然后单击**Trunk 配置**。</span><span class="sxs-lookup"><span data-stu-id="180c3-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="180c3-p105">在“Trunk 配置”**** 选项卡上，选择要删除的 SIP 中继配置设置的集合，单击“编辑”****，然后单击“删除”****。若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。</span><span class="sxs-lookup"><span data-stu-id="180c3-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="180c3-p106">集合的“状态”**** 属性将更新为“未提交”****。若要提交更改和删除集合，请单击“提交”****，然后单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="180c3-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="180c3-125">在“未提交的语音配置设置”**** 对话框中，单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="180c3-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="180c3-126">在**业务 Server Control Panel 的 Skype**对话框中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="180c3-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="180c3-127">如果你改变了想法并决定不删除集合，请单击“**提交**”，然后单击“**取消所有未提交的更改**”。</span><span class="sxs-lookup"><span data-stu-id="180c3-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="180c3-128">**Skype 的业务 Server Control Panel**对话框出现时，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="180c3-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="180c3-129">使用 Skype 业务 Server 命令行管理程序 Cmdlet 删除中继配置设置</span><span class="sxs-lookup"><span data-stu-id="180c3-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="180c3-130">您可以使用 Skype 的业务 Server 命令行管理程序和**Remove-cstrunkconfiguration** cmdlet 删除中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="180c3-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="180c3-131">您能运行此 cmdlet 从 Skype 业务 Server 命令行管理程序或从远程会话的 Skype 的业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="180c3-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="180c3-132">删除指定的设置集合</span><span class="sxs-lookup"><span data-stu-id="180c3-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="180c3-133">以下命令将删除应用于 Redmond 站点的中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="180c3-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="180c3-134">删除适用于站点范围的所有集合</span><span class="sxs-lookup"><span data-stu-id="180c3-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="180c3-135">以下命令将删除应用于服务作用域的所有中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="180c3-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="180c3-136">删除启用了媒体旁路的所有集合</span><span class="sxs-lookup"><span data-stu-id="180c3-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="180c3-137">以下命令将删除启用了媒体旁路的所有中继配置设置：</span><span class="sxs-lookup"><span data-stu-id="180c3-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="180c3-138">有关详细信息，请参阅[Remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="180c3-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

