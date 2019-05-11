---
title: 自定义业务服务器 Skype 的用户帐户属性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 您可以使用本节中的过程修改单个用户帐户属性。
ms.openlocfilehash: 1f2039180a2bfa44b3379f7cf6bf095e2d0a7c14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911831"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="959f4-103">自定义业务服务器 Skype 的用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="959f4-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="959f4-104">您可以使用本节中的过程修改单个用户帐户属性。</span><span class="sxs-lookup"><span data-stu-id="959f4-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="959f4-105">有两个可在单个用户级别的基本操作：</span><span class="sxs-lookup"><span data-stu-id="959f4-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="959f4-106">配置特定的用户帐户的电话选项</span><span class="sxs-lookup"><span data-stu-id="959f4-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="959f4-107">将用户移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="959f4-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="959f4-108">配置特定的用户帐户的电话选项</span><span class="sxs-lookup"><span data-stu-id="959f4-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="959f4-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="959f4-109"></span></span>

<span data-ttu-id="959f4-110">（前提是单个用户已启用的 Skype 业务服务器和组织支持电话），您可以自定义特定用户的电话设置。</span><span class="sxs-lookup"><span data-stu-id="959f4-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="959f4-111">Skype 的企业服务器用户电话选项包括：</span><span class="sxs-lookup"><span data-stu-id="959f4-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="959f4-112">**禁用音频/视频**用户不能与呼叫音频和视频。</span><span class="sxs-lookup"><span data-stu-id="959f4-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="959f4-113">**PC 到 PC 仅**用户可以发出仅限 PC 到 PC 音频或视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="959f4-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="959f4-114">**企业语音**用户可以使用 Business Server 基础结构 Skype 将所有传入和传出呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="959f4-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="959f4-115">用户还可以发出 PC 到 PC 呼叫。</span><span class="sxs-lookup"><span data-stu-id="959f4-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="959f4-116">**远程呼叫控制**用户可以使用 Skype 业务服务器来控制桌面电话，并还可以发出 PC 到 PC 呼叫。</span><span class="sxs-lookup"><span data-stu-id="959f4-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="959f4-117">有关配置为组织的电话的详细信息，请参阅部署文档中的[为 Skype 业务服务器中的企业语音用户启用](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)和[Skype 业务服务器中部署企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="959f4-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="959f4-118">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="959f4-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="959f4-119">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="959f4-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="959f4-120">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="959f4-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="959f4-121">在**搜索用户**框中键入所有或显示名称、 名字、 最后一个名称、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或行您希望，并单击**查找的用户帐户的统一资源标识符 (URI) 的第一部分**.</span><span class="sxs-lookup"><span data-stu-id="959f4-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="959f4-122">在表中，单击要修改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="959f4-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="959f4-123">在**编辑**菜单上，单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="959f4-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="959f4-124">在**电话**中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="959f4-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="959f4-125">若要禁用的用户的音频和视频呼叫，请单击**禁用音频/视频**。</span><span class="sxs-lookup"><span data-stu-id="959f4-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="959f4-126">若要启用 PC 到 PC 音频通信的用户，但没有远程呼叫控制或企业语音，请单击**PC 到 PC 仅**。</span><span class="sxs-lookup"><span data-stu-id="959f4-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="959f4-127">指定的用户进行 PC 到 PC 音频通信使用的电话**线路 URI**值。</span><span class="sxs-lookup"><span data-stu-id="959f4-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="959f4-128">若要将用户的电话呼叫路由使用的服务策略，包括 PC 到 PC 音频通信类按照业务基础结构 Skype 单击**企业语音**。</span><span class="sxs-lookup"><span data-stu-id="959f4-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="959f4-129">在**线路 URI**中，指定企业语音的电话号码。</span><span class="sxs-lookup"><span data-stu-id="959f4-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="959f4-130">在**拨号计划策略**和**语音策略**中，指定用户的相应策略。</span><span class="sxs-lookup"><span data-stu-id="959f4-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="959f4-131">若要指定转换为 E.164 格式的用户所拨打的电话号码的规范化规则，选择适当的位置配置文件**的位置策略**中。</span><span class="sxs-lookup"><span data-stu-id="959f4-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="959f4-132">要启用远程呼叫控件，它使用户可以控制业务服务器进行 PC 到 PC 呼叫以及 PC 到电话的呼叫的 Skype 从其桌面电话线，单击**远程呼叫控制**。</span><span class="sxs-lookup"><span data-stu-id="959f4-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="959f4-133">在**线路 URI**中，指定远程呼叫控制的电话号码。</span><span class="sxs-lookup"><span data-stu-id="959f4-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="959f4-134">用户必须拥有桌面电话和专用交换机 (pbx) 连接的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="959f4-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="959f4-135">将用户移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="959f4-135">Move users to another pool</span></span>
<span data-ttu-id="959f4-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="959f4-136"></span></span>

<span data-ttu-id="959f4-137">您可以使用业务 Server Control Panel 的 Skype 将用户分配给特定服务器或池。</span><span class="sxs-lookup"><span data-stu-id="959f4-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="959f4-138">从正在运行 Lync Server 2010 的源池或更早版本的复杂的 Active Directory 环境中的业务服务器目标池 Skype 移动所有现有用户可能会导致速度较慢的 Active Directory 复制。</span><span class="sxs-lookup"><span data-stu-id="959f4-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="959f4-139">若要避免此问题，可以使用搜索筛选器从正在运行 Lync Server 2010 的池中移动用户或更早版本分别，或者您可以使用 Skype 的业务 Server 命令行管理程序移动用户通过 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="959f4-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="959f4-140">此外，筛选器功能与 Skype 适用于企业服务器用户。</span><span class="sxs-lookup"><span data-stu-id="959f4-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="959f4-141">将所选的用户移动到其他服务器或池</span><span class="sxs-lookup"><span data-stu-id="959f4-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="959f4-142">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="959f4-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="959f4-143">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="959f4-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="959f4-144">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="959f4-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="959f4-145">在**搜索用户**框中键入所有或显示名称、 名字、 最后一个名称、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或行您希望，并单击**查找的用户帐户的统一资源标识符 (URI) 的第一部分**.</span><span class="sxs-lookup"><span data-stu-id="959f4-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="959f4-146">在表中，选择一个特定用户或列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="959f4-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="959f4-147">在**操作**菜单中，单击**移动所选的用户移动到池**。</span><span class="sxs-lookup"><span data-stu-id="959f4-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="959f4-148">在**移动用户**中，选择您想要将用户移动到的**目标注册器池**的池。</span><span class="sxs-lookup"><span data-stu-id="959f4-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="959f4-149">（可选）如果目标服务器或池不可用，则选择**强制**复选框。</span><span class="sxs-lookup"><span data-stu-id="959f4-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="959f4-150">如果选择**强制**，移动的用户帐户时，但任何关联的用户数据 （例如，用户已安排的会议） 中删除。</span><span class="sxs-lookup"><span data-stu-id="959f4-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="959f4-151">如果未选择它，移动帐户和关联的数据。</span><span class="sxs-lookup"><span data-stu-id="959f4-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="959f4-152">将所有用户从一个服务器或池移至其他服务器或池</span><span class="sxs-lookup"><span data-stu-id="959f4-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="959f4-153">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="959f4-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="959f4-154">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="959f4-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="959f4-155">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="959f4-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="959f4-156">在**操作**菜单中，单击**移动所有用户移动到池**。</span><span class="sxs-lookup"><span data-stu-id="959f4-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="959f4-157">在**移动用户**中，选择包含您要在**源注册器池**移动的用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="959f4-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="959f4-158">在**目标注册器池**，选择您想要将用户移动到池。</span><span class="sxs-lookup"><span data-stu-id="959f4-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="959f4-159">（可选）如果目标服务器或池不可用，则选择**强制**复选框。</span><span class="sxs-lookup"><span data-stu-id="959f4-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="959f4-160">如果选择**强制**，移动的用户帐户时，但任何关联的用户数据 （例如，用户已安排的会议） 中删除。</span><span class="sxs-lookup"><span data-stu-id="959f4-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="959f4-161">如果未选择它，移动帐户和关联的数据。</span><span class="sxs-lookup"><span data-stu-id="959f4-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="959f4-162">若要将用户从一个池移动到另一个池，使用筛选器</span><span class="sxs-lookup"><span data-stu-id="959f4-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="959f4-163">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="959f4-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="959f4-164">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="959f4-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="959f4-165">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="959f4-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="959f4-166">在**用户搜索**，单击**搜索**，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="959f4-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="959f4-167">在搜索条件中，选择**注册器池**，选择**等于**、 选择**当前池 FQDN**，，然后单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="959f4-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="959f4-168">在**操作**菜单中，单击**移动所有用户移动到池**。</span><span class="sxs-lookup"><span data-stu-id="959f4-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="959f4-169">当筛选器应用于现有一组用户，**移动到池的所有用户**是筛选子集的用户，不**所有**可能的用户的上下文中的选项。</span><span class="sxs-lookup"><span data-stu-id="959f4-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="959f4-170">在**移动用户**中，选择包含您要在**源注册器池**移动的用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="959f4-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="959f4-171">在**目标注册器池**，选择您想要移动的用户的池。</span><span class="sxs-lookup"><span data-stu-id="959f4-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="959f4-172">（可选）如果目标服务器或池不可用，则选择**强制**复选框。</span><span class="sxs-lookup"><span data-stu-id="959f4-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="959f4-173">如果选择**强制**，移动的用户帐户时，但任何关联的用户数据删除 （例如，用户已安排的会议和联系人）。</span><span class="sxs-lookup"><span data-stu-id="959f4-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="959f4-174">如果未选择它，移动帐户和关联的数据。</span><span class="sxs-lookup"><span data-stu-id="959f4-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="959f4-175">将用户从一个池移至另一个使用 Windows Powershell cmdlet</span><span class="sxs-lookup"><span data-stu-id="959f4-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="959f4-176">根据如何运行 Windows PowerShell 命令的 （即 （本地还是远程），您需要以登录正确的 Skype 业务服务器管理角色的成员，如下所示：</span><span class="sxs-lookup"><span data-stu-id="959f4-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="959f4-177">a.</span><span class="sxs-lookup"><span data-stu-id="959f4-177">a.</span></span> <span data-ttu-id="959f4-178">如果要在本地计算机 （例如，您直接登录前端服务器） 上运行命令： 登录到计算机的业务 Server Management Shell 的 Skype 成员身份的 RTCUniversalServerAdmins 组或具有所需的安装**Delegate Setup Permissions**中所述的用户权限。</span><span class="sxs-lookup"><span data-stu-id="959f4-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="959f4-179">b.</span><span class="sxs-lookup"><span data-stu-id="959f4-179">b.</span></span> <span data-ttu-id="959f4-180">如果您要在另一台计算机上远程运行命令 （例如，您登录到您的计算机上，在 Standard Edition 前端服务器上远程运行命令）： 使用分配给 CsUserAdministrator 角色或 CsAdministrator 的用户帐户角色，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="959f4-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="959f4-181">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**for Business 的 Skype**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="959f4-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="959f4-182">若要移动单个用户，请按以下方式使用 Move-csuser cmdlet:</span><span class="sxs-lookup"><span data-stu-id="959f4-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="959f4-183">其中移动用户是用户 Pilar Ackerman，该用户将是从其当前分配主池移至 pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="959f4-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="959f4-184">若要移动大量用户，将筛选器与**Get-csuser** cmdlet，并将生成的用户组传递给**Move-csuser**:</span><span class="sxs-lookup"><span data-stu-id="959f4-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="959f4-185">**Get-csuser**和**Move-csuser**命令结合可能会导致此：</span><span class="sxs-lookup"><span data-stu-id="959f4-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


