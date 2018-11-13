---
title: 业务服务器 Skype 中使用 Office 自定义工具 (OCT)
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 摘要： 如何使用 Office 自定义工具 Skype for Business 客户端。
ms.openlocfilehash: 98b5b663a92c659841a9d98f7fbc476f2908f73c
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295476"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="fc86d-103">业务服务器 Skype 中使用 Office 自定义工具 (OCT)</span><span class="sxs-lookup"><span data-stu-id="fc86d-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="fc86d-104">**摘要：** 如何使用 Office 自定义工具 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="fc86d-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="fc86d-105">Office 自定义工具 (OCT) 是安装程序的一部分，也是完成许多自定义操作的推荐工具。</span><span class="sxs-lookup"><span data-stu-id="fc86d-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="fc86d-106">使用 OCT 可以自定义 Office 并将您的自定义设置保存在安装程序自定义 .msp 文件中。</span><span class="sxs-lookup"><span data-stu-id="fc86d-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="fc86d-107">可将该文件放在网络安装点上的 Updates 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fc86d-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="fc86d-108">在安装 Office 时，安装程序会在 Updates 文件夹中查找安装程序自定义文件，并应用自定义设置。</span><span class="sxs-lookup"><span data-stu-id="fc86d-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="fc86d-109">可在 Updates 文件夹仅将软件更新部署期间初始安装 Office。</span><span class="sxs-lookup"><span data-stu-id="fc86d-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="fc86d-110">OCT 是安装的一部分，仅用于产品的批量许可版本。</span><span class="sxs-lookup"><span data-stu-id="fc86d-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="fc86d-111">通过键入以下内容运行 OCT`setup.exe /admin`中包含 Office 网络安装点的根目录的命令行在源文件。</span><span class="sxs-lookup"><span data-stu-id="fc86d-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="fc86d-112">例如，可使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="fc86d-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="fc86d-113">管理员可以使用 OCT 创建安装程序自定义.msp 文件和可自定义的以下方面：</span><span class="sxs-lookup"><span data-stu-id="fc86d-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="fc86d-114">**安装程序**用来指定客户端和默认单位名称、 其他网络安装源、 产品密钥、 最终用户许可协议的默认安装位置，显示级别、 早期版本的 Office 以删除，请运行过程中的自定义程序安装、 安全设置和安装程序属性。</span><span class="sxs-lookup"><span data-stu-id="fc86d-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="fc86d-115">**功能**用于配置用户设置和自定义 Office 功能的安装方式。</span><span class="sxs-lookup"><span data-stu-id="fc86d-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="fc86d-116">管理员可以使用 OCT 指定用户的 Office 应用程序设置的初始默认值。</span><span class="sxs-lookup"><span data-stu-id="fc86d-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="fc86d-117">用户可以在安装后修改大部分设置。</span><span class="sxs-lookup"><span data-stu-id="fc86d-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="fc86d-118">**其他内容**用于添加或删除文件、 添加或删除注册表项，并配置快捷方式。</span><span class="sxs-lookup"><span data-stu-id="fc86d-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="fc86d-119">**Outlook**用于自定义用户的默认 Outlook 配置文件、 指定 Exchange 设置、 添加帐户、 删除帐户和导出设置，并指定发送 \ 接收组。</span><span class="sxs-lookup"><span data-stu-id="fc86d-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="fc86d-120">有关 OCT 的信息，请参阅[使用 OCT 自定义 Office 2013](https://docs.microsoft.com/en-us/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))。</span><span class="sxs-lookup"><span data-stu-id="fc86d-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/en-us/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="fc86d-121">请注意，此信息也适用于 Office 的更高版本。</span><span class="sxs-lookup"><span data-stu-id="fc86d-121">Note that this information also applies to later versions of Office.</span></span>
  

