---
title: 使用Config.xml Skype for Business 客户端执行安装任务
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 摘要：如何使用 Config.xml文件指定其他安装说明。
ms.openlocfilehash: dbf4c4ba4e652f4b777e0c901fee4ffb0ad68af3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121136"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="5ad67-103">使用Config.xml Skype for Business 客户端执行安装任务</span><span class="sxs-lookup"><span data-stu-id="5ad67-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="5ad67-104">**摘要：** 如何使用 Config.xml 文件指定其他安装说明。</span><span class="sxs-lookup"><span data-stu-id="5ad67-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="5ad67-p101">尽管 Office 自定义工具 (OCT) 是用于自定义安装的主要工具，但管理员可以使用 Config.xml 文件指定在 OCT 中不可用的其他安装说明。下列自定义只能通过 Config.xml 文件来进行：</span><span class="sxs-lookup"><span data-stu-id="5ad67-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="5ad67-107">指定网络安装点的路径。</span><span class="sxs-lookup"><span data-stu-id="5ad67-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="5ad67-108">选择要安装的产品。</span><span class="sxs-lookup"><span data-stu-id="5ad67-108">Select the products to install.</span></span>

- <span data-ttu-id="5ad67-109">配置日志记录和安装程序自定义文件及软件更新的位置。</span><span class="sxs-lookup"><span data-stu-id="5ad67-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="5ad67-110">指定安装选项，如用户名。</span><span class="sxs-lookup"><span data-stu-id="5ad67-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="5ad67-111">无需安装 Office，将本地安装源 (LIS) 复制到用户的计算机上。</span><span class="sxs-lookup"><span data-stu-id="5ad67-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="5ad67-112">在安装中添加或删除语言。</span><span class="sxs-lookup"><span data-stu-id="5ad67-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="5ad67-113">我们建议你使用 Config.xml 文件配置 Skype for Business 无提示安装。</span><span class="sxs-lookup"><span data-stu-id="5ad67-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="5ad67-114">默认情况下，Config.xml核心产品文件夹中存储的文件 (例如\ _product_。WW) 指示安装程序安装该产品。</span><span class="sxs-lookup"><span data-stu-id="5ad67-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="5ad67-115">例如，以下Config.xml中的文件将安装 Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="5ad67-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="5ad67-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="5ad67-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="5ad67-117">下表Config.xml最常用于 Skype for Business 安装的元素。</span><span class="sxs-lookup"><span data-stu-id="5ad67-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="5ad67-118">**Config.xml 元素**</span><span class="sxs-lookup"><span data-stu-id="5ad67-118">**Config.xml elements**</span></span>


| <span data-ttu-id="5ad67-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="5ad67-119">**Element**</span></span>              | <span data-ttu-id="5ad67-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="5ad67-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5ad67-121">配置</span><span class="sxs-lookup"><span data-stu-id="5ad67-121">Configuration</span></span>  <br/>     | <span data-ttu-id="5ad67-122">顶级元素（必需）。</span><span class="sxs-lookup"><span data-stu-id="5ad67-122">Top-level element (required).</span></span> <span data-ttu-id="5ad67-123">包含 Product 属性，例如：Product=Lync (这适用于 Skype for Business 客户端) </span><span class="sxs-lookup"><span data-stu-id="5ad67-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="5ad67-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="5ad67-124">OptionState</span></span>  <br/>       | <span data-ttu-id="5ad67-125">指定在安装期间如何处理特定产品功能。</span><span class="sxs-lookup"><span data-stu-id="5ad67-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="5ad67-126">使用以下属性阻止安装 Business Connectivity Services，其中包括干扰 Outlook 的共享组件：</span><span class="sxs-lookup"><span data-stu-id="5ad67-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="5ad67-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="5ad67-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="5ad67-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="5ad67-128">State="Absent"</span></span> <br/>  <span data-ttu-id="5ad67-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="5ad67-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="5ad67-130">显示</span><span class="sxs-lookup"><span data-stu-id="5ad67-130">Display</span></span>  <br/>           | <span data-ttu-id="5ad67-p105">安装程序向用户显示的 UI 级别。典型属性包括：</span><span class="sxs-lookup"><span data-stu-id="5ad67-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="5ad67-133">CompletionNotice="Yes"</span><span class="sxs-lookup"><span data-stu-id="5ad67-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="5ad67-134">日志记录</span><span class="sxs-lookup"><span data-stu-id="5ad67-134">Logging</span></span>  <br/>           | <span data-ttu-id="5ad67-p106">安装程序执行的日志记录类型的选项。典型属性包括：</span><span class="sxs-lookup"><span data-stu-id="5ad67-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="5ad67-137">Type ="Off"</span><span class="sxs-lookup"><span data-stu-id="5ad67-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="5ad67-138">Setting</span><span class="sxs-lookup"><span data-stu-id="5ad67-138">Setting</span></span>  <br/>           | <span data-ttu-id="5ad67-p107">指定 Windows Installer 属性的值。典型属性包括：</span><span class="sxs-lookup"><span data-stu-id="5ad67-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="5ad67-141">Setting Id=" *name*" (Windows Installer 属性的名称) </span><span class="sxs-lookup"><span data-stu-id="5ad67-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="5ad67-142">Value=" *value*" (要分配给属性属性的值) </span><span class="sxs-lookup"><span data-stu-id="5ad67-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="5ad67-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="5ad67-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="5ad67-p108">从该位置运行安装的网络安装点的完全限定路径。包括 Location 属性：</span><span class="sxs-lookup"><span data-stu-id="5ad67-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="5ad67-146">Location=" *path*"</span><span class="sxs-lookup"><span data-stu-id="5ad67-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="5ad67-147">下面的示例演示 Skype for Business Config.xml典型无提示安装的示例文件。</span><span class="sxs-lookup"><span data-stu-id="5ad67-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="5ad67-148">有关使用 Config.xml 文件执行 Office 安装和维护任务的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) 。</span><span class="sxs-lookup"><span data-stu-id="5ad67-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="5ad67-149">自定义 Config.xml 文件</span><span class="sxs-lookup"><span data-stu-id="5ad67-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="5ad67-150">使用文本编辑器工具（例如记事本）打开 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="5ad67-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="5ad67-151">找到包含您要更改元素的行。</span><span class="sxs-lookup"><span data-stu-id="5ad67-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="5ad67-152">使用您需要的静默选项修改元素项。</span><span class="sxs-lookup"><span data-stu-id="5ad67-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="5ad67-153">请确保删除注释分隔符" \<!--" and "--\> "。</span><span class="sxs-lookup"><span data-stu-id="5ad67-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="5ad67-154">例如，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="5ad67-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="5ad67-155">保存 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="5ad67-155">Save the Config.xml file.</span></span>