---
title: Using the Skype for Business Server 2015 Stress and Performance Tool
ms.author: heidip
author: microsoftheidi
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.
ms.openlocfilehash: 5f73ef6733c2f09cdf3e06bc8a6495c743d8b423
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="dda54-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="dda54-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="dda54-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span><span class="sxs-lookup"><span data-stu-id="dda54-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="dda54-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span><span class="sxs-lookup"><span data-stu-id="dda54-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="dda54-106">Create Users and Contacts</span><span class="sxs-lookup"><span data-stu-id="dda54-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="dda54-107">Configure User Profile</span><span class="sxs-lookup"><span data-stu-id="dda54-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="dda54-108">Run LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="dda54-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="dda54-109">Interpreting the Results</span><span class="sxs-lookup"><span data-stu-id="dda54-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="dda54-110">Create Users and Contacts</span><span class="sxs-lookup"><span data-stu-id="dda54-110">Create Users and Contacts</span></span>
<span data-ttu-id="dda54-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="dda54-111"></span></span>

<span data-ttu-id="dda54-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span><span class="sxs-lookup"><span data-stu-id="dda54-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="dda54-113">This is a list of helpful terms that might be useful as you read through the topics:</span><span class="sxs-lookup"><span data-stu-id="dda54-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="dda54-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span><span class="sxs-lookup"><span data-stu-id="dda54-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="dda54-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span><span class="sxs-lookup"><span data-stu-id="dda54-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="dda54-116">**Distribution Lists** - Or DLs.</span><span class="sxs-lookup"><span data-stu-id="dda54-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="dda54-117">These are objects in AD DS that contain a list of AD DS users.</span><span class="sxs-lookup"><span data-stu-id="dda54-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="dda54-118">They're used to facilitate communications across groups of people.</span><span class="sxs-lookup"><span data-stu-id="dda54-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="dda54-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span><span class="sxs-lookup"><span data-stu-id="dda54-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="dda54-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span><span class="sxs-lookup"><span data-stu-id="dda54-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="dda54-121">Create Users and Contacts by using UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="dda54-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="dda54-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span><span class="sxs-lookup"><span data-stu-id="dda54-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="dda54-123">You need to do this, because you're going to be creating Active Directory users.</span><span class="sxs-lookup"><span data-stu-id="dda54-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="dda54-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span><span class="sxs-lookup"><span data-stu-id="dda54-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="dda54-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span><span class="sxs-lookup"><span data-stu-id="dda54-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="dda54-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span><span class="sxs-lookup"><span data-stu-id="dda54-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="dda54-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span><span class="sxs-lookup"><span data-stu-id="dda54-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dda54-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span><span class="sxs-lookup"><span data-stu-id="dda54-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="dda54-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span><span class="sxs-lookup"><span data-stu-id="dda54-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="dda54-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span><span class="sxs-lookup"><span data-stu-id="dda54-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="dda54-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span><span class="sxs-lookup"><span data-stu-id="dda54-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="dda54-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span><span class="sxs-lookup"><span data-stu-id="dda54-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="dda54-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span><span class="sxs-lookup"><span data-stu-id="dda54-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="dda54-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span><span class="sxs-lookup"><span data-stu-id="dda54-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="dda54-135">要配置服务器选项：</span><span class="sxs-lookup"><span data-stu-id="dda54-135">To configure server options:</span></span>

1. <span data-ttu-id="dda54-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span><span class="sxs-lookup"><span data-stu-id="dda54-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="dda54-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span><span class="sxs-lookup"><span data-stu-id="dda54-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="dda54-138">In the **Password** field, type a password that will be used across all the test user accounts.</span><span class="sxs-lookup"><span data-stu-id="dda54-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="dda54-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span><span class="sxs-lookup"><span data-stu-id="dda54-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="dda54-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span><span class="sxs-lookup"><span data-stu-id="dda54-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="dda54-141">(If the OU doesn't already exist, it'll be created for you).</span><span class="sxs-lookup"><span data-stu-id="dda54-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="dda54-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span><span class="sxs-lookup"><span data-stu-id="dda54-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="dda54-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span><span class="sxs-lookup"><span data-stu-id="dda54-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="dda54-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="dda54-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="dda54-145">In the **Number of Users** field, give the total number of test users you want to create.</span><span class="sxs-lookup"><span data-stu-id="dda54-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="dda54-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span><span class="sxs-lookup"><span data-stu-id="dda54-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![显示“创建用户”选项卡的“用户设置”工具。](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="dda54-148">Create Users button</span><span class="sxs-lookup"><span data-stu-id="dda54-148">Create Users button</span></span>

<span data-ttu-id="dda54-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span><span class="sxs-lookup"><span data-stu-id="dda54-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="dda54-150">If there are any validation errors, you'll be prompted to fix them.</span><span class="sxs-lookup"><span data-stu-id="dda54-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="dda54-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span><span class="sxs-lookup"><span data-stu-id="dda54-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="dda54-152">You'll see a progress bar at the bottom of the tool as it runs.</span><span class="sxs-lookup"><span data-stu-id="dda54-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="dda54-153">Don't close the application while the progress bar is active.</span><span class="sxs-lookup"><span data-stu-id="dda54-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="dda54-154">User creation takes time, so please plan accordingly.</span><span class="sxs-lookup"><span data-stu-id="dda54-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="dda54-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span><span class="sxs-lookup"><span data-stu-id="dda54-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="dda54-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span><span class="sxs-lookup"><span data-stu-id="dda54-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="dda54-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span><span class="sxs-lookup"><span data-stu-id="dda54-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="dda54-158">Here is an example:  *TestUser20@contoso.net*  .</span><span class="sxs-lookup"><span data-stu-id="dda54-158">Here is an example:  *TestUser20@contoso.net*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="dda54-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span><span class="sxs-lookup"><span data-stu-id="dda54-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="dda54-160">Delete Users button</span><span class="sxs-lookup"><span data-stu-id="dda54-160">Delete Users button</span></span>

<span data-ttu-id="dda54-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span><span class="sxs-lookup"><span data-stu-id="dda54-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="dda54-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dda54-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="dda54-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span><span class="sxs-lookup"><span data-stu-id="dda54-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dda54-164">Only U.S.-formatted phone numbers are supported.</span><span class="sxs-lookup"><span data-stu-id="dda54-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="dda54-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span><span class="sxs-lookup"><span data-stu-id="dda54-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="dda54-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span><span class="sxs-lookup"><span data-stu-id="dda54-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="dda54-167">For this reason,  *every user*  must have a *unique phone number*  .</span><span class="sxs-lookup"><span data-stu-id="dda54-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="dda54-168">**如果您需要两次创建用户时，该命令将失败，除非您使用不同的区号，或如果以前的用户已禁用通过禁用 CsUser cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="dda54-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dda54-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span><span class="sxs-lookup"><span data-stu-id="dda54-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dda54-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span><span class="sxs-lookup"><span data-stu-id="dda54-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="dda54-171">**If the users haven't finished replicating, you'll see an error.**</span><span class="sxs-lookup"><span data-stu-id="dda54-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="dda54-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span><span class="sxs-lookup"><span data-stu-id="dda54-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="dda54-173">联系人创建选项卡</span><span class="sxs-lookup"><span data-stu-id="dda54-173">Contacts Creation tab</span></span>

<span data-ttu-id="dda54-174">This tab lets you give users' contacts details for your testing.</span><span class="sxs-lookup"><span data-stu-id="dda54-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![显示“创建内容”选项卡的“用户设置”工具。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="dda54-176">To configure users' contacts, do the following:</span><span class="sxs-lookup"><span data-stu-id="dda54-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="dda54-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span><span class="sxs-lookup"><span data-stu-id="dda54-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="dda54-178">如果您想要创建相同数量的每个用户的联系人，请选择**固定**复选框。</span><span class="sxs-lookup"><span data-stu-id="dda54-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="dda54-179">If you want to vary the number of contacts created for users, clear that check box.</span><span class="sxs-lookup"><span data-stu-id="dda54-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="dda54-180">在**每个用户的平均联系组**字段中，输入每个用户的联系人组的数目。</span><span class="sxs-lookup"><span data-stu-id="dda54-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="dda54-181">该数字必须小于**平均每个用户的联系人**。</span><span class="sxs-lookup"><span data-stu-id="dda54-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="dda54-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span><span class="sxs-lookup"><span data-stu-id="dda54-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="dda54-183">将与联盟用户创建联系人的百分比。</span><span class="sxs-lookup"><span data-stu-id="dda54-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="dda54-184">在**联合 / 交叉池用户前缀**字段中，为联盟将被添加到本地用户的联系人列表的用户提供用户名。</span><span class="sxs-lookup"><span data-stu-id="dda54-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="dda54-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span><span class="sxs-lookup"><span data-stu-id="dda54-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="dda54-186">在**创建用户**选项卡中确保信息正确无误。</span><span class="sxs-lookup"><span data-stu-id="dda54-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="dda54-187">您的联系人将从创建用户选项卡上的值进行创建。</span><span class="sxs-lookup"><span data-stu-id="dda54-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="dda54-188">单击以开始创建联系人**创建联系人**。</span><span class="sxs-lookup"><span data-stu-id="dda54-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="dda54-189">此过程可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="dda54-189">This process can take several minutes.</span></span> <span data-ttu-id="dda54-190">它完成后，一个对话框将出现并显示消息之后,"操作已成功完成。"</span><span class="sxs-lookup"><span data-stu-id="dda54-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="dda54-191">您可以验证所创建的登录用户从创建用户选项卡创建的联系人。</span><span class="sxs-lookup"><span data-stu-id="dda54-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dda54-192">创建联系人后，此工具将所有前端服务器重新启动目标池中。</span><span class="sxs-lookup"><span data-stu-id="dda54-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="dda54-193">这取决于多少个联系人创建此操作可能需要更长的时间 （最多 2 小时） 的开始，前端服务器。</span><span class="sxs-lookup"><span data-stu-id="dda54-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="dda54-194">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="dda54-194">Distribution List</span></span>

<span data-ttu-id="dda54-195">Skype 业务服务器 2015年的压力和性能工具可以模拟 Skype 业务 2015年客户机中的通讯组列表 (DL) 扩展功能。</span><span class="sxs-lookup"><span data-stu-id="dda54-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="dda54-196">如果您不想要启用 DL 展开用户配置工具中的，您可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="dda54-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![显示“创建通讯组列表”选项卡的“用户设置”工具。](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="dda54-198">通讯组列表选项卡允许您创建将用于通讯组列表扩展功能的压力和性能工具的 Dl。</span><span class="sxs-lookup"><span data-stu-id="dda54-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="dda54-199">在创建之前 DLs，业务服务器 2015年的 Skype 需要部署，包括在运行 ForestPrep。</span><span class="sxs-lookup"><span data-stu-id="dda54-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="dda54-200">如果不这样做，DL 特性将不存在于 AD 架构，因此，该工具将无法创建 Dl。</span><span class="sxs-lookup"><span data-stu-id="dda54-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="dda54-201">若要配置通讯组列表：</span><span class="sxs-lookup"><span data-stu-id="dda54-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="dda54-202">在**数字通讯组列表中的**字段中，为您想要创建的 Dl 的总数 （这里的建议是开头是双倍数量的用户，您有一个值）。</span><span class="sxs-lookup"><span data-stu-id="dda54-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="dda54-203">在**通讯组列表前缀**字段中，输入您创建的所有 Dl 都有，例如*testDL*的前缀。</span><span class="sxs-lookup"><span data-stu-id="dda54-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="dda54-204">这意味着，在 100 DLs DL 名称将如下所示： testDL0，testDL1，高达 testDL99。</span><span class="sxs-lookup"><span data-stu-id="dda54-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="dda54-205">在**Dist.列表中最小的成员**字段中，输入用户放入每个 DL 中的最小数目。</span><span class="sxs-lookup"><span data-stu-id="dda54-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="dda54-206">在**Dist.列表中的最大成员**字段中，输入要在每个 DL 中添加用户的最大的数目。</span><span class="sxs-lookup"><span data-stu-id="dda54-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="dda54-207">创建通讯组列表的按钮</span><span class="sxs-lookup"><span data-stu-id="dda54-207">Create Distribution Lists button</span></span>

<span data-ttu-id="dda54-208">当单击创建通讯组列表按钮时，该工具将查询活动目录，是否通讯组列表匹配的前缀和编号已经存在，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dda54-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="dda54-209">该工具会创建不存在所有 Dl。</span><span class="sxs-lookup"><span data-stu-id="dda54-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="dda54-210">当这些新创建的通讯组列表中添加成员，它将从创建用户选项卡上指定的范围中选择的用户。</span><span class="sxs-lookup"><span data-stu-id="dda54-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="dda54-211">位置信息服务配置选项卡</span><span class="sxs-lookup"><span data-stu-id="dda54-211">Location Info Service Config tab</span></span>

<span data-ttu-id="dda54-212">为业务服务器 2015年压力和性能工具 Skype 的位置信息服务还可以生成虚拟配置文件。</span><span class="sxs-lookup"><span data-stu-id="dda54-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="dda54-213">注意，位置信息服务通常并不会显著影响性能的服务器上。</span><span class="sxs-lookup"><span data-stu-id="dda54-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![显示“位置信息服务配置”选项卡的“用户设置”工具。](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="dda54-215">如果选择此功能进行测试，填写在窗体中的值，然后单击生成 LIS 配置文件按钮，将创建。CSV 文件调用：</span><span class="sxs-lookup"><span data-stu-id="dda54-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="dda54-216">LIS_Subnet.csv</span><span class="sxs-lookup"><span data-stu-id="dda54-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="dda54-217">LIS_Switches.csv</span><span class="sxs-lookup"><span data-stu-id="dda54-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="dda54-218">LIS_Ports.csv</span><span class="sxs-lookup"><span data-stu-id="dda54-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="dda54-219">LIS_WAP.csv</span><span class="sxs-lookup"><span data-stu-id="dda54-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="dda54-220">若要导入这些文件到 LIS 数据库使用这些 PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="dda54-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="dda54-221">一组 CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="dda54-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="dda54-222">一组 CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="dda54-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="dda54-223">一组 CsLisPort</span><span class="sxs-lookup"><span data-stu-id="dda54-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="dda54-224">一组 CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="dda54-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="dda54-225">配置用户配置文件</span><span class="sxs-lookup"><span data-stu-id="dda54-225">Configure User Profile</span></span>
<span data-ttu-id="dda54-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="dda54-226"></span></span>

<span data-ttu-id="dda54-227">您的用户 （通过用户创建工具） 创建后可以具有的业务服务器 2015年负载配置工具 (UserProfileGenerator.exe) 的 Skype 来配置用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="dda54-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="dda54-228">运行业务服务器 2015年负载配置工具 Skype</span><span class="sxs-lookup"><span data-stu-id="dda54-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="dda54-229">启动加载配置工具 (UserProfileGenerator.exe)，并填写选项卡。</span><span class="sxs-lookup"><span data-stu-id="dda54-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="dda54-230">此工具创建一个目录为每个客户端计算机，您将需要运行您的模拟。</span><span class="sxs-lookup"><span data-stu-id="dda54-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="dda54-231">每个客户端目录附带了一个脚本来启动 Skype 业务服务器 2015年的压力和性能工具 (LyncPerfTool.exe)。</span><span class="sxs-lookup"><span data-stu-id="dda54-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="dda54-232">下面的章节将提供如何填写业务服务器 2015年负载配置工具 Skype 的每个选项卡上的字段的示例。</span><span class="sxs-lookup"><span data-stu-id="dda54-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dda54-233">加载配置工具 (UserProfileGenerator.exe) 中使用的特定于用户的值必须与在 Skype 业务 2015年用户创建工具 (UserProvisioningTool.exe) 为指定的值匹配为池。</span><span class="sxs-lookup"><span data-stu-id="dda54-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="dda54-234">常见的配置选项卡</span><span class="sxs-lookup"><span data-stu-id="dda54-234">Common Configuration tab</span></span>

<span data-ttu-id="dda54-235">负载配置工具的**通用配置**选项卡如下所示。</span><span class="sxs-lookup"><span data-stu-id="dda54-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="dda54-236">填写的字段的常见配置选项卡，如以下步骤所述。</span><span class="sxs-lookup"><span data-stu-id="dda54-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![显示“常见配置”选项卡的“用户设置”选项卡。](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="dda54-238">在**可用计算机数量**字段中，键入您想要使用运行压力和性能工具 (LyncPerfTool.exe) 的计算机的数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="dda54-239">我们建议您拥有一台计算机，您可以模拟，每个 4500 用户，但该数目可能会有所不同，如果降低负载级别，或者使用工具的可用功能 （在一般情况下选项卡上设置负载级别） 的子集。</span><span class="sxs-lookup"><span data-stu-id="dda54-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="dda54-240">在**用户名称的前缀**字段中，输入用户名字段的所有用户的前缀。</span><span class="sxs-lookup"><span data-stu-id="dda54-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="dda54-241">记录在统一资源标识符 (URI) 将是： *UserPrefix [用户启动索引...（用户 1 号]）@User 域*，例如 myUser009@Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="dda54-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="dda54-242">在**所有用户的密码**字段中，输入用户的创建期间使用的密码。</span><span class="sxs-lookup"><span data-stu-id="dda54-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="dda54-243">如果将此字段保留为空将作为密码设置用户名。</span><span class="sxs-lookup"><span data-stu-id="dda54-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="dda54-244">在**用户开始索引**字段中，输入要配置的第一个用户的索引。</span><span class="sxs-lookup"><span data-stu-id="dda54-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="dda54-245">您可以配置不同的范围，为不同类型或级别的负载，但一旦您想要配置每个范围，您必须运行加载配置工具 (UserProfileGenerator.exe)。</span><span class="sxs-lookup"><span data-stu-id="dda54-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="dda54-246">在**用户数量**字段中，输入您要配置的用户的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="dda54-247">在**用户域**字段中，输入用于 SIP URI 的域。</span><span class="sxs-lookup"><span data-stu-id="dda54-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="dda54-248">这用来构造 SIP URI 的每个用户在登录 Skype 业务服务器 2015年前端服务器或标准版服务器，可能会有所不同从帐户域。</span><span class="sxs-lookup"><span data-stu-id="dda54-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="dda54-249">在**帐户域**字段中，输入 AD DS 域登录。</span><span class="sxs-lookup"><span data-stu-id="dda54-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="dda54-250">**MPOP 百分比**（多个存在点百分比） 字段中，为提供值的多个机器或设备，例如 10%从登录的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="dda54-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="dda54-251">**登录 / 秒 （每个实例）**字段中输入并发的终结点的最大数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="dda54-252">这是最大数目为您的用户记录单元和建议是小于 / 等于 2，每秒的速率 (< = 2)。</span><span class="sxs-lookup"><span data-stu-id="dda54-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="dda54-253">在**访问代理服务器或池的 FQDN**字段中，输入所需的客户端连接到的服务器的完全合格的域名称 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="dda54-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="dda54-254">如果从外部登录的用户，您需要键入访问代理服务器。</span><span class="sxs-lookup"><span data-stu-id="dda54-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="dda54-255">如果用户是内部的给他们的企业版池或标准版服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="dda54-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="dda54-256">在**端口**字段中，输入您想让用户使用的 SIP 的端口 （此处的默认值为 5061）。</span><span class="sxs-lookup"><span data-stu-id="dda54-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="dda54-257">对于**外部网络服务器设置**字段中，提供访问代理服务器或池的 FQDN，再次，**端口**。</span><span class="sxs-lookup"><span data-stu-id="dda54-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="dda54-258">这些设置仅用于外部终结点的负载模拟。</span><span class="sxs-lookup"><span data-stu-id="dda54-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="dda54-259">一般情况下选项卡</span><span class="sxs-lookup"><span data-stu-id="dda54-259">General Scenarios tab</span></span>

![显示“常规方案”选项卡的“加载配置”工具。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="dda54-261">您可以确定您想要运行或将禁用所提供的一般方案的每个配置的负载水平和参数。</span><span class="sxs-lookup"><span data-stu-id="dda54-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="dda54-262">下面是您的常规选项：</span><span class="sxs-lookup"><span data-stu-id="dda54-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="dda54-263">负载级别值的所有字段，但本地信息服务被**禁用**，**低**、**中**、**高**、 或**自定义**。</span><span class="sxs-lookup"><span data-stu-id="dda54-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="dda54-264">如果您选择但已禁用任何设置，都生成每个客户端配置。</span><span class="sxs-lookup"><span data-stu-id="dda54-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="dda54-265">高会导致最大支持服务器的负担;介质是 60%的高负载;低为 30%。</span><span class="sxs-lookup"><span data-stu-id="dda54-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="dda54-266">**即时消息的**这包括对等和会议;对于负载级别选择适当的值。</span><span class="sxs-lookup"><span data-stu-id="dda54-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="dda54-267">**音频会议的**选择音频会议*只有*一个负载级别。</span><span class="sxs-lookup"><span data-stu-id="dda54-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="dda54-268">**声音方案**一节中，将稍后处理点到点调用。</span><span class="sxs-lookup"><span data-stu-id="dda54-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="dda54-269">打开**高级**选项卡启用多视图。</span><span class="sxs-lookup"><span data-stu-id="dda54-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="dda54-270">**应用程序共享的**选择应用程序共享一个负载级别。</span><span class="sxs-lookup"><span data-stu-id="dda54-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="dda54-271">**数据协作-**选择数据协作，其中包括数据会议的负载级别。</span><span class="sxs-lookup"><span data-stu-id="dda54-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="dda54-272">**通讯组列表扩展-**单击**高级**按钮，并使用相同用户创建工具 (UserProvisioningTool.exe) DL 选项卡上配置的值填充该字段。</span><span class="sxs-lookup"><span data-stu-id="dda54-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="dda54-273">选择负载级别。</span><span class="sxs-lookup"><span data-stu-id="dda54-273">Choose a load level.</span></span>
    
- <span data-ttu-id="dda54-274">**地址簿 Web 查询-**这是地址簿查找服务，而不是下载通讯簿文件。</span><span class="sxs-lookup"><span data-stu-id="dda54-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="dda54-275">如果您想要启用此通讯簿文件下载，请单击**高级**按钮，并将**EnableABSDownload**设置为 True。</span><span class="sxs-lookup"><span data-stu-id="dda54-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="dda54-276">对于负载级别赋予一个值。</span><span class="sxs-lookup"><span data-stu-id="dda54-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="dda54-277">**响应组服务-**单击**高级**按钮并指定响应组已创建时设置响应组服务代理的 Uri。</span><span class="sxs-lookup"><span data-stu-id="dda54-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="dda54-278">您必须选择至少一个响应组。</span><span class="sxs-lookup"><span data-stu-id="dda54-278">You must choose at least one response group.</span></span> <span data-ttu-id="dda54-279">若要使用的详细信息，请用分号分隔的响应组。</span><span class="sxs-lookup"><span data-stu-id="dda54-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="dda54-280">**RGSUriSuffixStartIndex**和**RGSUriSuffixEndIndex**更新为实际的值。</span><span class="sxs-lookup"><span data-stu-id="dda54-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="dda54-281">选择负载级别。</span><span class="sxs-lookup"><span data-stu-id="dda54-281">Choose a load level.</span></span>
    
- <span data-ttu-id="dda54-282">**位置信息服务-**选择启用或禁用的负载程度。</span><span class="sxs-lookup"><span data-stu-id="dda54-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dda54-283">每个方案都有高级按钮旁边，和一套使变体设置为默认设置的复选框。</span><span class="sxs-lookup"><span data-stu-id="dda54-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="dda54-284">选择*特别*将允许生成模拟的会议，将整个小时创建工具。</span><span class="sxs-lookup"><span data-stu-id="dda54-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="dda54-285">选择*大型会议*表示，将模拟一个大型的会议方案。</span><span class="sxs-lookup"><span data-stu-id="dda54-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="dda54-286">*外部*通知还模拟外部用户工具。</span><span class="sxs-lookup"><span data-stu-id="dda54-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="dda54-287">这些按钮和复选框都是特定于每个方案的额外值将更改的压力和性能工具的行为和使自定义项。</span><span class="sxs-lookup"><span data-stu-id="dda54-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="dda54-288">对于每个方案 （除了位置信息服务） 的一般方案选项卡上，如果负载级别的值是**自定义**、 然后对话速率将计算在高级对话框中使用的相应字段。</span><span class="sxs-lookup"><span data-stu-id="dda54-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="dda54-289">字段名称可能会有所不同，具体取决于该方案，但将状态字段的说明：*如果从下拉菜单中选择自定义只使用注意此数量*。</span><span class="sxs-lookup"><span data-stu-id="dda54-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="dda54-290">**高**、**中等**和**低**的值将改变每个嵌入的所有方案，一个都平衡的用户模型的模态的对话率。</span><span class="sxs-lookup"><span data-stu-id="dda54-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="dda54-291">如果需要更改每由于预期使用情况的不同成像设备的负载级别，请使用自定义对话速度。</span><span class="sxs-lookup"><span data-stu-id="dda54-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="dda54-292">声音方案选项卡</span><span class="sxs-lookup"><span data-stu-id="dda54-292">Voice Scenarios tab</span></span>

<span data-ttu-id="dda54-293">这是您所有与语音相关的方案的配置的选项卡。</span><span class="sxs-lookup"><span data-stu-id="dda54-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![“加载配置”工具“语音方案”选项卡。](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="dda54-295">选项为：</span><span class="sxs-lookup"><span data-stu-id="dda54-295">Your options are:</span></span>
  
- <span data-ttu-id="dda54-296">**VoIP 的**单击**高级**按钮，添加 PhoneAreaCode 和 LocationProfile （拨号计划） 字段的值。</span><span class="sxs-lookup"><span data-stu-id="dda54-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="dda54-297">对于负载级别，本文还提供一个值。</span><span class="sxs-lookup"><span data-stu-id="dda54-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="dda54-298">如果您选择为 VoIP 或 UC/PSTN 网关启用，然后公共交换电话网络 (PSTN) 为统一通信 (UC) 负载级别将生成配置文件来模拟外部调用。</span><span class="sxs-lookup"><span data-stu-id="dda54-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="dda54-299">**UC/PSTN 网关-**您需要选择负载级别值，并且之外其他禁用选择任何内容，您还需要通过单击**高级**按钮提供 PSTN 区域代码的值。</span><span class="sxs-lookup"><span data-stu-id="dda54-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="dda54-300">中介服务器和 PSTN 下单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="dda54-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="dda54-301">请确保已配置为区号的路由。</span><span class="sxs-lookup"><span data-stu-id="dda54-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="dda54-302">可用于任何一个 Skype 业务控制面板或 Skype 业务管理外壳程序的验证语音路由配置。</span><span class="sxs-lookup"><span data-stu-id="dda54-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="dda54-303">**会议助理-**对于负载级别提供一个值。</span><span class="sxs-lookup"><span data-stu-id="dda54-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="dda54-304">已禁用之外的任何值都将启用**电话号码**字段。</span><span class="sxs-lookup"><span data-stu-id="dda54-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="dda54-305">请输入您想要使用自动助理的电话号码。</span><span class="sxs-lookup"><span data-stu-id="dda54-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="dda54-306">单击**高级**，并为**LocationProfile**字段赋予一个值。</span><span class="sxs-lookup"><span data-stu-id="dda54-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="dda54-307">**停车服务的调用**在这里，提供负载级别。</span><span class="sxs-lookup"><span data-stu-id="dda54-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="dda54-308">**中介服务器和 PSTN 的**每个要使用的中介服务器需要自己 PSTN 模拟器。</span><span class="sxs-lookup"><span data-stu-id="dda54-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="dda54-309">已确定哪个客户端，您将使用的模拟器后，配置中介服务器来路由呼叫到该计算机在 PSTN 模拟器上您配置。</span><span class="sxs-lookup"><span data-stu-id="dda54-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="dda54-310">单击**添加**按钮以中介服务器的配置的值。</span><span class="sxs-lookup"><span data-stu-id="dda54-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dda54-311">每个方案都有它旁边位于高级按钮。</span><span class="sxs-lookup"><span data-stu-id="dda54-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="dda54-312">高级的对话框包含设置特定于每个方案，改变压力和性能工具的行为，并使自定义。</span><span class="sxs-lookup"><span data-stu-id="dda54-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="dda54-313">> 声音方案选项卡上的每种情况下，如果负载级别的值是**自定义**、 然后对话速率将计算通过使用在高级对话框中的相应字段。</span><span class="sxs-lookup"><span data-stu-id="dda54-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="dda54-314">字段名称可能会有所不同，具体取决于该方案，但将状态字段的说明：*如果从下拉菜单中选择自定义只使用注意此数量*。</span><span class="sxs-lookup"><span data-stu-id="dda54-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="dda54-315">Web 应用程序选项卡</span><span class="sxs-lookup"><span data-stu-id="dda54-315">Web App tab</span></span>

![“加载配置”工具“Web 应用”选项卡。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="dda54-317">Web 应用程序支持通过统一通信 Web API (UCWA) 服务器安装在前端服务器上的会议方案。</span><span class="sxs-lookup"><span data-stu-id="dda54-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="dda54-318">使用 Web 应用程序选项卡来配置所有 web 应用程序相关的方案。</span><span class="sxs-lookup"><span data-stu-id="dda54-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="dda54-319">选项包括：</span><span class="sxs-lookup"><span data-stu-id="dda54-319">Options are:</span></span>
  
- <span data-ttu-id="dda54-320">**常规 Web 应用程序设置-**单击**其他设置**按钮，将**ReachTargetServerUrl**设置为目录池虚拟 IP (VIP) 的前端池 VIP。</span><span class="sxs-lookup"><span data-stu-id="dda54-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="dda54-321">**应用程序共享的**为负载级别中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="dda54-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="dda54-322">**数据协作-**为负载级别中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="dda54-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="dda54-323">**即时消息的**为负载级别中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="dda54-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="dda54-324">**语音会议-**为负载级别中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="dda54-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dda54-325">每个方案都有位于它旁边的**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="dda54-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="dda54-326">高级的对话框包含特定于每个方案的值将更改的压力和性能工具的行为，并启用自定义项。 > 对于每个 Web 应用程序方案，如果负载级别**自定义**、 然后指定的值在**ConversationsPerHour**字段使用而不是默认值。</span><span class="sxs-lookup"><span data-stu-id="dda54-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="dda54-327">移动选项卡</span><span class="sxs-lookup"><span data-stu-id="dda54-327">Mobility tab</span></span>

<span data-ttu-id="dda54-328">使用此选项卡来配置所有的与移动相关的方案。</span><span class="sxs-lookup"><span data-stu-id="dda54-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![“加载配置”工具“移动性”选项卡。](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="dda54-330">此处的选项是：</span><span class="sxs-lookup"><span data-stu-id="dda54-330">The options here are:</span></span>
  
- <span data-ttu-id="dda54-331">**常规的移动设置-**单击**其他设置**，将 UcwaTargetServerUrl 字段设置为主任池虚拟 IP (VIP) 或前端池 VIP。</span><span class="sxs-lookup"><span data-stu-id="dda54-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="dda54-332">**状态和 P2P 即时消息传递/音频-**选择要启用移动模拟负载级别的值。</span><span class="sxs-lookup"><span data-stu-id="dda54-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dda54-333">每个方案都有位于它旁边的**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="dda54-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="dda54-334">高级的对话框包含特定于每个方案的值将更改的压力和性能工具的行为，并启用自定义项。 > 对于每一个行动方案，如果负载级别**自定义**、 然后指定的值在**ConversationsPerHour**字段使用而不是默认值。</span><span class="sxs-lookup"><span data-stu-id="dda54-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="dda54-335">摘要选项卡</span><span class="sxs-lookup"><span data-stu-id="dda54-335">Summary tab</span></span>

<span data-ttu-id="dda54-336">摘要选项卡表明哪些用户可以使用每个方案。</span><span class="sxs-lookup"><span data-stu-id="dda54-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![“加载配置”工具“摘要”选项卡。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="dda54-338">摘要选项卡表明哪些用户可以使用每个方案。</span><span class="sxs-lookup"><span data-stu-id="dda54-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="dda54-339">也可以手动配置用户的数字范围，通过选择**启用自定义用户范围生成**复选框，然后双击您要自定义的用户范围的表中的方案。</span><span class="sxs-lookup"><span data-stu-id="dda54-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="dda54-340">要包括在生成的批处理文件中对应的注册率延迟检查**(RunClient.bat) 添加登录延迟启动时**。</span><span class="sxs-lookup"><span data-stu-id="dda54-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="dda54-341">这将有助于在大量用户签名时可以防止服务器超载。</span><span class="sxs-lookup"><span data-stu-id="dda54-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="dda54-342">单击**生成文件**并选择要用来生成配置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dda54-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="dda54-343">已成功创建您的文件时，将出现一个对话框。</span><span class="sxs-lookup"><span data-stu-id="dda54-343">A dialog box will appear when your files have been successfully created.</span></span>
  
![“已成功生成加载配置文件”消息框。只需单击“确定”。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="dda54-346">运行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="dda54-346">Run LyncPerfTool</span></span>
<span data-ttu-id="dda54-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="dda54-347"></span></span>

<span data-ttu-id="dda54-348">您将需要在运行 Skype 业务服务器 2015年的压力和性能工具 (LyncPerfTool.exe) 之前创建的用户、 联系人和方案。</span><span class="sxs-lookup"><span data-stu-id="dda54-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="dda54-349">有关使用这些工具来执行这些操作的详细信息，请参阅[创建用户和联系人](using-the-tool.md#BKMK_CreateUsersAndContacts)和[配置用户配置文件](using-the-tool.md#BKMK_UserProfile)以前在这篇文章。</span><span class="sxs-lookup"><span data-stu-id="dda54-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="dda54-350">运行这些工具还将生成的文件，将压力和性能工具作为的一部分运行一个批处理文件与包含所需的参数。</span><span class="sxs-lookup"><span data-stu-id="dda54-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="dda54-351">运行业务服务器 2015年压力和性能工具 Skype</span><span class="sxs-lookup"><span data-stu-id="dda54-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="dda54-352">加载配置工具 (UserProfileGenerator.exe) 创建的批处理文件中，您可以通过注册性能计数器和加载 XML 配置文件来运行压力和性能工具 (LyncPerfTool.exe)。</span><span class="sxs-lookup"><span data-stu-id="dda54-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="dda54-353">每个配置文件，该批处理文件运行 LyncPerfTool.exe 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="dda54-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="dda54-354">若要运行该批处理文件，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="dda54-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="dda54-355">运行压力和性能测试</span><span class="sxs-lookup"><span data-stu-id="dda54-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="dda54-356">将配置文件夹中的文件与文件夹复制到每台客户端计算机的 LyncPerfTool.exe 目录。</span><span class="sxs-lookup"><span data-stu-id="dda54-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="dda54-357">（例如，如果名为 1.28_13.16.16 的文件夹中生成的配置文件，该将文件夹复制到 LyncPerfTool.exe 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dda54-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="dda54-358">执行此操作在每个客户端上。）</span><span class="sxs-lookup"><span data-stu-id="dda54-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="dda54-359">导航至客户端文件夹，然后运行**RunClient**批处理脚本。</span><span class="sxs-lookup"><span data-stu-id="dda54-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="dda54-360">您可以双击 Windows 资源管理器中的批处理文件，它将为该客户端运行的所有配置文件。</span><span class="sxs-lookup"><span data-stu-id="dda54-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="dda54-361">您可以通过使用以下语法从一个客户端文件夹运行脚本：</span><span class="sxs-lookup"><span data-stu-id="dda54-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
  ```
  RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
  ```

<span data-ttu-id="dda54-362">若要直接运行压力和性能工具，打开一个命令提示符并在命令行键入以下命令 (当第一次执行此操作，请务必注册的性能计数器和`regsvr32 /i /n /s LyncPerfToolPerf.dll`，如本主题中后面的注释中所示):</span><span class="sxs-lookup"><span data-stu-id="dda54-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="dda54-363">若要让该工具在配置文件中显示的值，包括`/displayfile`参数在上述命令中，以便使其如下所示：</span><span class="sxs-lookup"><span data-stu-id="dda54-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="dda54-364">到*结束*该进程，请按 Ctrl + C。</span><span class="sxs-lookup"><span data-stu-id="dda54-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dda54-365">直接运行压力和性能工具之前, 您必须注册性能计数器通过下面的命令：`regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="dda54-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="dda54-366">启动压力和性能工具的每个实例将立即开始登录用户，通常以一个用户每秒的速率。</span><span class="sxs-lookup"><span data-stu-id="dda54-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="dda54-367">用户登录用于峰值速率池是大约每秒 12。</span><span class="sxs-lookup"><span data-stu-id="dda54-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="dda54-368">这意味着您不应启动超过 12 LyncPerfTool.exe 实例在同一时间同时仍然登录用户。</span><span class="sxs-lookup"><span data-stu-id="dda54-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="dda54-369">一千的用户大约需要 20 分钟完全在一个每秒登录。</span><span class="sxs-lookup"><span data-stu-id="dda54-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="dda54-370">解释结果</span><span class="sxs-lookup"><span data-stu-id="dda54-370">Interpreting the Results</span></span>
<span data-ttu-id="dda54-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="dda54-371"></span></span>

<span data-ttu-id="dda54-372">为业务服务器 2015年压力和性能工具 Skype 有多个计数器，可帮助您了解客户机正在做什么，以及是否它会遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="dda54-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="dda54-373">客户端计数器</span><span class="sxs-lookup"><span data-stu-id="dda54-373">Client Counters</span></span>

<span data-ttu-id="dda54-374">LyncPerfTool.exe 运行每个的实例都有一个单独的计数器实例。</span><span class="sxs-lookup"><span data-stu-id="dda54-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="dda54-375">每个实例名称由其进程 id。</span><span class="sxs-lookup"><span data-stu-id="dda54-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="dda54-376">如果客户端是重载可以出现其他问题。</span><span class="sxs-lookup"><span data-stu-id="dda54-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="dda54-377">若要防止发生这些问题：</span><span class="sxs-lookup"><span data-stu-id="dda54-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="dda54-378">监视客户端计算机上的 CPU 和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="dda54-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="dda54-379">如果 CPU 90%以上是以一致的方式，减少用户的数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="dda54-380">如果内存需求量非常大，您可能会遇到问题中，如果页面文件开始用完所有空间。</span><span class="sxs-lookup"><span data-stu-id="dda54-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="dda54-381">确认提交费用不按计算机上的限制。</span><span class="sxs-lookup"><span data-stu-id="dda54-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="dda54-382">如果您正在运行内存限制为考虑增加页面文件的大小或降低用户的数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="dda54-383">这里是关键性能计数器的列表：</span><span class="sxs-lookup"><span data-stu-id="dda54-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="dda54-384">**一般信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-384">**General Information**</span></span>

|<span data-ttu-id="dda54-385">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-385">**Performance Counter**</span></span>|<span data-ttu-id="dda54-386">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-387">以分钟为单位的时间</span><span class="sxs-lookup"><span data-stu-id="dda54-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="dda54-388">自从启动进程以来，所用时间。</span><span class="sxs-lookup"><span data-stu-id="dda54-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="dda54-389">活动的终结点</span><span class="sxs-lookup"><span data-stu-id="dda54-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="dda54-390">当前连接到的服务器终结点的数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="dda54-391">失败的登录</span><span class="sxs-lookup"><span data-stu-id="dda54-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="dda54-392">端点登录失败的总次数。</span><span class="sxs-lookup"><span data-stu-id="dda54-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="dda54-393">登录尝试</span><span class="sxs-lookup"><span data-stu-id="dda54-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="dda54-394">终结点的登录尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="dda54-395">终结点断开连接</span><span class="sxs-lookup"><span data-stu-id="dda54-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="dda54-396">已断开连接的终结点的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="dda54-397">**出席信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-397">**Presence Information**</span></span>

|<span data-ttu-id="dda54-398">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-398">**Performance Counter**</span></span>|<span data-ttu-id="dda54-399">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-400">SetPresence 调用</span><span class="sxs-lookup"><span data-stu-id="dda54-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="dda54-401">总次数存在更改尝试。</span><span class="sxs-lookup"><span data-stu-id="dda54-401">Total number of presence change attempts.</span></span> <span data-ttu-id="dda54-402">不同类型的状态更改，请参见 SetPresence （存在类型） 调用的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="dda54-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="dda54-403">SetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="dda54-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="dda54-404">Nnn 响应代码从服务器接收到的总数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="dda54-405">GetPresence 调用</span><span class="sxs-lookup"><span data-stu-id="dda54-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="dda54-406">状态请求尝试获取的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="dda54-407">GetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="dda54-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="dda54-408">Nnn 响应代码从服务器接收到的总数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="dda54-409">**通讯簿服务信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-409">**Address Book service information**</span></span>

|<span data-ttu-id="dda54-410">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-410">**Performance Counter**</span></span>|<span data-ttu-id="dda54-411">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-412">ABS 完全/增量文件下载尝试</span><span class="sxs-lookup"><span data-stu-id="dda54-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="dda54-413">尝试执行完整备份或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="dda54-414">ABS 完全/增量文件下载成功</span><span class="sxs-lookup"><span data-stu-id="dda54-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="dda54-415">尝试执行完整备份或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="dda54-416">地址簿 Web 查询与服务相关的计数器</span><span class="sxs-lookup"><span data-stu-id="dda54-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="dda54-417">通讯簿文件下载相关的计数器。</span><span class="sxs-lookup"><span data-stu-id="dda54-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="dda54-418">ABS WS 调用尝试</span><span class="sxs-lookup"><span data-stu-id="dda54-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="dda54-419">尝试的地址簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="dda54-420">成功的 ABS WS 调用</span><span class="sxs-lookup"><span data-stu-id="dda54-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="dda54-421">返回一个成功的响应代码的地址簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="dda54-422">ABS WS 调用失败</span><span class="sxs-lookup"><span data-stu-id="dda54-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="dda54-423">返回了错误响应代码的地址簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="dda54-424">此类别包括一些计数器来监视通讯簿服务 (ABS) 文件下载和地址簿 Web 查询服务请求。</span><span class="sxs-lookup"><span data-stu-id="dda54-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="dda54-425">**通讯组列表 (DL) 信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="dda54-426">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-426">**Performance Counter**</span></span>|<span data-ttu-id="dda54-427">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-428">尝试调用</span><span class="sxs-lookup"><span data-stu-id="dda54-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="dda54-429">尝试的通讯组列表扩展 (DLX) web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="dda54-430">成功调用</span><span class="sxs-lookup"><span data-stu-id="dda54-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="dda54-431">返回一个成功的响应代码的 DLX web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="dda54-432">调用失败</span><span class="sxs-lookup"><span data-stu-id="dda54-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="dda54-433">返回了错误响应代码的 DLX web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="dda54-434">性能计数器下面列出报表编号所有语音 IP (VoIP) 的调用，包括调用中介服务器，A / V 会议服务器、 边缘服务器、 响应组的应用程序，以及会议自动助理，启用这些方案。</span><span class="sxs-lookup"><span data-stu-id="dda54-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="dda54-435">**VoIP 基本信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="dda54-436">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-436">**Performance Counter**</span></span>|<span data-ttu-id="dda54-437">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-438">调用活动</span><span class="sxs-lookup"><span data-stu-id="dda54-438">Calls Active</span></span>  <br/> |<span data-ttu-id="dda54-439">当前正在进行调用总数传入/传出的声音。</span><span class="sxs-lookup"><span data-stu-id="dda54-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="dda54-440">终止呼叫</span><span class="sxs-lookup"><span data-stu-id="dda54-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="dda54-441">传入/传出语音呼叫总数已终止。</span><span class="sxs-lookup"><span data-stu-id="dda54-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="dda54-442">调用被拒绝</span><span class="sxs-lookup"><span data-stu-id="dda54-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="dda54-443">拒绝的语音来电总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="dda54-444">传入/传出呼叫尝试</span><span class="sxs-lookup"><span data-stu-id="dda54-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="dda54-445">传入/传出语音呼叫尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="dda54-446">传入/传出呼叫建立</span><span class="sxs-lookup"><span data-stu-id="dda54-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="dda54-447">传入/传出语音呼叫建立的总数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="dda54-448">调用接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="dda54-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="dda54-449">Nnn 响应代码从服务器接收到的总数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="dda54-450">VoIP 通过率 （%）</span><span class="sxs-lookup"><span data-stu-id="dda54-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="dda54-451">总调用尝试建立总调用。</span><span class="sxs-lookup"><span data-stu-id="dda54-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="dda54-452">**响应组服务调用信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="dda54-453">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-453">**Performance Counter**</span></span>|<span data-ttu-id="dda54-454">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-455">调用活动</span><span class="sxs-lookup"><span data-stu-id="dda54-455">Calls Active</span></span>  <br/> |<span data-ttu-id="dda54-456">为响应组应用程序的活动调用的总次数。</span><span class="sxs-lookup"><span data-stu-id="dda54-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="dda54-457">尝试调用</span><span class="sxs-lookup"><span data-stu-id="dda54-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="dda54-458">尝试调用的总次数。</span><span class="sxs-lookup"><span data-stu-id="dda54-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="dda54-459">**即时消息 (IM) 调用信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="dda54-460">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-460">**Performance Counter**</span></span>|<span data-ttu-id="dda54-461">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-462">调用活动</span><span class="sxs-lookup"><span data-stu-id="dda54-462">Calls Active</span></span>  <br/> |<span data-ttu-id="dda54-463">不断传入/传出即时消息调用总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="dda54-464">终止呼叫</span><span class="sxs-lookup"><span data-stu-id="dda54-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="dda54-465">传入/传出即时消息调用的总次数已终止。</span><span class="sxs-lookup"><span data-stu-id="dda54-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="dda54-466">调用接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="dda54-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="dda54-467">Nnn 响应代码从服务器接收到的总数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="dda54-468">接收/发送的 IM 消息</span><span class="sxs-lookup"><span data-stu-id="dda54-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="dda54-469">消息总数接收或发送的所有会话。</span><span class="sxs-lookup"><span data-stu-id="dda54-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="dda54-470">传入/传出呼叫尝试</span><span class="sxs-lookup"><span data-stu-id="dda54-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="dda54-471">传入/传出即时消息调用尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="dda54-472">传入/传出呼叫建立</span><span class="sxs-lookup"><span data-stu-id="dda54-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="dda54-473">传入/传出建立即时消息调用的总次数。</span><span class="sxs-lookup"><span data-stu-id="dda54-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="dda54-474">**应用程序共享的呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="dda54-475">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-475">**Performance Counter**</span></span>|<span data-ttu-id="dda54-476">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-477">调用活动</span><span class="sxs-lookup"><span data-stu-id="dda54-477">Calls Active</span></span>  <br/> |<span data-ttu-id="dda54-478">不断传入/传出的应用程序共享的调用总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="dda54-479">终止呼叫</span><span class="sxs-lookup"><span data-stu-id="dda54-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="dda54-480">总数已共享调用传入/传出应用程序终止。</span><span class="sxs-lookup"><span data-stu-id="dda54-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="dda54-481">调用接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="dda54-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="dda54-482">Nnn 响应代码从服务器接收到的总数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="dda54-483">传入/传出呼叫尝试</span><span class="sxs-lookup"><span data-stu-id="dda54-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="dda54-484">传入/传出的应用程序共享尝试调用的总次数。</span><span class="sxs-lookup"><span data-stu-id="dda54-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="dda54-485">传入/传出呼叫建立</span><span class="sxs-lookup"><span data-stu-id="dda54-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="dda54-486">传入/传出的应用程序共享建立的调用总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="dda54-487">**CAA 呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-487">**CAA Call Information**</span></span>

|<span data-ttu-id="dda54-488">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-488">**Performance Counter**</span></span>|<span data-ttu-id="dda54-489">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-490">调用活动</span><span class="sxs-lookup"><span data-stu-id="dda54-490">Calls Active</span></span>  <br/> |<span data-ttu-id="dda54-491">目前正在进行调用传入/传出公用交换的电话网 (PSTN) 的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="dda54-492">终止呼叫</span><span class="sxs-lookup"><span data-stu-id="dda54-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="dda54-493">传入/传出 PSTN 呼叫总数已终止。</span><span class="sxs-lookup"><span data-stu-id="dda54-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="dda54-494">传入/传出呼叫尝试</span><span class="sxs-lookup"><span data-stu-id="dda54-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="dda54-495">传入/传出 PSTN 呼叫尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="dda54-496">传入/传出呼叫建立</span><span class="sxs-lookup"><span data-stu-id="dda54-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="dda54-497">传入/传出 PSTN 呼叫建立的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="dda54-498">**会议信息**</span><span class="sxs-lookup"><span data-stu-id="dda54-498">**Conference Information**</span></span>

|<span data-ttu-id="dda54-499">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-499">**Performance Counter**</span></span>|<span data-ttu-id="dda54-500">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-501">活动的即时消息会议</span><span class="sxs-lookup"><span data-stu-id="dda54-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="dda54-502">正在进行的即时消息会议的总次数。</span><span class="sxs-lookup"><span data-stu-id="dda54-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="dda54-503">当前的音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="dda54-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="dda54-504">总数持续音频/视频 (A / V) 会议。</span><span class="sxs-lookup"><span data-stu-id="dda54-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="dda54-505">活动应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="dda54-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="dda54-506">日常应用程序共享会议的总次数。</span><span class="sxs-lookup"><span data-stu-id="dda54-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="dda54-507">参与者人数</span><span class="sxs-lookup"><span data-stu-id="dda54-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="dda54-508">当前连接到会议参与者的总数。</span><span class="sxs-lookup"><span data-stu-id="dda54-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="dda54-509">会议计划失败</span><span class="sxs-lookup"><span data-stu-id="dda54-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="dda54-510">尝试安排会议时失败的总次数。</span><span class="sxs-lookup"><span data-stu-id="dda54-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="dda54-511">加入会议失败</span><span class="sxs-lookup"><span data-stu-id="dda54-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="dda54-512">尝试连接到会议时失败的总数量。</span><span class="sxs-lookup"><span data-stu-id="dda54-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="dda54-513">**UCWA 客户端计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="dda54-514">**性能计数器**</span><span class="sxs-lookup"><span data-stu-id="dda54-514">**Performance Counter**</span></span>|<span data-ttu-id="dda54-515">**说明**</span><span class="sxs-lookup"><span data-stu-id="dda54-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dda54-516">总数 IMMCU 连接成功</span><span class="sxs-lookup"><span data-stu-id="dda54-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="dda54-517">加入了即时消息会议的总次数。</span><span class="sxs-lookup"><span data-stu-id="dda54-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="dda54-518">总数 DMCU 连接成功</span><span class="sxs-lookup"><span data-stu-id="dda54-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="dda54-519">总数的 A / V 会议加入。</span><span class="sxs-lookup"><span data-stu-id="dda54-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

