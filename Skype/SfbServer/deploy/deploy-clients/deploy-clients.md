---
title: 为 Skype for Business Server 部署客户端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要：适用于 Skype for business 的企业客户端安装方法概述。
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778278"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="1fec2-103">为 Skype for Business Server 部署客户端</span><span class="sxs-lookup"><span data-stu-id="1fec2-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="1fec2-104">**摘要：** Skype for business 的企业客户端安装方法概述。</span><span class="sxs-lookup"><span data-stu-id="1fec2-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="1fec2-105">将 Skype for Business 部署到用户的方式取决于您是在 Office 365 计划中购买的 Skype for Business 还是您购买了 Skype for Business 的批量许可版本。</span><span class="sxs-lookup"><span data-stu-id="1fec2-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="1fec2-106">**Office 365**如果你有包含 Skype for Business 的 Office 365 计划，则使用的安装技术称为即点即用。</span><span class="sxs-lookup"><span data-stu-id="1fec2-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="1fec2-107">使用 Office 365，你可以让你的用户从 Microsoft 365 管理中心为自己安装 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="1fec2-107">With Office 365, you can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="1fec2-108">或者，您可以通过将软件下载到本地网络，然后使用您现有的软件部署工具（如 Microsoft 终结点配置管理器），将 Skype for Business 部署到用户。</span><span class="sxs-lookup"><span data-stu-id="1fec2-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="1fec2-109">有关 Office 365 附带的 Skype for business 安装信息，请参阅[在 office 365 中部署 skype For business 客户端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="1fec2-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="1fec2-110">**批量许可**如果你拥有批量许可版本的 Skype for Business 2015 或2016客户端，则使用的安装技术是 Windows Installer （MSI）。</span><span class="sxs-lookup"><span data-stu-id="1fec2-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="1fec2-111">基于 Windows Installer 的安装包包含多个 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="1fec2-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="1fec2-112">一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。</span><span class="sxs-lookup"><span data-stu-id="1fec2-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="1fec2-113">在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。</span><span class="sxs-lookup"><span data-stu-id="1fec2-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="1fec2-114">Skype for Business 2019 客户端使用即点即用安装程序。</span><span class="sxs-lookup"><span data-stu-id="1fec2-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="1fec2-115">本节中的主题介绍如何使用和自定义 Windows Installer，以通过常规过程将 Skype for Business 客户端部署到用户。</span><span class="sxs-lookup"><span data-stu-id="1fec2-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fec2-116">Microsoft Office 的 Skype 会议外接程序（支持从 Outlook 消息和协作客户端中进行会议管理）通过 Skype for Business 客户端自动安装。</span><span class="sxs-lookup"><span data-stu-id="1fec2-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1fec2-117">Office 365 安装程序不会卸载早期版本的 Lync。</span><span class="sxs-lookup"><span data-stu-id="1fec2-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="1fec2-118">Skype for Business 客户端将与其他 Lync 客户端并行安装。</span><span class="sxs-lookup"><span data-stu-id="1fec2-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="1fec2-119">安装 Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="1fec2-119">Installing Windows clients</span></span>

- [<span data-ttu-id="1fec2-120">在 Skype for Business Server 中自定义 Windows 客户端安装</span><span class="sxs-lookup"><span data-stu-id="1fec2-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="1fec2-121">配置 Skype for Business 的客户端体验</span><span class="sxs-lookup"><span data-stu-id="1fec2-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="1fec2-122">在 Skype for Business Server 中配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="1fec2-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="1fec2-123">安装设备客户端</span><span class="sxs-lookup"><span data-stu-id="1fec2-123">Installing device clients</span></span>

- [<span data-ttu-id="1fec2-124">安装和测试适用于 Windows Phone 的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1fec2-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="1fec2-125">安装和测试适用于 iOS 的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1fec2-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="1fec2-126">使用 Skype for Business Server 部署 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="1fec2-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="1fec2-127">在 Skype for Business Server 中部署 Web 可下载客户端</span><span class="sxs-lookup"><span data-stu-id="1fec2-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="1fec2-128">在 Skype for Business 中自定义 Mac 客户端体验</span><span class="sxs-lookup"><span data-stu-id="1fec2-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="1fec2-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fec2-129">See also</span></span>

[<span data-ttu-id="1fec2-130">在 Office 365 中部署 Skype for Business 客户端</span><span class="sxs-lookup"><span data-stu-id="1fec2-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
