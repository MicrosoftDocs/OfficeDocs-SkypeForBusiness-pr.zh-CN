---
title: 自定义业务服务器 2015年的 Skype 用户帐户属性
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 可以使用本节中的过程修改单个用户帐户属性。
ms.openlocfilehash: fc15dac499fe5d812d5d084a919db10096e6dc56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="customize-user-account-properties-for-skype-for-business-server-2015"></a><span data-ttu-id="deaf3-103">自定义业务服务器 2015年的 Skype 用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="deaf3-103">Customize user account properties for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="deaf3-104">可以使用本节中的过程修改单个用户帐户属性。</span><span class="sxs-lookup"><span data-stu-id="deaf3-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="deaf3-105">有可以在单个用户级别完成的两个基本操作：</span><span class="sxs-lookup"><span data-stu-id="deaf3-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="deaf3-106">配置电话服务使用特定用户帐户的选项</span><span class="sxs-lookup"><span data-stu-id="deaf3-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="deaf3-107">将用户移动到其他池</span><span class="sxs-lookup"><span data-stu-id="deaf3-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="deaf3-108">配置电话服务使用特定用户帐户的选项</span><span class="sxs-lookup"><span data-stu-id="deaf3-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="deaf3-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="deaf3-109"></span></span>

<span data-ttu-id="deaf3-110">（前提是个人用户已启用的 Skype 业务服务器 2015年和组织支持电话服务），可以自定义特定用户的电话设置。</span><span class="sxs-lookup"><span data-stu-id="deaf3-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server 2015 and the organization supports telephony).</span></span>
  
<span data-ttu-id="deaf3-111">Skype 的业务用户电话选项如下所示：</span><span class="sxs-lookup"><span data-stu-id="deaf3-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="deaf3-112">**音频/视频被禁用**用户不能调用带有音频和视频。</span><span class="sxs-lookup"><span data-stu-id="deaf3-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="deaf3-113">**PC 到 PC 只**用户可仅 PC 到 PC 音频或视频通话。</span><span class="sxs-lookup"><span data-stu-id="deaf3-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="deaf3-114">**企业语音**用户可以使用 Skype 业务服务器 2015年基础结构将所有传入和传出呼叫的路由。</span><span class="sxs-lookup"><span data-stu-id="deaf3-114">**Enterprise Voice** The user can use the Skype for Business Server 2015 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="deaf3-115">用户还可以进行 PC 到 PC 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="deaf3-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="deaf3-116">**远程呼叫控制**用户可以使用 Skype 的业务服务器 2015年控制桌面电话，并且还可以进行 PC 到 PC 的调用。</span><span class="sxs-lookup"><span data-stu-id="deaf3-116">**Remote call control** The user can use Skype for Business Server 2015 to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="deaf3-117">有关配置电话服务组织的详细信息，请参阅部署文档中[启用企业语音中业务服务器 2015年的 Skype 的用户](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)和[业务服务器 2015年的 Skype 在部署企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="deaf3-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="deaf3-118">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="deaf3-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="deaf3-119">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="deaf3-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="deaf3-120">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="deaf3-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="deaf3-121">在**搜索用户**框中，键入全部或第一部分的显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或统一资源标识符 (URI) 的用户帐户，您希望，并单击**查找行**.</span><span class="sxs-lookup"><span data-stu-id="deaf3-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="deaf3-122">在表中，单击想要修改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="deaf3-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="deaf3-123">在**编辑**菜单上，单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="deaf3-124">在**电话服务**中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="deaf3-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="deaf3-125">若要禁用用户的音频和视频呼叫，请单击**禁用音频/视频**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="deaf3-126">若要启用 PC 到 PC 的音频通信的用户，但没有远程呼叫控制或企业语音，请单击**PC 到 PC 只**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="deaf3-127">为用户对 PC 到 PC 的音频通信电话**线路**uri 中指定一个值。</span><span class="sxs-lookup"><span data-stu-id="deaf3-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="deaf3-128">若要将用户的电话路由通过 Skype 业务基础结构的服务策略，包括 PC 到 PC 的音频通信类根据单击**企业语音**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="deaf3-129">在**行的 URI**，指定企业语音的电话号码。</span><span class="sxs-lookup"><span data-stu-id="deaf3-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="deaf3-130">在**拨号计划策略**和**语音策略**，指定用户的相应策略。</span><span class="sxs-lookup"><span data-stu-id="deaf3-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="deaf3-131">若要指定用于转换为 E.164 格式的用户拨入的电话号码规范化规则，选择适当的位置配置文件**位置策略**中。</span><span class="sxs-lookup"><span data-stu-id="deaf3-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="deaf3-132">若要启用远程调用控件，使用户能够控制从 Skype 的业务服务器 2015 进行 PC 到 PC 的呼叫和 PC 到电话的呼叫其桌面电话线路，请单击**远程呼叫控制**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server 2015 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="deaf3-133">在**行的 URI**，指定远程呼叫控制的电话号码。</span><span class="sxs-lookup"><span data-stu-id="deaf3-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="deaf3-134">用户必须具有桌面电话和专用分组交换机 (PBX) 连接以将呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="deaf3-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="deaf3-135">将用户移动到其他池</span><span class="sxs-lookup"><span data-stu-id="deaf3-135">Move users to another pool</span></span>
<span data-ttu-id="deaf3-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="deaf3-136"></span></span>

<span data-ttu-id="deaf3-137">Skype 业务服务器控件面板用于将用户分配到特定的服务器或池。</span><span class="sxs-lookup"><span data-stu-id="deaf3-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="deaf3-138">将所有现有用户移动源库运行 Lync Server 2010 中或更早版本复杂的活动目录环境中的业务服务器 2015年目标池的 Skype 可能会导致速度慢的 Active Directory 复制。</span><span class="sxs-lookup"><span data-stu-id="deaf3-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server 2015 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="deaf3-139">若要避免此问题，可以使用搜索筛选器从池中正在运行 Lync Server 2010 中的移动用户或前面单独设置，也可以使用 Skype 业务服务器管理外壳为移动用户提供 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="deaf3-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="deaf3-140">同时，筛选器功能与 Skype 业务服务器 2015年用户工作。</span><span class="sxs-lookup"><span data-stu-id="deaf3-140">Also, the filter functionality works with Skype for Business Server 2015 users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="deaf3-141">若要将选定的用户移动到其他服务器或池</span><span class="sxs-lookup"><span data-stu-id="deaf3-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="deaf3-142">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="deaf3-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="deaf3-143">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="deaf3-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="deaf3-144">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="deaf3-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="deaf3-145">在**搜索用户**框中，键入全部或第一部分的显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或统一资源标识符 (URI) 的用户帐户，您希望，并单击**查找行**.</span><span class="sxs-lookup"><span data-stu-id="deaf3-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="deaf3-146">在表中，选择某一特定用户或用户列表中。</span><span class="sxs-lookup"><span data-stu-id="deaf3-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="deaf3-147">在**操作**菜单上，单击**移动到池的所选的用户**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="deaf3-148">在**移动用户**选择您想要将用户移动到**目标注册**池中的池。</span><span class="sxs-lookup"><span data-stu-id="deaf3-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="deaf3-149">（可选）如果目标服务器或池不可用，请选择**强制**复选框。</span><span class="sxs-lookup"><span data-stu-id="deaf3-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="deaf3-150">如果选择了**强制**，移动用户帐户，但删除任何关联的用户数据 （例如，用户已安排的会议）。</span><span class="sxs-lookup"><span data-stu-id="deaf3-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="deaf3-151">如果不选取它，移动帐户和相关联的数据。</span><span class="sxs-lookup"><span data-stu-id="deaf3-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="deaf3-152">将所有用户从一个服务器或池移动到其他服务器或池</span><span class="sxs-lookup"><span data-stu-id="deaf3-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="deaf3-153">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="deaf3-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="deaf3-154">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="deaf3-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="deaf3-155">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="deaf3-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="deaf3-156">在**操作**菜单上，单击**移动到池中的所有用户**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="deaf3-157">在**移动用户**选择包含您想要在**源池注册器**中移动用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="deaf3-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="deaf3-158">在**目标注册池**，选择您想要将用户移动到的池。</span><span class="sxs-lookup"><span data-stu-id="deaf3-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="deaf3-159">（可选）如果目标服务器或池不可用，请选择**强制**复选框。</span><span class="sxs-lookup"><span data-stu-id="deaf3-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="deaf3-160">如果选择了**强制**，移动用户帐户，但删除任何关联的用户数据 （例如，用户已安排的会议）。</span><span class="sxs-lookup"><span data-stu-id="deaf3-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="deaf3-161">如果不选取它，移动帐户和相关联的数据。</span><span class="sxs-lookup"><span data-stu-id="deaf3-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="deaf3-162">若要使用筛选器将用户从一个池移动到其他池</span><span class="sxs-lookup"><span data-stu-id="deaf3-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="deaf3-163">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="deaf3-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="deaf3-164">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="deaf3-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="deaf3-165">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="deaf3-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="deaf3-166">在**用户搜索**中，单击**搜索**，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="deaf3-167">在搜索条件中，选择**注册池**，选择**等于**，选择**当前池的 FQDN**，，然后单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="deaf3-168">在**操作**菜单上，单击**移动到池中的所有用户**。</span><span class="sxs-lookup"><span data-stu-id="deaf3-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="deaf3-169">当筛选器应用于一组现有用户中，**移动到池中的所有用户**将筛选出的那部分用户，没有**所有**可能的用户的上下文中的选项。</span><span class="sxs-lookup"><span data-stu-id="deaf3-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="deaf3-170">在**移动用户**选择包含您想要在**源池注册器**中移动用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="deaf3-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="deaf3-171">在**目标注册池**，选择您想要移动用户的池。</span><span class="sxs-lookup"><span data-stu-id="deaf3-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="deaf3-172">（可选）如果目标服务器或池不可用，请选择**强制**复选框。</span><span class="sxs-lookup"><span data-stu-id="deaf3-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="deaf3-173">如果选择了**强制**，移动用户帐户，但任何关联的用户数据则会删除 （例如，用户已计划的会议和联系人）。</span><span class="sxs-lookup"><span data-stu-id="deaf3-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="deaf3-174">如果不选取它，移动帐户和相关联的数据。</span><span class="sxs-lookup"><span data-stu-id="deaf3-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="deaf3-175">若要将用户从一个池移动到另一个使用 Windows Powershell cmdlet</span><span class="sxs-lookup"><span data-stu-id="deaf3-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="deaf3-176">这取决于如何运行 Windows PowerShell 命令时 （即本地或远程），您需要登录正确 Skype 业务服务器 2015年管理角色的成员，如下所示：</span><span class="sxs-lookup"><span data-stu-id="deaf3-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server 2015 administrative roles as follows:</span></span>
    
   <span data-ttu-id="deaf3-177">a.</span><span class="sxs-lookup"><span data-stu-id="deaf3-177">a.</span></span> <span data-ttu-id="deaf3-178">如果本地计算机 （例如，登录直接到前端服务器） 上运行这些命令： 登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或具有所需的安装位置的计算机所述**代理安装程序权限**的用户权限。</span><span class="sxs-lookup"><span data-stu-id="deaf3-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="deaf3-179">b.</span><span class="sxs-lookup"><span data-stu-id="deaf3-179">b.</span></span> <span data-ttu-id="deaf3-180">如果您正在另一台计算机上远程运行命令 （例如，您登录到您的计算机上，在标准版前端服务器上远程运行命令）： 从用户帐户分配到 CsUserAdministrator 角色或 CsAdministrator角色，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="deaf3-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="deaf3-181">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="deaf3-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="deaf3-182">要移动一个用户，使用移动 CsUser cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="deaf3-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="deaf3-183">其中用户可以移动赵华，用户和用户将会从移动他们当前已分配的主池到池 pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="deaf3-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="deaf3-184">若要移动大量的用户，对**Get CsUser** cmdlet 使用筛选器和传递到**移动 CsUser**得到的用户集：</span><span class="sxs-lookup"><span data-stu-id="deaf3-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="deaf3-185">**获得 CsUser**和**移动 CsUser**的组合的命令可能会导致于：</span><span class="sxs-lookup"><span data-stu-id="deaf3-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


