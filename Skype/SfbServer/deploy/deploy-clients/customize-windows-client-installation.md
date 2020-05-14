---
title: 在 Skype for Business Server 中自定义 Windows 客户端安装
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 摘要：适用于 Skype for business 的安装方法和工具的概述。
ms.openlocfilehash: ea8a07bf6a6e00eee93f2a0a8b3ffc756b239ce9
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220832"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="eddb2-103">在 Skype for Business Server 中自定义 Windows 客户端安装</span><span class="sxs-lookup"><span data-stu-id="eddb2-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="eddb2-104">**摘要：** Skype for business 的安装方法和工具概述。</span><span class="sxs-lookup"><span data-stu-id="eddb2-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eddb2-105">有关 Microsoft 365 和 Office 365 附带的 Skype for business 的安装信息，请参阅[在 microsoft 365 或 office 365 中部署 skype For business 客户端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="eddb2-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="eddb2-106">企业管理员可以使用本节中讨论的方法来自定义 Skype for Business 的批量许可版本的基于 Windows Installer （.msi）的安装。</span><span class="sxs-lookup"><span data-stu-id="eddb2-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="eddb2-107">由于没有一个工具提供所有自定义选项，因此您可能在 Skype for Business 部署中使用这些方法的组合。</span><span class="sxs-lookup"><span data-stu-id="eddb2-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="eddb2-108">您可以使用以下各节中介绍的工具：</span><span class="sxs-lookup"><span data-stu-id="eddb2-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="eddb2-109">[在 skype For Business Server 中使用 Office 自定义工具（OCT）](use-the-office-customization-tool-oct.md)自定义 Skype for business 和其他 Office 程序的安装选项和功能。</span><span class="sxs-lookup"><span data-stu-id="eddb2-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="eddb2-110">[使用 config.xml 在 Skype For Business Server 中执行安装任务](use-config-xml-to-perform-installation-tasks.md)，以指定网络安装点的路径并执行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="eddb2-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="eddb2-111">[使用 Skype For Business Server 中的安装程序命令行选项](use-setup-command-line-options.md)指定要在安装过程中使用的 config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="eddb2-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="eddb2-112">使用组策略对象编辑器 MMC 管理单元在[Skype For Business Server 中配置客户端引导策略](configure-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="eddb2-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="eddb2-113">在部署 Office 产品套件时，可能需要配置其他选项。</span><span class="sxs-lookup"><span data-stu-id="eddb2-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="eddb2-114">本节中的主题提供了这些自定义工具的概述，并讨论了特定于 Skype for business 的注意事项。</span><span class="sxs-lookup"><span data-stu-id="eddb2-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="eddb2-115">包含的是指向每个工具的详细 Office 帮助的链接。</span><span class="sxs-lookup"><span data-stu-id="eddb2-115">Included are links to detailed Office help for each tool.</span></span> 
  

