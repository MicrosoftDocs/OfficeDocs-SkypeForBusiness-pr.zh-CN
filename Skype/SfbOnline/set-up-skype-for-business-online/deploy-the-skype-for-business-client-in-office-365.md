---
title: 在 Office 365 中部署 Skype for Business 客户端
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '了解如何在小型、中型和大型组织中规划和部署 Skype for Business，并让你的用户可以使用它。 '
ms.openlocfilehash: 052cc4cb8aa1242628e0f57a57a3fe5532be3d71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706497"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a><span data-ttu-id="e394c-103">在 Office 365 中部署 Skype for Business 客户端</span><span class="sxs-lookup"><span data-stu-id="e394c-103">Deploy the Skype for Business client in Office 365</span></span>

<span data-ttu-id="e394c-104">本文介绍**[管理员](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 可如何将 Skype for business 应用部署到组织中的人员的选项。</span><span class="sxs-lookup"><span data-stu-id="e394c-104">This article explains options for how you, the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, can deploy the Skype for Business app to the people in your organization.</span></span>
  
<span data-ttu-id="e394c-105">在将 Skype for business 部署到你的用户之前，请确保在本文[设置 skype For Business Online](set-up-skype-for-business-online.md)中执行了步骤1-3。</span><span class="sxs-lookup"><span data-stu-id="e394c-105">Before you deploy Skype for Business to your users, make sure you've done steps 1-3 in the article [Set up Skype for Business Online](set-up-skype-for-business-online.md).</span></span> <span data-ttu-id="e394c-106">这样，将为您的域设置 Skype for business，每个人都将拥有自己的许可证，并且您将在您的组织的[Skype for Business Online 中](configure-presence-in-skype-for-business-online.md)配置了 IM 并配置状态。</span><span class="sxs-lookup"><span data-stu-id="e394c-106">This way, Skype for Business will be set up with your domain, everyone will have their licenses, and you will have configured IM and [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md) for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e394c-107">对于要安装 Skype for Business 应用的用户，他们需要在其 PC 或设备上是本地管理员。</span><span class="sxs-lookup"><span data-stu-id="e394c-107">For users to install the Skype for Business app, they need to be local admins on their PC or device.</span></span> <span data-ttu-id="e394c-108">或者，它们必须是可在其电脑或设备上安装应用的本地组的一部分。</span><span class="sxs-lookup"><span data-stu-id="e394c-108">Or they will need to be part of a local group that can install apps on their PC or devices.</span></span> <span data-ttu-id="e394c-109">如果你的用户不能在其设备上安装软件，你需要为其安装 Skype for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e394c-109">If your users aren't allowed to install software on their devices, you'll need to install the Skype for Business app for them.</span></span> 
  
## <a name="for-most-small-and-medium-sized-businesses"></a><span data-ttu-id="e394c-110">适用于大多数小型企业和中等规模的企业</span><span class="sxs-lookup"><span data-stu-id="e394c-110">For most small and medium-sized businesses</span></span>

 <span data-ttu-id="e394c-111">**分步安装说明：** 如果您有小型企业或中型企业版，我们建议您只需让用户在其 PC 上安装 Skype for Business 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e394c-111">**Step-by-step installation instructions:** If you have a small or medium-sized business, we recommend that you simply ask your users to install the Skype for Business app on their PC.</span></span> <span data-ttu-id="e394c-112">请点击以下说明：[安装 Skype For business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)。</span><span class="sxs-lookup"><span data-stu-id="e394c-112">Point them to these instructions: [Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb).</span></span> <span data-ttu-id="e394c-113">如果他们使用 Mac，请将其指向为[Office 365 设置 Lync For Mac 2011](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)。</span><span class="sxs-lookup"><span data-stu-id="e394c-113">If they are using Macs, point them to [Set up Lync for Mac 2011 for Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88).</span></span> <span data-ttu-id="e394c-114">Skype for Business 应用与其余 Office 应用分开安装。</span><span class="sxs-lookup"><span data-stu-id="e394c-114">The Skype for Business app is installed separately from the rest of the Office apps.</span></span>
  
 <span data-ttu-id="e394c-115">**Office 365 专业增强版客户：** 如果你的企业使用包含 Office 365 专业增强版的 Office 365 计划（如 E3 计划），则在你的用户下载和安装 Word、Excel、PowerPoint 等的同时安装 Skype for Business 应用。这还意味着他们无法卸载 Skype for Business，除非他们卸载了所有的 Office。</span><span class="sxs-lookup"><span data-stu-id="e394c-115">**Office 365 ProPlus customers:** If your business is using an Office 365 plan that includes Office 365 ProPlus, such as the E3 plan, the Skype for Business app is installed at the same time your users download and install Word, Excel, PowerPoint, etc. This also means they can't uninstall Skype for Business unless they uninstall all of Office.</span></span>
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a><span data-ttu-id="e394c-116">选择是否让你的用户可以使用 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e394c-116">Choose whether to make Skype for Business available to your users</span></span>

<span data-ttu-id="e394c-117">作为[管理员](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)，你可以选择是否将 Skype for business 应用程序提供给你的用户。</span><span class="sxs-lookup"><span data-stu-id="e394c-117">As the [admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) you can choose whether to make the Skype for Business app available to your users.</span></span>
  
- <span data-ttu-id="e394c-118">**控制公司中的每个人是否获取软件**：登录到 Microsoft 365 管理中心，请转到 "**安装我的软件**"，然后选择要为用户提供的软件。</span><span class="sxs-lookup"><span data-stu-id="e394c-118">**To control whether everyone in your company gets the software**: Sign in to the Microsoft 365 admin center, go to **Install my software**, and then select the software you want to be available for users.</span></span>
    
    ![选择您希望为公司中的人员提供的软件。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- <span data-ttu-id="e394c-120">**控制公司中的特定人员是否获取软件**：登录到 Microsoft 365 管理中心，转到 "**用户** > **活动用户**"，选择要向其授予软件访问权限的人员，然后单击 "**产品许可证**" 旁边的 "**编辑**"，然后打开或关闭许可证。</span><span class="sxs-lookup"><span data-stu-id="e394c-120">**To control whether specific people in your company get the software**: Sign in to the Microsoft 365 admin center, go to **Users** > **Active users**, select the person who you want to give access to the software, and then click **Edit** next to **Product licenses** and turn the license on or off.</span></span>
    
    ![选择希望用户访问的软件。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> <span data-ttu-id="e394c-122">如果需要查看为组织中的人员分配了哪些计划，请登录 Microsoft 365 管理中心 >**用户** > **活动用户**。</span><span class="sxs-lookup"><span data-stu-id="e394c-122">If you need to see what plans are assigned to people in your organization, sign in to the Microsoft 365 admin center > **Users** > **Active users**.</span></span> <span data-ttu-id="e394c-123">从列表中选择人员，然后在 "**产品许可证**" 下查看。</span><span class="sxs-lookup"><span data-stu-id="e394c-123">Select the person from the list then look under **Product licenses**.</span></span> <span data-ttu-id="e394c-124">如果您使用的是经典管理中心，请在 "**分配的许可证**" 下查看。</span><span class="sxs-lookup"><span data-stu-id="e394c-124">If you are using the classic admin center, look under **Assigned license**.</span></span> 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a><span data-ttu-id="e394c-125">手动为用户部署 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e394c-125">Manually deploying Skype for Business to your users</span></span>
<span data-ttu-id="e394c-126"><a name="bkmk_manual_1"> </a></span><span class="sxs-lookup"><span data-stu-id="e394c-126"><a name="bkmk_manual_1"> </a></span></span>

<span data-ttu-id="e394c-127">如果希望用户从网络上的某个位置（而不是从 Internet）安装 Skype for Business 应用，可以下载安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="e394c-127">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files.</span></span> <span data-ttu-id="e394c-128">若要执行此操作，请转到 Microsoft 365 管理中心的 "**手动部署用户软件**" 部分。</span><span class="sxs-lookup"><span data-stu-id="e394c-128">To do this go to the **Manually deploy user software** section of the Microsoft 365 admin center.</span></span> <span data-ttu-id="e394c-129">然后，您可以选择 "**安装**并将 setup.exe 文件保存到网络位置"。</span><span class="sxs-lookup"><span data-stu-id="e394c-129">You can then select **Install** and save the setup .exe file to a network location.</span></span>
  
<span data-ttu-id="e394c-130">另一种方法是为你的用户下载 Skype for Business Basic 应用。</span><span class="sxs-lookup"><span data-stu-id="e394c-130">Another option is to download the Skype for Business Basic app for your users.</span></span> <span data-ttu-id="e394c-131">您可以下载[Microsoft Skype For Business Basic （32或64位）](https://www.microsoft.com/download/details.aspx?id=49440)。</span><span class="sxs-lookup"><span data-stu-id="e394c-131">You can download [Microsoft Skype for Business Basic (32 or 64 Bit)](https://www.microsoft.com/download/details.aspx?id=49440).</span></span>
  
<span data-ttu-id="e394c-132">对于完整版和基本版 Skype for business 应用，在下载安装程序文件之后，你需要手动发送（例如，在电子邮件中）用户的网络路径，以便他们可以运行安装程序以在其计算机上安装该应用。</span><span class="sxs-lookup"><span data-stu-id="e394c-132">For both the full and basic Skype for Business apps, after you have downloaded the setup files, you will need to manually send (for example, in email) the network path to the users so they can run the setup program to install the app on their computer.</span></span>
  
<span data-ttu-id="e394c-133">你还可以使用这些下载将 Skype for Business 应用部署到你的用户，方法是使用现有软件部署工具和进程。</span><span class="sxs-lookup"><span data-stu-id="e394c-133">You can also use these downloads to deploy the Skype for Business app to your users by using your existing software deployment tools and processes.</span></span>
  
## <a name="for-larger-and-enterprise-organizations"></a><span data-ttu-id="e394c-134">对于大型企业组织</span><span class="sxs-lookup"><span data-stu-id="e394c-134">For larger and enterprise organizations</span></span>

> [!NOTE]
> <span data-ttu-id="e394c-135">本部分仅适用于通过 Office 365 计划提供的 Skype for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e394c-135">This section only applies to the Skype for Business app available through Office 365 plans.</span></span> <span data-ttu-id="e394c-136">如果你的组织使用的是基于 Windows Installer （MSI）的 Skype for business 应用批量许可版本，请参阅[在 Skype For Business 服务器中自定义 Windows 客户端安装](https://technet.microsoft.com/library/jj204934.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e394c-136">If your organization is using a volume licensed version of the Skype for Business app, which is Windows Installer-based (MSI), see [Customize Windows client installation in Skype for Business Server](https://technet.microsoft.com/library/jj204934.aspx).</span></span>
  
<span data-ttu-id="e394c-137">在许多企业或大型组织中，不允许用户在其计算机上安装软件。</span><span class="sxs-lookup"><span data-stu-id="e394c-137">In many enterprises or large organizations, users aren't allowed to install software on their computers.</span></span> <span data-ttu-id="e394c-138">相反，IT 部门将必要的软件部署到用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="e394c-138">Instead, the IT departments deploy the necessary software to the users' computers.</span></span> <span data-ttu-id="e394c-139">IT 部门还可能希望控制组织中使用的 Internet 或网络带宽量，以便他们可以从网络上的附近位置（而不是通过 Internet 或整个企业网络）安装软件。</span><span class="sxs-lookup"><span data-stu-id="e394c-139">IT departments also might want to control the amount of Internet or network bandwidth used in their organization, so they want to install software from a nearby location on their network instead of from across the Internet or across the corporate network.</span></span>
  
<span data-ttu-id="e394c-140">使用 Office 365，如果要控制安装 Skype for Business 应用的位置，则可以使用多个选项来部署 Skype for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e394c-140">With Office 365, you have several options for deploying the Skype for Business app if you want to control where it's installed from.</span></span> <span data-ttu-id="e394c-141">其中一些选项包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="e394c-141">Some of those options include the following:</span></span>
  
- <span data-ttu-id="e394c-142">将 Skype for Business 应用从 Microsoft 365 管理中心下载到您的本地网络，如[手动向用户部署 Skype for](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)business 中所述。</span><span class="sxs-lookup"><span data-stu-id="e394c-142">Download the Skype for Business app to your local network from the Microsoft 365 admin center, as described in [Manually deploying Skype for Business to your users](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span></span>
    
- <span data-ttu-id="e394c-143">使用**[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 将 Office 365 专业增强版或 Skype for business 应用下载到您的本地网络。</span><span class="sxs-lookup"><span data-stu-id="e394c-143">Use the **[Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** to download either Office 365 ProPlus or the Skype for Business app to your local network.</span></span> <span data-ttu-id="e394c-144">然后，使用 Office 部署工具将应用部署到你的用户。</span><span class="sxs-lookup"><span data-stu-id="e394c-144">Then, use the Office Deployment Tool to deploy the app to your users.</span></span> <span data-ttu-id="e394c-145">Office 部署工具使你能够控制部署的某些方面，例如语言和版本（32位或64位）。</span><span class="sxs-lookup"><span data-stu-id="e394c-145">The Office Deployment Tool gives you the ability to control certain aspects of the deployment, such as languages and version (32-bit or 64-bit).</span></span>
    
- <span data-ttu-id="e394c-146">使用现有软件部署工具和进程（如 Microsoft 终结点配置管理器）将 Office 365 专业增强版或 Skype for Business 应用部署到你的用户。</span><span class="sxs-lookup"><span data-stu-id="e394c-146">Use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy Office 365 ProPlus or the Skype for Business app to your users.</span></span> <span data-ttu-id="e394c-147">你可以将现有工具和进程与[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)或从 Microsoft 365 管理中心下载的软件结合使用。</span><span class="sxs-lookup"><span data-stu-id="e394c-147">You can use your existing tools and processes with the [Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) or with the software that you've downloaded from the Microsoft 365 admin center.</span></span>
    
### <a name="more-info-on-using-the-office-deployment-tool"></a><span data-ttu-id="e394c-148">有关使用 Office 部署工具的详细信息</span><span class="sxs-lookup"><span data-stu-id="e394c-148">More info on using the Office Deployment Tool</span></span>

<span data-ttu-id="e394c-149">有关下载 Office 部署工具的详细信息以及有关安装 Skype for Business 应用和其他 Office 365 客户端应用的详细信息，请参阅[管理 Office 365 中的软件下载设置](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。</span><span class="sxs-lookup"><span data-stu-id="e394c-149">For details on downloading the Office Deployment Tool and more information on installing the Skype for Business app and other Office 365 client apps, see [Manage software download settings in Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span></span>
  
<span data-ttu-id="e394c-150">下面概述了使用 Office 部署工具部署应用时所涉及的步骤：</span><span class="sxs-lookup"><span data-stu-id="e394c-150">Here's an overview of the steps involved in using the Office Deployment Tool to deploy an app:</span></span>
  
1. <span data-ttu-id="e394c-151">从 Microsoft 下载中心**[下载最新的 Office 部署工具](https://www.microsoft.com/download/details.aspx?id=49117)**。</span><span class="sxs-lookup"><span data-stu-id="e394c-151">**[Download the newest Office Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117)** from the Microsoft Download Center.</span></span>
    
2. <span data-ttu-id="e394c-152">创建要与 Office 部署工具一起使用的 config.xml 文件，该工具具有所需的客户端应用程序设置，如设置版本（32位或64位）、安装语言等。</span><span class="sxs-lookup"><span data-stu-id="e394c-152">Create the configuration.xml file to be used with the Office Deployment Tool that has the client app settings you want, such as setting the version (32-bit or 64-bit), the installation language, etc.</span></span>
    
3. <span data-ttu-id="e394c-153">使用 Office 部署工具和配置 .xml 文件，从 Office 内容交付网络（CDN）将安装文件下载到本地或内部网络。</span><span class="sxs-lookup"><span data-stu-id="e394c-153">Use the Office Deployment Tool and the configuration.xml file to download the setup files to your local or internal network from the Office Content Delivery Network (CDN).</span></span>
    
4. <span data-ttu-id="e394c-154">使用 Office 部署工具和配置 .xml 安装 Office 客户端应用，包括 Skype for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e394c-154">Use Office Deployment Tool and the configuration.xml to install the Office client apps, including the Skype for Business app.</span></span>
    
<span data-ttu-id="e394c-155">有关使用 Office 部署工具和配置 .xml 文件的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e394c-155">For details on using the Office Deployment Tool and configuration.xml file, see the following articles:</span></span>
  
- [<span data-ttu-id="e394c-156">Office 部署工具概述</span><span class="sxs-lookup"><span data-stu-id="e394c-156">Office Deployment Tool overview</span></span>](https://technet.microsoft.com/library/jj219422.aspx)
    
- [<span data-ttu-id="e394c-157">配置 xml 设置</span><span class="sxs-lookup"><span data-stu-id="e394c-157">Configuration.xml settings</span></span>](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="e394c-158">有关使用 Microsoft 终结点配置管理器的详细信息</span><span class="sxs-lookup"><span data-stu-id="e394c-158">More info on using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="e394c-159">你可以使用现有软件部署工具和进程（如 Microsoft 终结点配置管理器）部署 Skype for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e394c-159">You can use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy the Skype for Business app.</span></span> <span data-ttu-id="e394c-160">你可以将这些工具和进程与从 Microsoft 365 管理中心或 Office 部署工具下载的软件配合使用。</span><span class="sxs-lookup"><span data-stu-id="e394c-160">You can use these tools and processes with either the software that you download from the Microsoft 365 admin center or with the Office Deployment Tool.</span></span>
  
<span data-ttu-id="e394c-161">有关使用 Configuration Manager 部署软件的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e394c-161">For more information about using Configuration Manager to deploy software, see the following articles:</span></span>
  
- [<span data-ttu-id="e394c-162">在 Configuration Manager 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="e394c-162">Create applications in Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [<span data-ttu-id="e394c-163">通过 Configuration Manager 部署应用程序</span><span class="sxs-lookup"><span data-stu-id="e394c-163">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
<span data-ttu-id="e394c-164">如果你要在部署 Office 365 专业增强版时部署 Skype for Business 应用，请参阅[通过 Configuration Manager 管理 Office 365 专业增强版](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)。</span><span class="sxs-lookup"><span data-stu-id="e394c-164">If you're deploying the Skype for Business app as part of deploying Office 365 ProPlus, see [Manage Office 365 ProPlus with Configuration Manager](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates).</span></span>
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a><span data-ttu-id="e394c-165">规划 Skype for Business 应用更新</span><span class="sxs-lookup"><span data-stu-id="e394c-165">Planning for updates to the Skype for Business app</span></span>

<span data-ttu-id="e394c-166">作为部署 Skype for Business 应用的一部分，你需要考虑在安装 Skype for Business 后你希望如何获取更新。</span><span class="sxs-lookup"><span data-stu-id="e394c-166">As part of deploying the Skype for Business app, you need to consider how you want to get updates after Skype for Business is installed.</span></span> <span data-ttu-id="e394c-167">这些更新可以包括新功能、安全更新或非安全更新，例如提供稳定性或性能改进的更新。</span><span class="sxs-lookup"><span data-stu-id="e394c-167">These updates can include new features, security updates, or non-security updates, such as updates that provide stability or performance improvements.</span></span> <span data-ttu-id="e394c-168">需要考虑的两个主要方面是：</span><span class="sxs-lookup"><span data-stu-id="e394c-168">The two primary things you need to consider are :</span></span>
  
- <span data-ttu-id="e394c-169">您希望从何处获取更新</span><span class="sxs-lookup"><span data-stu-id="e394c-169">Where do you want to get updates from</span></span>
    
- <span data-ttu-id="e394c-170">你希望多长时间获取一项功能更新</span><span class="sxs-lookup"><span data-stu-id="e394c-170">How often do you want to get feature updates</span></span>
    
<span data-ttu-id="e394c-171">虽然你可以控制从何处获取更新以及获取功能更新的频率，但你无法选择获取哪些特定安全更新或非安全更新。</span><span class="sxs-lookup"><span data-stu-id="e394c-171">While you can control where you get updates from and how often you get feature updates, you can't choose which specific security updates or non-security updates you get.</span></span>
  
 <span data-ttu-id="e394c-172">**从何处获取更新**</span><span class="sxs-lookup"><span data-stu-id="e394c-172">**Where to get updates from**</span></span>
  
<span data-ttu-id="e394c-173">默认情况下，在安装 Skype for Business 应用后，当 Microsoft 提供更新时，将从 Internet 自动下载更新。</span><span class="sxs-lookup"><span data-stu-id="e394c-173">By default, after the Skype for Business app is installed, updates will be automatically downloaded from the Internet when they are available from Microsoft.</span></span> <span data-ttu-id="e394c-174">如果你希望更好地控制何时发生更新或安装更新的位置，可以使用 Office 部署工具或组策略来配置。</span><span class="sxs-lookup"><span data-stu-id="e394c-174">If you want more control over when updates occur or where the updates are installed from, you can use the Office Deployment Tool or Group Policy to configure that.</span></span>
  
<span data-ttu-id="e394c-175">例如，许多组织希望先对一组用户测试更新，然后再在整个组织中部署这些更新。</span><span class="sxs-lookup"><span data-stu-id="e394c-175">For example, many organizations want to test updates with a group of users before deploying them throughout the organization.</span></span> <span data-ttu-id="e394c-176">你可以通过使用 Office 部署工具或组策略将 Skype for Business 应用配置为从网络上的特定位置（而不是从 Internet 自动）获取更新来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e394c-176">You can do this by using the Office Deployment Tool or Group Policy to configure the Skype for Business app to get updates from a specific location on your network, instead of automatically from the Internet.</span></span> <span data-ttu-id="e394c-177">然后，你可以使用 Office 部署工具将每月的更新下载到本地网络。</span><span class="sxs-lookup"><span data-stu-id="e394c-177">Then, you can use the Office Deployment Tool to download the updates every month to your local network.</span></span>
  
<span data-ttu-id="e394c-178">有关 Office 365 软件的更新如何工作的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e394c-178">For more information about how updates work for Office 365 software, see these articles:</span></span>
  
- [<span data-ttu-id="e394c-179">Office 365 专业增强版更新流程概述</span><span class="sxs-lookup"><span data-stu-id="e394c-179">Overview of the update process for Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761709.aspx)
    
- [<span data-ttu-id="e394c-180">选择如何管理 Office 365 的更新专业增强版</span><span class="sxs-lookup"><span data-stu-id="e394c-180">Choose how to manage updates to Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761707.aspx)
    
- [<span data-ttu-id="e394c-181">配置 Office 365 的更新设置专业增强版</span><span class="sxs-lookup"><span data-stu-id="e394c-181">Configure update settings for Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761708.aspx)
    
  <span data-ttu-id="e394c-182">**获取功能更新的频率**</span><span class="sxs-lookup"><span data-stu-id="e394c-182">**How often to get feature updates**</span></span>
  
<span data-ttu-id="e394c-183">除了从中获取更新的位置，还可以控制为 Skype for business 客户端获取新功能的频率。</span><span class="sxs-lookup"><span data-stu-id="e394c-183">In addition to where you get updates from, you can also control how often you get new features for the Skype for Business client.</span></span> <span data-ttu-id="e394c-184">这两个选项如下所示：</span><span class="sxs-lookup"><span data-stu-id="e394c-184">The two choices are the following:</span></span>
  
- <span data-ttu-id="e394c-185">如果有新功能，则每月获取功能更新</span><span class="sxs-lookup"><span data-stu-id="e394c-185">Get feature updates every month, if there are new features</span></span>
    
- <span data-ttu-id="e394c-186">获取功能每六个月更新一次</span><span class="sxs-lookup"><span data-stu-id="e394c-186">Get features updates every six months</span></span>
    
<span data-ttu-id="e394c-187">对于某些组织，他们希望使用时间测试新功能，以便他们只需一年的两次（而不是每个月）获取功能更新。</span><span class="sxs-lookup"><span data-stu-id="e394c-187">For some organizations, they want time to test new features, so they want to get feature updates only twice a year instead of every month.</span></span>
  
<span data-ttu-id="e394c-188">你可以通过使用 Office 部署工具或组策略配置更新通道来控制获取功能更新的频率。</span><span class="sxs-lookup"><span data-stu-id="e394c-188">You can control how often you get feature updates by using the Office Deployment Tool or Group Policy to configure the update channel.</span></span> <span data-ttu-id="e394c-189">每月频道为您提供每月（大约）的功能更新，而半年度频道每六个月提供一次功能更新。</span><span class="sxs-lookup"><span data-stu-id="e394c-189">The Monthly Channel gives you feature updates monthly (approximately), while the Semi-Annual Channel gives you feature updates every six months.</span></span> <span data-ttu-id="e394c-190">有关频道的详细信息，请参阅[Office 365 专业增强版更新频道概述](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。</span><span class="sxs-lookup"><span data-stu-id="e394c-190">For more information about channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e394c-191">相关主题</span><span class="sxs-lookup"><span data-stu-id="e394c-191">Related topics</span></span>

[<span data-ttu-id="e394c-192">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e394c-192">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="e394c-193">Skype for Business 和 Microsoft Teams 加载项许可</span><span class="sxs-lookup"><span data-stu-id="e394c-193">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
