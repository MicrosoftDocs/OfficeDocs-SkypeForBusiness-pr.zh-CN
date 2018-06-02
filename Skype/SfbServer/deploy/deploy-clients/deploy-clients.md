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
description: 摘要： 企业客户端安装方法的 Skype for Business 的概述。
ms.openlocfilehash: 4c1253613befd5bf71add33b7ab9cab826d4a490
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2018
ms.locfileid: "19546467"
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a><span data-ttu-id="13981-103">为 Skype for Business Server 2015 部署客户端</span><span class="sxs-lookup"><span data-stu-id="13981-103">Deploy clients for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="13981-104">**摘要：** Overview of for Business 的 Skype 的企业客户端安装方法。</span><span class="sxs-lookup"><span data-stu-id="13981-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="13981-105">如何向用户部署 for Business 的 Skype 取决于是否购买 Office 365 计划的一部分的业务的 Skype 或购买 for Business 的 Skype 的批量许可的版本。</span><span class="sxs-lookup"><span data-stu-id="13981-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="13981-106">**365 office**如果您有包含 for Business 的 Skype 的 Office 365 计划，使用的安装技术称为单击即点即用。</span><span class="sxs-lookup"><span data-stu-id="13981-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="13981-107">与 Office 365，您可以让您从 Office 365 门户安装自己的 Skype for Business 的用户。</span><span class="sxs-lookup"><span data-stu-id="13981-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="13981-108">或者，您可以通过将软件下载到本地网络，然后使用您现有的软件部署工具，如使用 Microsoft System Center Configuration Manager 向用户部署 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="13981-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="13981-109">有关 Office 365 附带的业务的 Skype 安装信息，请参阅[部署 Office 365 中的商业客户端 Skype](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="13981-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="13981-110">**批量许可**如果您有 for Business 的 Skype 的批量许可版本，使用的安装技术是 Windows Installer (MSI)。</span><span class="sxs-lookup"><span data-stu-id="13981-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="13981-111">基于 Windows Installer 的安装包包含多个 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="13981-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="13981-112">一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。</span><span class="sxs-lookup"><span data-stu-id="13981-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="13981-113">在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。</span><span class="sxs-lookup"><span data-stu-id="13981-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span>
    
<span data-ttu-id="13981-114">本节中的主题介绍如何使用和自定义 Windows Installer 部署到您的用户通过您的常规过程的业务客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="13981-114">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13981-115">联机会议外接程序的业务，支持会议管理的在 Outlook 消息和协作客户端，将自动安装与 for Business 的 Skype 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="13981-115">The Online meeting Add-in for Skype for Business, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="13981-116">Office 365 安装程序不会卸载早期版本的 Lync 或 Office Communicator。</span><span class="sxs-lookup"><span data-stu-id="13981-116">The Office 365 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="13981-117">业务客户端 Skype 与其他 Lync 或 Office Communicator 客户端安装并行。</span><span class="sxs-lookup"><span data-stu-id="13981-117">The Skype for Business client installs side-by-side with other Lync or Office Communicator clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="13981-118">安装 Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="13981-118">Installing Windows clients</span></span>

- [<span data-ttu-id="13981-119">自定义 Windows 客户端安装中 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="13981-119">Customize Windows client installation in Skype for Business Server 2015</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="13981-120">使用 for Business 的 Skype 配置客户端体验</span><span class="sxs-lookup"><span data-stu-id="13981-120">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="13981-121">在 Skype for Business Server 中配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="13981-121">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="13981-122">安装客户端设备</span><span class="sxs-lookup"><span data-stu-id="13981-122">Installing device clients</span></span>

- [<span data-ttu-id="13981-123">安装和测试业务的 Windows Phone Skype</span><span class="sxs-lookup"><span data-stu-id="13981-123">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="13981-124">安装和测试适用于 iOS 的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="13981-124">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="13981-125">为业务服务器部署中 Skype 的 Skype 会议室系统</span><span class="sxs-lookup"><span data-stu-id="13981-125">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="13981-126">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="13981-126">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="13981-127">部署 Lync VDI 插件与 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="13981-127">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="13981-128">部署业务服务器 2015 Skype Web 可下载客户端</span><span class="sxs-lookup"><span data-stu-id="13981-128">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="13981-129">自定义中的业务的 Skype 的 Mac 客户端体验</span><span class="sxs-lookup"><span data-stu-id="13981-129">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="13981-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13981-130">See also</span></span>

[<span data-ttu-id="13981-131">部署 Office 365 中的商业客户端 Skype</span><span class="sxs-lookup"><span data-stu-id="13981-131">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)