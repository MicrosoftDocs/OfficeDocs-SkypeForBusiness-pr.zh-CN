---
title: 自定义 Skype for Business Server 的用户帐户属性
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
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 您可以使用本节中的过程修改单个用户帐户属性。
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826262"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="45bfa-103">自定义 Skype for Business Server 的用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="45bfa-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="45bfa-104">您可以使用本节中的过程修改单个用户帐户属性。</span><span class="sxs-lookup"><span data-stu-id="45bfa-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="45bfa-105">可以在单个用户级别执行两个基本操作：</span><span class="sxs-lookup"><span data-stu-id="45bfa-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="45bfa-106">为特定用户帐户配置电话选项</span><span class="sxs-lookup"><span data-stu-id="45bfa-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="45bfa-107">将用户移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="45bfa-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="45bfa-108">为特定用户帐户配置电话选项</span><span class="sxs-lookup"><span data-stu-id="45bfa-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="45bfa-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="45bfa-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="45bfa-110">你可以为特定用户自定义电话设置 (只要为单个用户启用了 Skype for Business Server，并且组织支持电话服务) 。</span><span class="sxs-lookup"><span data-stu-id="45bfa-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="45bfa-111">Skype for Business Server 用户电话选项包括：</span><span class="sxs-lookup"><span data-stu-id="45bfa-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="45bfa-112">**禁用音频/视频** 用户无法使用音频和视频进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="45bfa-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="45bfa-113">**仅 PC 到 PC** 用户只能进行 PC 到 PC 音频或视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="45bfa-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="45bfa-114">**企业语音** 用户可以使用 Skype for Business Server 基础结构路由所有传入和传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="45bfa-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="45bfa-115">用户还可以进行 PC 到 PC 呼叫。</span><span class="sxs-lookup"><span data-stu-id="45bfa-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="45bfa-116">**远程呼叫控制** 用户可以使用 Skype for Business Server 控制桌面电话，还可以进行 PC 到 PC 呼叫。</span><span class="sxs-lookup"><span data-stu-id="45bfa-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="45bfa-117">有关为组织配置电话的详细信息，请参阅部署文档中的"在 Skype for Business Server 中为用户启用[企业语音，](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)在 Skype for Business Server 中部署[企业语音。](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)</span><span class="sxs-lookup"><span data-stu-id="45bfa-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="45bfa-118">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="45bfa-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45bfa-119">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="45bfa-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="45bfa-120">在左侧导航栏中，单击“用户”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="45bfa-121">在 **“搜索用户”** 框中，键入所需用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击 **“查找”**。</span><span class="sxs-lookup"><span data-stu-id="45bfa-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="45bfa-122">在表中，单击要修改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="45bfa-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="45bfa-123">在“编辑”菜单上，单击“修改”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="45bfa-124">在“电话”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="45bfa-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="45bfa-125">要为用户禁用音频和视频呼叫，请单击“禁用音频/视频”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="45bfa-p102">要为用户启用 PC 到 PC 音频通信，但不启用远程呼叫控制或企业语音，请单击“仅限 PC 到 PC”。为用户用于进行 PC 到 PC 音频通信的电话指定“线路 URI”值。</span><span class="sxs-lookup"><span data-stu-id="45bfa-p102">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="45bfa-128">若要根据服务策略类别（包括 PC 到 PC 音频通信）使用 Skype for Business 基础结构路由用户电话呼叫，请单击 **企业语音。**</span><span class="sxs-lookup"><span data-stu-id="45bfa-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="45bfa-129">在“线路 URI”中，指定用于企业语音的电话号码。</span><span class="sxs-lookup"><span data-stu-id="45bfa-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="45bfa-130">在“拨号计划策略”和“语音策略”中，为用户指定相应的策略。</span><span class="sxs-lookup"><span data-stu-id="45bfa-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="45bfa-131">要指定用于将用户拨打的电话号码转换为 E.164 格式的规范化规则，请在“位置策略”中选择相应的位置配置文件。</span><span class="sxs-lookup"><span data-stu-id="45bfa-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="45bfa-132">若要启用远程呼叫控制，从而使用户能够控制其桌面电话线路从 Skype for Business Server 进行 PC 到 PC 呼叫和 PC 到电话呼叫，请单击 **"远程呼叫控制"。**</span><span class="sxs-lookup"><span data-stu-id="45bfa-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="45bfa-133">在“线路 URI”中，指定用于远程呼叫控制的电话号码。</span><span class="sxs-lookup"><span data-stu-id="45bfa-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="45bfa-134">要进行呼叫路由，用户必须具有桌面电话和专用交换机 (PBX) 连接。</span><span class="sxs-lookup"><span data-stu-id="45bfa-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="45bfa-135">将用户移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="45bfa-135">Move users to another pool</span></span>
<span data-ttu-id="45bfa-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="45bfa-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="45bfa-137">可以使用 Skype for Business Server 控制面板将用户分配到特定服务器或池。</span><span class="sxs-lookup"><span data-stu-id="45bfa-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="45bfa-138">将所有现有用户从运行 Lync Server 2010 或更早的源池移动到复杂 Active Directory 环境中 Skype for Business Server 目标池可能会导致 Active Directory 复制速度变慢。</span><span class="sxs-lookup"><span data-stu-id="45bfa-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="45bfa-139">为了避免这种情况，您可以使用搜索筛选器将用户从单独运行 Lync Server 2010 或更早版本池移动，或者可以使用 Skype for Business Server 命令行管理程序移动带 cmdlet 的用户。</span><span class="sxs-lookup"><span data-stu-id="45bfa-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="45bfa-140">此外，筛选器功能适用于 Skype for Business Server 用户。</span><span class="sxs-lookup"><span data-stu-id="45bfa-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="45bfa-141">将所选用户移至其他服务器或池</span><span class="sxs-lookup"><span data-stu-id="45bfa-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="45bfa-142">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="45bfa-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45bfa-143">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="45bfa-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="45bfa-144">在左侧导航栏中，单击“用户”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="45bfa-145">在“搜索用户”框中，键入所需用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="45bfa-146">在表中，选择列表中的一个或多个特定用户。</span><span class="sxs-lookup"><span data-stu-id="45bfa-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="45bfa-147">在“操作”菜单中，单击“将所选用户移动到池”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="45bfa-148">在“移动用户”的“目标注册器池”中，选择要将用户移动到的池。</span><span class="sxs-lookup"><span data-stu-id="45bfa-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="45bfa-149">（可选）如果目标服务器或池不可用，则选中“强制”复选框。</span><span class="sxs-lookup"><span data-stu-id="45bfa-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="45bfa-p106">如果选中“强制”，将移动用户帐户，但会删除任何关联的用户数据（例如，用户已安排的会议）。如果不选中，将同时移动帐户和关联数据。</span><span class="sxs-lookup"><span data-stu-id="45bfa-p106">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="45bfa-152">将所有用户从一个服务器或池移至另一个服务器或池</span><span class="sxs-lookup"><span data-stu-id="45bfa-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="45bfa-153">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="45bfa-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45bfa-154">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="45bfa-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="45bfa-155">在左侧导航栏中，单击“用户”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="45bfa-156">在“操作”菜单上，单击“将所有用户移动到池”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="45bfa-157">在“移动用户”的“源注册器池”中，选择包含要移动的用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="45bfa-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="45bfa-158">在“目标注册器池”中，选择要将用户移动到的池。</span><span class="sxs-lookup"><span data-stu-id="45bfa-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="45bfa-159">（可选）如果目标服务器或池不可用，则选中“强制”复选框。</span><span class="sxs-lookup"><span data-stu-id="45bfa-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="45bfa-p107">如果选中“强制”，将移动用户帐户，但会删除任何关联的用户数据（例如，用户已安排的会议）。如果不选中，将同时移动帐户和关联数据。</span><span class="sxs-lookup"><span data-stu-id="45bfa-p107">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="45bfa-162">使用筛选器将用户从一个池移至另一个池</span><span class="sxs-lookup"><span data-stu-id="45bfa-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="45bfa-163">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="45bfa-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45bfa-164">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="45bfa-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="45bfa-165">在左侧导航栏中，单击“用户”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="45bfa-166">在 **"用户搜索**"中，**单击"搜索**"，然后单击"**添加筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="45bfa-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="45bfa-167">在搜索条件中，依次选择“注册器池”、“等于”和“当前池 FQDN”，然后单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="45bfa-168">在“操作”菜单上，单击“将所有用户移动到池”。</span><span class="sxs-lookup"><span data-stu-id="45bfa-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45bfa-169">将筛选器应用于现有用户组时，选项“将所有用户移动到池”出现在经过筛选的用户子集上下文中，而不是出现在 **所有** 可能的用户上下文中。</span><span class="sxs-lookup"><span data-stu-id="45bfa-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="45bfa-170">在“移动用户”的“源注册器池”中，选择包含要移动的用户帐户的池。</span><span class="sxs-lookup"><span data-stu-id="45bfa-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="45bfa-171">在“目标注册器池”中，选择要将用户移动到的池。</span><span class="sxs-lookup"><span data-stu-id="45bfa-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="45bfa-172">（可选）如果目标服务器或池不可用，则选中“强制”复选框。</span><span class="sxs-lookup"><span data-stu-id="45bfa-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="45bfa-p108">如果选中“强制”，将移动用户帐户，但会删除任何关联的用户数据（例如，用户已安排的会议和联系人）。如果不选中，将同时移动帐户和关联数据。</span><span class="sxs-lookup"><span data-stu-id="45bfa-p108">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="45bfa-175">使用 Windows Powershell cmdlet 将用户从一个池移动到另一个池</span><span class="sxs-lookup"><span data-stu-id="45bfa-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="45bfa-176">根据运行 Windows PowerShell 命令 (（本地或远程) ）的不同，你需要以正确的 Skype for Business Server 管理角色成员登录，如下所示：</span><span class="sxs-lookup"><span data-stu-id="45bfa-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="45bfa-177">a.</span><span class="sxs-lookup"><span data-stu-id="45bfa-177">a.</span></span> <span data-ttu-id="45bfa-178">例如，如果在本地计算机上运行命令 (，请直接登录到前端服务器) ：以 RTCUniversalServerAdmins 组的成员或具有委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序的计算机。 </span><span class="sxs-lookup"><span data-stu-id="45bfa-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="45bfa-179">b.</span><span class="sxs-lookup"><span data-stu-id="45bfa-179">b.</span></span> <span data-ttu-id="45bfa-180">例如，如果在另一台计算机 (远程运行命令，请登录到计算机，在 Standard Edition 前端服务器) 上远程运行命令：从分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="45bfa-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45bfa-181">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，单击 **"Skype for Business"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="45bfa-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="45bfa-182">若要移动单个用户，请按如下方式使用 Move-CsUser cmdlet：</span><span class="sxs-lookup"><span data-stu-id="45bfa-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="45bfa-183">其中，要移动的用户是用户 Pilar Ackerman，该用户将从当前分配的主池移至 pool01.contoso.net 池</span><span class="sxs-lookup"><span data-stu-id="45bfa-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="45bfa-184">若要移动大量用户，请将筛选器与 **Get-CsUser** cmdlet 配合使用，并将生成的用户组传递给 **Move-CsUser**：</span><span class="sxs-lookup"><span data-stu-id="45bfa-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="45bfa-185">**Get-CsUser** 和 **Move-CsUser** 命令结合使用时可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="45bfa-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


