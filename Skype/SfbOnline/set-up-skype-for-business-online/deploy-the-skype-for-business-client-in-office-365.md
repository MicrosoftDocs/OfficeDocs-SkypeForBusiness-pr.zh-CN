---
title: 在 Skype for Business 部署 Microsoft 365 客户端Office 365
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
description: '了解如何在小型、中型Skype for Business组织中计划和部署客户，以及如何让用户使用。 '
ms.openlocfilehash: e23d4310d47bfae68a12c2b928741a2994588a57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239895"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a><span data-ttu-id="e797f-103">将 Skype for Business 客户端部署到 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="e797f-103">Deploy the Skype for Business client in Microsoft 365 or Office 365</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e797f-104">本文介绍管理员如何向组织Skype for Business部署应用的选项 **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**。</span><span class="sxs-lookup"><span data-stu-id="e797f-104">This article explains options for how you, the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, can deploy the Skype for Business app to the people in your organization.</span></span>
  
<span data-ttu-id="e797f-105">在将Skype for Business用户之前，请确保已完成在线设置文章的 1-3 [Skype for Business步骤](set-up-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="e797f-105">Before you deploy Skype for Business to your users, make sure you've done steps 1-3 in the article [Set up Skype for Business Online](set-up-skype-for-business-online.md).</span></span> <span data-ttu-id="e797f-106">这样，Skype for Business设置您的域，每个人都将拥有其许可证，并且您将为您的组织配置 IM 和配置 Skype for Business [Online](configure-presence-in-skype-for-business-online.md)中的状态。</span><span class="sxs-lookup"><span data-stu-id="e797f-106">This way, Skype for Business will be set up with your domain, everyone will have their licenses, and you will have configured IM and [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md) for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e797f-107">若要让用户安装 Skype for Business 应用，他们需要是电脑或设备上的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="e797f-107">For users to install the Skype for Business app, they need to be local admins on their PC or device.</span></span> <span data-ttu-id="e797f-108">或者，他们需要是可以在电脑或设备上安装应用的本地组的一部分。</span><span class="sxs-lookup"><span data-stu-id="e797f-108">Or they will need to be part of a local group that can install apps on their PC or devices.</span></span> <span data-ttu-id="e797f-109">如果你的用户不允许在设备上安装软件，你需要为用户安装Skype for Business应用。</span><span class="sxs-lookup"><span data-stu-id="e797f-109">If your users aren't allowed to install software on their devices, you'll need to install the Skype for Business app for them.</span></span> 
  
## <a name="for-most-small-and-medium-sized-businesses"></a><span data-ttu-id="e797f-110">适用于大多数中小型企业</span><span class="sxs-lookup"><span data-stu-id="e797f-110">For most small and medium-sized businesses</span></span>

 <span data-ttu-id="e797f-111">**分步安装说明：** 如果你有一家小型或中型企业，我们建议你直接要求用户Skype for Business电脑上安装该应用。</span><span class="sxs-lookup"><span data-stu-id="e797f-111">**Step-by-step installation instructions:** If you have a small or medium-sized business, we recommend that you simply ask your users to install the Skype for Business app on their PC.</span></span> <span data-ttu-id="e797f-112">请指向以下说明：安装[Skype for Business。](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)</span><span class="sxs-lookup"><span data-stu-id="e797f-112">Point them to these instructions: [Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb).</span></span> <span data-ttu-id="e797f-113">如果他们使用的是 Mac，请将其指向设置[Lync for Mac 2011 for Office 365。](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)</span><span class="sxs-lookup"><span data-stu-id="e797f-113">If they are using Macs, point them to [Set up Lync for Mac 2011 for Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88).</span></span> <span data-ttu-id="e797f-114">Skype for Business应用单独安装，与应用的其余部分Office安装。</span><span class="sxs-lookup"><span data-stu-id="e797f-114">The Skype for Business app is installed separately from the rest of the Office apps.</span></span>
  
 <span data-ttu-id="e797f-115">**Microsoft 365 企业应用版客户：** 如果你的企业使用的是包含 Microsoft 365 企业应用版 的 Office 365 计划（如 E3 计划），则当用户下载并安装 Word、Excel、PowerPoint 等时，将同时安装 Skype for Business 应用。这也意味着他们无法卸载Skype for Business，除非卸载所有Office。</span><span class="sxs-lookup"><span data-stu-id="e797f-115">**Microsoft 365 Apps for enterprise customers:** If your business is using an Office 365 plan that includes Microsoft 365 Apps for enterprise, such as the E3 plan, the Skype for Business app is installed at the same time your users download and install Word, Excel, PowerPoint, etc. This also means they can't uninstall Skype for Business unless they uninstall all of Office.</span></span>
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a><span data-ttu-id="e797f-116">选择是否Skype for Business用户可用</span><span class="sxs-lookup"><span data-stu-id="e797f-116">Choose whether to make Skype for Business available to your users</span></span>

<span data-ttu-id="e797f-117">作为[管理员](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)，你可以选择是否向用户Skype for Business应用。</span><span class="sxs-lookup"><span data-stu-id="e797f-117">As the [admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) you can choose whether to make the Skype for Business app available to your users.</span></span>
  
- <span data-ttu-id="e797f-118">**若要控制贵公司的每个人** 是否获取软件：登录到 Microsoft 365 管理中心，转到"安装 **我的** 软件"，然后选择希望可供用户使用的软件。</span><span class="sxs-lookup"><span data-stu-id="e797f-118">**To control whether everyone in your company gets the software**: Sign in to the Microsoft 365 admin center, go to **Install my software**, and then select the software you want to be available for users.</span></span>
    
    ![选择要提供给公司人员的软件。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- <span data-ttu-id="e797f-120">要控制贵公司的特定人员是否获取软件：登录到 Microsoft 365 管理中心，转到"用户  >  **活动** 用户"，选择要授予其软件访问权限的用户，然后单击"产品许可证"旁边的"编辑"，然后打开或关闭许可证。</span><span class="sxs-lookup"><span data-stu-id="e797f-120">**To control whether specific people in your company get the software**: Sign in to the Microsoft 365 admin center, go to **Users** > **Active users**, select the person who you want to give access to the software, and then click **Edit** next to **Product licenses** and turn the license on or off.</span></span>
    
    ![选择希望用户访问的软件。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> <span data-ttu-id="e797f-122">如果需要查看为组织人员分配了哪些计划，请登录到管理中心Microsoft 365"用户>  >  **活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="e797f-122">If you need to see what plans are assigned to people in your organization, sign in to the Microsoft 365 admin center > **Users** > **Active users**.</span></span> <span data-ttu-id="e797f-123">从列表中选择人员，然后在"产品许可证 **"下查看**。</span><span class="sxs-lookup"><span data-stu-id="e797f-123">Select the person from the list then look under **Product licenses**.</span></span> <span data-ttu-id="e797f-124">如果使用经典管理中心，请查找"分配的 **许可证"下**。</span><span class="sxs-lookup"><span data-stu-id="e797f-124">If you are using the classic admin center, look under **Assigned license**.</span></span> 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a><span data-ttu-id="e797f-125">手动将Skype for Business部署到用户</span><span class="sxs-lookup"><span data-stu-id="e797f-125">Manually deploying Skype for Business to your users</span></span>
<span data-ttu-id="e797f-126"><a name="bkmk_manual_1"> </a></span><span class="sxs-lookup"><span data-stu-id="e797f-126"><a name="bkmk_manual_1"> </a></span></span>

<span data-ttu-id="e797f-127">如果希望用户从网络Skype for Business位置（而不是从 Internet）安装应用，可以下载安装文件。</span><span class="sxs-lookup"><span data-stu-id="e797f-127">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files.</span></span> <span data-ttu-id="e797f-128">为此，请转到管理中心的"手动部署用户 **Microsoft 365** 部分。</span><span class="sxs-lookup"><span data-stu-id="e797f-128">To do this go to the **Manually deploy user software** section of the Microsoft 365 admin center.</span></span> <span data-ttu-id="e797f-129">然后，可以选择 **"安装** "，将安装程序.exe文件保存到网络位置。</span><span class="sxs-lookup"><span data-stu-id="e797f-129">You can then select **Install** and save the setup .exe file to a network location.</span></span>
  
<span data-ttu-id="e797f-130">另一个选项是Skype for Business基本应用。</span><span class="sxs-lookup"><span data-stu-id="e797f-130">Another option is to download the Skype for Business Basic app for your users.</span></span> <span data-ttu-id="e797f-131">可以下载[Microsoft Skype for Business Basic (32 或 64 位) 。 ](https://www.microsoft.com/download/details.aspx?id=49440)</span><span class="sxs-lookup"><span data-stu-id="e797f-131">You can download [Microsoft Skype for Business Basic (32 or 64 Bit)](https://www.microsoft.com/download/details.aspx?id=49440).</span></span>
  
<span data-ttu-id="e797f-132">对于完整和基本 Skype for Business 应用，下载安装文件后，需要手动发送 (，例如，在电子邮件) 中向用户发送网络路径，以便他们可以运行安装程序以将应用安装到其计算机上。</span><span class="sxs-lookup"><span data-stu-id="e797f-132">For both the full and basic Skype for Business apps, after you have downloaded the setup files, you will need to manually send (for example, in email) the network path to the users so they can run the setup program to install the app on their computer.</span></span>
  
<span data-ttu-id="e797f-133">也可使用这些下载，通过现有的软件部署工具和Skype for Business将应用部署到用户。</span><span class="sxs-lookup"><span data-stu-id="e797f-133">You can also use these downloads to deploy the Skype for Business app to your users by using your existing software deployment tools and processes.</span></span>
  
## <a name="for-larger-and-enterprise-organizations"></a><span data-ttu-id="e797f-134">对于大型和企业组织</span><span class="sxs-lookup"><span data-stu-id="e797f-134">For larger and enterprise organizations</span></span>

> [!NOTE]
> <span data-ttu-id="e797f-135">本部分仅适用于通过Skype for Business计划Office 365应用。</span><span class="sxs-lookup"><span data-stu-id="e797f-135">This section only applies to the Skype for Business app available through Office 365 plans.</span></span> <span data-ttu-id="e797f-136">如果你的组织使用的是 Skype for Business Windows 应用的批量许可版本（基于安装程序的 (MSI) ，请参阅在 Skype for Business Server 中自定义[Windows 客户端安装](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="e797f-136">If your organization is using a volume licensed version of the Skype for Business app, which is Windows Installer-based (MSI), see [Customize Windows client installation in Skype for Business Server](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md).</span></span>
  
<span data-ttu-id="e797f-137">在许多企业或大型组织中，不允许用户在计算机上安装软件。</span><span class="sxs-lookup"><span data-stu-id="e797f-137">In many enterprises or large organizations, users aren't allowed to install software on their computers.</span></span> <span data-ttu-id="e797f-138">相反，IT 部门将必要的软件部署到用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="e797f-138">Instead, the IT departments deploy the necessary software to the users' computers.</span></span> <span data-ttu-id="e797f-139">IT 部门可能还希望控制其组织中使用的 Internet 或网络带宽量，因此他们希望从其网络中附近的位置安装软件，而不是通过 Internet 或公司网络安装软件。</span><span class="sxs-lookup"><span data-stu-id="e797f-139">IT departments also might want to control the amount of Internet or network bandwidth used in their organization, so they want to install software from a nearby location on their network instead of from across the Internet or across the corporate network.</span></span>
  
<span data-ttu-id="e797f-140">使用 Office 365，如果要控制安装应用Skype for Business，可以使用多个选项来部署应用。</span><span class="sxs-lookup"><span data-stu-id="e797f-140">With Office 365, you have several options for deploying the Skype for Business app if you want to control where it's installed from.</span></span> <span data-ttu-id="e797f-141">其中一些选项包括：</span><span class="sxs-lookup"><span data-stu-id="e797f-141">Some of those options include the following:</span></span>
  
- <span data-ttu-id="e797f-142">将Skype for Business应用从 Microsoft 365 管理中心下载到本地网络，如手动将 Skype for Business[部署到用户 中所述](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)。</span><span class="sxs-lookup"><span data-stu-id="e797f-142">Download the Skype for Business app to your local network from the Microsoft 365 admin center, as described in [Manually deploying Skype for Business to your users](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span></span>
    
- <span data-ttu-id="e797f-143">使用 **[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 将 Microsoft 365 企业应用版 或 Skype for Business 应用下载到本地网络。</span><span class="sxs-lookup"><span data-stu-id="e797f-143">Use the **[Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** to download either Microsoft 365 Apps for enterprise or the Skype for Business app to your local network.</span></span> <span data-ttu-id="e797f-144">然后，使用 Office 部署工具将应用部署到用户。</span><span class="sxs-lookup"><span data-stu-id="e797f-144">Then, use the Office Deployment Tool to deploy the app to your users.</span></span> <span data-ttu-id="e797f-145">使用 Office 部署工具可以控制部署的某些方面，例如语言和版本 (32 位或 64 位) 。</span><span class="sxs-lookup"><span data-stu-id="e797f-145">The Office Deployment Tool gives you the ability to control certain aspects of the deployment, such as languages and version (32-bit or 64-bit).</span></span>
    
- <span data-ttu-id="e797f-146">使用现有的软件部署工具和过程（例如 Microsoft Endpoint Configuration Manager）Microsoft 365 企业应用版或 Skype for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e797f-146">Use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy Microsoft 365 Apps for enterprise or the Skype for Business app to your users.</span></span> <span data-ttu-id="e797f-147">可以将现有工具和过程与 Office[部署](https://go.microsoft.com/fwlink/p/?LinkID=626065)工具或从管理中心下载Microsoft 365一起使用。</span><span class="sxs-lookup"><span data-stu-id="e797f-147">You can use your existing tools and processes with the [Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) or with the software that you've downloaded from the Microsoft 365 admin center.</span></span>
    
### <a name="more-info-on-using-the-office-deployment-tool"></a><span data-ttu-id="e797f-148">有关使用 Office 部署工具的信息</span><span class="sxs-lookup"><span data-stu-id="e797f-148">More info on using the Office Deployment Tool</span></span>

<span data-ttu-id="e797f-149">有关下载 Office 部署工具的详细信息以及安装 Skype for Business 应用和其他 Office 365 客户端应用的详细信息，请参阅在 Office 365[中管理软件下载设置](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。</span><span class="sxs-lookup"><span data-stu-id="e797f-149">For details on downloading the Office Deployment Tool and more information on installing the Skype for Business app and other Office 365 client apps, see [Manage software download settings in Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span></span>
  
<span data-ttu-id="e797f-150">下面概述了使用 Office 部署工具部署应用涉及的步骤：</span><span class="sxs-lookup"><span data-stu-id="e797f-150">Here's an overview of the steps involved in using the Office Deployment Tool to deploy an app:</span></span>
  
1. <span data-ttu-id="e797f-151">从 Microsoft **[下载Office](https://www.microsoft.com/download/details.aspx?id=49117)** 下载最新的部署工具。</span><span class="sxs-lookup"><span data-stu-id="e797f-151">**[Download the newest Office Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117)** from the Microsoft Download Center.</span></span>
    
2. <span data-ttu-id="e797f-152">创建用于 Office 部署工具的 configuration.xml 文件，该工具具有想要的客户端应用设置，例如设置 (32 位或 64 位) 版本、安装语言等。</span><span class="sxs-lookup"><span data-stu-id="e797f-152">Create the configuration.xml file to be used with the Office Deployment Tool that has the client app settings you want, such as setting the version (32-bit or 64-bit), the installation language, etc.</span></span>
    
3. <span data-ttu-id="e797f-153">使用 Office 部署工具和 configuration.xml 文件将安装程序文件从本地或内部网络下载到 Office 内容分发网络 (CDN) 。</span><span class="sxs-lookup"><span data-stu-id="e797f-153">Use the Office Deployment Tool and the configuration.xml file to download the setup files to your local or internal network from the Office Content Delivery Network (CDN).</span></span>
    
4. <span data-ttu-id="e797f-154">使用 Office 部署工具和 configuration.xml 安装 Office 客户端应用，包括 Skype for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e797f-154">Use Office Deployment Tool and the configuration.xml to install the Office client apps, including the Skype for Business app.</span></span>
    
<span data-ttu-id="e797f-155">有关使用 Office 部署工具和configuration.xml的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e797f-155">For details on using the Office Deployment Tool and configuration.xml file, see the following articles:</span></span>
  
- [<span data-ttu-id="e797f-156">Office部署工具概述</span><span class="sxs-lookup"><span data-stu-id="e797f-156">Office Deployment Tool overview</span></span>](/deployoffice/overview-office-deployment-tool)
    
- [<span data-ttu-id="e797f-157">Configuration.xml设置</span><span class="sxs-lookup"><span data-stu-id="e797f-157">Configuration.xml settings</span></span>](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="e797f-158">有关使用 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e797f-158">More info on using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="e797f-159">可以使用现有的软件部署工具和进程（例如 Microsoft Endpoint Configuration Manager）来部署 Skype for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e797f-159">You can use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy the Skype for Business app.</span></span> <span data-ttu-id="e797f-160">可以将这些工具和过程与从 Microsoft 365 管理中心下载的软件或 Office 部署工具一起使用。</span><span class="sxs-lookup"><span data-stu-id="e797f-160">You can use these tools and processes with either the software that you download from the Microsoft 365 admin center or with the Office Deployment Tool.</span></span>
  
<span data-ttu-id="e797f-161">有关使用 Configuration Manager 部署软件的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e797f-161">For more information about using Configuration Manager to deploy software, see the following articles:</span></span>
  
- [<span data-ttu-id="e797f-162">在 Configuration Manager 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="e797f-162">Create applications in Configuration Manager</span></span>](/configmgr/apps/deploy-use/create-applications)
    
- [<span data-ttu-id="e797f-163">使用 Configuration Manager 部署应用程序</span><span class="sxs-lookup"><span data-stu-id="e797f-163">Deploy applications with Configuration Manager</span></span>](/configmgr/apps/deploy-use/deploy-applications)
    
<span data-ttu-id="e797f-164">如果在部署应用时Skype for Business部署 Microsoft 365 企业应用版，请参阅使用 Configuration Manager Microsoft 365 企业应用版[管理应用程序](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)。</span><span class="sxs-lookup"><span data-stu-id="e797f-164">If you're deploying the Skype for Business app as part of deploying Microsoft 365 Apps for enterprise, see [Manage Microsoft 365 Apps for enterprise with Configuration Manager](/configmgr/sum/deploy-use/manage-office-365-proplus-updates).</span></span>
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a><span data-ttu-id="e797f-165">计划更新 Skype for Business 应用</span><span class="sxs-lookup"><span data-stu-id="e797f-165">Planning for updates to the Skype for Business app</span></span>

<span data-ttu-id="e797f-166">在部署 Skype for Business 应用时，需要考虑在安装更新后Skype for Business更新。</span><span class="sxs-lookup"><span data-stu-id="e797f-166">As part of deploying the Skype for Business app, you need to consider how you want to get updates after Skype for Business is installed.</span></span> <span data-ttu-id="e797f-167">这些更新可能包括新功能、安全更新或非安全更新，例如提供稳定性或性能改进的更新。</span><span class="sxs-lookup"><span data-stu-id="e797f-167">These updates can include new features, security updates, or non-security updates, such as updates that provide stability or performance improvements.</span></span> <span data-ttu-id="e797f-168">需要考虑的两个主要方面是：</span><span class="sxs-lookup"><span data-stu-id="e797f-168">The two primary things you need to consider are :</span></span>
  
- <span data-ttu-id="e797f-169">希望从何处获取更新</span><span class="sxs-lookup"><span data-stu-id="e797f-169">Where do you want to get updates from</span></span>
    
- <span data-ttu-id="e797f-170">希望获取功能更新多久一次</span><span class="sxs-lookup"><span data-stu-id="e797f-170">How often do you want to get feature updates</span></span>
    
<span data-ttu-id="e797f-171">虽然你可以控制从何处获取更新以及获取功能更新的频繁性，但无法选择获取哪些特定安全更新或非安全更新。</span><span class="sxs-lookup"><span data-stu-id="e797f-171">While you can control where you get updates from and how often you get feature updates, you can't choose which specific security updates or non-security updates you get.</span></span>
  
 <span data-ttu-id="e797f-172">**从何处获取更新**</span><span class="sxs-lookup"><span data-stu-id="e797f-172">**Where to get updates from**</span></span>
  
<span data-ttu-id="e797f-173">默认情况下，安装 Skype for Business应用后，更新会在 Microsoft 提供时自动从 Internet 下载。</span><span class="sxs-lookup"><span data-stu-id="e797f-173">By default, after the Skype for Business app is installed, updates will be automatically downloaded from the Internet when they are available from Microsoft.</span></span> <span data-ttu-id="e797f-174">如果希望对更新发生的时间或安装更新的安装位置进行更多控制，可以使用 Office 部署工具或组策略进行配置。</span><span class="sxs-lookup"><span data-stu-id="e797f-174">If you want more control over when updates occur or where the updates are installed from, you can use the Office Deployment Tool or Group Policy to configure that.</span></span>
  
<span data-ttu-id="e797f-175">例如，许多组织想要在将更新部署到整个组织之前，先与一组用户一起测试更新。</span><span class="sxs-lookup"><span data-stu-id="e797f-175">For example, many organizations want to test updates with a group of users before deploying them throughout the organization.</span></span> <span data-ttu-id="e797f-176">为此，可以使用 Office 部署工具或组策略将 Skype for Business 应用配置为从网络的特定位置获取更新，而不是从 Internet 自动获取更新。</span><span class="sxs-lookup"><span data-stu-id="e797f-176">You can do this by using the Office Deployment Tool or Group Policy to configure the Skype for Business app to get updates from a specific location on your network, instead of automatically from the Internet.</span></span> <span data-ttu-id="e797f-177">然后，可以使用 Office 部署工具每月将更新下载到本地网络。</span><span class="sxs-lookup"><span data-stu-id="e797f-177">Then, you can use the Office Deployment Tool to download the updates every month to your local network.</span></span>
  
<span data-ttu-id="e797f-178">有关更新如何适用于软件Office 365，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e797f-178">For more information about how updates work for Office 365 software, see these articles:</span></span>
  
- [<span data-ttu-id="e797f-179">更新过程概述Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="e797f-179">Overview of the update process for Microsoft 365 Apps for enterprise</span></span>](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [<span data-ttu-id="e797f-180">选择如何管理更新Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="e797f-180">Choose how to manage updates to Microsoft 365 Apps for enterprise</span></span>](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [<span data-ttu-id="e797f-181">配置更新Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="e797f-181">Configure update settings for Microsoft 365 Apps for enterprise</span></span>](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  <span data-ttu-id="e797f-182">**获取功能更新多久一次**</span><span class="sxs-lookup"><span data-stu-id="e797f-182">**How often to get feature updates**</span></span>
  
<span data-ttu-id="e797f-183">除了从何处获取更新外，还可以控制获取新客户端的新功能Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="e797f-183">In addition to where you get updates from, you can also control how often you get new features for the Skype for Business client.</span></span> <span data-ttu-id="e797f-184">两个选项如下：</span><span class="sxs-lookup"><span data-stu-id="e797f-184">The two choices are the following:</span></span>
  
- <span data-ttu-id="e797f-185">如果有新功能，则每月获取功能更新</span><span class="sxs-lookup"><span data-stu-id="e797f-185">Get feature updates every month, if there are new features</span></span>
    
- <span data-ttu-id="e797f-186">每六个月获取一次功能更新</span><span class="sxs-lookup"><span data-stu-id="e797f-186">Get features updates every six months</span></span>
    
<span data-ttu-id="e797f-187">对于一些组织，他们希望有时间来测试新功能，因此他们希望一年只获取两次功能更新，而不是每月获取一次。</span><span class="sxs-lookup"><span data-stu-id="e797f-187">For some organizations, they want time to test new features, so they want to get feature updates only twice a year instead of every month.</span></span>
  
<span data-ttu-id="e797f-188">可以使用部署工具或组策略配置更新Office控制获取功能更新的频繁时间。</span><span class="sxs-lookup"><span data-stu-id="e797f-188">You can control how often you get feature updates by using the Office Deployment Tool or Group Policy to configure the update channel.</span></span> <span data-ttu-id="e797f-189">每月频道每月提供功能更新， (更新) ，Semi-Annual频道每六个月提供一次功能更新。</span><span class="sxs-lookup"><span data-stu-id="e797f-189">The Monthly Channel gives you feature updates monthly (approximately), while the Semi-Annual Channel gives you feature updates every six months.</span></span> <span data-ttu-id="e797f-190">有关频道详细信息，请参阅适用于 Microsoft 365 企业应用版[的更新Microsoft 365 企业应用版。](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)</span><span class="sxs-lookup"><span data-stu-id="e797f-190">For more information about channels, see [Overview of update channels for Microsoft 365 Apps for enterprise](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e797f-191">相关主题</span><span class="sxs-lookup"><span data-stu-id="e797f-191">Related topics</span></span>

[<span data-ttu-id="e797f-192">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e797f-192">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="e797f-193">Skype for Business 和 Microsoft Teams 加载项许可</span><span class="sxs-lookup"><span data-stu-id="e797f-193">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
