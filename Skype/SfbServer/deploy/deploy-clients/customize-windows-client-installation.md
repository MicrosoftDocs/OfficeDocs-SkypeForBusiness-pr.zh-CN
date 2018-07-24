---
title: 自定义 Windows 客户端中 Skype 业务服务器安装
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 摘要： 概述安装方法和 Skype for Business 的工具。
ms.openlocfilehash: e5d575e7a1efc54ade19d76575f3d5ec2937de62
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009170"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="e3141-103">自定义 Windows 客户端中 Skype 业务服务器安装</span><span class="sxs-lookup"><span data-stu-id="e3141-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="e3141-104">**摘要：** 安装方法和工具的 Skype for Business 概述。</span><span class="sxs-lookup"><span data-stu-id="e3141-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3141-105">有关 Office 365 附带的业务的 Skype 安装信息，请参阅[部署 Office 365 中的商业客户端 Skype](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="e3141-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="e3141-106">企业管理员可以使用本节中讨论的方法自定义基于 Windows Installer (.msi) 安装的 Skype for Business 的批量许可版本。</span><span class="sxs-lookup"><span data-stu-id="e3141-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="e3141-107">因为没有单个工具提供了所有自定义选项，您将业务部署，在您 Skype 中可能使用这些方法的组合。</span><span class="sxs-lookup"><span data-stu-id="e3141-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="e3141-108">您可以使用以下章节中所述的工具：</span><span class="sxs-lookup"><span data-stu-id="e3141-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="e3141-109">[使用 Office 自定义工具 (OCT) 中的业务服务器 Skype](use-the-office-customization-tool-oct.md)自定义安装程序选项和功能的 Skype 业务和其他 Office 程序。</span><span class="sxs-lookup"><span data-stu-id="e3141-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="e3141-110">[使用 Config.xml 执行安装任务 Skype 业务服务器中的](use-config-xml-to-perform-installation-tasks.md)，指定网络安装点的路径并执行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="e3141-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="e3141-111">[Skype 业务服务器中的使用 Setup command-line options](use-setup-command-line-options.md)指定要在安装过程中使用的 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="e3141-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="e3141-112">使用组策略对象编辑器 mmc 管理单元[中的业务服务器 Skype 的配置客户端引导策略](configure-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e3141-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="e3141-113">可能将您需要配置的产品的 Office 套件部署时其他的选项。</span><span class="sxs-lookup"><span data-stu-id="e3141-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="e3141-114">本节中的主题概要介绍这些自定义工具，并讨论特定到 Skype 的注意事项业务。</span><span class="sxs-lookup"><span data-stu-id="e3141-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="e3141-115">包含的是指向每个工具的详细 Office 帮助的链接。</span><span class="sxs-lookup"><span data-stu-id="e3141-115">Included are links to detailed Office help for each tool.</span></span> 
  

