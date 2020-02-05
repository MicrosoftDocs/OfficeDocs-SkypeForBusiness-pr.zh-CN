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
description: 摘要： Skype for business 的企业客户端安装方法概述。
ms.openlocfilehash: 0e7859fe207ed80aa7dceef794aa57d15cc0c79b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768725"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="3bd6f-103">为 Skype for Business Server 部署客户端</span><span class="sxs-lookup"><span data-stu-id="3bd6f-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="3bd6f-104">**摘要：** Skype for business 的企业客户端安装方法概述。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="3bd6f-105">如何将 Skype for business 部署到你的用户取决于你是在 Office 365 计划中购买的 Skype for business 还是你购买了批量许可版本的 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="3bd6f-106">**Office 365**如果您有包含 Skype for Business 的 Office 365 计划，则使用的安装技术称为即点即用。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="3bd6f-107">通过 Office 365，你可以让你的用户从 Office 365 门户为自己安装 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="3bd6f-108">或者，你可以通过将软件下载到本地网络，然后使用现有软件部署工具（如 Microsoft 终结点配置管理器），将 Skype for business 部署到你的用户。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="3bd6f-109">有关 Office 365 附带的 Skype for business 的安装信息，请参阅[在 office 365 中部署 skype for business 客户端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="3bd6f-110">**批量许可**如果你拥有 Skype for Business 2015 或2016客户端的批量许可版本，则使用的安装技术是 Windows Installer （MSI）。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="3bd6f-111">基于 Windows Installer 的安装程序包由多个 MSI 文件组成。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="3bd6f-112">一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="3bd6f-113">在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="3bd6f-114">Skype for Business 2019 客户端使用即点即用安装程序。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="3bd6f-115">本部分中的主题介绍如何使用和自定义 Windows 安装程序，以便通过常规过程将 Skype for Business 客户端部署到用户。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bd6f-116">用于 Microsoft Office 的 Skype 会议加载项（支持来自 Outlook 消息和协作客户端的会议管理）将自动与 Skype for Business 客户端一起安装。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3bd6f-117">Office 365 安装程序不会卸载以前版本的 Lync。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="3bd6f-118">Skype for Business 客户端与其他 Lync 客户端并排安装。</span><span class="sxs-lookup"><span data-stu-id="3bd6f-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="3bd6f-119">安装 Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="3bd6f-119">Installing Windows clients</span></span>

- [<span data-ttu-id="3bd6f-120">在 Skype for Business 服务器中自定义 Windows 客户端安装</span><span class="sxs-lookup"><span data-stu-id="3bd6f-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="3bd6f-121">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3bd6f-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="3bd6f-122">在 Skype for Business Server 中配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="3bd6f-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="3bd6f-123">安装设备客户端</span><span class="sxs-lookup"><span data-stu-id="3bd6f-123">Installing device clients</span></span>

- [<span data-ttu-id="3bd6f-124">Install and test Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="3bd6f-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="3bd6f-125">Install and test Skype for Business for iOS</span><span class="sxs-lookup"><span data-stu-id="3bd6f-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="3bd6f-126">通过 Skype for Business 服务器部署 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="3bd6f-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="3bd6f-127">在 Skype for Business 服务器中部署 Web 可下载的客户端</span><span class="sxs-lookup"><span data-stu-id="3bd6f-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="3bd6f-128">在 Skype for Business 中自定义 Mac 客户端体验</span><span class="sxs-lookup"><span data-stu-id="3bd6f-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="3bd6f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bd6f-129">See also</span></span>

[<span data-ttu-id="3bd6f-130">在 Office 365 中部署 Skype for Business 客户端</span><span class="sxs-lookup"><span data-stu-id="3bd6f-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
