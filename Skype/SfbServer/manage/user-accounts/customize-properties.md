---
title: 自定义 Skype for Business 服务器的用户帐户属性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 你可以使用本部分中的过程修改单个用户帐户属性。
ms.openlocfilehash: fda11a1b52519f3653c841837af20392383cadd1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222059"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="3c272-103">自定义 Skype for Business 服务器的用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="3c272-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="3c272-104">你可以使用本部分中的过程修改单个用户帐户属性。</span><span class="sxs-lookup"><span data-stu-id="3c272-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="3c272-105">可以在单个用户级别执行两项基本操作:</span><span class="sxs-lookup"><span data-stu-id="3c272-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="3c272-106">为特定用户帐户配置电话选项</span><span class="sxs-lookup"><span data-stu-id="3c272-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="3c272-107">将用户移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="3c272-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="3c272-108">为特定用户帐户配置电话选项</span><span class="sxs-lookup"><span data-stu-id="3c272-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="3c272-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="3c272-109"></span></span>

<span data-ttu-id="3c272-110">你可以自定义特定用户的电话设置 (只要个人用户已启用 Skype for business 服务器且组织支持电话服务)。</span><span class="sxs-lookup"><span data-stu-id="3c272-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="3c272-111">Skype for business 服务器用户电话选项包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="3c272-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="3c272-112">**音频/视频已禁用**用户无法使用音频和视频进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="3c272-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="3c272-113">**仅适用于 pc 到 pc**用户只能进行 PC 到 PC 的音频或视频通话。</span><span class="sxs-lookup"><span data-stu-id="3c272-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="3c272-114">**企业语音**用户可以使用 Skype for Business 服务器基础结构路由所有传入和传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="3c272-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="3c272-115">用户还可以进行 PC 到 PC 呼叫。</span><span class="sxs-lookup"><span data-stu-id="3c272-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="3c272-116">**远程呼叫控制**用户可以使用 Skype for Business 服务器控制桌面电话, 也可以进行 PC 到 PC 的通话。</span><span class="sxs-lookup"><span data-stu-id="3c272-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="3c272-117">有关为组织配置电话的详细信息, 请参阅在 "skype for business"[服务器中启用企业语音的用户](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md), 并在部署文档中[部署 Skype for business 服务器中的企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="3c272-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="3c272-118">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3c272-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c272-119">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3c272-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3c272-120">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3c272-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c272-121">在 "**搜索用户**" 框中, 键入所需用户帐户的所有或第一部分的显示名称、"名字"、"姓氏"、安全帐户管理器 (SAM) 帐户名、SIP 地址或行统一资源标识符 (URI), 然后单击 "**查找"**.</span><span class="sxs-lookup"><span data-stu-id="3c272-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="3c272-122">在表中, 单击要修改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3c272-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="3c272-123">在 "**编辑**" 菜单上, 单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="3c272-124">在**电话服务**中, 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3c272-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="3c272-125">若要为用户禁用音频和视频呼叫, 请单击 "**音频/视频已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="3c272-126">若要为用户启用 PC 至 PC 音频通信, 但不支持远程呼叫控制或企业语音, 请单击 "**仅 pc 到 pc**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="3c272-127">为用户用于 PC 到 PC 音频通信的电话指定**行 URI**的值。</span><span class="sxs-lookup"><span data-stu-id="3c272-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="3c272-128">若要根据服务策略类别 (包括 PC 到 PC 音频通信) 使用 Skype for Business 基础结构路由用户的电话呼叫, 请单击 "**企业语音**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="3c272-129">在 "**行 URI**" 中, 指定企业语音的电话号码。</span><span class="sxs-lookup"><span data-stu-id="3c272-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="3c272-130">在 "**拨号计划策略**" 和 "**语音策略**" 中, 为用户指定适当的策略。</span><span class="sxs-lookup"><span data-stu-id="3c272-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="3c272-131">若要指定将用户拨打的电话号码转换为电子164格式的规范化规则, 请在 "**位置策略**" 中选择相应的位置配置文件。</span><span class="sxs-lookup"><span data-stu-id="3c272-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="3c272-132">要启用 "远程呼叫控制", 使用户能够从 Skype for Business 服务器控制其桌面电话线路, 以进行 PC 到 PC 呼叫和 PC 至电话呼叫, 请单击 "**远程呼叫控制**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="3c272-133">在 "**行 URI**" 中, 指定远程呼叫控制的电话号码。</span><span class="sxs-lookup"><span data-stu-id="3c272-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="3c272-134">用户必须具有桌面电话和专用分支 exchange (PBX) 连接才能使用呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="3c272-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="3c272-135">将用户移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="3c272-135">Move users to another pool</span></span>
<span data-ttu-id="3c272-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="3c272-136"></span></span>

<span data-ttu-id="3c272-137">可以使用 Skype for Business 服务器控制面板将用户分配到特定的服务器或池。</span><span class="sxs-lookup"><span data-stu-id="3c272-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="3c272-138">将所有现有用户从运行 Lync Server 2010 或更早版本的源池中移动到复杂的 Active Directory 环境中的 Skype for business 服务器目标池可能会导致 Active Directory 复制速度较慢。</span><span class="sxs-lookup"><span data-stu-id="3c272-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="3c272-139">为避免这种情况, 您可以使用搜索筛选器从运行 Lync Server 2010 或更早版本的池中移动用户, 也可以使用 Skype for Business Server Management Shell 将用户与 cmdlet 一起移动。</span><span class="sxs-lookup"><span data-stu-id="3c272-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="3c272-140">此外, 筛选器功能可与 Skype for Business 服务器用户配合使用。</span><span class="sxs-lookup"><span data-stu-id="3c272-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="3c272-141">将所选用户移动到其他服务器或池</span><span class="sxs-lookup"><span data-stu-id="3c272-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="3c272-142">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3c272-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c272-143">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3c272-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3c272-144">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3c272-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c272-145">在 "**搜索用户**" 框中, 键入所需用户帐户的所有或第一部分的显示名称、"名字"、"姓氏"、安全帐户管理器 (SAM) 帐户名、SIP 地址或行统一资源标识符 (URI), 然后单击 "**查找"**.</span><span class="sxs-lookup"><span data-stu-id="3c272-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="3c272-146">在表中, 选择列表中的特定用户或用户。</span><span class="sxs-lookup"><span data-stu-id="3c272-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="3c272-147">在 "**操作**" 菜单上, 单击 "**将所选用户移至池**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="3c272-148">在 "**移动用户**" 中, 选择要将用户移动到 "**目标注册机构" 池中**的池。</span><span class="sxs-lookup"><span data-stu-id="3c272-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="3c272-149">可选如果目标服务器或池不可用, 请选中 "**强制**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3c272-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3c272-150">如果您选择 "**强制**", 则用户帐户将被移动, 但任何相关联的用户数据 (例如, 用户已安排的会议) 都将被删除。</span><span class="sxs-lookup"><span data-stu-id="3c272-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3c272-151">如果不选择该帐户, 将同时移动帐户和关联的数据。</span><span class="sxs-lookup"><span data-stu-id="3c272-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="3c272-152">将所有用户从一个服务器或池移动到另一个服务器或池</span><span class="sxs-lookup"><span data-stu-id="3c272-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="3c272-153">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3c272-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c272-154">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3c272-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3c272-155">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3c272-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c272-156">在 "**操作**" 菜单上, 单击 "**将所有用户移至池**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="3c272-157">在 "**移动用户**" 中, 选择包含要在**源注册机构池中**移动的用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="3c272-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="3c272-158">在 "**目标注册机构" 池中**, 选择要将用户移动到的池。</span><span class="sxs-lookup"><span data-stu-id="3c272-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="3c272-159">可选如果目标服务器或池不可用, 请选中 "**强制**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3c272-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3c272-160">如果您选择 "**强制**", 则用户帐户将被移动, 但任何相关联的用户数据 (例如, 用户已安排的会议) 都将被删除。</span><span class="sxs-lookup"><span data-stu-id="3c272-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3c272-161">如果不选择该帐户, 将同时移动帐户和关联的数据。</span><span class="sxs-lookup"><span data-stu-id="3c272-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="3c272-162">使用筛选器将用户从一个池移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="3c272-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="3c272-163">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3c272-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c272-164">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3c272-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3c272-165">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3c272-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c272-166">在 "**用户搜索**" 中, 单击 "**搜索**", 然后单击 "**添加筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="3c272-167">在搜索条件中, 选择 "**注册机构池**", 选择 "**等于**", 选择 "**当前池 FQDN**", 然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="3c272-168">在 "**操作**" 菜单上, 单击 "**将所有用户移至池**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c272-169">将筛选器应用于现有用户集时, 选项 "**将所有用户移至池中**" 将位于已筛选的用户子集的上下文中, 而不是**所有**可能的用户。</span><span class="sxs-lookup"><span data-stu-id="3c272-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="3c272-170">在 "**移动用户**" 中, 选择包含要在**源注册机构池中**移动的用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="3c272-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="3c272-171">在 "**目标注册机构" 池中**, 选择要将用户移动到的池。</span><span class="sxs-lookup"><span data-stu-id="3c272-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="3c272-172">可选如果目标服务器或池不可用, 请选中 "**强制**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3c272-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3c272-173">如果您选择 "**强制**", 则用户帐户将被移动, 但任何相关联的用户数据 (例如, 用户已安排和联系人的会议) 都将被删除。</span><span class="sxs-lookup"><span data-stu-id="3c272-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="3c272-174">如果不选择该帐户, 将同时移动帐户和关联的数据。</span><span class="sxs-lookup"><span data-stu-id="3c272-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="3c272-175">使用 Windows Powershell cmdlet 将用户从一个池移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="3c272-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="3c272-176">根据你运行的 Windows PowerShell 命令 (本地或远程) 的运行方式, 你需要以正确的 Skype for Business 服务器管理角色的成员身份登录, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3c272-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="3c272-177">a.</span><span class="sxs-lookup"><span data-stu-id="3c272-177">a.</span></span> <span data-ttu-id="3c272-178">如果你在本地计算机上运行命令 (例如, 直接登录到前端服务器), 请执行以下操作: 登录到安装了 Skype for Business Server Management Shell 的计算机或具有必要的 RTCUniversalServerAdmins 组的成员如 "**委派设置权限**" 中所述的用户权限。</span><span class="sxs-lookup"><span data-stu-id="3c272-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="3c272-179">b.</span><span class="sxs-lookup"><span data-stu-id="3c272-179">b.</span></span> <span data-ttu-id="3c272-180">如果您在另一台计算机上远程运行命令 (例如, 登录到计算机并在标准版前端服务器上远程运行命令): 从分配给 CsUserAdministrator 角色或 CsAdministrator 的用户帐户。角色, 请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3c272-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c272-181">启动 Skype for Business 服务器命令行管理程序: 单击 "**开始**", 单击 "**所有程序**", 单击 " **skype**for Business", 然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="3c272-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3c272-182">若要移动单个用户, 请使用 Move-csuser cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3c272-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="3c272-183">要移动的用户是用户 Pilar Ackerman, 用户将从其当前分配的主池移动到该池 pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3c272-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="3c272-184">若要移动大量用户, 请将筛选器与**move-csuser** cmdlet 配合使用, 并将生成的用户集传递到**move-csuser**:</span><span class="sxs-lookup"><span data-stu-id="3c272-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="3c272-185">**Move-csuser**和**move-csuser**的合并命令可能会导致以下情况:</span><span class="sxs-lookup"><span data-stu-id="3c272-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


