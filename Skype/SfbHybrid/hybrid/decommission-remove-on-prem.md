---
title: 停用 Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 有关停用 Skype for Business Server 的说明。
ms.openlocfilehash: 9c6051a07fc05297985b3692351c36791d8842bb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656688"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="00bee-103">删除本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="00bee-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="00bee-104">本文介绍了如何删除本地 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="00bee-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="00bee-105">这是停止使用本地环境的以下步骤的第 4 步：</span><span class="sxs-lookup"><span data-stu-id="00bee-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="00bee-106">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="00bee-106">Step 1.</span></span> <span data-ttu-id="00bee-107">[将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="00bee-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="00bee-108">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="00bee-108">Step 2.</span></span> <span data-ttu-id="00bee-109">[禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="00bee-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="00bee-110">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="00bee-110">Step 3.</span></span> [<span data-ttu-id="00bee-111">将混合应用程序终结点从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="00bee-111">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="00bee-112">**步骤 4.删除本地 Skype for Business 部署。**</span><span class="sxs-lookup"><span data-stu-id="00bee-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="00bee-113"> (本文) </span><span class="sxs-lookup"><span data-stu-id="00bee-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="00bee-114">本文中的步骤仅在使用方法 2 管理用户属性时适用，如此处 [所述](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="00bee-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="00bee-115">如果使用方法 1，请不要使用本文中所述的步骤删除 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="00bee-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="00bee-116">相反，你可以重新映像服务器。</span><span class="sxs-lookup"><span data-stu-id="00bee-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="00bee-117">若要完成本文中的步骤，需要 Schema Admins 组和企业管理员组的权限。</span><span class="sxs-lookup"><span data-stu-id="00bee-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="00bee-118">你将需要这些权限来撤消对 Active Directory 域服务的 Skype for Business Server 架构和林级别更改。</span><span class="sxs-lookup"><span data-stu-id="00bee-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="00bee-119">您还需要是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="00bee-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="00bee-120">准备删除 Skype for Business 部署</span><span class="sxs-lookup"><span data-stu-id="00bee-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="00bee-121">将所有必需的用户帐户移动到云后，可能仍有一些需要清理的其余本地对象，如联系人和应用程序。</span><span class="sxs-lookup"><span data-stu-id="00bee-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="00bee-122">使用以下步骤清理这些对象，并确保你是本地管理员组和 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="00bee-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="00bee-123">请注意，ExUmContacts 和 PersistantChatEndPoints 在 Skype for Business Server 2019 中不可用。</span><span class="sxs-lookup"><span data-stu-id="00bee-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="00bee-124">如果你有 Skype for Business Server 2019，应省略以下步骤中的相应 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00bee-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="00bee-125">若要检查是否有与 Skype for Business Server 本地部署关联的联系人或应用程序，请运行以下 Skype for Business Server PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00bee-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. <span data-ttu-id="00bee-126">查看步骤 1 中 cmdlet 的输出列表。</span><span class="sxs-lookup"><span data-stu-id="00bee-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="00bee-127">然后，如果可以删除对象，请运行以下 Skype for Business Server PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="00bee-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="00bee-128">删除本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="00bee-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="00bee-129">完成所有初步步骤后，可以按照以下步骤删除 Skype for Business 部署：</span><span class="sxs-lookup"><span data-stu-id="00bee-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="00bee-130">逻辑删除 Skype for Business Server 部署，单个前端除外，如下所示：</span><span class="sxs-lookup"><span data-stu-id="00bee-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="00bee-131">a.</span><span class="sxs-lookup"><span data-stu-id="00bee-131">a.</span></span> <span data-ttu-id="00bee-132">将 Skype for Business Server 拓扑更新为具有单个前端池：</span><span class="sxs-lookup"><span data-stu-id="00bee-132">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="00bee-133">在拓扑生成器中，下载新副本并导航到前端池。</span><span class="sxs-lookup"><span data-stu-id="00bee-133">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="00bee-134">右键单击该池，然后单击“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="00bee-134">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="00bee-135">在 **"关联"中\*\*\*\*，** 取消选中 (媒体组件关联边缘) 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="00bee-135">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="00bee-136">如果存在多个前端池，请删除其余所有池的关联。</span><span class="sxs-lookup"><span data-stu-id="00bee-136">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="00bee-137">选择 **"删除>操作"。**</span><span class="sxs-lookup"><span data-stu-id="00bee-137">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="00bee-138">选择 **"操作>发布拓扑"。**</span><span class="sxs-lookup"><span data-stu-id="00bee-138">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="00bee-139">b.</span><span class="sxs-lookup"><span data-stu-id="00bee-139">b.</span></span> <span data-ttu-id="00bee-140">发布拓扑后，完成向导中所述的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="00bee-140">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="00bee-141">通过运行以下 Skype for Business Server PowerShell cmdlet 删除 Skype for Business Server 会议目录：</span><span class="sxs-lookup"><span data-stu-id="00bee-141">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="00bee-142">通过运行以下 Skype for Business Server PowerShell cmdlet 完成 Skype for Business Server 部署的卸载：</span><span class="sxs-lookup"><span data-stu-id="00bee-142">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="00bee-143">如果此步骤返回错误，请打开 Microsoft 支持票证，获取删除其余过时对象的帮助。</span><span class="sxs-lookup"><span data-stu-id="00bee-143">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="00bee-144">通过运行以下 Skype for Business Server PowerShell cmdlet 删除中央管理存储服务控制点：</span><span class="sxs-lookup"><span data-stu-id="00bee-144">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="00bee-145">通过运行以下 Skype for Business Server PowerShell cmdlet 撤消 Skype for Business Server Active Directory 域林级更改：</span><span class="sxs-lookup"><span data-stu-id="00bee-145">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="00bee-146">通过运行以下 Skype for Business Server PowerShell cmdlet 撤消 Skype for Business Server Active Directory 域架构更改：</span><span class="sxs-lookup"><span data-stu-id="00bee-146">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="00bee-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00bee-147">See also</span></span>

- [<span data-ttu-id="00bee-148">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="00bee-148">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="00bee-149">将所有所需的用户从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="00bee-149">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="00bee-150">禁用混合配置</span><span class="sxs-lookup"><span data-stu-id="00bee-150">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="00bee-151">将混合应用程序终结点从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="00bee-151">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)











