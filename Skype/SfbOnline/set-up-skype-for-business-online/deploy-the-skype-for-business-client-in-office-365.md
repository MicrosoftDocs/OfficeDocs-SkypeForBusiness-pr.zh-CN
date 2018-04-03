---
title: 部署 Office 365 中的业务客户端的 Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: '了解如何规划和部署业务的 Skype 在小型、 中型和大型企业，并将它们提供给您的用户。 '
ms.openlocfilehash: ee7799116f20a8ca1e9f1cb71d8616d44df93c8e
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a><span data-ttu-id="a42ac-103">部署 Office 365 中的业务客户端的 Skype</span><span class="sxs-lookup"><span data-stu-id="a42ac-103">Deploy the Skype for Business client in Office 365</span></span>

<span data-ttu-id="a42ac-104">本文介绍了如何，**[管理](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**，部署业务应用程序为 Skype 的人在组织中的选项。</span><span class="sxs-lookup"><span data-stu-id="a42ac-104">This article explains options for how you, the **[admin](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**, can deploy the Skype for Business app to the people in your organization.</span></span>
  
<span data-ttu-id="a42ac-105">对于业务用户，请确保部署 Skype 之前所做的[设置 Skype 业务在线](set-up-skype-for-business-online.md)文章中的步骤 1-3。</span><span class="sxs-lookup"><span data-stu-id="a42ac-105">Before you deploy Skype for Business to your users, make sure you've done steps 1-3 in the article [Set up Skype for Business Online](set-up-skype-for-business-online.md).</span></span> <span data-ttu-id="a42ac-106">这样一来，Skype 业务将设置为与您的域，每个人都将拥有其许可证，并且您将已配置即时消息和[Skype 的在线业务中的配置状态](configure-presence-in-skype-for-business-online.md)为您的组织。</span><span class="sxs-lookup"><span data-stu-id="a42ac-106">This way, Skype for Business will be set up with your domain, everyone will have their licenses, and you will have configured IM and [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md) for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a42ac-107">对于安装 Skype 的业务应用程序的用户，他们需要将其 PC 或设备上的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="a42ac-107">For users to install the Skype for Business app, they need to be local admins on their PC or device.</span></span> <span data-ttu-id="a42ac-108">或者他们需要将可以在他们的 PC 或设备安装应用程序的本地组的一部分。</span><span class="sxs-lookup"><span data-stu-id="a42ac-108">Or they will need to be part of a local group that can install apps on their PC or devices.</span></span> <span data-ttu-id="a42ac-109">如果您的用户不会允许在其设备上安装软件，您需要为它们安装 Skype 的业务应用程序。</span><span class="sxs-lookup"><span data-stu-id="a42ac-109">If your users aren't allowed to install software on their devices, you'll need to install the Skype for Business app for them.</span></span> 
  
## <a name="for-most-small-and-medium-sized-businesses"></a><span data-ttu-id="a42ac-110">对于大多数小型和中型企业</span><span class="sxs-lookup"><span data-stu-id="a42ac-110">For most small and medium-sized businesses</span></span>

 <span data-ttu-id="a42ac-111">**的逐步安装说明：**如果您有小型或中等规模的业务，我们建议您只需要求用户在其 PC 上安装 Skype 的业务应用程序。</span><span class="sxs-lookup"><span data-stu-id="a42ac-111">**Step-by-step installation instructions:** If you have a small or medium-sized business, we recommend that you simply ask your users to install the Skype for Business app on their PC.</span></span> <span data-ttu-id="a42ac-112">其指向这些说明：[企业安装 Skype](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a42ac-112">Point them to these instructions: [Install Skype for Business](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US).</span></span> <span data-ttu-id="a42ac-113">如果他们使用的 Mac，其指向[设置 Office 365 的 Mac 2011 的 Lync](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a42ac-113">If they are using Macs, point them to [Set up Lync for Mac 2011 for Office 365](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US).</span></span> <span data-ttu-id="a42ac-114">Skype 的业务应用程序是 Office 应用程序的其余部分分开安装。</span><span class="sxs-lookup"><span data-stu-id="a42ac-114">The Skype for Business app is installed separately from the rest of the Office apps.</span></span>
  
 <span data-ttu-id="a42ac-115">**Office 365 ProPlus 的客户：**如果您的业务使用例如 E3 计划包括 Office 365 ProPlus Office 365 计划，Skype 的业务应用程序被安装在同一时间，您的用户下载和安装 Word、 Excel、 PowerPoint 等。这也意味着他们不能卸载 Skype 的业务，除非它们卸载所有办公室。</span><span class="sxs-lookup"><span data-stu-id="a42ac-115">**Office 365 ProPlus customers:** If your business is using an Office 365 plan that includes Office 365 ProPlus, such as the E3 plan, the Skype for Business app is installed at the same time your users download and install Word, Excel, PowerPoint, etc. This also means they can't uninstall Skype for Business unless they uninstall all of Office.</span></span>
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a><span data-ttu-id="a42ac-116">选择是否要让用户 Skype 业务</span><span class="sxs-lookup"><span data-stu-id="a42ac-116">Choose whether to make Skype for Business available to your users</span></span>

<span data-ttu-id="a42ac-117">[管理员](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)可以选择是否让用户 Skype 为业务应用程序。</span><span class="sxs-lookup"><span data-stu-id="a42ac-117">As the [admin](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) you can choose whether to make the Skype for Business app available to your users.</span></span>
  
- <span data-ttu-id="a42ac-118">**控制是否在公司中的每个人都获取软件**： 登录到 Office 365 管理中心，转至**安装软件**，然后选择您想要为用户提供的软件。</span><span class="sxs-lookup"><span data-stu-id="a42ac-118">**To control whether everyone in your company gets the software**: Sign in to the Office 365 admin center, go to **Install my software**, and then select the software you want to be available for users.</span></span>
    
    ![选择您想要向您的公司中的人员提供的软件。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- <span data-ttu-id="a42ac-120">**控制是否在您公司的特定人员获取软件**： 登录到 Office 365 管理的中心，请转到**用户** > **活动用户**，选择您想要让软件，访问者，然后单击**编辑****产品许可证**旁边并打开或关闭该许可证。</span><span class="sxs-lookup"><span data-stu-id="a42ac-120">**To control whether specific people in your company get the software**: Sign in to the Office 365 admin center, go to **Users** > **Active users**, select the person who you want to give access to the software, and then click **Edit** next to **Product licenses** and turn the license on or off.</span></span>
    
    ![选择您希望用户可以访问哪些软件。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> <span data-ttu-id="a42ac-122">如果您需要查看分配给组织中的人员方面有何计划，登录到新的 Office 365 管理中心 >**用户** > **活动的用户**。</span><span class="sxs-lookup"><span data-stu-id="a42ac-122">If you need to see what plans are assigned to people in your organization, sign in to the new Office 365 admin center > **Users** > **Active users**.</span></span> <span data-ttu-id="a42ac-123">从列表中选择此人然后看看下面的**产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="a42ac-123">Select the person from the list then look under **Product licenses**.</span></span> <span data-ttu-id="a42ac-124">如果您使用的经典的 Office 365 管理中心，看下**分配许可证**。</span><span class="sxs-lookup"><span data-stu-id="a42ac-124">If you are using the classic Office 365 admin center, look under **Assigned license**.</span></span> 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a><span data-ttu-id="a42ac-125">手动部署到您的用户的 Skype 业务</span><span class="sxs-lookup"><span data-stu-id="a42ac-125">Manually deploying Skype for Business to your users</span></span>
<span data-ttu-id="a42ac-126"><a name="bkmk_manual_1"> </a></span><span class="sxs-lookup"><span data-stu-id="a42ac-126"></span></span>

<span data-ttu-id="a42ac-127">如果您希望用户从互联网而不是您的网络上的某个位置安装 Skype 的业务应用程序，您可以下载安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="a42ac-127">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files.</span></span> <span data-ttu-id="a42ac-128">为此，请转到 Office 365 管理中心**手动部署用户软件**部分。</span><span class="sxs-lookup"><span data-stu-id="a42ac-128">To do this go to the **Manually deploy user software** section of the Office 365 admin center.</span></span> <span data-ttu-id="a42ac-129">然后可以选择**安装**，并将安装程序.exe 文件保存到网络位置。</span><span class="sxs-lookup"><span data-stu-id="a42ac-129">You can then select **Install** and save the setup .exe file to a network location.</span></span>
  
<span data-ttu-id="a42ac-130">另一种方法是下载 Skype 业务基本应用程序为您的用户。</span><span class="sxs-lookup"><span data-stu-id="a42ac-130">Another option is to download the Skype for Business Basic app for your users.</span></span> <span data-ttu-id="a42ac-131">您可以下载[Microsoft Skype 的基本业务 （32 或 64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=49440)。</span><span class="sxs-lookup"><span data-stu-id="a42ac-131">You can download [Microsoft Skype for Business Basic (32 or 64 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).</span></span>
  
<span data-ttu-id="a42ac-132">为两个完整和基本 Skype 的业务应用程序，您下载的安装文件之后, 您需要手动发送 （例如，电子邮件） 中的网络路径的用户使其可以运行安装程序以在其计算机上安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a42ac-132">For both the full and basic Skype for Business apps, after you have downloaded the setup files, you will need to manually send (for example, in email) the network path to the users so they can run the setup program to install the app on their computer.</span></span>
  
<span data-ttu-id="a42ac-133">这些下载内容还可用于使用您现有的软件部署工具和流程部署到您的用户 Skype 为业务应用程序。</span><span class="sxs-lookup"><span data-stu-id="a42ac-133">You can also use these downloads to deploy the Skype for Business app to your users by using your existing software deployment tools and processes.</span></span>
  
## <a name="for-larger-and-enterprise-organizations"></a><span data-ttu-id="a42ac-134">对于较大和企业公司</span><span class="sxs-lookup"><span data-stu-id="a42ac-134">For larger and enterprise organizations</span></span>

> [!NOTE]
> <span data-ttu-id="a42ac-135">此部分仅适用于为业务应用程序可通过 Office 365 计划 Skype。</span><span class="sxs-lookup"><span data-stu-id="a42ac-135">This section only applies to the Skype for Business app available through Office 365 plans.</span></span> <span data-ttu-id="a42ac-136">如果您的组织使用的业务应用程序，它是基于 Windows 安装程序 (MSI)，Skype 的批量许可版本，请参阅[自定义客户端安装在商业服务器 2015年的 Skype](https://technet.microsoft.com/en-us/library/jj204934.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a42ac-136">If your organization is using a volume licensed version of the Skype for Business app, which is Windows Installer-based (MSI), see [Customize client installation in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx).</span></span> 
  
<span data-ttu-id="a42ac-137">在很多企业或大型组织，不允许用户在其计算机上安装软件。</span><span class="sxs-lookup"><span data-stu-id="a42ac-137">In many enterprises or large organizations, users aren't allowed to install software on their computers.</span></span> <span data-ttu-id="a42ac-138">相反，IT 部门将所需的软件部署到用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="a42ac-138">Instead, the IT departments deploy the necessary software to the users' computers.</span></span> <span data-ttu-id="a42ac-139">IT 部门还可能需要控制互联网或网络使用的带宽量在其组织中，因此他们希望通过 Internet 或企业网络，从附近而不是从其网络位置安装软件。</span><span class="sxs-lookup"><span data-stu-id="a42ac-139">IT departments also might want to control the amount of Internet or network bandwidth used in their organization, so they want to install software from a nearby location on their network instead of from across the Internet or across the corporate network.</span></span>
  
<span data-ttu-id="a42ac-140">与 Office 365 可以几个用于部署业务应用程序的 Skype，如果您想要控制从何处安装的选项。</span><span class="sxs-lookup"><span data-stu-id="a42ac-140">With Office 365, you have several options for deploying the Skype for Business app if you want to control where it's installed from.</span></span> <span data-ttu-id="a42ac-141">这些选项包括：</span><span class="sxs-lookup"><span data-stu-id="a42ac-141">Some of those options include the following:</span></span>
  
- <span data-ttu-id="a42ac-142">下载 Skype 的业务应用程序到您的本地网络从 Office 365 管理中心，[手动部署业务用户的 Skype](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)所述。</span><span class="sxs-lookup"><span data-stu-id="a42ac-142">Download the Skype for Business app to your local network from the Office 365 admin center, as described in [Manually deploying Skype for Business to your users](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span></span>
    
- <span data-ttu-id="a42ac-143">使用**[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)**将 Office 365 ProPlus 或 Skype 的业务应用程序下载到您的本地网络。</span><span class="sxs-lookup"><span data-stu-id="a42ac-143">Use the **[Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** to download either Office 365 ProPlus or the Skype for Business app to your local network.</span></span> <span data-ttu-id="a42ac-144">然后，使用 Office 部署工具来将应用程序部署到您的用户。</span><span class="sxs-lookup"><span data-stu-id="a42ac-144">Then, use the Office Deployment Tool to deploy the app to your users.</span></span> <span data-ttu-id="a42ac-145">Office 部署工具使您能够控制部署，如语言和版本 （32 位或 64 位） 的某些方面。</span><span class="sxs-lookup"><span data-stu-id="a42ac-145">The Office Deployment Tool gives you the ability to control certain aspects of the deployment, such as languages and version (32-bit or 64-bit).</span></span>
    
- <span data-ttu-id="a42ac-146">使用您的现有软件部署工具和进程，例如系统中心配置管理器中，可以将 Office 365 ProPlus 或 Skype 的业务应用程序部署到您的用户。</span><span class="sxs-lookup"><span data-stu-id="a42ac-146">Use your existing software deployment tools and processes, such as System Center Configuration Manager, to deploy Office 365 ProPlus or the Skype for Business app to your users.</span></span> <span data-ttu-id="a42ac-147">与[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)或从 Office 365 管理中心已经下载的软件，可以使用您现有的工具和流程。</span><span class="sxs-lookup"><span data-stu-id="a42ac-147">You can use your existing tools and processes with the [Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) or with the software that you've downloaded from the Office 365 admin center.</span></span>
    
### <a name="more-info-on-using-the-office-deployment-tool"></a><span data-ttu-id="a42ac-148">有关使用 Office 部署工具的详细信息</span><span class="sxs-lookup"><span data-stu-id="a42ac-148">More info on using the Office Deployment Tool</span></span>

<span data-ttu-id="a42ac-149">有关下载 Office 部署工具和安装 Skype 业务应用程序和其他 Office 365 的客户端应用程序的详细信息的详细信息，请参阅[在 Office 365 管理用户软件](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。</span><span class="sxs-lookup"><span data-stu-id="a42ac-149">For details on downloading the Office Deployment Tool and more information on installing the Skype for Business app and other Office 365 client apps, see [Manage user software in Office 365](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span></span>
  
<span data-ttu-id="a42ac-150">下面是使用 Office 部署工具来部署应用程序所涉及的步骤概述：</span><span class="sxs-lookup"><span data-stu-id="a42ac-150">Here's an overview of the steps involved in using the Office Deployment Tool to deploy an app:</span></span>
  
1. <span data-ttu-id="a42ac-151">从 Microsoft 下载中心**[下载最新的 Office 部署工具](https://www.microsoft.com/en-us/download/details.aspx?id=49117)**。</span><span class="sxs-lookup"><span data-stu-id="a42ac-151">**[Download the newest Office Deployment Tool](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** from the Microsoft Download Center.</span></span>
    
2. <span data-ttu-id="a42ac-152">创建 configuration.xml 文件用于 Office 部署工具中包含客户端应用程序所需的设置，如设置的版本 （32 位或 64 位）、 安装语言，等等。</span><span class="sxs-lookup"><span data-stu-id="a42ac-152">Create the configuration.xml file to be used with the Office Deployment Tool that has the client app settings you want, such as setting the version (32-bit or 64-bit), the installation language, etc.</span></span>
    
3. <span data-ttu-id="a42ac-153">使用 Office 部署工具和 configuration.xml 文件将安装文件下载到您的本地或内部网络从 Office 内容传递网络 (CDN)。</span><span class="sxs-lookup"><span data-stu-id="a42ac-153">Use the Office Deployment Tool and the configuration.xml file to download the setup files to your local or internal network from the Office Content Delivery Network (CDN).</span></span>
    
4. <span data-ttu-id="a42ac-154">使用 Office 部署工具和 configuration.xml 安装 Office 客户端应用程序，包括 Skype 的业务应用程序。</span><span class="sxs-lookup"><span data-stu-id="a42ac-154">Use Office Deployment Tool and the configuration.xml to install the Office client apps, including the Skype for Business app.</span></span>
    
<span data-ttu-id="a42ac-155">有关使用 Office 部署工具和 configuration.xml 文件的详细信息，请参阅下列文章：</span><span class="sxs-lookup"><span data-stu-id="a42ac-155">For details on using the Office Deployment Tool and configuration.xml file, see the following articles:</span></span>
  
- [<span data-ttu-id="a42ac-156">Office 部署工具概述</span><span class="sxs-lookup"><span data-stu-id="a42ac-156">Office Deployment Tool overview</span></span>](https://technet.microsoft.com/library/jj219422.aspx)
    
- [<span data-ttu-id="a42ac-157">Configuration.xml 设置</span><span class="sxs-lookup"><span data-stu-id="a42ac-157">Configuration.xml settings</span></span>](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a><span data-ttu-id="a42ac-158">有关使用系统中心配置管理器的详细信息</span><span class="sxs-lookup"><span data-stu-id="a42ac-158">More info on using System Center Configuration Manager</span></span>

<span data-ttu-id="a42ac-159">您可以使用您现有的软件部署工具和流程，如系统中心配置管理器中，部署业务应用程序为 Skype。</span><span class="sxs-lookup"><span data-stu-id="a42ac-159">You can use your existing software deployment tools and processes, such as System Center Configuration Manager, to deploy the Skype for Business app.</span></span> <span data-ttu-id="a42ac-160">与从 Office 365 管理中心下载的任何软件或 Office 部署工具，可以使用这些工具和进程。</span><span class="sxs-lookup"><span data-stu-id="a42ac-160">You can use these tools and processes with either the software that you download from the Office 365 admin center or with the Office Deployment Tool.</span></span>
  
<span data-ttu-id="a42ac-161">有关使用配置管理器部署软件的详细信息，请参阅下列文章：</span><span class="sxs-lookup"><span data-stu-id="a42ac-161">For more information about using Configuration Manager to deploy software, see the following articles:</span></span>
  
- [<span data-ttu-id="a42ac-162">如何创建配置管理器中的应用</span><span class="sxs-lookup"><span data-stu-id="a42ac-162">How to Create Applications in Configuration Manager</span></span>](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [<span data-ttu-id="a42ac-163">如何部署应用程序在配置管理器</span><span class="sxs-lookup"><span data-stu-id="a42ac-163">How to Deploy Applications in Configuration Manager</span></span>](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
<span data-ttu-id="a42ac-164">如果您正在部署业务应用程序一部分的 Skype 的部署 Office 365 ProPlus，请参阅[部署 Office 365 ProPlus 使用系统中心配置管理器](https://technet.microsoft.com/en-us/library/dn708063.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a42ac-164">If you're deploying the Skype for Business app as part of deploying Office 365 ProPlus, see [Deploy Office 365 ProPlus by using the System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).</span></span>
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a><span data-ttu-id="a42ac-165">规划对 Skype 的业务应用程序的更新</span><span class="sxs-lookup"><span data-stu-id="a42ac-165">Planning for updates to the Skype for Business app</span></span>

<span data-ttu-id="a42ac-166">作为部署 Skype 的业务应用程序的一部分，您需要考虑要如何获取更新后安装 Skype 业务。</span><span class="sxs-lookup"><span data-stu-id="a42ac-166">As part of deploying the Skype for Business app, you need to consider how you want to get updates after Skype for Business is installed.</span></span> <span data-ttu-id="a42ac-167">这些更新可以包括新功能、 安全更新、 与安全无关的更新，如提供稳定性和性能改进的更新。</span><span class="sxs-lookup"><span data-stu-id="a42ac-167">These updates can include new features, security updates, or non-security updates, such as updates that provide stability or performance improvements.</span></span> <span data-ttu-id="a42ac-168">您需要考虑的两个主要方面是：</span><span class="sxs-lookup"><span data-stu-id="a42ac-168">The two primary things you need to consider are :</span></span>
  
- <span data-ttu-id="a42ac-169">要获得更新的位置</span><span class="sxs-lookup"><span data-stu-id="a42ac-169">Where do you want to get updates from</span></span>
    
- <span data-ttu-id="a42ac-170">要获取功能更新频率如何</span><span class="sxs-lookup"><span data-stu-id="a42ac-170">How often do you want to get feature updates</span></span>
    
<span data-ttu-id="a42ac-171">您可以控制您从何处获取更新和获取功能更新的频率，而不能选择的特定安全更新或您获得的非安全更新。</span><span class="sxs-lookup"><span data-stu-id="a42ac-171">While you can control where you get updates from and how often you get feature updates, you can't choose which specific security updates or non-security updates you get.</span></span>
  
 <span data-ttu-id="a42ac-172">**从何处获取更新**</span><span class="sxs-lookup"><span data-stu-id="a42ac-172">**Where to get updates from**</span></span>
  
<span data-ttu-id="a42ac-173">默认情况下，安装 Skype 的业务应用程序之后，更新将自动下载从互联网时可从 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="a42ac-173">By default, after the Skype for Business app is installed, updates will be automatically downloaded from the Internet when they are available from Microsoft.</span></span> <span data-ttu-id="a42ac-174">如果需要更多的控制通过更新发生时或在从已安装这些更新，可以使用 Office 部署工具或组策略来配置它。</span><span class="sxs-lookup"><span data-stu-id="a42ac-174">If you want more control over when updates occur or where the updates are installed from, you can use the Office Deployment Tool or Group Policy to configure that.</span></span>
  
<span data-ttu-id="a42ac-175">例如，许多组织都希望在整个组织部署之前测试的一组用户更新。</span><span class="sxs-lookup"><span data-stu-id="a42ac-175">For example, many organizations want to test updates with a group of users before deploying them throughout the organization.</span></span> <span data-ttu-id="a42ac-176">您可以使用 Office 部署工具或组策略配置为业务应用程序自动从 Internet 获取而不是从您的网络上的特定位置更新 Skype 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a42ac-176">You can do this by using the Office Deployment Tool or Group Policy to configure the Skype for Business app to get updates from a specific location on your network, instead of automatically from the Internet.</span></span> <span data-ttu-id="a42ac-177">然后，可以使用 Office 部署工具将每月更新下载到您的本地网络。</span><span class="sxs-lookup"><span data-stu-id="a42ac-177">Then, you can use the Office Deployment Tool to download the updates every month to your local network.</span></span>
  
<span data-ttu-id="a42ac-178">有关 Office 365 提供软件更新如何工作的详细信息，请参阅下列文章：</span><span class="sxs-lookup"><span data-stu-id="a42ac-178">For more information about how updates work for Office 365 software, see these articles:</span></span>
  
- [<span data-ttu-id="a42ac-179">对于 Office 365 ProPlus 更新过程概述</span><span class="sxs-lookup"><span data-stu-id="a42ac-179">Overview of the update process for Office 365 ProPlus</span></span>](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [<span data-ttu-id="a42ac-180">选择如何管理对 Office 365 ProPlus 更新</span><span class="sxs-lookup"><span data-stu-id="a42ac-180">Choose how to manage updates to Office 365 ProPlus</span></span>](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [<span data-ttu-id="a42ac-181">配置更新设置 Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="a42ac-181">Configure update settings for Office 365 ProPlus</span></span>](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 <span data-ttu-id="a42ac-182">**如何经常获取功能更新**</span><span class="sxs-lookup"><span data-stu-id="a42ac-182">**How often to get feature updates**</span></span>
  
<span data-ttu-id="a42ac-183">除了哪里您获取更新，您还可以控制新功能获得 Skype 业务客户端的频率。</span><span class="sxs-lookup"><span data-stu-id="a42ac-183">In addition to where you get updates from, you can also control how often you get new features for the Skype for Business client.</span></span> <span data-ttu-id="a42ac-184">两个选项如下所示：</span><span class="sxs-lookup"><span data-stu-id="a42ac-184">The two choices are the following:</span></span>
  
- <span data-ttu-id="a42ac-185">获取功能更新每个月，如果有新功能</span><span class="sxs-lookup"><span data-stu-id="a42ac-185">Get feature updates every month, if there are new features</span></span>
    
- <span data-ttu-id="a42ac-186">获取功能更新每六个月</span><span class="sxs-lookup"><span data-stu-id="a42ac-186">Get features updates every six months</span></span>
    
<span data-ttu-id="a42ac-187">对于一些组织来说，他们想要测试新的功能，所以他们想要获取功能更新只每年两次而不是每个月的时间。</span><span class="sxs-lookup"><span data-stu-id="a42ac-187">For some organizations, they want time to test new features, so they want to get feature updates only twice a year instead of every month.</span></span>
  
<span data-ttu-id="a42ac-188">您可以控制通过使用 Office 部署工具或组策略来配置更新通道获取功能更新的频率。</span><span class="sxs-lookup"><span data-stu-id="a42ac-188">You can control how often you get feature updates by using the Office Deployment Tool or Group Policy to configure the update channel.</span></span> <span data-ttu-id="a42ac-189">您的功能更新每月 （大约），而半年通道为您提供了每月一次通道使功能更新每六个月。</span><span class="sxs-lookup"><span data-stu-id="a42ac-189">The Monthly Channel gives you feature updates monthly (approximately), while the Semi-Annual Channel gives you feature updates every six months.</span></span> <span data-ttu-id="a42ac-190">有关通道的详细信息，请参阅[Office 365 ProPlus 更新通道的概述](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。</span><span class="sxs-lookup"><span data-stu-id="a42ac-190">For more information about channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a42ac-191">相关主题</span><span class="sxs-lookup"><span data-stu-id="a42ac-191">Related topics</span></span>

[<span data-ttu-id="a42ac-192">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a42ac-192">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="a42ac-193">Skype for Business 和 Microsoft Teams 外接程序许可</span><span class="sxs-lookup"><span data-stu-id="a42ac-193">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
