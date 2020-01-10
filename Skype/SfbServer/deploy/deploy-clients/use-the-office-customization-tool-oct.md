---
title: 在 Skype for Business 服务器中使用 Office 自定义工具（OCT）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 摘要：如何将 Office 自定义工具与 Skype for Business 客户端配合使用。
ms.openlocfilehash: b5c66fee4f6c879c8ded2897b64e63654dd950be
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001592"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="c5916-103">在 Skype for Business 服务器中使用 Office 自定义工具（OCT）</span><span class="sxs-lookup"><span data-stu-id="c5916-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="c5916-104">**摘要：** 如何将 Office 自定义工具与 Skype for Business 客户端配合使用。</span><span class="sxs-lookup"><span data-stu-id="c5916-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="c5916-105">Office 自定义工具 (OCT) 是安装程序的一部分，也是完成许多自定义操作的推荐工具。</span><span class="sxs-lookup"><span data-stu-id="c5916-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="c5916-106">使用 OCT 可以自定义 Office 并将您的自定义设置保存在安装程序自定义 .msp 文件中。</span><span class="sxs-lookup"><span data-stu-id="c5916-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="c5916-107">可将该文件放在网络安装点上的 Updates 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c5916-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="c5916-108">在安装 Office 时，安装程序会在 Updates 文件夹中查找安装程序自定义文件，并应用自定义设置。</span><span class="sxs-lookup"><span data-stu-id="c5916-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="c5916-109">"更新" 文件夹仅可用于在 Office 的初始安装期间部署软件更新。</span><span class="sxs-lookup"><span data-stu-id="c5916-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="c5916-110">OCT 是设置的一部分，它仅用于批量许可的产品版本。</span><span class="sxs-lookup"><span data-stu-id="c5916-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="c5916-111">通过从包含 Office 源文件的`setup.exe /admin`网络安装点的根处键入命令行来运行 OCT。</span><span class="sxs-lookup"><span data-stu-id="c5916-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="c5916-112">例如，可使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="c5916-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="c5916-113">管理员使用 OCT 创建安装程序自定义 .msp 文件，并可自定义以下区域：</span><span class="sxs-lookup"><span data-stu-id="c5916-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="c5916-114">**设置**用于指定客户端的默认安装位置和默认组织名称、其他网络安装源、产品密钥、最终用户许可协议、显示级别、早期版本的 Office 以删除、在安装期间运行的自定义程序、安全设置和设置属性。</span><span class="sxs-lookup"><span data-stu-id="c5916-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="c5916-115">**功能**用于配置用户设置和自定义 Office 功能的安装方式。</span><span class="sxs-lookup"><span data-stu-id="c5916-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="c5916-116">管理员可以使用 OCT 指定用户的 Office 应用程序设置的初始默认值。</span><span class="sxs-lookup"><span data-stu-id="c5916-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="c5916-117">安装后，用户可以修改大多数设置。</span><span class="sxs-lookup"><span data-stu-id="c5916-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="c5916-118">**其他内容**用于添加或删除文件、添加或删除注册表项以及配置快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c5916-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="c5916-119">**Outlook**用于自定义用户的默认 Outlook 配置文件、指定 Exchange 设置、添加帐户、删除帐户和导出设置，以及指定 Send\Receive 组。</span><span class="sxs-lookup"><span data-stu-id="c5916-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="c5916-120">有关 OCT 的详细信息，请参阅[使用 OCT 自定义 Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))。</span><span class="sxs-lookup"><span data-stu-id="c5916-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="c5916-121">请注意，此信息也适用于 Office 的更高版本。</span><span class="sxs-lookup"><span data-stu-id="c5916-121">Note that this information also applies to later versions of Office.</span></span>
  

