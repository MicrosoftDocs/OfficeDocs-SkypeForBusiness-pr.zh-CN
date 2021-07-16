---
title: 停用Skype for Business Server
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
description: 有关停止使用Skype for Business Server。
ms.openlocfilehash: e96c4cd37d09fc62fbfbe34a8b8d61c79ea08289
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454335"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="b3982-103">删除本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="b3982-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="b3982-104">本文介绍如何删除本地部署Skype for Business部署。</span><span class="sxs-lookup"><span data-stu-id="b3982-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="b3982-105">这是停止使用本地环境的以下步骤的第 4 步：</span><span class="sxs-lookup"><span data-stu-id="b3982-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="b3982-106">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="b3982-106">Step 1.</span></span> <span data-ttu-id="b3982-107">[将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="b3982-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="b3982-108">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="b3982-108">Step 2.</span></span> <span data-ttu-id="b3982-109">[禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="b3982-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="b3982-110">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="b3982-110">Step 3.</span></span> [<span data-ttu-id="b3982-111">将混合应用程序终结点从本地迁移到联机</span><span class="sxs-lookup"><span data-stu-id="b3982-111">Migrate hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="b3982-112">**步骤 4.删除本地部署Skype for Business部署。**</span><span class="sxs-lookup"><span data-stu-id="b3982-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="b3982-113"> (本文) </span><span class="sxs-lookup"><span data-stu-id="b3982-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="b3982-114">本文中的步骤仅在使用方法 2 管理用户属性时适用，如此处 [所述](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="b3982-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="b3982-115">如果使用的是方法 1，请不要使用本文中所述的步骤删除Skype for Business服务器。</span><span class="sxs-lookup"><span data-stu-id="b3982-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="b3982-116">相反，你可以重新映像服务器。</span><span class="sxs-lookup"><span data-stu-id="b3982-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="b3982-117">若要完成本文中的步骤，需要 Schema Admins 组和管理员组Enterprise权限。</span><span class="sxs-lookup"><span data-stu-id="b3982-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="b3982-118">您需要这些权限来撤消对 Active Directory 域Skype for Business Server和林级别的更改。</span><span class="sxs-lookup"><span data-stu-id="b3982-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="b3982-119">您还需要是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="b3982-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="b3982-120">准备删除Skype for Business部署</span><span class="sxs-lookup"><span data-stu-id="b3982-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="b3982-121">将所有必需的用户帐户移动到云后，可能仍有一些需要清理的其余本地对象，如联系人和应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3982-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="b3982-122">使用以下步骤清理这些对象，并确保你是本地管理员组和 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="b3982-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="b3982-123">请注意，ExUmContacts 和 PersistantChatEndPoints 在 Skype for Business Server 2019 中不可用。</span><span class="sxs-lookup"><span data-stu-id="b3982-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b3982-124">如果您拥有 Skype for Business Server 2019，则应省略以下步骤中的相应 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b3982-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="b3982-125">若要检查是否有与本地部署Skype for Business Server联系人或应用程序，请运行以下 Skype for Business Server PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b3982-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="b3982-126">查看步骤 1 中 cmdlet 的输出列表。</span><span class="sxs-lookup"><span data-stu-id="b3982-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="b3982-127">然后，如果可以删除对象，请运行以下 Skype for Business Server PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b3982-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="b3982-128">删除本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="b3982-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="b3982-129">完成所有初步步骤后，可以按照以下步骤删除Skype for Business部署：</span><span class="sxs-lookup"><span data-stu-id="b3982-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="b3982-130">逻辑删除Skype for Business Server部署，单个前端除外，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b3982-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   1. <span data-ttu-id="b3982-131">将Skype for Business Server拓扑更新为具有单个前端池：</span><span class="sxs-lookup"><span data-stu-id="b3982-131">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

      1. <span data-ttu-id="b3982-132">在拓扑生成器中，下载新副本并导航到前端池。</span><span class="sxs-lookup"><span data-stu-id="b3982-132">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
      1. <span data-ttu-id="b3982-133">右键单击该池，然后单击“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="b3982-133">Right-click the pool, and then click **Edit Properties**.</span></span>
      1. <span data-ttu-id="b3982-134">在 **"关联"中\*\*\*\*，** 取消选中 (媒体组件关联边缘) 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="b3982-134">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
      1. <span data-ttu-id="b3982-135">如果存在多个前端池，请删除其余所有池的关联。</span><span class="sxs-lookup"><span data-stu-id="b3982-135">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
      1. <span data-ttu-id="b3982-136">选择 **"删除>操作"。**</span><span class="sxs-lookup"><span data-stu-id="b3982-136">Select **Action > Remove Deployment**.</span></span>
      1. <span data-ttu-id="b3982-137">选择 **"操作>发布拓扑"。**</span><span class="sxs-lookup"><span data-stu-id="b3982-137">Select **Action > Publish Topology**.</span></span>

    1. <span data-ttu-id="b3982-138">发布拓扑后，完成向导中所述的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="b3982-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="b3982-139">通过Skype for Business Server PowerShell cmdlet Skype for Business Server删除会议目录：</span><span class="sxs-lookup"><span data-stu-id="b3982-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="b3982-140">通过运行以下 PowerShell cmdlet Skype for Business Server卸载 Skype for Business Server部署：</span><span class="sxs-lookup"><span data-stu-id="b3982-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="b3982-141">如果此步骤返回错误，请打开 Microsoft 支持票证，获取删除其余过时对象的帮助。</span><span class="sxs-lookup"><span data-stu-id="b3982-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="b3982-142">通过运行以下 PowerShell cmdlet Skype for Business Server中央管理存储服务控制点：</span><span class="sxs-lookup"><span data-stu-id="b3982-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="b3982-143">通过Skype for Business Server PowerShell cmdlet 中的以下代码撤消 Active Directory 域Skype for Business Server更改：</span><span class="sxs-lookup"><span data-stu-id="b3982-143">Undo Skype for Business Server Active Directory domain-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="b3982-144">通过Skype for Business Server以下 PowerShell cmdlet 撤消 Active Directory 林Skype for Business Server更改：</span><span class="sxs-lookup"><span data-stu-id="b3982-144">Undo Skype for Business Server Active Directory forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="b3982-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3982-145">See also</span></span>

- [<span data-ttu-id="b3982-146">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="b3982-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="b3982-147">将所有所需的用户从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="b3982-147">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="b3982-148">禁用混合配置</span><span class="sxs-lookup"><span data-stu-id="b3982-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="b3982-149">将混合应用程序终结点从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="b3982-149">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

