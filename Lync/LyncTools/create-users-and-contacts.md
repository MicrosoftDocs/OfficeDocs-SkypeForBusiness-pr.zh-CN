---
title: 创建用户和联系人
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f90e6cbb1afb9c4c2dd2b43e1448ca635899531b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="2635d-102">创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="2635d-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2635d-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2635d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2635d-104">必须使用 Lync Server 2013 用户预配工具（UserProvisioningTool.exe）创建用户和联系人，以准备压力和性能负载测试。</span><span class="sxs-lookup"><span data-stu-id="2635d-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="2635d-105">下面是您在阅读本主题时可能会用到的术语和定义的列表。</span><span class="sxs-lookup"><span data-stu-id="2635d-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="2635d-106">组织单位– Active Directory 域服务组织单位（OU）。</span><span class="sxs-lookup"><span data-stu-id="2635d-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="2635d-107">联合/跨池–将启用的用户与其他即时消息（IM）服务（如 Internet 服务的 MSN 网络、AOL®和 Yahoo®）进行通信 \! 。</span><span class="sxs-lookup"><span data-stu-id="2635d-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="2635d-108">通讯组列表–包含 Active Directory 域服务用户列表的 Active Directory 域服务中的对象，用于启动与一组用户的通信。</span><span class="sxs-lookup"><span data-stu-id="2635d-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="2635d-109">Location Info Service – Lync Server 2013 服务，在每个电话启用和配置后，支持检索增强9-1-1 （E9-1-1）服务的物理位置。</span><span class="sxs-lookup"><span data-stu-id="2635d-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="2635d-110">美国电话号码–分配给用户的电话号码，以及用于路由入站和出站呼叫和反向号码查找（RNL）的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="2635d-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="2635d-111">使用 UserProvisioningTool.exe 创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="2635d-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="2635d-112">必须使用 Lync Server 用户预配工具为负载模拟创建用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="2635d-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="2635d-113">Lync Server 用户预配工具随 Lync Server 压力和性能工具包一起安装。</span><span class="sxs-lookup"><span data-stu-id="2635d-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="2635d-114">请确保已在前端服务器或 Standard Edition server 上运行程序包安装程序（CapacityPlanningTool.msi）。</span><span class="sxs-lookup"><span data-stu-id="2635d-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="2635d-115">通过在 \\ 前端服务器或 Standard Edition server 上运行文件 UserProvisioningTool.exe （位于% InstalledDirectory% LyncStressAndPerfTool LyncStress）来启动 Lync Server 用户预配工具。</span><span class="sxs-lookup"><span data-stu-id="2635d-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2635d-116">您必须以域管理员安全组成员的身份登录才能运行 UserProvisioningTool.exe。</span><span class="sxs-lookup"><span data-stu-id="2635d-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="2635d-117">由于 UserProvisioningTool.exe 将创建和配置新的 Active Directory 域服务用户，因此需要从该上下文运行此上下文。</span><span class="sxs-lookup"><span data-stu-id="2635d-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2635d-118">当您创建了大量用户（10000或更多）时，请从高端计算机运行 UserProvisioningTool.exe。</span><span class="sxs-lookup"><span data-stu-id="2635d-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="2635d-119">请注意，在创建用户时，域控制器也会遇到负载较高的情况。</span><span class="sxs-lookup"><span data-stu-id="2635d-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="2635d-120">当 Lync Server 用户预配工具打开时，单击 "**配置**"，然后选择 "**加载配置**"。</span><span class="sxs-lookup"><span data-stu-id="2635d-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="2635d-121">若要开始配置用户和联系人，请加载程序包中包含的默认文件 SampleData.xml。</span><span class="sxs-lookup"><span data-stu-id="2635d-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="2635d-122">这将预填充包含您的系统需要修改的示例数据的字段。</span><span class="sxs-lookup"><span data-stu-id="2635d-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="2635d-123">如果已预配置的 XML 文件已包含自定义设置，则改为加载该文件。</span><span class="sxs-lookup"><span data-stu-id="2635d-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="2635d-124">填写 Lync Server 用户预配工具中的字段，如以下各节所述。</span><span class="sxs-lookup"><span data-stu-id="2635d-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="2635d-125">!["用户创建" 选项卡。](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg ""用户创建" 选项卡。")</span><span class="sxs-lookup"><span data-stu-id="2635d-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="2635d-126">若要配置服务器选项，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="2635d-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="2635d-127">在 "**前端池 FQDN**" 中，键入要在其中承载用户的 Standard Edition Server 或前端池的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="2635d-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="2635d-128">在 "**用户名前缀**" 中，键入要用于出于测试目的生成用户名的前缀。</span><span class="sxs-lookup"><span data-stu-id="2635d-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="2635d-129">在 "**密码**" 中，指定将应用于所有测试用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="2635d-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="2635d-130">在 " **SIP 域**" 中，键入要用于测试用户的 SIP Uri （统一资源标识符）的域名。</span><span class="sxs-lookup"><span data-stu-id="2635d-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="2635d-131">在 "**帐户域**" 中，键入您要在其中创建测试用户的当前 Active Directory 域服务域的域名。</span><span class="sxs-lookup"><span data-stu-id="2635d-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="2635d-132">在 "**组织单位**" 中，键入要在其中创建用户对象的 Active Directory 域服务 OU 的名称。</span><span class="sxs-lookup"><span data-stu-id="2635d-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="2635d-133">如果 OU 不存在，则会创建它。</span><span class="sxs-lookup"><span data-stu-id="2635d-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="2635d-134">在 "**电话区号**" 中，键入将用于测试用户帐户的三位数区域代码。</span><span class="sxs-lookup"><span data-stu-id="2635d-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="2635d-135">确保电话区号不会与 Active Directory 域服务中的任何其他用户的区号发生冲突。</span><span class="sxs-lookup"><span data-stu-id="2635d-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="2635d-136">如果要为测试用户启用企业语音，请选中 "**已启用语音**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="2635d-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="2635d-137">在 "**用户数**" 中，指定要创建的测试用户的总数。</span><span class="sxs-lookup"><span data-stu-id="2635d-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="2635d-138">在 "**起始索引**" 中，指定将用作用户名前缀的后缀的起始编号。</span><span class="sxs-lookup"><span data-stu-id="2635d-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="2635d-139">"创建用户" 按钮</span><span class="sxs-lookup"><span data-stu-id="2635d-139">Create Users Button</span></span>

<span data-ttu-id="2635d-140">当您单击 "创建用户" 按钮时，它将验证所有输入参数。</span><span class="sxs-lookup"><span data-stu-id="2635d-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="2635d-141">如果存在任何验证错误，它将提示您更正这些输入值。</span><span class="sxs-lookup"><span data-stu-id="2635d-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="2635d-142">如果所有输入值都是正确的，则会开始在 Active Directory 域服务中创建用户。</span><span class="sxs-lookup"><span data-stu-id="2635d-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="2635d-143">将在此窗体的底部显示一个进度栏。</span><span class="sxs-lookup"><span data-stu-id="2635d-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="2635d-144">我们建议您不要在进度栏处于活动状态时关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="2635d-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="2635d-145">用户创建过程较慢。</span><span class="sxs-lookup"><span data-stu-id="2635d-145">User Creation is a slow process.</span></span> <span data-ttu-id="2635d-146">可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="2635d-146">It can take several minutes.</span></span> <span data-ttu-id="2635d-147">如果用户数量非常大，该过程甚至可能需要几个小时的时间。</span><span class="sxs-lookup"><span data-stu-id="2635d-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="2635d-148">如果用户已存在，则会使用任何更改对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="2635d-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="2635d-149">您可以通过登录为范围中的用户之一来验证用户是否已创建。</span><span class="sxs-lookup"><span data-stu-id="2635d-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="2635d-150">使用用户前缀、用户号和 @sipDomain 作为用户名（例如，LyncUser10@contoso.net）以及指定的密码。</span><span class="sxs-lookup"><span data-stu-id="2635d-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="2635d-151">"删除用户" 按钮</span><span class="sxs-lookup"><span data-stu-id="2635d-151">Delete Users Button</span></span>

<span data-ttu-id="2635d-152">当您单击 "删除用户" 按钮时，它将验证所有输入参数。</span><span class="sxs-lookup"><span data-stu-id="2635d-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="2635d-153">如果存在任何验证错误，它将提示您更正这些输入值。</span><span class="sxs-lookup"><span data-stu-id="2635d-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="2635d-154">如果所有输入值都是正确的，它将在 Active Directory 域服务中开始禁用和删除用户。</span><span class="sxs-lookup"><span data-stu-id="2635d-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="2635d-155">将在此窗体的底部显示一个进度栏。</span><span class="sxs-lookup"><span data-stu-id="2635d-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="2635d-156">我们建议您不要在进度栏处于活动状态时关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="2635d-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="2635d-157">仅支持美国格式的电话号码。</span><span class="sxs-lookup"><span data-stu-id="2635d-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="2635d-158">始终将电话号码分配给用户，并且由 UserProvisioningTool.exe 创建的所有用户均可为企业语音启用。</span><span class="sxs-lookup"><span data-stu-id="2635d-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="2635d-159">任何使用电话号码的方案（如会议自动助理或 UC-PSTN 呼叫），都可以使用此电话号码正确路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="2635d-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="2635d-160">因此，每个用户必须具有唯一的电话号码。</span><span class="sxs-lookup"><span data-stu-id="2635d-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="2635d-161">如果您必须创建两次用户，则该命令将失败，除非您使用不同的区号，或者以前的用户已通过使用<STRONG>get-csuser</STRONG> cmdlet 禁用。</span><span class="sxs-lookup"><span data-stu-id="2635d-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="2635d-162">在创建联系人之前，必须首先完成从 "用户" 选项卡执行的用户复制。如果你刚刚创建了用户，则必须等到 Lync Server 复制完成，并填充数据库中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2635d-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="2635d-163">如果用户尚未完成复制，您将看到错误。</span><span class="sxs-lookup"><span data-stu-id="2635d-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="2635d-164">如果安装了 Lync Server 2013 前端服务，或者在最后一个用户上成功运行<STRONG>get-csuser</STRONG> cmdlet，您将知道用户何时完成复制。</span><span class="sxs-lookup"><span data-stu-id="2635d-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="2635d-165">联系人创建选项卡</span><span class="sxs-lookup"><span data-stu-id="2635d-165">Contacts Creation Tab</span></span>

<span data-ttu-id="2635d-166">通过 "联系人创建" 选项卡，可以指定用户联系人的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2635d-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="2635d-167">!["联系人创建" 选项卡。](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg ""联系人创建" 选项卡。")</span><span class="sxs-lookup"><span data-stu-id="2635d-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="2635d-168">若要配置用户的联系人，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2635d-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="2635d-169">在 "每个用户的平均联系人" 中，指定要在联系人列表中为每个用户填充的平均联系人数。</span><span class="sxs-lookup"><span data-stu-id="2635d-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="2635d-170">如果要为每个用户创建相等数量的联系人，请选中 "固定" 复选框。</span><span class="sxs-lookup"><span data-stu-id="2635d-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="2635d-171">如果要改变为用户创建的联系人数量，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="2635d-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="2635d-172">在 "每个用户的平均联系人组" 中，指定每个用户的联系人组数。</span><span class="sxs-lookup"><span data-stu-id="2635d-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="2635d-173">此数字必须小于每个用户的平均联系人数。</span><span class="sxs-lookup"><span data-stu-id="2635d-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="2635d-174">在 "联合/跨池联系人百分比" 中，指定一个介于0和100之间的数字。</span><span class="sxs-lookup"><span data-stu-id="2635d-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="2635d-175">将使用联合用户创建此联系人百分比。</span><span class="sxs-lookup"><span data-stu-id="2635d-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="2635d-176">在 "联合/跨池用户前缀" 中，指定将添加到本地用户的联系人列表中的联盟用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="2635d-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="2635d-177">在联合/跨池用户 SIP 域中，指定联盟用户的 SIP 域名称。</span><span class="sxs-lookup"><span data-stu-id="2635d-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2635d-178">创建联系人时不应登录任何用户。</span><span class="sxs-lookup"><span data-stu-id="2635d-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="2635d-179">在 "用户创建" 选项卡中，验证参数是否正确。</span><span class="sxs-lookup"><span data-stu-id="2635d-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="2635d-180">将为其创建联系人的用户的范围是从 "用户创建" 选项卡获取的。</span><span class="sxs-lookup"><span data-stu-id="2635d-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="2635d-181">单击 "创建联系人" 以开始创建联系人。</span><span class="sxs-lookup"><span data-stu-id="2635d-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="2635d-182">此过程可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="2635d-182">This process can take several minutes.</span></span> <span data-ttu-id="2635d-183">完成后，将显示一个对话框，其中包含 "操作已成功完成" 的消息。</span><span class="sxs-lookup"><span data-stu-id="2635d-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="2635d-184">您可以通过以用户创建选项卡上创建的用户的登录方式来验证所创建的联系人。</span><span class="sxs-lookup"><span data-stu-id="2635d-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2635d-185">创建联系人后，此工具将重新启动目标池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2635d-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="2635d-186">它可能需要更长时间（最长为2小时）才能启动前端服务器，具体取决于此操作创建的联系人数量。</span><span class="sxs-lookup"><span data-stu-id="2635d-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="2635d-187">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="2635d-187">Distribution List</span></span>

<span data-ttu-id="2635d-188">Lync Server 2013 压力和性能工具的功能之一是在 Lync 2013 中模拟通讯组列表（DL）扩展功能。</span><span class="sxs-lookup"><span data-stu-id="2635d-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="2635d-189">如果您不打算在 UserProvisioningTool 中启用 DL 扩展，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="2635d-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="2635d-190">!["通讯组列表创建" 选项卡。](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg ""通讯组列表创建" 选项卡。")</span><span class="sxs-lookup"><span data-stu-id="2635d-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="2635d-191">通过 "通讯组列表" 选项卡，您可以创建压力和性能工具将用于通讯组列表扩展功能的 DLs。</span><span class="sxs-lookup"><span data-stu-id="2635d-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="2635d-192">在创建 Dl 之前，必须已安装 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="2635d-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="2635d-193">您必须已运行 Lync Server 2013 ForestPrep。</span><span class="sxs-lookup"><span data-stu-id="2635d-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="2635d-194">否则，在 Active Directory 域服务架构中不存在 DL 属性，并且该工具将无法创建 Dl。</span><span class="sxs-lookup"><span data-stu-id="2635d-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="2635d-195">若要配置通讯组列表，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2635d-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="2635d-196">在 "通讯组列表数" 中，指定要创建的 Dl 的总数。</span><span class="sxs-lookup"><span data-stu-id="2635d-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="2635d-197">（我们建议您从用户数的两倍开始）。</span><span class="sxs-lookup"><span data-stu-id="2635d-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="2635d-198">它们的编号从0到 n-1。</span><span class="sxs-lookup"><span data-stu-id="2635d-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="2635d-199">在 "通讯组列表前缀" 中，指定 Dl 将具有的前缀。</span><span class="sxs-lookup"><span data-stu-id="2635d-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="2635d-200">例如，如果您指定 100 Dl 和 testDL 的前缀，则 Dl 将通过 testDL99 命名为 testDL0、testDL1 等。</span><span class="sxs-lookup"><span data-stu-id="2635d-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="2635d-201">在 Dist 的最小成员中，指定每个通讯组列表中要添加的最小用户数。</span><span class="sxs-lookup"><span data-stu-id="2635d-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="2635d-202">在 "Dist 的最大成员数" 列表中，指定每个通讯组列表中要添加的最大用户数。</span><span class="sxs-lookup"><span data-stu-id="2635d-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="2635d-203">"创建通讯组列表" 按钮</span><span class="sxs-lookup"><span data-stu-id="2635d-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="2635d-204">当您单击 "创建通讯组列表" 按钮时，该工具会查询 Active Directory 域服务，以查看与已存在的前缀和号码相匹配的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="2635d-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="2635d-205">该工具将仅创建尚不存在的工具。</span><span class="sxs-lookup"><span data-stu-id="2635d-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="2635d-206">将成员添加到这些新创建的通讯组列表时，将从 "用户创建" 选项卡上指定的区域中选择用户。</span><span class="sxs-lookup"><span data-stu-id="2635d-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="2635d-207">位置信息服务配置选项卡</span><span class="sxs-lookup"><span data-stu-id="2635d-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="2635d-208">Lync Server 2013 压力和性能工具的功能之一是为 Location 信息服务生成虚拟配置文件。</span><span class="sxs-lookup"><span data-stu-id="2635d-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="2635d-209">位置信息服务通常不会对服务器产生显著的性能影响。</span><span class="sxs-lookup"><span data-stu-id="2635d-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="2635d-210">![Location Info Service Config 选项卡。](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config 选项卡。")</span><span class="sxs-lookup"><span data-stu-id="2635d-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="2635d-211">如果选择测试此功能，则可以填写表单中提及的值，然后单击 "生成 IIS 配置文件" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2635d-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="2635d-212">它将生成名为 .LIS \_Subnet.csv、iis \_Switches.csv、.Lis \_Ports.csv 和 .LISWAP.csv \_ 的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="2635d-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="2635d-213">然后，您可以分别使用**CsLisSubnet** Cmdlet、 **CsLisSwitch** cmdlet、 **CsLisPort** CMDLET 和**CsWirelessAccessPoint** CMDLET 将这些 CSV 文件导入到 .lis 数据库中。</span><span class="sxs-lookup"><span data-stu-id="2635d-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

