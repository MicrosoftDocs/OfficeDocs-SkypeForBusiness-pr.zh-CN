---
title: 自定义 Windows 客户端安装在 Skype 业务服务器 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 摘要： 概述安装方法和 Skype 业务的工具。
ms.openlocfilehash: 8f74f3930e296d8f49eca4bf2a097c88883d7981
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="customize-windows-client-installation-in-skype-for-business-server-2015"></a><span data-ttu-id="07b1d-103">自定义 Windows 客户端安装在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="07b1d-103">Customize Windows client installation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="07b1d-104">**摘要：**安装方法和工具 Skype 业务概述。</span><span class="sxs-lookup"><span data-stu-id="07b1d-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07b1d-105">有关业务所附带 Office 365 的 Skype 的安装信息，请参见[部署 Office 365 中的业务客户端的 Skype](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="07b1d-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="07b1d-106">企业管理员可以自定义使用本节中介绍的方法基于 Windows 安装程序 (.msi) 安装 Skype 业务的批量许可版本。</span><span class="sxs-lookup"><span data-stu-id="07b1d-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="07b1d-107">因为没有单一的工具提供了所有的自定义选项，可能将业务部署在您 Skype 使用这些方法的组合。</span><span class="sxs-lookup"><span data-stu-id="07b1d-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="07b1d-108">您可以使用以下章节中所述的工具：</span><span class="sxs-lookup"><span data-stu-id="07b1d-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="07b1d-109">[使用 Office 自定义工具 (OCT) 业务服务器 2015年的 Skype 在](use-the-office-customization-tool-oct.md)自定义安装选项和功能的 Skype 业务以及其他 Office 程序。</span><span class="sxs-lookup"><span data-stu-id="07b1d-109">[Use the Office Customization Tool (OCT) in Skype for Business Server 2015](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="07b1d-110">[使用类可以执行安装任务的业务服务器 2015 Skype 在](use-config-xml-to-perform-installation-tasks.md)指定网络安装点的路径，并执行静默式安装。</span><span class="sxs-lookup"><span data-stu-id="07b1d-110">[Use Config.xml to perform installation tasks in Skype for Business Server 2015](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="07b1d-111">[在业务服务器 2015年的 Skype 使用安装程序命令行选项](use-setup-command-line-options.md)指定要在安装过程中使用的类文件。</span><span class="sxs-lookup"><span data-stu-id="07b1d-111">[Use Setup command-line options in Skype for Business Server 2015](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="07b1d-112">通过使用组策略对象编辑器 mmc 管理单元[中的业务服务器 2015 Skype 的配置客户端引导策略](configure-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="07b1d-112">[Configure client bootstrapping policies in Skype for Business Server 2015](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="07b1d-113">将可能需要配置在部署 Office 套件产品的其他选项。</span><span class="sxs-lookup"><span data-stu-id="07b1d-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="07b1d-114">本节中的主题提供这些自定义工具的概述并讨论特殊考虑到 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="07b1d-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="07b1d-115">包含的是指向每个工具的详细 Office 帮助的链接。</span><span class="sxs-lookup"><span data-stu-id="07b1d-115">Included are links to detailed Office help for each tool.</span></span> 
  

