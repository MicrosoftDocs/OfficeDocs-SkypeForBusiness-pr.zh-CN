---
title: 使用 Skype for Business Server 2015 应力和性能工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: 若要运行 Skype for Business Server 2015 应力和性能工具，你需要能够同时管理用户、联系人和用户配置文件、配置工具以运行，然后查看工具生成的输出或结果。
ms.openlocfilehash: 0bdffee133e583ebaf4177d3226479838495c69f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888861"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="8f911-103">使用 Skype for Business Server 2015 应力和性能工具</span><span class="sxs-lookup"><span data-stu-id="8f911-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="8f911-104">若要运行 Skype for Business Server 2015 应力和性能工具，你需要能够同时管理用户、联系人和用户配置文件、配置工具以运行，然后查看工具生成的输出或结果。</span><span class="sxs-lookup"><span data-stu-id="8f911-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="8f911-105">运行 Skype for Business Server 2015 应力和性能工具（可执行文件为 LyncPerfTool）有四个区域：</span><span class="sxs-lookup"><span data-stu-id="8f911-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="8f911-106">创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="8f911-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="8f911-107">配置用户配置文件</span><span class="sxs-lookup"><span data-stu-id="8f911-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="8f911-108">运行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="8f911-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="8f911-109">解释结果</span><span class="sxs-lookup"><span data-stu-id="8f911-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="8f911-110">创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="8f911-110">Create Users and Contacts</span></span>
<span data-ttu-id="8f911-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="8f911-111"><a name="BKMK_CreateUsersAndContacts"> </a></span></span>

<span data-ttu-id="8f911-112">你需要使用 Skype for Business Server 2015 （SB 2015）用户预配工具（UserProvisioningTool）为你的压力和性能测试创建用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="8f911-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="8f911-113">这是在阅读主题时可能有用的有用术语列表：</span><span class="sxs-lookup"><span data-stu-id="8f911-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="8f911-114">**组织单位**-Active Directory 域服务（AD DS）组织单位（OU）。</span><span class="sxs-lookup"><span data-stu-id="8f911-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="8f911-115">**联盟/跨库**-可以与其他即时消息（IM）服务中的用户进行通信的用户。</span><span class="sxs-lookup"><span data-stu-id="8f911-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="8f911-116">**通讯组列表**或 DLs。</span><span class="sxs-lookup"><span data-stu-id="8f911-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="8f911-117">这些是 AD DS 中的对象，其中包含广告 DS 用户的列表。</span><span class="sxs-lookup"><span data-stu-id="8f911-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="8f911-118">它们用于促进跨用户组的通信。</span><span class="sxs-lookup"><span data-stu-id="8f911-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="8f911-119">**位置信息服务**-Skype For business Server 2015 服务，每个电话启用并配置该服务时，都允许检索增强的911（E911）服务的物理位置。</span><span class="sxs-lookup"><span data-stu-id="8f911-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="8f911-120">**美国电话号码**-除了用于在反向号码查找（RNL）路由入站和出站呼叫的 SIP URI 之外，还分配给用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="8f911-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="8f911-121">使用 UserProvisioningTool 创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="8f911-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="8f911-122">在开始之前，请务必确保你已作为域管理员安全组的成员登录以运行此工具。</span><span class="sxs-lookup"><span data-stu-id="8f911-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="8f911-123">你需要执行此操作，因为你将创建 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="8f911-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="8f911-124">您必须使用 Skype for Business 服务器用户预配工具为负载模拟创建用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="8f911-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="8f911-125">Skype for business **Server 用户预配工具**随**Skype For business 服务器压力和性能工具**包一起安装。</span><span class="sxs-lookup"><span data-stu-id="8f911-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="8f911-126">请确保程序包安装程序（CapacityPlanningTool）已在前端服务器或你想要测试的标准版服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="8f911-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="8f911-127">你可以通过在前端服务器或标准版服务器上运行文件 UserProvisioningTool （位于% InstalledDirectory% LyncStressAndPerfTool \ LyncStress）来启动 Skype for Business Server 用户预配工具。</span><span class="sxs-lookup"><span data-stu-id="8f911-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8f911-128">当创建大量用户（例如，10000或更多）时，请运行 UserProvisioningTool。</span><span class="sxs-lookup"><span data-stu-id="8f911-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="8f911-129">你将需要执行此操作，因为该工具将创建和配置*新*的 AD 用户。</span><span class="sxs-lookup"><span data-stu-id="8f911-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="8f911-130">当用户预配工具打开时，单击 "配置"，然后选择 "加载配置"。</span><span class="sxs-lookup"><span data-stu-id="8f911-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="8f911-131">若要开始配置用户和联系人，请加载程序包中包含的默认文件，名为 "SampleData"。</span><span class="sxs-lookup"><span data-stu-id="8f911-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="8f911-132">这将预填充示例数据的字段，你需要更改这些字段才能使其与你的部署相关。</span><span class="sxs-lookup"><span data-stu-id="8f911-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="8f911-133">如果你有一个已经包含自定义设置的预配置 XML 文件，则可以改为加载该文件。</span><span class="sxs-lookup"><span data-stu-id="8f911-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="8f911-134">填写 "用户预配" 工具中的字段，如下部分所述。</span><span class="sxs-lookup"><span data-stu-id="8f911-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="8f911-135">要配置服务器选项，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8f911-135">To configure server options:</span></span>

1. <span data-ttu-id="8f911-136">在 "**前端池 FQDN** " 字段中，键入标准版服务器的完全限定的域名（FQDN），或者键入要在其中托管用户的前端池的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="8f911-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="8f911-137">在 "**用户名前缀**" 字段中，键入要用于为测试目的 bust 用户名的前缀（如 "TestUser"）。</span><span class="sxs-lookup"><span data-stu-id="8f911-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="8f911-138">在 "**密码**" 字段中，键入将跨所有测试用户帐户使用的密码。</span><span class="sxs-lookup"><span data-stu-id="8f911-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="8f911-139">在 "**帐户域**" 字段中，键入当前 AD 域（要在其中创建测试用户）的域名。</span><span class="sxs-lookup"><span data-stu-id="8f911-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="8f911-140">在 "**组织单位**" 字段中，键入要在其中创建这些测试用户的 AD 域的名称。</span><span class="sxs-lookup"><span data-stu-id="8f911-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="8f911-141">（如果该 OU 尚不存在，将为你创建它）。</span><span class="sxs-lookup"><span data-stu-id="8f911-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="8f911-142">在 "**电话区域代码**" 字段中，键入要在所有测试用户帐户中使用的三位数区域代码。</span><span class="sxs-lookup"><span data-stu-id="8f911-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="8f911-143">确保所选区号与广告中的其他用户区域代码不冲突。</span><span class="sxs-lookup"><span data-stu-id="8f911-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="8f911-144">如果要启用企业语音测试用户，请单击以选中 "**已启用语音**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="8f911-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="8f911-145">在 "**用户数**" 字段中，给出要创建的测试用户总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="8f911-146">在 "**开始索引**" 字段中，提供将用作用户名前缀的后缀的起始编号（例如，前缀为 "TestUser"，第一个名称将在下面的示例中以 "0" 结尾）。）</span><span class="sxs-lookup"><span data-stu-id="8f911-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![显示“创建用户”选项卡的“用户设置”工具。](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="8f911-148">"创建用户" 按钮</span><span class="sxs-lookup"><span data-stu-id="8f911-148">Create Users button</span></span>

<span data-ttu-id="8f911-149">单击 "**创建用户**" 按钮时，你输入的输入参数将得到验证。</span><span class="sxs-lookup"><span data-stu-id="8f911-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="8f911-150">如果存在任何验证错误，系统将提示您修复它们。</span><span class="sxs-lookup"><span data-stu-id="8f911-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="8f911-151">或者，如果所有值都是正确的，用户将在广告中显示（在任何指定的 OU 中）。</span><span class="sxs-lookup"><span data-stu-id="8f911-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="8f911-152">在工具运行时，你将在工具底部看到一个进度栏。</span><span class="sxs-lookup"><span data-stu-id="8f911-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="8f911-153">在进度栏处于活动状态时不要关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f911-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="8f911-154">用户创建需要花费时间，因此请相应地进行规划。</span><span class="sxs-lookup"><span data-stu-id="8f911-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="8f911-155">对于大量用户，此过程可能需要几分钟的时间，几分钟时间才可用于几个用户。</span><span class="sxs-lookup"><span data-stu-id="8f911-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="8f911-156">如果你无法访问你的测试环境中的 AD 域控制器，你仍然可以通过以你指定要创建的用户范围中的某个用户身份登录来验证用户创建。</span><span class="sxs-lookup"><span data-stu-id="8f911-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="8f911-157">请记住使用前缀和后缀以及 @sipDomain 作为用户名。</span><span class="sxs-lookup"><span data-stu-id="8f911-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="8f911-158">下面是一个示例： <em>TestUser20@contoso.net</em> 。</span><span class="sxs-lookup"><span data-stu-id="8f911-158">Here is an example:  <em>TestUser20@contoso.net</em>  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f911-159">如果用户已存在，单击 "创建用户" 按钮将通过任何配置更改对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="8f911-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="8f911-160">"删除用户" 按钮</span><span class="sxs-lookup"><span data-stu-id="8f911-160">Delete Users button</span></span>

<span data-ttu-id="8f911-161">单击 "**删除用户**" 按钮时，将验证选项卡的输入参数。</span><span class="sxs-lookup"><span data-stu-id="8f911-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="8f911-162">如果存在验证错误，系统将提示您修复这些错误，如果输入值正确，则将禁用指定的测试用户并将其从 Active Directory 中删除。</span><span class="sxs-lookup"><span data-stu-id="8f911-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="8f911-163">同样，进度栏将出现在此选项卡的底部，不应在进度栏处于活动状态时关闭该应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f911-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f911-164">仅支持美国格式的电话号码。</span><span class="sxs-lookup"><span data-stu-id="8f911-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="8f911-165">电话号码始终分配给用户，并且所有由 UserProvisioningTool 创建的用户在默认情况下都启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="8f911-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="8f911-166">使用电话号码的任何方案（如会议自动助理或 UC PSTN 呼叫）均可使用此电话号码正确路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="8f911-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="8f911-167">出于此原因，*每个用户*都必须有*唯一的电话号码*。</span><span class="sxs-lookup"><span data-stu-id="8f911-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f911-168">**如果你必须创建两次用户，该命令将失败，除非你使用不同的区号，或者使用 Disable-Move-csuser cmdlet 禁用了以前的用户。**</span><span class="sxs-lookup"><span data-stu-id="8f911-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8f911-169">在创建联系人之前，您首先需要完成用户复制（从 "用户" 选项卡完成的操作）。</span><span class="sxs-lookup"><span data-stu-id="8f911-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8f911-170">如果您刚刚创建了用户，则需要等待，直到 Skype for Business 服务器复制完成，并填充数据库中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8f911-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="8f911-171">**如果用户尚未完成复制，您将看到一个错误。**</span><span class="sxs-lookup"><span data-stu-id="8f911-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="8f911-172">如果 Skype for Business Server 2015 前端服务已启动，或者在你指定的总数的最后一个用户上成功运行 Move-csuser cmdlet，你将知道用户已完成复制的时间。</span><span class="sxs-lookup"><span data-stu-id="8f911-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="8f911-173">"创建联系人" 选项卡</span><span class="sxs-lookup"><span data-stu-id="8f911-173">Contacts Creation tab</span></span>

<span data-ttu-id="8f911-174">此选项卡允许你为你的测试提供用户的联系人详细信息。</span><span class="sxs-lookup"><span data-stu-id="8f911-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![显示“创建内容”选项卡的“用户设置”工具。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="8f911-176">若要配置用户的联系人，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8f911-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="8f911-177">在 "**每位用户平均联系人**" 字段中，输入要在联系人列表中为每位用户填充的平均联系人数。</span><span class="sxs-lookup"><span data-stu-id="8f911-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="8f911-178">如果要为每位用户创建同等数量的联系人，请选中 "**固定**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="8f911-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="8f911-179">如果想要更改为用户创建的联系人数量，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="8f911-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="8f911-180">在 "**每位用户的平均联系人组**" 字段中，输入每位用户的联系人组数。</span><span class="sxs-lookup"><span data-stu-id="8f911-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="8f911-181">此号码必须小于**每位用户的平均联系**人数。</span><span class="sxs-lookup"><span data-stu-id="8f911-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="8f911-182">在 "**联盟/跨池联系人百分比**" 字段中，为介于0和100之间的数字。</span><span class="sxs-lookup"><span data-stu-id="8f911-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="8f911-183">此联系人的百分比将与联盟用户一起创建。</span><span class="sxs-lookup"><span data-stu-id="8f911-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="8f911-184">在 "**联盟/跨池用户前缀**" 字段中，为将添加到本地用户的联系人列表的联盟用户提供用户名。</span><span class="sxs-lookup"><span data-stu-id="8f911-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="8f911-185">在 "**联盟/跨池用户 SIP 域**" 字段中，为联盟用户提供 SIP 域名称。</span><span class="sxs-lookup"><span data-stu-id="8f911-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="8f911-186">在 "**用户创建**" 选项卡中，请确保信息正确。</span><span class="sxs-lookup"><span data-stu-id="8f911-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="8f911-187">将从 "用户创建" 选项卡上的值创建联系人。</span><span class="sxs-lookup"><span data-stu-id="8f911-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="8f911-188">单击 "**创建联系人**" 以开始创建联系人。</span><span class="sxs-lookup"><span data-stu-id="8f911-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="8f911-189">此过程可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="8f911-189">This process can take several minutes.</span></span> <span data-ttu-id="8f911-190">完成后，将出现一个对话框，其中显示 "操作已成功完成" 消息。</span><span class="sxs-lookup"><span data-stu-id="8f911-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="8f911-191">你可以通过以用户 "创建" 选项卡上创建的用户身份登录来验证已创建的联系人。</span><span class="sxs-lookup"><span data-stu-id="8f911-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8f911-192">创建联系人后，此工具将重新启动目标池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="8f911-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="8f911-193">可能需要更长时间（最多2小时）才能启动前端服务器，具体取决于此操作创建的联系人数量。</span><span class="sxs-lookup"><span data-stu-id="8f911-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="8f911-194">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="8f911-194">Distribution List</span></span>

<span data-ttu-id="8f911-195">Skype for Business Server 2015 应力和性能工具可以模拟 Skype for Business 2015 客户端中的通讯组列表（DL）扩展功能。</span><span class="sxs-lookup"><span data-stu-id="8f911-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="8f911-196">如果您不打算在用户预配工具中启用 DL 扩展，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="8f911-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![显示“创建通讯组列表”选项卡的“用户设置”工具。](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="8f911-198">通过 "通讯组列表" 选项卡，你可以创建压力和性能工具将用于通讯组列表扩展功能的 DLs。</span><span class="sxs-lookup"><span data-stu-id="8f911-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="8f911-199">在创建 Dl 之前，需要部署 Skype for business Server 2015，包括运行 ForestPrep。</span><span class="sxs-lookup"><span data-stu-id="8f911-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="8f911-200">如果未执行此操作，则不会在 AD 架构中存在 DL 属性，因此该工具将无法创建 Dl。</span><span class="sxs-lookup"><span data-stu-id="8f911-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="8f911-201">要配置通讯组列表，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8f911-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="8f911-202">在 "**通讯组列表数**" 字段中，提供要创建的 DLs 的总数（此处的建议是，您开始的值是您拥有的用户数的两倍。）</span><span class="sxs-lookup"><span data-stu-id="8f911-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="8f911-203">在 "**通讯组列表前缀**" 字段中，输入你创建的所有 DLs 将具有的前缀，例如*testDL* 。</span><span class="sxs-lookup"><span data-stu-id="8f911-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="8f911-204">这意味着，在 100 Dl 中，你的 DL 名称将如下所示： testDL0、testDL1、最高 testDL99。</span><span class="sxs-lookup"><span data-stu-id="8f911-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="8f911-205">在 Dist 的 "**最少成员" 列表**中，输入要放在每个 DL 中的最小用户数。</span><span class="sxs-lookup"><span data-stu-id="8f911-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="8f911-206">在 " **Dist" 的最大成员中**，输入要在每个 DL 中添加的最大用户数。</span><span class="sxs-lookup"><span data-stu-id="8f911-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="8f911-207">创建通讯组列表按钮</span><span class="sxs-lookup"><span data-stu-id="8f911-207">Create Distribution Lists button</span></span>

<span data-ttu-id="8f911-208">单击 "创建通讯组列表" 按钮时，该工具将查询 Active Directory 以查看是否存在与前缀和号码相匹配的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="8f911-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="8f911-209">该工具将创建任何尚不存在的 Dl。</span><span class="sxs-lookup"><span data-stu-id="8f911-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="8f911-210">将成员添加到这些新创建的通讯组列表时，它将从 "用户创建" 选项卡上指定的范围内选择用户。</span><span class="sxs-lookup"><span data-stu-id="8f911-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="8f911-211">位置信息服务配置选项卡</span><span class="sxs-lookup"><span data-stu-id="8f911-211">Location Info Service Config tab</span></span>

<span data-ttu-id="8f911-212">Skype for Business Server 2015 应力和性能工具还可以为位置信息服务生成虚拟配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f911-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="8f911-213">请注意，位置信息服务通常对服务器性能没有显著影响。</span><span class="sxs-lookup"><span data-stu-id="8f911-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![显示“位置信息服务配置”选项卡的“用户设置”工具。](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="8f911-215">如果你选择测试此功能，请填写表单中的值，然后单击 "生成 IIS 配置文件" 按钮（将创建该按钮）。名为的 CSV 文件：</span><span class="sxs-lookup"><span data-stu-id="8f911-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="8f911-216">LIS_Subnet .csv</span><span class="sxs-lookup"><span data-stu-id="8f911-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="8f911-217">LIS_Switches .csv</span><span class="sxs-lookup"><span data-stu-id="8f911-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="8f911-218">LIS_Ports .csv</span><span class="sxs-lookup"><span data-stu-id="8f911-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="8f911-219">LIS_WAP .csv</span><span class="sxs-lookup"><span data-stu-id="8f911-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="8f911-220">若要将这些文件导入到 .LIS 数据库中，请使用以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8f911-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="8f911-221">Set-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="8f911-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="8f911-222">Set-CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="8f911-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="8f911-223">Set-CsLisPort</span><span class="sxs-lookup"><span data-stu-id="8f911-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="8f911-224">Set-CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="8f911-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="8f911-225">配置用户配置文件</span><span class="sxs-lookup"><span data-stu-id="8f911-225">Configure User Profile</span></span>
<span data-ttu-id="8f911-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="8f911-226"><a name="BKMK_UserProfile"> </a></span></span>

<span data-ttu-id="8f911-227">创建用户后（通过用户创建工具），您可以使用 Skype for Business Server 2015 加载配置工具（UserProfileGenerator）配置用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f911-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="8f911-228">运行 Skype for Business Server 2015 加载配置工具</span><span class="sxs-lookup"><span data-stu-id="8f911-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="8f911-229">启动 "加载配置工具" （UserProfileGenerator）并填写选项卡。</span><span class="sxs-lookup"><span data-stu-id="8f911-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="8f911-230">此工具将为每个需要运行模拟的客户端计算机创建一个目录。</span><span class="sxs-lookup"><span data-stu-id="8f911-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="8f911-231">每个客户端目录附带一个脚本，用于启动 Skype for Business Server 2015 应力和性能工具（LyncPerfTool）。</span><span class="sxs-lookup"><span data-stu-id="8f911-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="8f911-232">下面的部分将提供有关如何在 Skype for Business Server 2015 加载配置工具的每个选项卡上填写字段的示例。</span><span class="sxs-lookup"><span data-stu-id="8f911-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8f911-233">"加载配置工具" （UserProfileGenerator）中使用的特定于用户的值必须与池的 Skype for Business Server 2015 用户创建工具（UserProvisioningTool）中指定的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="8f911-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="8f911-234">通用配置选项卡</span><span class="sxs-lookup"><span data-stu-id="8f911-234">Common Configuration tab</span></span>

<span data-ttu-id="8f911-235">"加载配置" 工具的 "**通用配置**" 选项卡如下所示。</span><span class="sxs-lookup"><span data-stu-id="8f911-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="8f911-236">填写 "通用配置" 选项卡的字段，如以下步骤中所述。</span><span class="sxs-lookup"><span data-stu-id="8f911-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![显示“常见配置”选项卡的“用户设置”选项卡。](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="8f911-238">在 "**可用计算机数**" 字段中，键入要用于运行压力和性能工具（LyncPerfTool）的计算机数。</span><span class="sxs-lookup"><span data-stu-id="8f911-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="8f911-239">我们建议你将模拟的每个4500用户拥有一台计算机，但该数字可能因你降低负载级别而异，或者仅使用工具的可用功能子集（在 "常规方案" 选项卡上设置负载级别）。</span><span class="sxs-lookup"><span data-stu-id="8f911-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="8f911-240">在 "**用户名前缀**" 字段中，为所有用户输入 "用户名" 字段的前缀。</span><span class="sxs-lookup"><span data-stu-id="8f911-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="8f911-241">若要登录到 "统一资源标识符（URI）"，请执行以下操作： *UserPrefix [用户开始索引 .。。（用户数-1）]@User 域*，例如 myUser009@Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="8f911-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="8f911-242">在 "**所有用户的密码**" 字段中，输入创建用户期间使用的密码。</span><span class="sxs-lookup"><span data-stu-id="8f911-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="8f911-243">如果将此字段留空，用户名将被设置为密码。</span><span class="sxs-lookup"><span data-stu-id="8f911-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="8f911-244">在 "**用户起始索引**" 字段中，输入要配置的第一个用户的索引。</span><span class="sxs-lookup"><span data-stu-id="8f911-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="8f911-245">你可以为不同类型或不同级别的负载配置不同的范围，但你必须针对要配置的区域运行一次 "加载配置工具" （UserProfileGenerator）。</span><span class="sxs-lookup"><span data-stu-id="8f911-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="8f911-246">在 "**用户数**" 字段中，输入你要配置的用户总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="8f911-247">在 "**用户域**" 字段中，输入用于 SIP URI 的域。</span><span class="sxs-lookup"><span data-stu-id="8f911-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="8f911-248">这用于构造每个用户的 SIP URI 以登录到 Skype for business Server 2015 前端服务器或标准版服务器，并且可能不同于帐户域。</span><span class="sxs-lookup"><span data-stu-id="8f911-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="8f911-249">在 "**帐户域**" 字段中，输入 AD DS 域登录。</span><span class="sxs-lookup"><span data-stu-id="8f911-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="8f911-250">在 " **MPOP 百分比**（多点状态百分比）" 域中，为从多台计算机或设备登录的用户的百分比提供一个值，例如10%。</span><span class="sxs-lookup"><span data-stu-id="8f911-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="8f911-251">在 "**每秒登录次数" （每个实例）** 字段中输入并发终结点的最大数量。</span><span class="sxs-lookup"><span data-stu-id="8f911-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="8f911-252">这是您的用户的最大登录次数，建议值为小于/等于每秒2的速率（<= 2）。</span><span class="sxs-lookup"><span data-stu-id="8f911-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="8f911-253">在 "**访问代理服务器或池 FQDN** " 字段中，输入希望客户端连接到的服务器的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="8f911-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="8f911-254">如果用户在外部登录，则需要键入访问代理服务器。</span><span class="sxs-lookup"><span data-stu-id="8f911-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="8f911-255">如果用户是内部用户，请提供其企业版池或标准版服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8f911-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="8f911-256">在 "**端口**" 字段中，输入希望用户用于 SIP 的端口（此处的默认值为5061）。</span><span class="sxs-lookup"><span data-stu-id="8f911-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="8f911-257">对于 "**外部网络服务器设置**" 字段，请提供访问代理服务器或池 FQDN，然后再次授予该**端口**。</span><span class="sxs-lookup"><span data-stu-id="8f911-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="8f911-258">这些设置仅用于外部终结点负载模拟。</span><span class="sxs-lookup"><span data-stu-id="8f911-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="8f911-259">"常规方案" 选项卡</span><span class="sxs-lookup"><span data-stu-id="8f911-259">General Scenarios tab</span></span>

![显示“常规方案”选项卡的“加载配置”工具。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="8f911-261">你可以通过确定你想要运行或保留禁用的内容，为每个常规方案配置负载级别和参数。</span><span class="sxs-lookup"><span data-stu-id="8f911-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="8f911-262">下面是您的常规选项：</span><span class="sxs-lookup"><span data-stu-id="8f911-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f911-263">为所有字段加载级别值，但本地信息服务**已禁用**、**低**、**中**、**高**或**自定义**。</span><span class="sxs-lookup"><span data-stu-id="8f911-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="8f911-264">如果你选择了任何设置但禁用了该设置，则将为每个客户端生成配置。</span><span class="sxs-lookup"><span data-stu-id="8f911-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="8f911-265">高导致服务器支持的最大负载;中等是高负载的 60%;"低" 为30%。</span><span class="sxs-lookup"><span data-stu-id="8f911-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="8f911-266">**即时消息-** 这包括对等和会议;为负载级别选择适当的值。</span><span class="sxs-lookup"><span data-stu-id="8f911-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="8f911-267">\**音频会议-\*\*\*仅*选择音频会议的负载级别。</span><span class="sxs-lookup"><span data-stu-id="8f911-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="8f911-268">对等呼叫稍后将在 "**语音方案**" 部分 tackled。</span><span class="sxs-lookup"><span data-stu-id="8f911-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="8f911-269">打开 "**高级**" 选项卡以启用 "各页"。</span><span class="sxs-lookup"><span data-stu-id="8f911-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="8f911-270">**应用程序共享-** 选择应用程序共享的负载级别。</span><span class="sxs-lookup"><span data-stu-id="8f911-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="8f911-271">**数据协作-** 选择数据协作的负载级别，其中包括数据会议。</span><span class="sxs-lookup"><span data-stu-id="8f911-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="8f911-272">**通讯组列表扩展-** 单击 "**高级**" 按钮，并使用在 "用户创建工具" （UserProvisioningTool）的 "DL" 选项卡上配置的相同值填充该字段。</span><span class="sxs-lookup"><span data-stu-id="8f911-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="8f911-273">选择一个负载级别。</span><span class="sxs-lookup"><span data-stu-id="8f911-273">Choose a load level.</span></span>
    
- <span data-ttu-id="8f911-274">**通讯簿 Web 查询-** 这是通讯簿查找服务，而不是通讯簿文件下载。</span><span class="sxs-lookup"><span data-stu-id="8f911-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="8f911-275">如果要为通讯簿文件下载启用此操作，请单击 "**高级**" 按钮，然后将**EnableABSDownload**设置为 True。</span><span class="sxs-lookup"><span data-stu-id="8f911-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="8f911-276">为负载级别提供值。</span><span class="sxs-lookup"><span data-stu-id="8f911-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="8f911-277">**响应组服务-** 单击 "**高级**" 按钮，并指定你在设置响应组服务代理时已创建的响应组的 uri。</span><span class="sxs-lookup"><span data-stu-id="8f911-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="8f911-278">必须至少选择一个响应组。</span><span class="sxs-lookup"><span data-stu-id="8f911-278">You must choose at least one response group.</span></span> <span data-ttu-id="8f911-279">若要使用更多，请用分号分隔响应组。</span><span class="sxs-lookup"><span data-stu-id="8f911-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="8f911-280">将**RGSUriSuffixStartIndex**和**RGSUriSuffixEndIndex**更新为实际值。</span><span class="sxs-lookup"><span data-stu-id="8f911-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="8f911-281">选择一个负载级别。</span><span class="sxs-lookup"><span data-stu-id="8f911-281">Choose a load level.</span></span>
    
- <span data-ttu-id="8f911-282">**位置信息服务-** 选择 "已启用" 或 "已禁用" 的加载级别。</span><span class="sxs-lookup"><span data-stu-id="8f911-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8f911-283">每个方案都有一个位于它旁边的 "高级" 按钮，以及一组支持默认设置变体的复选框。</span><span class="sxs-lookup"><span data-stu-id="8f911-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="8f911-284">选择 *"临时"* 将允许工具生成将在整个时间内创建的会议模拟。</span><span class="sxs-lookup"><span data-stu-id="8f911-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="8f911-285">选择 "*大型*会议" 意味着将模拟大型会议方案。</span><span class="sxs-lookup"><span data-stu-id="8f911-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="8f911-286">*外部*告知工具还可模拟外部用户。</span><span class="sxs-lookup"><span data-stu-id="8f911-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="8f911-287">这些按钮和复选框是特定于每个方案的额外值，并且将更改压力和性能工具的行为，并使自定义成为可能。</span><span class="sxs-lookup"><span data-stu-id="8f911-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="8f911-288">对于 "常规方案" 选项卡上的每个方案（"位置信息服务" 除外），如果 "负载级别" 的值为 "**自定义**"，则使用 "高级" 对话框中对应的字段计算对话费率。</span><span class="sxs-lookup"><span data-stu-id="8f911-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="8f911-289">字段名称可能会有所不同，具体取决于方案，但字段说明将状态：*注意，仅当从下拉菜单中选择 "自定义" 时，才会使用此号码*。</span><span class="sxs-lookup"><span data-stu-id="8f911-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="8f911-290">值 "**高**"、"**中**" 和 "**低**" 将更改每个模式的会话费率与使用所有方案平衡的用户模型一致。</span><span class="sxs-lookup"><span data-stu-id="8f911-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="8f911-291">如果由于预期用法的差异而需要更改每个模态的负载级别，请使用自定义对话费率。</span><span class="sxs-lookup"><span data-stu-id="8f911-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="8f911-292">语音方案选项卡</span><span class="sxs-lookup"><span data-stu-id="8f911-292">Voice Scenarios tab</span></span>

<span data-ttu-id="8f911-293">这是用于配置所有语音相关方案的选项卡。</span><span class="sxs-lookup"><span data-stu-id="8f911-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![“加载配置”工具“语音方案”选项卡。](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="8f911-295">选项包括：</span><span class="sxs-lookup"><span data-stu-id="8f911-295">Your options are:</span></span>
  
- <span data-ttu-id="8f911-296">**VoIP-** 单击 "**高级**" 按钮，并添加 "PhoneAreaCode" 和 "LocationProfile" （拨号计划）字段的值。</span><span class="sxs-lookup"><span data-stu-id="8f911-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="8f911-297">你还将为加载级别提供一个值。</span><span class="sxs-lookup"><span data-stu-id="8f911-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="8f911-298">如果你选择启用 VoIP 或 UC/PSTN 网关的负载级别，则将生成一个公共交换电话网络（PSTN）到统一通信（UC）配置文件，以模拟外部呼叫。</span><span class="sxs-lookup"><span data-stu-id="8f911-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="8f911-299">**UC/PSTN 网关-** 您需要选择一个负载级别值，并且当您选择 "禁用" 之外的任何内容时，您也可以通过单击 "**高级**" 按钮为 PSTN 区域代码提供一个值。</span><span class="sxs-lookup"><span data-stu-id="8f911-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="8f911-300">单击 "中介服务器和 PSTN" 下的 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="8f911-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="8f911-301">请确保您已为区号配置了路线。</span><span class="sxs-lookup"><span data-stu-id="8f911-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8f911-302">您可以使用 Skype for Business 控制面板或 Skype for business 管理外壳程序来验证您的语音路线配置。</span><span class="sxs-lookup"><span data-stu-id="8f911-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="8f911-303">**会议助理-** 为负载级别提供一个值。</span><span class="sxs-lookup"><span data-stu-id="8f911-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="8f911-304">除 "已禁用" 之外的任何值都将启用 "**电话号码**" 字段。</span><span class="sxs-lookup"><span data-stu-id="8f911-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="8f911-305">输入要使用的自动助理的电话号码。</span><span class="sxs-lookup"><span data-stu-id="8f911-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="8f911-306">单击 "**高级**"，并为 " **LocationProfile** " 字段提供一个值。</span><span class="sxs-lookup"><span data-stu-id="8f911-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="8f911-307">**呼叫停车服务-** 在此处，提供一个负载级别。</span><span class="sxs-lookup"><span data-stu-id="8f911-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="8f911-308">**中介服务器和 PSTN-** 要使用的每个中介服务器都需要其自己的 PSTN 模拟器。</span><span class="sxs-lookup"><span data-stu-id="8f911-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="8f911-309">确定要用于模拟器的客户端后，配置中介服务器以将呼叫路由到您配置的 PSTN 模拟器上的该计算机。</span><span class="sxs-lookup"><span data-stu-id="8f911-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="8f911-310">单击 "**添加**" 按钮以配置中介服务器的值。</span><span class="sxs-lookup"><span data-stu-id="8f911-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8f911-311">每个方案旁边都有一个 "高级" 按钮。</span><span class="sxs-lookup"><span data-stu-id="8f911-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="8f911-312">高级对话框包含特定于每个方案的设置，这些设置将更改压力和性能工具的行为并启用自定义。</span><span class="sxs-lookup"><span data-stu-id="8f911-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="8f911-313">> 对于 "语音方案" 选项卡上的每个方案，如果 "加载" 级别的值为 "**自定义**"，则将使用 "高级" 对话框中的相应字段计算对话费率。</span><span class="sxs-lookup"><span data-stu-id="8f911-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="8f911-314">字段名称可能会有所不同，具体取决于方案，但字段说明将状态：*注意，仅当从下拉菜单中选择 "自定义" 时，才会使用此号码*。</span><span class="sxs-lookup"><span data-stu-id="8f911-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="8f911-315">Web App 选项卡</span><span class="sxs-lookup"><span data-stu-id="8f911-315">Web App tab</span></span>

![“加载配置”工具“Web 应用”选项卡。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="8f911-317">Web App 通过安装在前端服务器上的统一通信 Web API （UCWA）服务器支持会议方案。</span><span class="sxs-lookup"><span data-stu-id="8f911-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="8f911-318">使用 "Web 应用" 选项卡配置所有与 Web 应用相关的方案。</span><span class="sxs-lookup"><span data-stu-id="8f911-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="8f911-319">选项包括：</span><span class="sxs-lookup"><span data-stu-id="8f911-319">Options are:</span></span>
  
- <span data-ttu-id="8f911-320">**常规 Web 应用设置-** 单击 "**其他设置**" 按钮，并将**ReachTargetServerUrl**设置为前端池 VIP 的目录池虚拟 IP （vip）。</span><span class="sxs-lookup"><span data-stu-id="8f911-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="8f911-321">**应用程序共享-** 选择 "负载级别" 的值。</span><span class="sxs-lookup"><span data-stu-id="8f911-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="8f911-322">**数据协作-** 选择 "负载级别" 的值。</span><span class="sxs-lookup"><span data-stu-id="8f911-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="8f911-323">**即时消息-** 选择 "负载级别" 的值。</span><span class="sxs-lookup"><span data-stu-id="8f911-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="8f911-324">**语音会议-** 选择 "负载级别" 的值。</span><span class="sxs-lookup"><span data-stu-id="8f911-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8f911-325">每个方案旁边都有一个 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="8f911-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="8f911-326">高级对话框包含特定于每个方案的值，这些值将更改压力和性能工具的行为并启用自定义。 > 对于每个 Web 应用方案，如果加载级别为 "**自定义**"，则使用 " **ConversationsPerHour** " 字段中指定的值，而不是默认值。</span><span class="sxs-lookup"><span data-stu-id="8f911-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="8f911-327">移动选项卡</span><span class="sxs-lookup"><span data-stu-id="8f911-327">Mobility tab</span></span>

<span data-ttu-id="8f911-328">使用此选项卡可以配置所有与移动相关的方案。</span><span class="sxs-lookup"><span data-stu-id="8f911-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![“加载配置”工具“移动性”选项卡。](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="8f911-330">此处的选项有：</span><span class="sxs-lookup"><span data-stu-id="8f911-330">The options here are:</span></span>
  
- <span data-ttu-id="8f911-331">**常规移动设置-** 单击 "**其他设置**"，然后将 "字段 UcwaTargetServerUrl" 设置为 "控制器池虚拟 IP （vip）" 或 "前端池 VIP"。</span><span class="sxs-lookup"><span data-stu-id="8f911-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="8f911-332">**状态和 P2P 即时消息/音频-** 选择 "负载级别" 的值以启用移动模拟。</span><span class="sxs-lookup"><span data-stu-id="8f911-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8f911-333">每个方案旁边都有一个 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="8f911-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="8f911-334">高级对话框包含特定于每个方案的值，这些值将更改压力和性能工具的行为并启用自定义。 > 对于每个移动方案，如果加载级别为 "**自定义**"，则使用 " **ConversationsPerHour** " 字段中指定的值，而不是默认值。</span><span class="sxs-lookup"><span data-stu-id="8f911-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="8f911-335">"摘要" 选项卡</span><span class="sxs-lookup"><span data-stu-id="8f911-335">Summary tab</span></span>

<span data-ttu-id="8f911-336">"摘要" 选项卡指示要针对每个方案使用的用户。</span><span class="sxs-lookup"><span data-stu-id="8f911-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![“加载配置”工具“摘要”选项卡。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="8f911-338">"摘要" 选项卡指示要针对每个方案使用的用户。</span><span class="sxs-lookup"><span data-stu-id="8f911-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="8f911-339">通过选中 "**启用自定义用户范围生成**" 复选框，然后双击包含要自定义的用户区域的表中的方案，可以手动配置用户编号范围。</span><span class="sxs-lookup"><span data-stu-id="8f911-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="8f911-340">检查 **（RunClient）在启动时添加登录延迟**，以便包括所生成的批处理文件中的延迟以对应于登录速率。</span><span class="sxs-lookup"><span data-stu-id="8f911-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="8f911-341">这在登录大量用户时避免服务器超载非常有用。</span><span class="sxs-lookup"><span data-stu-id="8f911-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="8f911-342">单击 "**生成文件**"，然后选择要在其中生成配置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8f911-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="8f911-343">成功创建文件后，将显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="8f911-343">A dialog box will appear when your files have been successfully created.</span></span>
  
![“已成功生成加载配置文件”消息框。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="8f911-346">运行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="8f911-346">Run LyncPerfTool</span></span>
<span data-ttu-id="8f911-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="8f911-347"><a name="BKMK_RunTool"> </a></span></span>

<span data-ttu-id="8f911-348">您需要先创建用户、联系人和方案，然后再运行 Skype for Business Server 2015 应力和性能工具（LyncPerfTool）。</span><span class="sxs-lookup"><span data-stu-id="8f911-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="8f911-349">有关使用工具执行这些操作的详细信息，请参阅[创建用户和联系人](using-the-tool.md#BKMK_CreateUsersAndContacts)和配置本文前面的[用户配置文件](using-the-tool.md#BKMK_UserProfile)。</span><span class="sxs-lookup"><span data-stu-id="8f911-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="8f911-350">运行这些工具还将生成一个文件，该文件将随压力和性能工具一起运行，作为批处理文件的一部分，其中包括所需的参数。</span><span class="sxs-lookup"><span data-stu-id="8f911-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="8f911-351">运行 Skype for Business Server 2015 应力和性能工具</span><span class="sxs-lookup"><span data-stu-id="8f911-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="8f911-352">加载配置工具（UserProfileGenerator）将创建一个批处理文件，通过注册性能计数器并加载 XML 配置文件，可以运行压力和性能工具（LyncPerfTool）。</span><span class="sxs-lookup"><span data-stu-id="8f911-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="8f911-353">批处理文件针对每个配置文件运行 LyncPerfTool 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="8f911-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="8f911-354">若要运行批处理文件，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8f911-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="8f911-355">运行压力测试和性能测试</span><span class="sxs-lookup"><span data-stu-id="8f911-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="8f911-356">将包含配置文件夹和文件的文件夹复制到每台客户端计算机上具有 LyncPerfTool 的目录中。</span><span class="sxs-lookup"><span data-stu-id="8f911-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="8f911-357">（例如，如果你在名为 1.28 _ 13.16.16 的文件夹中生成了配置文件，请将该文件夹复制到其中包含 LyncPerfTool .exe 的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8f911-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="8f911-358">在每个客户端上执行此操作。）</span><span class="sxs-lookup"><span data-stu-id="8f911-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="8f911-359">导航到客户端文件夹并运行**RunClient**批处理脚本。</span><span class="sxs-lookup"><span data-stu-id="8f911-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="8f911-360">你可以在 Windows 资源管理器中双击批处理文件，它将为该客户端运行所有配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f911-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="8f911-361">还可以通过使用以下语法，从客户端文件夹运行脚本：</span><span class="sxs-lookup"><span data-stu-id="8f911-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

<span data-ttu-id="8f911-362">若要直接运行 "压力和性能" 工具，请打开命令提示符，然后在命令行中键入以下命令（第一次执行此操作时，请确保注册性能计数器`regsvr32 /i /n /s LyncPerfToolPerf.dll`，如本主题后面的说明所示）：</span><span class="sxs-lookup"><span data-stu-id="8f911-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="8f911-363">若要让该工具显示配置文件中的值，请在`/displayfile`前面的命令上包含该参数，使其如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f911-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="8f911-364">若要*结束*进程，请按 Ctrl + C。</span><span class="sxs-lookup"><span data-stu-id="8f911-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f911-365">直接运行压力和性能工具之前，必须通过以下命令注册性能计数器：`regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="8f911-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f911-366">你启动的压力和性能工具的每个实例将立即开始登录用户，通常以每秒一个用户的速率登录。</span><span class="sxs-lookup"><span data-stu-id="8f911-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="8f911-367">池的最大用户登录速率为每秒12次。</span><span class="sxs-lookup"><span data-stu-id="8f911-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="8f911-368">这意味着，当用户仍在登录时，你不应同时启动超过12个 LyncPerfTool 实例。</span><span class="sxs-lookup"><span data-stu-id="8f911-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="8f911-369">1000用户大约需要20分钟才能每秒完全登录一次。</span><span class="sxs-lookup"><span data-stu-id="8f911-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="8f911-370">解释结果</span><span class="sxs-lookup"><span data-stu-id="8f911-370">Interpreting the Results</span></span>
<span data-ttu-id="8f911-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="8f911-371"><a name="BKMK_Interpret"> </a></span></span>

<span data-ttu-id="8f911-372">Skype for Business Server 2015 应力和性能工具具有许多计数器，可帮助你了解客户端正在执行的操作以及是否遇到问题。</span><span class="sxs-lookup"><span data-stu-id="8f911-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="8f911-373">客户端计数器</span><span class="sxs-lookup"><span data-stu-id="8f911-373">Client Counters</span></span>

<span data-ttu-id="8f911-374">LyncPerfTool 运行的每个实例都有一个单独的计数器实例。</span><span class="sxs-lookup"><span data-stu-id="8f911-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="8f911-375">每个实例均按其进程 ID 命名。</span><span class="sxs-lookup"><span data-stu-id="8f911-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="8f911-376">如果客户超载，可能会出现其他问题。</span><span class="sxs-lookup"><span data-stu-id="8f911-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="8f911-377">若要防止这些问题：</span><span class="sxs-lookup"><span data-stu-id="8f911-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="8f911-378">在客户端计算机上监视 CPU 和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="8f911-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="8f911-379">如果 CPU 持续超过90%，请减少用户数。</span><span class="sxs-lookup"><span data-stu-id="8f911-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="8f911-380">当内存占用空间较高时，如果页面文件开始耗尽空间，则可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="8f911-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="8f911-381">验证确认费用未达到计算机的限制。</span><span class="sxs-lookup"><span data-stu-id="8f911-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="8f911-382">如果运行内存限制，请考虑增加页面文件大小或减少用户数。</span><span class="sxs-lookup"><span data-stu-id="8f911-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="8f911-383">下面是关键性能计数器的列表：</span><span class="sxs-lookup"><span data-stu-id="8f911-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="8f911-384">**常规信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-384">**General Information**</span></span>

|<span data-ttu-id="8f911-385">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-385">**Performance Counter**</span></span>|<span data-ttu-id="8f911-386">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-387">分钟花费的时间</span><span class="sxs-lookup"><span data-stu-id="8f911-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="8f911-388">启动流程后所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="8f911-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="8f911-389">活动终结点</span><span class="sxs-lookup"><span data-stu-id="8f911-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="8f911-390">当前连接到服务器的终结点的数量。</span><span class="sxs-lookup"><span data-stu-id="8f911-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="8f911-391">失败的登录</span><span class="sxs-lookup"><span data-stu-id="8f911-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="8f911-392">终结点登录失败总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="8f911-393">登录尝试</span><span class="sxs-lookup"><span data-stu-id="8f911-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="8f911-394">终结点登录尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="8f911-395">终结点断开连接</span><span class="sxs-lookup"><span data-stu-id="8f911-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="8f911-396">已断开连接的终结点的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="8f911-397">**状态信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-397">**Presence Information**</span></span>

|<span data-ttu-id="8f911-398">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-398">**Performance Counter**</span></span>|<span data-ttu-id="8f911-399">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-400">SetPresence 通话</span><span class="sxs-lookup"><span data-stu-id="8f911-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="8f911-401">联机状态更改尝试总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-401">Total number of presence change attempts.</span></span> <span data-ttu-id="8f911-402">对于不同类型的状态更改，请参阅 SetPresence （状态类型）调用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="8f911-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="8f911-403">SetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="8f911-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="8f911-404">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="8f911-405">GetPresence 通话</span><span class="sxs-lookup"><span data-stu-id="8f911-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="8f911-406">获取状态请求尝试的总次数。</span><span class="sxs-lookup"><span data-stu-id="8f911-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="8f911-407">GetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="8f911-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="8f911-408">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="8f911-409">**通讯簿服务信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-409">**Address Book service information**</span></span>

|<span data-ttu-id="8f911-410">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-410">**Performance Counter**</span></span>|<span data-ttu-id="8f911-411">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-412">已尝试绝对值完整/增量文件下载</span><span class="sxs-lookup"><span data-stu-id="8f911-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="8f911-413">已尝试的完整或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="8f911-414">ABS 完整/增量文件下载成功</span><span class="sxs-lookup"><span data-stu-id="8f911-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="8f911-415">已尝试的完整或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="8f911-416">通讯簿 Web 查询服务相关计数器</span><span class="sxs-lookup"><span data-stu-id="8f911-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="8f911-417">通讯簿文件下载相关计数器。</span><span class="sxs-lookup"><span data-stu-id="8f911-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="8f911-418">尝试进行 ABS WS 呼叫</span><span class="sxs-lookup"><span data-stu-id="8f911-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="8f911-419">尝试的通讯簿 Web 查询服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="8f911-420">ABS WS 呼叫成功</span><span class="sxs-lookup"><span data-stu-id="8f911-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="8f911-421">返回成功响应代码的通讯簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="8f911-422">ABS WS 呼叫失败</span><span class="sxs-lookup"><span data-stu-id="8f911-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="8f911-423">返回错误响应代码的通讯簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="8f911-424">此类别包括用于监视通讯簿服务（ABS）文件下载和通讯簿 Web 查询服务请求的计数器。</span><span class="sxs-lookup"><span data-stu-id="8f911-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="8f911-425">**通讯组列表（DL）信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="8f911-426">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-426">**Performance Counter**</span></span>|<span data-ttu-id="8f911-427">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-428">已尝试呼叫</span><span class="sxs-lookup"><span data-stu-id="8f911-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="8f911-429">尝试的通讯组列表展开（DLX） web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="8f911-430">通话成功</span><span class="sxs-lookup"><span data-stu-id="8f911-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="8f911-431">返回成功响应代码的 DLX web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="8f911-432">呼叫失败</span><span class="sxs-lookup"><span data-stu-id="8f911-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="8f911-433">返回了错误响应代码的 DLX web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="8f911-434">以下列出的性能计数器将在启用这些方案时针对所有 IP 语音（VoIP）呼叫（包括中介服务器、A/V 会议服务器、边缘服务器、响应组应用程序和会议自动助理）的报告编号。</span><span class="sxs-lookup"><span data-stu-id="8f911-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="8f911-435">**VoIP 基本信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="8f911-436">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-436">**Performance Counter**</span></span>|<span data-ttu-id="8f911-437">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-438">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="8f911-438">Calls Active</span></span>  <br/> |<span data-ttu-id="8f911-439">当前正在进行的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="8f911-440">通话终止</span><span class="sxs-lookup"><span data-stu-id="8f911-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="8f911-441">已终止的传入/传出语音通话总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="8f911-442">通话被拒绝</span><span class="sxs-lookup"><span data-stu-id="8f911-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="8f911-443">已拒绝的传入语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="8f911-444">已尝试拨入/拨出电话</span><span class="sxs-lookup"><span data-stu-id="8f911-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="8f911-445">已尝试传入/传出语音通话的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="8f911-446">已建立传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="8f911-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="8f911-447">已建立的传入/传出语音通话的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="8f911-448">呼叫接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="8f911-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="8f911-449">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="8f911-450">VoIP 传递率（%）</span><span class="sxs-lookup"><span data-stu-id="8f911-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="8f911-451">已建立通话总次数/尝试的通话总次数。</span><span class="sxs-lookup"><span data-stu-id="8f911-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="8f911-452">**响应组服务呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="8f911-453">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-453">**Performance Counter**</span></span>|<span data-ttu-id="8f911-454">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-455">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="8f911-455">Calls Active</span></span>  <br/> |<span data-ttu-id="8f911-456">对响应组应用程序的活动呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="8f911-457">已尝试呼叫</span><span class="sxs-lookup"><span data-stu-id="8f911-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="8f911-458">尝试的通话总次数。</span><span class="sxs-lookup"><span data-stu-id="8f911-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="8f911-459">**即时消息（IM）呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="8f911-460">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-460">**Performance Counter**</span></span>|<span data-ttu-id="8f911-461">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-462">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="8f911-462">Calls Active</span></span>  <br/> |<span data-ttu-id="8f911-463">正在进行的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="8f911-464">通话终止</span><span class="sxs-lookup"><span data-stu-id="8f911-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="8f911-465">已终止的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="8f911-466">呼叫接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="8f911-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="8f911-467">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="8f911-468">接收/发送的 IM 消息</span><span class="sxs-lookup"><span data-stu-id="8f911-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="8f911-469">所有会话的已接收或已发送邮件的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="8f911-470">已尝试拨入/拨出电话</span><span class="sxs-lookup"><span data-stu-id="8f911-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="8f911-471">尝试的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="8f911-472">已建立传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="8f911-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="8f911-473">已建立的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="8f911-474">**应用共享呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="8f911-475">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-475">**Performance Counter**</span></span>|<span data-ttu-id="8f911-476">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-477">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="8f911-477">Calls Active</span></span>  <br/> |<span data-ttu-id="8f911-478">正在进行的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="8f911-479">通话终止</span><span class="sxs-lookup"><span data-stu-id="8f911-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="8f911-480">已终止的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="8f911-481">呼叫接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="8f911-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="8f911-482">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="8f911-483">已尝试拨入/拨出电话</span><span class="sxs-lookup"><span data-stu-id="8f911-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="8f911-484">尝试的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="8f911-485">已建立传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="8f911-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="8f911-486">已建立的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="8f911-487">**CAA 通话信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-487">**CAA Call Information**</span></span>

|<span data-ttu-id="8f911-488">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-488">**Performance Counter**</span></span>|<span data-ttu-id="8f911-489">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-490">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="8f911-490">Calls Active</span></span>  <br/> |<span data-ttu-id="8f911-491">当前正在进行的传入/传出公共交换电话网络（PSTN）呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="8f911-492">通话终止</span><span class="sxs-lookup"><span data-stu-id="8f911-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="8f911-493">已终止的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="8f911-494">已尝试拨入/拨出电话</span><span class="sxs-lookup"><span data-stu-id="8f911-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="8f911-495">尝试的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="8f911-496">已建立传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="8f911-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="8f911-497">已建立的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="8f911-498">**会议信息**</span><span class="sxs-lookup"><span data-stu-id="8f911-498">**Conference Information**</span></span>

|<span data-ttu-id="8f911-499">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-499">**Performance Counter**</span></span>|<span data-ttu-id="8f911-500">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-501">活动即时消息会议</span><span class="sxs-lookup"><span data-stu-id="8f911-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="8f911-502">正在进行的即时消息会议总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="8f911-503">活动音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="8f911-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="8f911-504">正在进行的音频/视频（A/V）会议总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="8f911-505">活动应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="8f911-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="8f911-506">正在进行的应用程序共享会议总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="8f911-507">参与者的人数</span><span class="sxs-lookup"><span data-stu-id="8f911-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="8f911-508">当前连接到会议的参与者总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="8f911-509">会议计划失败</span><span class="sxs-lookup"><span data-stu-id="8f911-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="8f911-510">尝试安排会议时失败的总次数。</span><span class="sxs-lookup"><span data-stu-id="8f911-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="8f911-511">加入会议失败</span><span class="sxs-lookup"><span data-stu-id="8f911-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="8f911-512">尝试连接到会议时失败的总次数。</span><span class="sxs-lookup"><span data-stu-id="8f911-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="8f911-513">**UCWA 客户端计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="8f911-514">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="8f911-514">**Performance Counter**</span></span>|<span data-ttu-id="8f911-515">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f911-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f911-516">已成功联接的 IMMCU 总数</span><span class="sxs-lookup"><span data-stu-id="8f911-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="8f911-517">已加入的即时消息会议的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="8f911-518">已成功联接的 DMCU 总数</span><span class="sxs-lookup"><span data-stu-id="8f911-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="8f911-519">已加入/V 会议的总数。</span><span class="sxs-lookup"><span data-stu-id="8f911-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

