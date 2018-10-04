---
title: 使用 Skype 业务服务器 2015年压力和性能工具
ms.author: heidip
author: microsoftheidi
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: 若要运行 Skype 的业务服务器 2015年压力和性能工具，您将需要能够管理用户、 联系人和用户配置文件配置正在运行，工具，然后检查输出或工具生成的结果。
ms.openlocfilehash: 829bedbd2a042234e67285045ac67cff30064936
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375437"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="fe48b-103">使用 Skype 业务服务器 2015年压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="fe48b-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="fe48b-104">若要运行 Skype 的业务服务器 2015年压力和性能工具，您将需要能够管理用户、 联系人和用户配置文件配置正在运行，工具，然后检查输出或工具生成的结果。</span><span class="sxs-lookup"><span data-stu-id="fe48b-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="fe48b-105">有四个方面所涉及的业务 Server 2015 压力和性能工具 （可执行文件是 LyncPerfTool.exe） 运行 Skype:</span><span class="sxs-lookup"><span data-stu-id="fe48b-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="fe48b-106">创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="fe48b-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="fe48b-107">配置用户配置文件</span><span class="sxs-lookup"><span data-stu-id="fe48b-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="fe48b-108">运行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="fe48b-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="fe48b-109">解释结果</span><span class="sxs-lookup"><span data-stu-id="fe48b-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="fe48b-110">创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="fe48b-110">Create Users and Contacts</span></span>
<span data-ttu-id="fe48b-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="fe48b-111"></span></span>

<span data-ttu-id="fe48b-112">您需要使用业务服务器 2015 (SB 2015) 用户设置工具 (UserProvisioningTool.exe) Skype 创建用户和联系人以进行压力和性能测试。</span><span class="sxs-lookup"><span data-stu-id="fe48b-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="fe48b-113">这是在阅读主题可能有用的有用词的列表：</span><span class="sxs-lookup"><span data-stu-id="fe48b-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="fe48b-114">**组织单位**的 Active Directory 域服务 (AD DS) 的组织单位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="fe48b-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="fe48b-115">**联盟 / 跨池**-用户可以与来自其他即时消息 (IM) 服务的用户通信。</span><span class="sxs-lookup"><span data-stu-id="fe48b-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="fe48b-116">**通讯组列表**的或 Dl。</span><span class="sxs-lookup"><span data-stu-id="fe48b-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="fe48b-117">这些是包含 AD DS 用户的列表的 AD DS 中的对象。</span><span class="sxs-lookup"><span data-stu-id="fe48b-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="fe48b-118">它们用于加快跨组的人员的通信。</span><span class="sxs-lookup"><span data-stu-id="fe48b-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="fe48b-119">**位置信息服务**-业务服务器 2015年服务的增强型 911 (E911) 服务的物理位置检索已启用并配置每个电话，对其时允许 Skype。</span><span class="sxs-lookup"><span data-stu-id="fe48b-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="fe48b-120">**美国电话号码**的电话号码分配给用户除了用于路由入站和出站呼叫中反向号码查找 (RNL) 的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="fe48b-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="fe48b-121">使用 UserProvisioningTool.exe 创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="fe48b-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="fe48b-122">即使开始之前，请确保绝对登录要运行此工具的 Domain Admins 安全组成员身份。</span><span class="sxs-lookup"><span data-stu-id="fe48b-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="fe48b-123">您需要执行此操作，因为您将创建 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="fe48b-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="fe48b-124">您需要企业服务器用户设置工具 Skype 用于创建用户和负载模拟的联系人。</span><span class="sxs-lookup"><span data-stu-id="fe48b-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="fe48b-125">**Skype 业务服务器用户设置工具**安装的**Skype 的业务 Server 压力和性能工具**程序包。</span><span class="sxs-lookup"><span data-stu-id="fe48b-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="fe48b-126">确保已在前端服务器或想要测试的 Standard Edition 服务器上执行的程序包安装程序 (CapacityPlanningTool.msi)。</span><span class="sxs-lookup"><span data-stu-id="fe48b-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="fe48b-127">您可以通过运行文件 UserProvisioningTool.exe （位于 %installeddirectory%lyncstressandperftool\lyncstress） 的业务服务器用户设置工具开始 Skype 在前端服务器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="fe48b-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fe48b-128">当您创建大量的用户 （例如，10000 或多个），运行 UserProvisioningTool.exe。</span><span class="sxs-lookup"><span data-stu-id="fe48b-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="fe48b-129">您需要执行此操作，因为该工具将创建并配置*新*AD 用户。</span><span class="sxs-lookup"><span data-stu-id="fe48b-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="fe48b-130">当用户设置工具打开时，单击配置，然后选择负载配置。</span><span class="sxs-lookup"><span data-stu-id="fe48b-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="fe48b-131">若要开始配置用户和联系人，加载附带的程序包，名为"SampleData.xml"的默认文件。</span><span class="sxs-lookup"><span data-stu-id="fe48b-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="fe48b-132">这将预填充您需要更改以使其与您的部署相关的示例数据的字段。</span><span class="sxs-lookup"><span data-stu-id="fe48b-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="fe48b-133">如果您有一个预配置的 XML 文件已包含自定义的设置，您可以改为加载该文件。</span><span class="sxs-lookup"><span data-stu-id="fe48b-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="fe48b-134">填写字段在用户设置工具中，以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="fe48b-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="fe48b-135">配置服务器选项：</span><span class="sxs-lookup"><span data-stu-id="fe48b-135">To configure server options:</span></span>

1. <span data-ttu-id="fe48b-136">在**前端池 FQDN**字段中，键入 Standard Edition server 或要承载用户的前端池的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="fe48b-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="fe48b-137">在**用户名称前缀**字段中，键入您想要用于 bust 您出于测试目的 （例如"TestUser") 的用户名的前缀。</span><span class="sxs-lookup"><span data-stu-id="fe48b-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="fe48b-138">在**密码**字段中，键入将使用的所有测试用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="fe48b-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="fe48b-139">在**帐户域**字段中，键入您的当前 AD 域的域名 （要在其中创建测试用户的那个）。</span><span class="sxs-lookup"><span data-stu-id="fe48b-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="fe48b-140">在**组织单位**字段中，键入名称这些 AD 域您想要创建的测试用户。</span><span class="sxs-lookup"><span data-stu-id="fe48b-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="fe48b-141">（如果尚不存在 OU，则它将为您创建。）</span><span class="sxs-lookup"><span data-stu-id="fe48b-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="fe48b-142">在**电话区号**字段中，键入用于跨所有测试用户帐户的三个数字区域代码。</span><span class="sxs-lookup"><span data-stu-id="fe48b-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="fe48b-143">请确保您选择不会发生冲突与其他用户的区域代码区域代码 AD 中。</span><span class="sxs-lookup"><span data-stu-id="fe48b-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="fe48b-144">单击以选中**语音启用**复选框，如果您想要测试用户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="fe48b-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="fe48b-145">在**用户数量**字段中，提供您想要创建的测试用户的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="fe48b-146">在**开始的索引**字段中，为将用作用户名称前缀为后缀的起始编号 （例如，前缀是"TestUser"和"0"在下面的示例中将结束第一个名称。）</span><span class="sxs-lookup"><span data-stu-id="fe48b-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![显示“创建用户”选项卡的“用户设置”工具。](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="fe48b-148">创建用户按钮</span><span class="sxs-lookup"><span data-stu-id="fe48b-148">Create Users button</span></span>

<span data-ttu-id="fe48b-149">当您单击**创建用户**按钮时，验证您输入的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="fe48b-150">如果有任何验证错误，将提示您进行修复。</span><span class="sxs-lookup"><span data-stu-id="fe48b-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="fe48b-151">或者，如果所有的值是否正确，用户将启动显示 （无论您指定的 OU) 中的 AD 中。</span><span class="sxs-lookup"><span data-stu-id="fe48b-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="fe48b-152">在运行，您将看到进度栏底部的工具。</span><span class="sxs-lookup"><span data-stu-id="fe48b-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="fe48b-153">进度栏处于活动状态时不关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe48b-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="fe48b-154">创建用户需要花费的时间，相应地请计划。</span><span class="sxs-lookup"><span data-stu-id="fe48b-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="fe48b-155">此过程可以花几分钟，以便将一些用户为大型数量的用户的几个小时。</span><span class="sxs-lookup"><span data-stu-id="fe48b-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="fe48b-156">如果在测试环境中没有访问 AD 域控制器，您仍可以通过以下方式之一的用户指定要创建范围中的用户验证用户创建。</span><span class="sxs-lookup"><span data-stu-id="fe48b-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="fe48b-157">请记住使用前缀和后缀，以及作为用户名 @sipDomain。</span><span class="sxs-lookup"><span data-stu-id="fe48b-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="fe48b-158">下面是一个示例： <em>TestUser20@contoso.net</em> 。</span><span class="sxs-lookup"><span data-stu-id="fe48b-158">Here is an example:  <em>TestUser20@contoso.net</em>  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe48b-159">如果用户已存在，请单击创建用户按钮将更新它们与任何配置更改。</span><span class="sxs-lookup"><span data-stu-id="fe48b-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="fe48b-160">删除用户按钮</span><span class="sxs-lookup"><span data-stu-id="fe48b-160">Delete Users button</span></span>

<span data-ttu-id="fe48b-161">当您单击**删除用户**按钮时，将验证选项卡的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="fe48b-162">如果存在验证错误，您将会提示来修复这些，并且正确的输入的值时，将禁用并从 Active Directory 中删除指定的测试用户。</span><span class="sxs-lookup"><span data-stu-id="fe48b-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="fe48b-163">同样，在底部的此选项卡上，将显示进度栏和进度栏处于活动状态时，不应关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe48b-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe48b-164">支持仅美国格式的电话号码。</span><span class="sxs-lookup"><span data-stu-id="fe48b-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="fe48b-165">电话号码始终分配给用户，并通过 UserProvisioningTool.exe 创建的所有用户都启用企业语音默认情况下。</span><span class="sxs-lookup"><span data-stu-id="fe48b-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="fe48b-166">使用的电话号码，如会议自动助理或 UC-PSTN 呼叫的任何方案使用此电话号码以正确路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="fe48b-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="fe48b-167">因此，*每个用户*必须拥有*唯一的电话号码*。</span><span class="sxs-lookup"><span data-stu-id="fe48b-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe48b-168">**如果您有两次创建用户，该命令将失败，除非您使用不同的区域代码，或上一用户已禁用使用 Disable-csuser cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="fe48b-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fe48b-169">创建联系人之前，首先需要完成用户复制 （这通过用户选项卡）。</span><span class="sxs-lookup"><span data-stu-id="fe48b-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fe48b-170">如果您刚才创建您的用户，您将需要等待，直到 Skype 业务服务器复制完成并填充数据库中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fe48b-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="fe48b-171">**如果用户尚未复制完成后，您将看到一个错误。**</span><span class="sxs-lookup"><span data-stu-id="fe48b-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="fe48b-172">您将了解当用户完复制如果 Skype 业务 Server 2015 前端服务已启动，或通过成功运行 Get-csuser cmdlet 的最后一个用户的您指定的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="fe48b-173">联系人创建选项卡</span><span class="sxs-lookup"><span data-stu-id="fe48b-173">Contacts Creation tab</span></span>

<span data-ttu-id="fe48b-174">此选项卡使您的测试授予用户的联系人详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe48b-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![显示“创建内容”选项卡的“用户设置”工具。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="fe48b-176">若要配置用户的联系人，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fe48b-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="fe48b-177">在**平均每个用户的联系人**字段中，输入的平均联系人数填充为每个用户的联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="fe48b-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="fe48b-178">如果您想要创建的每个用户等于联系人数，请选择**修复**复选框。</span><span class="sxs-lookup"><span data-stu-id="fe48b-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="fe48b-179">如果您想要改变为用户创建的联系人数，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="fe48b-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="fe48b-180">在**每个用户的平均联系人组**字段中，输入每个用户的联系人组的数目。</span><span class="sxs-lookup"><span data-stu-id="fe48b-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="fe48b-181">此号码必须小于**每个用户的平均联系人**。</span><span class="sxs-lookup"><span data-stu-id="fe48b-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="fe48b-182">在**联盟 / 跨池联系人百分比**字段中，为介于 0 和 100 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="fe48b-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="fe48b-183">将与联盟用户创建此联系人的百分比。</span><span class="sxs-lookup"><span data-stu-id="fe48b-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="fe48b-184">在**联盟 / 跨池用户前缀**字段中，将添加到本地用户的联系人列表的联盟用户授予用户名。</span><span class="sxs-lookup"><span data-stu-id="fe48b-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="fe48b-185">在**联盟 / 跨池用户的 SIP 域**字段中，为联盟用户的 SIP 域名称。</span><span class="sxs-lookup"><span data-stu-id="fe48b-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="fe48b-186">在**用户创建**选项卡上确保信息正确无误。</span><span class="sxs-lookup"><span data-stu-id="fe48b-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="fe48b-187">从用户创建选项卡上的值，将创建您的联系人。</span><span class="sxs-lookup"><span data-stu-id="fe48b-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="fe48b-188">单击**创建联系人**开始联系人创建。</span><span class="sxs-lookup"><span data-stu-id="fe48b-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="fe48b-189">此过程可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="fe48b-189">This process can take several minutes.</span></span> <span data-ttu-id="fe48b-190">它完成邮件，将出现一个对话框后，"操作成功完成。"</span><span class="sxs-lookup"><span data-stu-id="fe48b-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="fe48b-191">您可以验证创建的以从用户创建选项卡中创建用户登录的联系人。</span><span class="sxs-lookup"><span data-stu-id="fe48b-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe48b-192">创建联系人之后，此工具将在重新启动所有前端服务器目标池。</span><span class="sxs-lookup"><span data-stu-id="fe48b-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="fe48b-193">根据多少联系人创建的此操作可能需要更长时间 （最多 2 小时） 开始，前端服务器。</span><span class="sxs-lookup"><span data-stu-id="fe48b-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="fe48b-194">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="fe48b-194">Distribution List</span></span>

<span data-ttu-id="fe48b-195">为业务服务器 2015年压力和性能工具 Skype 可以模拟业务 2015年客户端 Skype 中的通讯组列表 (DL) 扩展功能。</span><span class="sxs-lookup"><span data-stu-id="fe48b-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="fe48b-196">如果您不想要启用用户设置工具中的 DL 扩展，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="fe48b-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![显示“创建通讯组列表”选项卡的“用户设置”工具。](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="fe48b-198">通讯组列表选项卡，可以创建 Dl 压力和性能工具将使用通讯组列表扩展功能。</span><span class="sxs-lookup"><span data-stu-id="fe48b-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="fe48b-199">创建 Dl 之前, 的业务服务器 2015 Skype 需要部署，包括具有运行 ForestPrep。</span><span class="sxs-lookup"><span data-stu-id="fe48b-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="fe48b-200">如果不这样做，DL 属性将不在 AD 架构中，存在，因此该工具将无法创建 Dl。</span><span class="sxs-lookup"><span data-stu-id="fe48b-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="fe48b-201">配置通讯组列表：</span><span class="sxs-lookup"><span data-stu-id="fe48b-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="fe48b-202">在**列表的通讯组数**字段中，提供您想要创建的 Dl 的总数 （此处的建议。 您与 double 您具有的用户数的值开始）。</span><span class="sxs-lookup"><span data-stu-id="fe48b-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="fe48b-203">在**通讯组列表前缀**字段中，输入您创建的所有 Dl 将都具有，例如*testDL*前缀。</span><span class="sxs-lookup"><span data-stu-id="fe48b-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="fe48b-204">这意味着，在 100 Dl DL 名称将显示如下： testDL0，testDL1，最多为 testDL99。</span><span class="sxs-lookup"><span data-stu-id="fe48b-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="fe48b-205">在**最小 Dist.列表中的成员**字段中，输入的最小放入每个 DL 用户数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="fe48b-206">在**Dist.列表中的最大成员**字段中，输入的最大在每个 DL 中添加的用户数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="fe48b-207">创建通讯组列表的按钮</span><span class="sxs-lookup"><span data-stu-id="fe48b-207">Create Distribution Lists button</span></span>

<span data-ttu-id="fe48b-208">当您单击创建通讯组列表按钮时，该工具将查询 Active Directory 以查看是否通讯组列表匹配前缀和号码已经存在。</span><span class="sxs-lookup"><span data-stu-id="fe48b-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="fe48b-209">此工具创建尚不存在任何 Dl。</span><span class="sxs-lookup"><span data-stu-id="fe48b-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="fe48b-210">时将成员添加到这些新创建的通讯组列表，它将在用户创建选项卡上指定的区域选择的用户。</span><span class="sxs-lookup"><span data-stu-id="fe48b-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="fe48b-211">位置信息服务配置选项卡</span><span class="sxs-lookup"><span data-stu-id="fe48b-211">Location Info Service Config tab</span></span>

<span data-ttu-id="fe48b-212">业务 Server 2015 压力和性能工具 Skype 还可以生成的位置信息服务的虚拟配置文件。</span><span class="sxs-lookup"><span data-stu-id="fe48b-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="fe48b-213">请注意，位置信息服务通常不会显著影响性能的服务器上。</span><span class="sxs-lookup"><span data-stu-id="fe48b-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![显示“位置信息服务配置”选项卡的“用户设置”工具。](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="fe48b-215">如果您选择要测试此功能，填充窗体中的值，然后单击生成 LIS 配置文件按钮，将创建。调用 CSV 文件：</span><span class="sxs-lookup"><span data-stu-id="fe48b-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="fe48b-216">LIS_Subnet.csv</span><span class="sxs-lookup"><span data-stu-id="fe48b-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="fe48b-217">LIS_Switches.csv</span><span class="sxs-lookup"><span data-stu-id="fe48b-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="fe48b-218">LIS_Ports.csv</span><span class="sxs-lookup"><span data-stu-id="fe48b-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="fe48b-219">LIS_WAP.csv</span><span class="sxs-lookup"><span data-stu-id="fe48b-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="fe48b-220">若要导入到 LIS 数据库这些文件，请使用以下 PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fe48b-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="fe48b-221">设置 CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="fe48b-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="fe48b-222">设置 CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="fe48b-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="fe48b-223">设置 CsLisPort</span><span class="sxs-lookup"><span data-stu-id="fe48b-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="fe48b-224">设置 CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="fe48b-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="fe48b-225">配置用户配置文件</span><span class="sxs-lookup"><span data-stu-id="fe48b-225">Configure User Profile</span></span>
<span data-ttu-id="fe48b-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="fe48b-226"></span></span>

<span data-ttu-id="fe48b-227">您的用户 （通过用户创建工具） 创建后您可以配置与业务服务器 2015年负载配置工具 (UserProfileGenerator.exe) Skype 的用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="fe48b-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="fe48b-228">运行 Business Server 2015 负载配置工具的 Skype</span><span class="sxs-lookup"><span data-stu-id="fe48b-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="fe48b-229">启动加载配置工具 (UserProfileGenerator.exe)，并填写选项卡。</span><span class="sxs-lookup"><span data-stu-id="fe48b-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="fe48b-230">此工具创建一个目录的每个客户端需要运行您模拟的计算机。</span><span class="sxs-lookup"><span data-stu-id="fe48b-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="fe48b-231">每个客户端目录附带的脚本来启动 Skype 的业务 Server 2015 压力和性能工具 (LyncPerfTool.exe)。</span><span class="sxs-lookup"><span data-stu-id="fe48b-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="fe48b-232">以下各节将提供有关如何填充 Business Server 2015 负载配置工具的 Skype 的每个选项卡上的域中的示例。</span><span class="sxs-lookup"><span data-stu-id="fe48b-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fe48b-233">负载配置工具 (UserProfileGenerator.exe) 中使用的特定于用户的值必须为池匹配业务 2015年用户创建工具 (UserProvisioningTool.exe) Skype 中指定的值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="fe48b-234">常见配置选项卡</span><span class="sxs-lookup"><span data-stu-id="fe48b-234">Common Configuration tab</span></span>

<span data-ttu-id="fe48b-235">负载配置工具的**通用配置**选项卡如下所示。</span><span class="sxs-lookup"><span data-stu-id="fe48b-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="fe48b-236">填写的通用配置选项卡字段中的以下步骤所述。</span><span class="sxs-lookup"><span data-stu-id="fe48b-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![显示“常见配置”选项卡的“用户设置”选项卡。](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="fe48b-238">在**可用机号码**字段中，键入您想要用于运行压力和性能工具 (LyncPerfTool.exe) 的计算机数量。</span><span class="sxs-lookup"><span data-stu-id="fe48b-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="fe48b-239">我们建议您有一台计算机，您将模拟，每个 4500 用户，但该号码可能会有所不同，如果减少负载级别，或使用该工具的可用功能 （在常规方案选项卡设置负载级别） 的子集。</span><span class="sxs-lookup"><span data-stu-id="fe48b-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="fe48b-240">在**前缀用户名**字段中，输入用户名字段的所有用户的前缀。</span><span class="sxs-lookup"><span data-stu-id="fe48b-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="fe48b-241">若要登录的统一资源标识符 (URI) 将是： *UserPrefix [用户开始索引...（数用户-1）]@User 域*，例如，myUser009@Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="fe48b-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="fe48b-242">在**为所有用户的密码**字段中，输入的用户的创建过程中使用的密码。</span><span class="sxs-lookup"><span data-stu-id="fe48b-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="fe48b-243">如果将此字段留空将设置用户名的密码。</span><span class="sxs-lookup"><span data-stu-id="fe48b-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="fe48b-244">在**用户启动索引**字段中，输入要配置的第一个用户的索引。</span><span class="sxs-lookup"><span data-stu-id="fe48b-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="fe48b-245">您可以配置不同范围的不同类型或级别的负载，但您想要配置每个范围后，必须运行负载配置工具 (UserProfileGenerator.exe)。</span><span class="sxs-lookup"><span data-stu-id="fe48b-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="fe48b-246">在**用户数量**字段中，输入您要配置的用户总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="fe48b-247">在**用户域**字段中，输入用于 SIP URI 的域。</span><span class="sxs-lookup"><span data-stu-id="fe48b-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="fe48b-248">这用于构造 SIP URI 的每个用户登录到 Skype 对于业务 Server 2015 前端服务器或 Standard Edition 服务器，并且可能不同帐户的域。</span><span class="sxs-lookup"><span data-stu-id="fe48b-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="fe48b-249">在**帐户域**字段中，输入 AD DS 域登录。</span><span class="sxs-lookup"><span data-stu-id="fe48b-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="fe48b-250">在**MPOP 百分比**（多个状态点百分比） 字段中，为提供登录来自多个计算机或设备，例如 10%的用户的百分比的值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="fe48b-251">在**登录每秒 （每个实例）** 字段中输入并发终结点的最大数量。</span><span class="sxs-lookup"><span data-stu-id="fe48b-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="fe48b-252">这是最大数量为您的用户，记录项和建议是小于 / 等于每秒 2 的速率 (< = 2)。</span><span class="sxs-lookup"><span data-stu-id="fe48b-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="fe48b-253">在**访问代理服务器或池 FQDN**字段中，输入您希望客户端连接到的服务器的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="fe48b-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="fe48b-254">如果用户要外部登录，您需要键入访问代理服务器。</span><span class="sxs-lookup"><span data-stu-id="fe48b-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="fe48b-255">如果用户是内部，使其企业版池或 Standard Edition 服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fe48b-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="fe48b-256">在**端口**字段中，输入您希望用户使用 SIP 的端口 （此处的默认值为 5061）。</span><span class="sxs-lookup"><span data-stu-id="fe48b-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="fe48b-257">对于**外部网络服务器设置**字段中，提供访问代理服务器或池 FQDN，同样，**端口**。</span><span class="sxs-lookup"><span data-stu-id="fe48b-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="fe48b-258">这些设置将用于外部终结点负载模拟。</span><span class="sxs-lookup"><span data-stu-id="fe48b-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="fe48b-259">常规方案选项卡</span><span class="sxs-lookup"><span data-stu-id="fe48b-259">General Scenarios tab</span></span>

![显示“常规方案”选项卡的“加载配置”工具。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="fe48b-261">可以为每个常规方案提供通过确定想要运行或离开已禁用配置的负载级别和参数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="fe48b-262">下面是常规选项：</span><span class="sxs-lookup"><span data-stu-id="fe48b-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe48b-263">对于所有字段，但本地信息服务负载级别值是**已禁用**、**低**、**中等**、**高**，或**自定义**。</span><span class="sxs-lookup"><span data-stu-id="fe48b-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="fe48b-264">如果选择任何设置，但已禁用，然后配置生成的每个客户端中。</span><span class="sxs-lookup"><span data-stu-id="fe48b-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="fe48b-265">高导致服务器; 中受支持的最大负载medium 为 60%的高负载;低为 30%。</span><span class="sxs-lookup"><span data-stu-id="fe48b-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="fe48b-266">**即时消息-** 这包括对等和会议;负载级别选择适当的值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="fe48b-267">**音频会议-** 选择音频会议*仅*负载级别。</span><span class="sxs-lookup"><span data-stu-id="fe48b-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="fe48b-268">**语音方案**一节中，将稍后处理对等呼叫。</span><span class="sxs-lookup"><span data-stu-id="fe48b-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="fe48b-269">打开**高级**选项卡启用多视图。</span><span class="sxs-lookup"><span data-stu-id="fe48b-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="fe48b-270">**应用程序共享-** 选择应用程序共享负载级别。</span><span class="sxs-lookup"><span data-stu-id="fe48b-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="fe48b-271">**数据协作-** 选择数据协作，其中包括数据会议负载级别。</span><span class="sxs-lookup"><span data-stu-id="fe48b-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="fe48b-272">**通讯组列表扩展-** 单击**高级**按钮，具有相同的用户创建工具 (UserProvisioningTool.exe) 的 DL 选项卡上配置的值填充该字段。</span><span class="sxs-lookup"><span data-stu-id="fe48b-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="fe48b-273">选择负载级别。</span><span class="sxs-lookup"><span data-stu-id="fe48b-273">Choose a load level.</span></span>
    
- <span data-ttu-id="fe48b-274">**通讯簿 Web 查询-** 这是通讯簿查找服务，而不是通讯簿文件下载。</span><span class="sxs-lookup"><span data-stu-id="fe48b-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="fe48b-275">如果您希望此启用通讯簿文件下载，请单击**高级**按钮，并将**EnableABSDownload**设置为 True。</span><span class="sxs-lookup"><span data-stu-id="fe48b-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="fe48b-276">负载级别赋予一个值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="fe48b-277">**响应组服务-** 单击**高级**按钮并指定响应组已设置响应组服务代理时创建的 Uri。</span><span class="sxs-lookup"><span data-stu-id="fe48b-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="fe48b-278">您必须选择至少一个响应组。</span><span class="sxs-lookup"><span data-stu-id="fe48b-278">You must choose at least one response group.</span></span> <span data-ttu-id="fe48b-279">若要使用的详细信息，请用分号分隔的响应组。</span><span class="sxs-lookup"><span data-stu-id="fe48b-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="fe48b-280">**RGSUriSuffixStartIndex**和**RGSUriSuffixEndIndex**更新到实际值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="fe48b-281">选择负载级别。</span><span class="sxs-lookup"><span data-stu-id="fe48b-281">Choose a load level.</span></span>
    
- <span data-ttu-id="fe48b-282">**位置信息服务-** 选择启用或禁用负载级别。</span><span class="sxs-lookup"><span data-stu-id="fe48b-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe48b-283">为每个方案具有高级按钮旁边，和一组启用变体设置为默认设置的复选框。</span><span class="sxs-lookup"><span data-stu-id="fe48b-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="fe48b-284">选择*临时*将允许生成模拟将整个小时创建的会议的工具。</span><span class="sxs-lookup"><span data-stu-id="fe48b-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="fe48b-285">选择*大型会议*意味着，将模拟大型会议方案。</span><span class="sxs-lookup"><span data-stu-id="fe48b-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="fe48b-286">*外部*通知工具还模拟外部用户。</span><span class="sxs-lookup"><span data-stu-id="fe48b-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="fe48b-287">这些按钮和复选框是特定于每个方案的额外值将更改压力和性能工具的行为和进行自定义项可能。</span><span class="sxs-lookup"><span data-stu-id="fe48b-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="fe48b-288">对于每个方案 （除外位置信息服务） 的常规方案选项卡上，如果负载级别的值为**自定义**，然后对话速率将计算使用高级对话框中的相应字段。</span><span class="sxs-lookup"><span data-stu-id="fe48b-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="fe48b-289">字段名称可能有所不同，具体取决于情况，但将状态字段的说明：*将只使用注意此号码，如果从下拉菜单中选择自定义*。</span><span class="sxs-lookup"><span data-stu-id="fe48b-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="fe48b-290">**高**、**中等**和**低**的值将更改每种形式嵌入到用户模型的所有方案的平衡对话率。</span><span class="sxs-lookup"><span data-stu-id="fe48b-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="fe48b-291">如果需要更改每种形式由于预期用法差异的负载级别，请使用自定义对话速度。</span><span class="sxs-lookup"><span data-stu-id="fe48b-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="fe48b-292">语音方案选项卡</span><span class="sxs-lookup"><span data-stu-id="fe48b-292">Voice Scenarios tab</span></span>

<span data-ttu-id="fe48b-293">这是您所有语音相关的方案的配置的选项卡。</span><span class="sxs-lookup"><span data-stu-id="fe48b-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![“加载配置”工具“语音方案”选项卡。](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="fe48b-295">是您的选项：</span><span class="sxs-lookup"><span data-stu-id="fe48b-295">Your options are:</span></span>
  
- <span data-ttu-id="fe48b-296">**-VoIP**单击**高级**按钮，并添加 PhoneAreaCode 和 LocationProfile （拨号计划） 字段的值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="fe48b-297">您还将负载级别授予一个值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="fe48b-298">如果您选择负载级别 VoIP 或 UC/PSTN 网关启用，然后公共交换电话交换网 (PSTN) 与统一通信 (UC) 将生成配置文件以模拟外部呼叫。</span><span class="sxs-lookup"><span data-stu-id="fe48b-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="fe48b-299">**UC/PSTN 网关-** 您需要选择负载级别值，并且当以外禁用选择任何内容，您还需要通过单击**高级**按钮提供 PSTN 区号的值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="fe48b-300">在中介服务器和 PSTN 下，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="fe48b-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="fe48b-301">请确保已配置为区号的路由。</span><span class="sxs-lookup"><span data-stu-id="fe48b-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="fe48b-302">您可用于任一 Skype 业务控制面板或 Skype 的业务命令行管理程序来验证语音路由配置。</span><span class="sxs-lookup"><span data-stu-id="fe48b-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="fe48b-303">**会议助理-** 提供针对负载级别值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="fe48b-304">禁用之外的任何值将启用**电话号码**字段。</span><span class="sxs-lookup"><span data-stu-id="fe48b-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="fe48b-305">输入您想要使用的自动助理的电话号码。</span><span class="sxs-lookup"><span data-stu-id="fe48b-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="fe48b-306">单击**高级**，并对**LocationProfile**字段为一个值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="fe48b-307">**呼叫驻留服务-** 此处提供负载级别。</span><span class="sxs-lookup"><span data-stu-id="fe48b-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="fe48b-308">**中介服务器和 PSTN-** 您想要使用的每台中介服务器需要其自己的 PSTN 模拟器。</span><span class="sxs-lookup"><span data-stu-id="fe48b-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="fe48b-309">您已确定您要用于模拟器哪些客户端后，配置中介服务器路由到的计算机在呼叫 PSTN 模拟器您配置。</span><span class="sxs-lookup"><span data-stu-id="fe48b-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="fe48b-310">单击**添加**按钮为中介服务器配置值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fe48b-311">每个方案有旁边它位于高级按钮。</span><span class="sxs-lookup"><span data-stu-id="fe48b-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="fe48b-312">高级的对话框包含设置特定于每个方案更改压力和性能工具的行为，并且启用自定义。</span><span class="sxs-lookup"><span data-stu-id="fe48b-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="fe48b-313">> 的语音方案选项卡上的每个方案中，如果负载级别的值为**自定义**，然后对话速率将计算使用高级对话框中的对应字段。</span><span class="sxs-lookup"><span data-stu-id="fe48b-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="fe48b-314">字段名称可能有所不同，具体取决于情况，但将状态字段的说明：*将只使用注意此号码，如果从下拉菜单中选择自定义*。</span><span class="sxs-lookup"><span data-stu-id="fe48b-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="fe48b-315">Web 应用程序选项卡</span><span class="sxs-lookup"><span data-stu-id="fe48b-315">Web App tab</span></span>

![“加载配置”工具“Web 应用”选项卡。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="fe48b-317">Web 应用程序支持通过统一通信 Web API (UCWA) 服务器的前端服务器上安装了会议方案。</span><span class="sxs-lookup"><span data-stu-id="fe48b-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="fe48b-318">使用 Web 应用程序选项卡可以配置所有 web 应用程序相关方案。</span><span class="sxs-lookup"><span data-stu-id="fe48b-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="fe48b-319">选项如下：</span><span class="sxs-lookup"><span data-stu-id="fe48b-319">Options are:</span></span>
  
- <span data-ttu-id="fe48b-320">**常规 Web 应用程序设置-** 单击**其他设置**按钮并设置到目录池虚拟 IP (VIP) 的前端池 VIP 的**ReachTargetServerUrl** 。</span><span class="sxs-lookup"><span data-stu-id="fe48b-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="fe48b-321">**应用程序共享-** 为负载级别选择一个值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="fe48b-322">**数据协作-** 为负载级别选择一个值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="fe48b-323">**即时消息-** 为负载级别选择一个值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="fe48b-324">**语音会议 –** 为负载级别选择一个值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe48b-325">为每个方案都有旁边它位于**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="fe48b-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="fe48b-326">高级的对话框包含特定于每个方案的值将更改压力和性能工具的行为和启用自定义。 > 对于每个 Web 应用程序方案，如果负载级别为**自定义**，然后中指定的值**ConversationsPerHour**而不是默认使用字段。</span><span class="sxs-lookup"><span data-stu-id="fe48b-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="fe48b-327">移动选项卡</span><span class="sxs-lookup"><span data-stu-id="fe48b-327">Mobility tab</span></span>

<span data-ttu-id="fe48b-328">使用此选项卡配置的所有 mobility 相关方案。</span><span class="sxs-lookup"><span data-stu-id="fe48b-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![“加载配置”工具“移动性”选项卡。](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="fe48b-330">此处的选项是：</span><span class="sxs-lookup"><span data-stu-id="fe48b-330">The options here are:</span></span>
  
- <span data-ttu-id="fe48b-331">**常规的移动性设置-** 单击**其他设置**，并将字段 UcwaTargetServerUrl 设置为控制器池虚拟 IP (VIP) 或前端池 VIP。</span><span class="sxs-lookup"><span data-stu-id="fe48b-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="fe48b-332">**状态和 P2P 即时消息/音频-** 选择要启用移动模拟的负载级别值。</span><span class="sxs-lookup"><span data-stu-id="fe48b-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe48b-333">为每个方案都有旁边它位于**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="fe48b-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="fe48b-334">高级的对话框包含特定于每个方案的值将更改压力和性能工具的行为和启用自定义。 > 对于每个移动性应用场景，如果负载级别为**自定义**，然后中指定的值**ConversationsPerHour**而不是默认使用字段。</span><span class="sxs-lookup"><span data-stu-id="fe48b-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="fe48b-335">摘要选项卡</span><span class="sxs-lookup"><span data-stu-id="fe48b-335">Summary tab</span></span>

<span data-ttu-id="fe48b-336">摘要选项卡指示哪些用户用于为每个方案。</span><span class="sxs-lookup"><span data-stu-id="fe48b-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![“加载配置”工具“摘要”选项卡。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="fe48b-338">摘要选项卡指示哪些用户用于为每个方案。</span><span class="sxs-lookup"><span data-stu-id="fe48b-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="fe48b-339">就可以通过选择**生成启用自定义用户范围**复选框，然后双击具有您要自定义用户范围的表中的方案中手动配置用户号码范围。</span><span class="sxs-lookup"><span data-stu-id="fe48b-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="fe48b-340">检查 **(RunClient.bat) 添加登录延迟启动时**才能在对应的登录速率生成的批处理文件中包含延迟。</span><span class="sxs-lookup"><span data-stu-id="fe48b-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="fe48b-341">这会阻止服务器过载大量用户在登录时很有用。</span><span class="sxs-lookup"><span data-stu-id="fe48b-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="fe48b-342">单击**生成文件**，然后选择要用来生成配置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fe48b-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="fe48b-343">已成功创建您的文件时，将出现一个对话框。</span><span class="sxs-lookup"><span data-stu-id="fe48b-343">A dialog box will appear when your files have been successfully created.</span></span>
  
![“已成功生成加载配置文件”消息框。只需单击“确定”。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="fe48b-346">运行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="fe48b-346">Run LyncPerfTool</span></span>
<span data-ttu-id="fe48b-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="fe48b-347"></span></span>

<span data-ttu-id="fe48b-348">您需要创建的业务 Server 2015 压力和性能工具 (LyncPerfTool.exe) 运行 Skype 之前的用户、 联系人和方案。</span><span class="sxs-lookup"><span data-stu-id="fe48b-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="fe48b-349">有关使用这些工具才能执行这些操作的详细信息，请参阅[创建用户和联系人](using-the-tool.md#BKMK_CreateUsersAndContacts)和[配置用户配置文件](using-the-tool.md#BKMK_UserProfile)之前本文中。</span><span class="sxs-lookup"><span data-stu-id="fe48b-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="fe48b-350">运行这些工具还将生成的文件将运行的使用压力和性能工具批处理文件的一部分包含所需的参数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="fe48b-351">运行 Business Server 2015 压力和性能工具 Skype</span><span class="sxs-lookup"><span data-stu-id="fe48b-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="fe48b-352">负载配置工具 (UserProfileGenerator.exe) 创建批处理文件，使您能够通过注册性能计数器和加载 XML 配置文件来运行压力和性能工具 (LyncPerfTool.exe)。</span><span class="sxs-lookup"><span data-stu-id="fe48b-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="fe48b-353">批处理文件运行每个配置文件的一个实例 LyncPerfTool.exe。</span><span class="sxs-lookup"><span data-stu-id="fe48b-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="fe48b-354">若要运行的批处理文件，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fe48b-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="fe48b-355">运行压力和性能测试</span><span class="sxs-lookup"><span data-stu-id="fe48b-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="fe48b-356">将具有的配置文件夹和文件内的文件夹复制到每个客户端计算机具有 LyncPerfTool.exe 的目录。</span><span class="sxs-lookup"><span data-stu-id="fe48b-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="fe48b-357">（例如，如果您在名为 1.28_13.16.16 的文件夹中生成的配置文件，复制该文件夹到与 LyncPerfTool.exe 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fe48b-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="fe48b-358">执行此操作在每个客户端上。）</span><span class="sxs-lookup"><span data-stu-id="fe48b-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="fe48b-359">导航到客户端文件夹，然后运行**RunClient**批处理脚本。</span><span class="sxs-lookup"><span data-stu-id="fe48b-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="fe48b-360">您可以双击在 Windows 资源管理器中的批处理文件，它将为该客户端运行的所有配置文件。</span><span class="sxs-lookup"><span data-stu-id="fe48b-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="fe48b-361">此外可以使用以下语法，从客户端文件夹中运行该脚本：</span><span class="sxs-lookup"><span data-stu-id="fe48b-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
   ```
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

<span data-ttu-id="fe48b-362">若要直接运行压力和性能工具，打开命令提示符并键入以下命令，在命令行 (当第一次执行此操作，请务必注册性能计数器和`regsvr32 /i /n /s LyncPerfToolPerf.dll`，如本主题后面的备注中所示):</span><span class="sxs-lookup"><span data-stu-id="fe48b-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="fe48b-363">若要配置文件中显示的值该工具，包括`/displayfile`参数上述命令中，使其类似于此：</span><span class="sxs-lookup"><span data-stu-id="fe48b-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="fe48b-364">*结束*流程，按 Ctrl + C。</span><span class="sxs-lookup"><span data-stu-id="fe48b-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe48b-365">直接运行压力和性能工具时之前, 必须注册性能计数器通过以下命令：`regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="fe48b-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe48b-366">压力和性能工具开始的每个实例将立即开始，通常为用户的每秒的一个用户在登录。</span><span class="sxs-lookup"><span data-stu-id="fe48b-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="fe48b-367">峰值用户登录速率为池为大约每秒的 12。</span><span class="sxs-lookup"><span data-stu-id="fe48b-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="fe48b-368">这意味着，您不应启动超过 12 LyncPerfTool.exe 实例同时时用户仍登录。</span><span class="sxs-lookup"><span data-stu-id="fe48b-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="fe48b-369">一个千用户大约需要 20 分钟完全 1 秒登录。</span><span class="sxs-lookup"><span data-stu-id="fe48b-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="fe48b-370">解释结果</span><span class="sxs-lookup"><span data-stu-id="fe48b-370">Interpreting the Results</span></span>
<span data-ttu-id="fe48b-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="fe48b-371"></span></span>

<span data-ttu-id="fe48b-372">为业务服务器 2015年压力和性能工具 Skype 具有许多可帮助您了解客户端执行和是否它会遇到问题的计数器。</span><span class="sxs-lookup"><span data-stu-id="fe48b-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="fe48b-373">客户端计数器</span><span class="sxs-lookup"><span data-stu-id="fe48b-373">Client Counters</span></span>

<span data-ttu-id="fe48b-374">LyncPerfTool.exe 运行每个的实例都具有单独的计数器实例。</span><span class="sxs-lookup"><span data-stu-id="fe48b-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="fe48b-375">每个实例名为通过其进程 id。</span><span class="sxs-lookup"><span data-stu-id="fe48b-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="fe48b-376">如果客户端是重载会发生其他问题。</span><span class="sxs-lookup"><span data-stu-id="fe48b-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="fe48b-377">若要防止这些问题：</span><span class="sxs-lookup"><span data-stu-id="fe48b-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="fe48b-378">监视客户端计算机上的 CPU 和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="fe48b-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="fe48b-379">如果 CPU 始终为 90%以上，减少用户的数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="fe48b-380">高的内存需求量后，您可能会遇到问题，如果页面文件开始运行空间不足。</span><span class="sxs-lookup"><span data-stu-id="fe48b-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="fe48b-381">验证提交费用未命中的计算机上的限制。</span><span class="sxs-lookup"><span data-stu-id="fe48b-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="fe48b-382">如果遇到内存限制考虑增加页面文件的大小或减少用户的数量。</span><span class="sxs-lookup"><span data-stu-id="fe48b-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="fe48b-383">下面是关键性能计数器的列表：</span><span class="sxs-lookup"><span data-stu-id="fe48b-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="fe48b-384">**常规信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-384">**General Information**</span></span>

|<span data-ttu-id="fe48b-385">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-385">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-386">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-387">以分钟为单位的时间</span><span class="sxs-lookup"><span data-stu-id="fe48b-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="fe48b-388">自从启动以来过程所用时间。</span><span class="sxs-lookup"><span data-stu-id="fe48b-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="fe48b-389">活动终结点</span><span class="sxs-lookup"><span data-stu-id="fe48b-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="fe48b-390">当前连接到服务器的终结点的数目。</span><span class="sxs-lookup"><span data-stu-id="fe48b-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="fe48b-391">失败的登录</span><span class="sxs-lookup"><span data-stu-id="fe48b-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="fe48b-392">终结点登录失败的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="fe48b-393">登录尝试次数</span><span class="sxs-lookup"><span data-stu-id="fe48b-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="fe48b-394">终结点登录尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="fe48b-395">断开连接的终结点</span><span class="sxs-lookup"><span data-stu-id="fe48b-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="fe48b-396">已断开的终结点的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="fe48b-397">**状态信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-397">**Presence Information**</span></span>

|<span data-ttu-id="fe48b-398">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-398">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-399">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-400">SetPresence 呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="fe48b-401">总数状态更改尝试。</span><span class="sxs-lookup"><span data-stu-id="fe48b-401">Total number of presence change attempts.</span></span> <span data-ttu-id="fe48b-402">有关不同类型的状态更改，请参阅 SetPresence （状态类型） 调用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="fe48b-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="fe48b-403">NNN 响应的 SetPresence</span><span class="sxs-lookup"><span data-stu-id="fe48b-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="fe48b-404">Nnn 响应代码从服务器接收的总次数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="fe48b-405">对 GetPresence 呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="fe48b-406">获取状态请求尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="fe48b-407">NNN 响应的 GetPresence</span><span class="sxs-lookup"><span data-stu-id="fe48b-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="fe48b-408">Nnn 响应代码从服务器接收的总次数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="fe48b-409">**通讯簿服务信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-409">**Address Book service information**</span></span>

|<span data-ttu-id="fe48b-410">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-410">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-411">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-412">尝试 ABS 完全/增量文件下载</span><span class="sxs-lookup"><span data-stu-id="fe48b-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="fe48b-413">尝试完全或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="fe48b-414">ABS 完全/增量文件下载成功</span><span class="sxs-lookup"><span data-stu-id="fe48b-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="fe48b-415">尝试完全或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="fe48b-416">通讯簿 Web 查询服务相关的计数器</span><span class="sxs-lookup"><span data-stu-id="fe48b-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="fe48b-417">通讯簿文件下载相关的计数器。</span><span class="sxs-lookup"><span data-stu-id="fe48b-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="fe48b-418">ABS WS 呼叫尝试</span><span class="sxs-lookup"><span data-stu-id="fe48b-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="fe48b-419">尝试的通讯簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="fe48b-420">ABS WS 呼叫成功</span><span class="sxs-lookup"><span data-stu-id="fe48b-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="fe48b-421">返回一个成功的响应代码的通讯簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="fe48b-422">ABS WS 呼叫失败</span><span class="sxs-lookup"><span data-stu-id="fe48b-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="fe48b-423">返回错误响应代码的通讯簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="fe48b-424">此类别包括用于监视通讯簿服务 (ABS) 文件下载和通讯簿 Web 查询服务请求的计数器。</span><span class="sxs-lookup"><span data-stu-id="fe48b-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="fe48b-425">**通讯组列表 (DL) 信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="fe48b-426">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-426">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-427">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-428">尝试的呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="fe48b-429">尝试的通讯组列表扩展 (DLX) web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="fe48b-430">成功呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="fe48b-431">返回一个成功的响应代码的 DLX web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="fe48b-432">失败的呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="fe48b-433">返回错误响应代码的 DLX web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="fe48b-434">性能计数器下面列出报表编号的所有语音 IP (电话 VoIP) 呼叫，包括呼叫到中介服务器，A / V 会议服务器、 边缘服务器，响应组应用程序和会议自动助理，启用这些方案时。</span><span class="sxs-lookup"><span data-stu-id="fe48b-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="fe48b-435">**VoIP Basic 信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="fe48b-436">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-436">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-437">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-438">呼叫活动</span><span class="sxs-lookup"><span data-stu-id="fe48b-438">Calls Active</span></span>  <br/> |<span data-ttu-id="fe48b-439">当前正在进行调用的传入/传出语音总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="fe48b-440">终止呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="fe48b-441">已终止的传入/传出语音呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="fe48b-442">拒绝呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="fe48b-443">拒绝的传入语音呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="fe48b-444">尝试的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="fe48b-445">传入/传出语音呼叫尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="fe48b-446">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="fe48b-447">传入/传出建立语音呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="fe48b-448">呼叫接收到的 NNN</span><span class="sxs-lookup"><span data-stu-id="fe48b-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="fe48b-449">Nnn 响应代码从服务器接收的总次数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="fe48b-450">VoIP 通过率 （%）</span><span class="sxs-lookup"><span data-stu-id="fe48b-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="fe48b-451">总呼叫尝试建立总呼叫。</span><span class="sxs-lookup"><span data-stu-id="fe48b-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="fe48b-452">**响应组服务呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="fe48b-453">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-453">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-454">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-455">呼叫活动</span><span class="sxs-lookup"><span data-stu-id="fe48b-455">Calls Active</span></span>  <br/> |<span data-ttu-id="fe48b-456">对响应组应用程序的活动呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="fe48b-457">尝试的呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="fe48b-458">呼叫尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="fe48b-459">**即时消息 (IM) 呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="fe48b-460">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-460">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-461">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-462">呼叫活动</span><span class="sxs-lookup"><span data-stu-id="fe48b-462">Calls Active</span></span>  <br/> |<span data-ttu-id="fe48b-463">正在进行传入/传出即时消息呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="fe48b-464">终止呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="fe48b-465">已终止的传入/传出即时消息的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="fe48b-466">呼叫接收到的 NNN</span><span class="sxs-lookup"><span data-stu-id="fe48b-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="fe48b-467">Nnn 响应代码从服务器接收的总次数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="fe48b-468">收到发送的 IM 消息</span><span class="sxs-lookup"><span data-stu-id="fe48b-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="fe48b-469">消息的总数收到或发送的所有会话。</span><span class="sxs-lookup"><span data-stu-id="fe48b-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="fe48b-470">尝试的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="fe48b-471">传入/传出即时消息呼叫尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="fe48b-472">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="fe48b-473">建立传入/传出即时消息呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="fe48b-474">**应用程序共享呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="fe48b-475">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-475">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-476">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-477">呼叫活动</span><span class="sxs-lookup"><span data-stu-id="fe48b-477">Calls Active</span></span>  <br/> |<span data-ttu-id="fe48b-478">正在进行的传入/传出的应用程序共享呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="fe48b-479">终止呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="fe48b-480">终止传入/传出的应用程序已共享呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="fe48b-481">呼叫接收到的 NNN</span><span class="sxs-lookup"><span data-stu-id="fe48b-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="fe48b-482">Nnn 响应代码从服务器接收的总次数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="fe48b-483">尝试的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="fe48b-484">传入/传出的应用程序共享呼叫尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="fe48b-485">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="fe48b-486">传入/传出的应用程序共享建立呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="fe48b-487">**CAA 呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-487">**CAA Call Information**</span></span>

|<span data-ttu-id="fe48b-488">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-488">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-489">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-490">呼叫活动</span><span class="sxs-lookup"><span data-stu-id="fe48b-490">Calls Active</span></span>  <br/> |<span data-ttu-id="fe48b-491">当前正在进行调用的传入/传出公用电话交换网 (PSTN) 的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="fe48b-492">终止呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="fe48b-493">已终止的传入/传出 PSTN 呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="fe48b-494">尝试的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="fe48b-495">传入/传出 PSTN 呼叫尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="fe48b-496">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="fe48b-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="fe48b-497">建立传入/传出 PSTN 呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="fe48b-498">**会议信息**</span><span class="sxs-lookup"><span data-stu-id="fe48b-498">**Conference Information**</span></span>

|<span data-ttu-id="fe48b-499">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-499">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-500">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-501">活动的即时消息会议</span><span class="sxs-lookup"><span data-stu-id="fe48b-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="fe48b-502">正在进行的即时消息会议的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="fe48b-503">活动的音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="fe48b-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="fe48b-504">总数正在进行音频/视频 (A / V) 会议。</span><span class="sxs-lookup"><span data-stu-id="fe48b-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="fe48b-505">活动应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="fe48b-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="fe48b-506">正在进行的应用程序共享会议的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="fe48b-507">参与者数目</span><span class="sxs-lookup"><span data-stu-id="fe48b-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="fe48b-508">当前连接到会议的参与者的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="fe48b-509">会议计划失败</span><span class="sxs-lookup"><span data-stu-id="fe48b-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="fe48b-510">试图安排会议时失败的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="fe48b-511">加入会议失败</span><span class="sxs-lookup"><span data-stu-id="fe48b-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="fe48b-512">尝试连接到会议时失败的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="fe48b-513">**UCWA 客户端计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="fe48b-514">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="fe48b-514">**Performance Counter**</span></span>|<span data-ttu-id="fe48b-515">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe48b-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe48b-516">总数 IMMCU 加入成功</span><span class="sxs-lookup"><span data-stu-id="fe48b-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="fe48b-517">加入即时消息会议的总数。</span><span class="sxs-lookup"><span data-stu-id="fe48b-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="fe48b-518">总数 DMCU 加入成功</span><span class="sxs-lookup"><span data-stu-id="fe48b-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="fe48b-519">总数 A / V 会议加入。</span><span class="sxs-lookup"><span data-stu-id="fe48b-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

