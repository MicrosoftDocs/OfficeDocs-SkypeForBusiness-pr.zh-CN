---
title: 为 Skype for Business Server 2015 部署客户端
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要： Skype 业务的企业客户端安装方法概述。
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a><span data-ttu-id="601a2-103">为 Skype for Business Server 2015 部署客户端</span><span class="sxs-lookup"><span data-stu-id="601a2-103">Deploy clients for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="601a2-104">**摘要：**Skype 业务的企业客户端安装方法的概述。</span><span class="sxs-lookup"><span data-stu-id="601a2-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="601a2-105">如何向用户部署 Skype 业务取决于您是否购买 Skype 业务作为 Office 365 计划的一部分或购买业务的 Skype 卷许可的版。</span><span class="sxs-lookup"><span data-stu-id="601a2-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="601a2-106">**365 office**如果您拥有 Office 365 计划，包括业务的 Skype，使用的安装技术称为即点即用。</span><span class="sxs-lookup"><span data-stu-id="601a2-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="601a2-107">与 Office 365 可以让您的用户从 Office 365 提供门户网站自己安装 Skype 业务。</span><span class="sxs-lookup"><span data-stu-id="601a2-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="601a2-108">或者，您可以给您的用户通过将软件下载到您的本地网络并使用现有的软件部署工具，如使用 Microsoft 系统中心配置管理器部署 Skype 业务。</span><span class="sxs-lookup"><span data-stu-id="601a2-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="601a2-109">有关业务所附带 Office 365 的 Skype 的安装信息，请参见[部署 Office 365 中的业务客户端的 Skype](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="601a2-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="601a2-110">**许可的卷**如果您有业务的 Skype 的批量许可版本，则使用的安装技术是 Windows 安装程序 (MSI)。</span><span class="sxs-lookup"><span data-stu-id="601a2-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="601a2-111">一个基于 Windows 安装程序的安装程序包包含多个 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="601a2-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="601a2-112">一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。</span><span class="sxs-lookup"><span data-stu-id="601a2-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="601a2-113">在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。</span><span class="sxs-lookup"><span data-stu-id="601a2-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span>
    
<span data-ttu-id="601a2-114">本节中的主题介绍如何使用和自定义 Windows 安装程序将 Skype 业务客户端部署到您的用户通过您的正常过程。</span><span class="sxs-lookup"><span data-stu-id="601a2-114">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="601a2-115">联机会议外接程序为 Skype 为会议从 Outlook 中的管理的支持消息传递和协作客户端会自动安装与 Skype 业务有关的业务。</span><span class="sxs-lookup"><span data-stu-id="601a2-115">The Online meeting Add-in for Skype for Business, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="601a2-116">Office 365 提供安装程序不会卸载以前版本的 Lync 或 Office Communicator。</span><span class="sxs-lookup"><span data-stu-id="601a2-116">The Office 365 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="601a2-117">业务客户端的 Skype 与其他 Lync 或 Office Communicator 客户端安装并排比较。</span><span class="sxs-lookup"><span data-stu-id="601a2-117">The Skype for Business client installs side-by-side with other Lync or Office Communicator clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="601a2-118">安装 Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="601a2-118">Installing Windows clients</span></span>

- [<span data-ttu-id="601a2-119">自定义 Windows 客户端安装在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="601a2-119">Customize Windows client installation in Skype for Business Server 2015</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="601a2-120">使用 Skype 业务配置的客户端体验</span><span class="sxs-lookup"><span data-stu-id="601a2-120">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="601a2-121">在 Skype 为业务服务器配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="601a2-121">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="601a2-122">安装客户端设备</span><span class="sxs-lookup"><span data-stu-id="601a2-122">Installing device clients</span></span>

- [<span data-ttu-id="601a2-123">安装并测试 Skype 业务为 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="601a2-123">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="601a2-124">安装和测试业务的 Skype 的 iOS</span><span class="sxs-lookup"><span data-stu-id="601a2-124">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="601a2-125">为业务服务器部署在 Skype 的 Skype 的空间系统</span><span class="sxs-lookup"><span data-stu-id="601a2-125">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="601a2-126">部署 Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="601a2-126">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="601a2-127">插件使用 Skype Lync VDI 部署业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="601a2-127">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="601a2-128">为业务服务器 2015年部署在 Skype 的 Web 下载客户端</span><span class="sxs-lookup"><span data-stu-id="601a2-128">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="601a2-129">自定义业务的 Skype 的 Mac 客户端体验</span><span class="sxs-lookup"><span data-stu-id="601a2-129">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="601a2-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="601a2-130">See also</span></span>

#### 

[<span data-ttu-id="601a2-131">Skype 的为您的组织的业务客户端部署</span><span class="sxs-lookup"><span data-stu-id="601a2-131">Deploy the Skype for Business client for your organization</span></span>](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

