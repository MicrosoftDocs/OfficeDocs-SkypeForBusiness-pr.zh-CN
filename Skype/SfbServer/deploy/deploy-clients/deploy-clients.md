---
title: 为业务 Server 部署 Skype 客户的端
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要： 企业客户端安装方法的 Skype for Business 的概述。
ms.openlocfilehash: 7b58b712f5b6dec7383bcb8a58e1b17b0ed4d870
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699279"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="b06fb-103">为业务 Server 部署 Skype 客户的端</span><span class="sxs-lookup"><span data-stu-id="b06fb-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="b06fb-104">**摘要：** Overview of for Business 的 Skype 的企业客户端安装方法。</span><span class="sxs-lookup"><span data-stu-id="b06fb-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="b06fb-105">如何向用户部署 for Business 的 Skype 取决于是否购买 Office 365 计划的一部分的业务的 Skype 或购买 for Business 的 Skype 的批量许可的版本。</span><span class="sxs-lookup"><span data-stu-id="b06fb-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="b06fb-106">**365 office**如果您有包含 for Business 的 Skype 的 Office 365 计划，使用的安装技术称为单击即点即用。</span><span class="sxs-lookup"><span data-stu-id="b06fb-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="b06fb-107">与 Office 365，您可以让您从 Office 365 门户安装自己的 Skype for Business 的用户。</span><span class="sxs-lookup"><span data-stu-id="b06fb-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="b06fb-108">或者，您可以通过将软件下载到本地网络，然后使用您现有的软件部署工具，如使用 Microsoft System Center Configuration Manager 向用户部署 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="b06fb-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="b06fb-109">有关 Office 365 附带的业务的 Skype 安装信息，请参阅[部署 Office 365 中的商业客户端 Skype](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="b06fb-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="b06fb-110">**批量许可**如果您有业务 2015年或 2016年客户端 Skype 的批量许可的版本，使用的安装技术是 Windows Installer (MSI)。</span><span class="sxs-lookup"><span data-stu-id="b06fb-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="b06fb-111">基于 Windows Installer 的安装包包含多个 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="b06fb-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="b06fb-112">一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。</span><span class="sxs-lookup"><span data-stu-id="b06fb-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="b06fb-113">在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。</span><span class="sxs-lookup"><span data-stu-id="b06fb-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="b06fb-114">业务 2019年客户端 Skype 使用单击即点即用安装程序。</span><span class="sxs-lookup"><span data-stu-id="b06fb-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="b06fb-115">本节中的主题介绍如何使用和自定义 Windows Installer 部署到您的用户通过您的常规过程的业务客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="b06fb-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b06fb-116">Skype 会议外接程序 Microsoft Office，支持会议管理的在 Outlook 消息和协作客户端中，将自动安装与 Skype 的业务客户端。</span><span class="sxs-lookup"><span data-stu-id="b06fb-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b06fb-117">Office 365 安装程序不会卸载早期版本的 Lync。</span><span class="sxs-lookup"><span data-stu-id="b06fb-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="b06fb-118">业务客户端 Skype 与其他 Lync 客户端安装并行。</span><span class="sxs-lookup"><span data-stu-id="b06fb-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="b06fb-119">安装 Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="b06fb-119">Installing Windows clients</span></span>

- [<span data-ttu-id="b06fb-120">自定义 Windows 客户端中 Skype 业务服务器安装</span><span class="sxs-lookup"><span data-stu-id="b06fb-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="b06fb-121">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b06fb-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="b06fb-122">在 Skype for Business Server 中配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="b06fb-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="b06fb-123">安装客户端设备</span><span class="sxs-lookup"><span data-stu-id="b06fb-123">Installing device clients</span></span>

- [<span data-ttu-id="b06fb-124">Install and test Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b06fb-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="b06fb-125">Install and test Skype for Business for iOS</span><span class="sxs-lookup"><span data-stu-id="b06fb-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="b06fb-126">在 Skype for Business Server 中部署 Skype 会议室系统</span><span class="sxs-lookup"><span data-stu-id="b06fb-126">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="b06fb-127">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="b06fb-127">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="b06fb-128">部署 Lync VDI 插件与 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="b06fb-128">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="b06fb-129">为业务服务器部署中 Skype Web 可下载的客户端</span><span class="sxs-lookup"><span data-stu-id="b06fb-129">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="b06fb-130">在 Skype for Business 中自定义 Mac 客户端体验</span><span class="sxs-lookup"><span data-stu-id="b06fb-130">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="b06fb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b06fb-131">See also</span></span>

[<span data-ttu-id="b06fb-132">部署 Office 365 中的商业客户端 Skype</span><span class="sxs-lookup"><span data-stu-id="b06fb-132">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)