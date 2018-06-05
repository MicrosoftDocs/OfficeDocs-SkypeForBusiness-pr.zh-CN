---
title: 在 Skype for Business Server 2015 中使用 Config.xml 执行安装任务
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 摘要： 如何使用 Config.xml 文件来指定其他安装说明。
ms.openlocfilehash: 4e3c27aab3e821f7dcd621e40fd4339e4db2b985
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568554"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-server-2015"></a><span data-ttu-id="5aa78-103">在 Skype for Business Server 2015 中使用 Config.xml 执行安装任务</span><span class="sxs-lookup"><span data-stu-id="5aa78-103">Use Config.xml to perform installation tasks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5aa78-104">**摘要：** 如何使用 Config.xml 文件指定附加安装说明。</span><span class="sxs-lookup"><span data-stu-id="5aa78-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>
  
<span data-ttu-id="5aa78-p101">尽管 Office 自定义工具 (OCT) 是用于自定义安装的主要工具，但管理员可以使用 Config.xml 文件指定在 OCT 中不可用的其他安装说明。下列自定义只能通过 Config.xml 文件来进行：</span><span class="sxs-lookup"><span data-stu-id="5aa78-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>
  
- <span data-ttu-id="5aa78-107">指定网络安装点的路径。</span><span class="sxs-lookup"><span data-stu-id="5aa78-107">Specify the path of the network installation point.</span></span>
    
- <span data-ttu-id="5aa78-108">选择要安装的产品。</span><span class="sxs-lookup"><span data-stu-id="5aa78-108">Select the products to install.</span></span>
    
- <span data-ttu-id="5aa78-109">配置日志记录和安装程序自定义文件及软件更新的位置。</span><span class="sxs-lookup"><span data-stu-id="5aa78-109">Configure logging and the location of the Setup customization file and software updates.</span></span>
    
- <span data-ttu-id="5aa78-110">指定安装选项，如用户名。</span><span class="sxs-lookup"><span data-stu-id="5aa78-110">Specify installation options, such as user name.</span></span>
    
- <span data-ttu-id="5aa78-111">无需安装 Office，将本地安装源 (LIS) 复制到用户的计算机上。</span><span class="sxs-lookup"><span data-stu-id="5aa78-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>
    
- <span data-ttu-id="5aa78-112">在安装中添加语言或从安装中删除语言。</span><span class="sxs-lookup"><span data-stu-id="5aa78-112">Add or remove languages from the installation.</span></span>
    
<span data-ttu-id="5aa78-113">我们建议使用 Config.xml 文件配置 Skype 的业务无提示安装。</span><span class="sxs-lookup"><span data-stu-id="5aa78-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 
  
<span data-ttu-id="5aa78-114">默认情况下，存储在核心产品文件夹中的 Config.xml 文件 (例如，\_产品_。WW) 指示安装程序来安装该产品。</span><span class="sxs-lookup"><span data-stu-id="5aa78-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="5aa78-115">例如，以下文件夹中的 Config.xml 文件安装 for Business 的 Skype:</span><span class="sxs-lookup"><span data-stu-id="5aa78-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>
  
- <span data-ttu-id="5aa78-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="5aa78-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>
    
<span data-ttu-id="5aa78-117">下表中列出的最常用的 Skype 业务安装的 Config.xml 元素。</span><span class="sxs-lookup"><span data-stu-id="5aa78-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>
  
<span data-ttu-id="5aa78-118">**Config.xml 元素**</span><span class="sxs-lookup"><span data-stu-id="5aa78-118">**Config.xml elements**</span></span>

|<span data-ttu-id="5aa78-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="5aa78-119">**Element**</span></span>|<span data-ttu-id="5aa78-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="5aa78-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5aa78-121">配置</span><span class="sxs-lookup"><span data-stu-id="5aa78-121">Configuration</span></span>  <br/> |<span data-ttu-id="5aa78-p103">顶级元素（必需）。包含 Product 属性，例如：Product=Lync（这适用于 Skype for Business 客户端）</span><span class="sxs-lookup"><span data-stu-id="5aa78-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/> |
|<span data-ttu-id="5aa78-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="5aa78-124">OptionState</span></span>  <br/> | <span data-ttu-id="5aa78-125">指定在安装期间如何处理特定产品功能。</span><span class="sxs-lookup"><span data-stu-id="5aa78-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="5aa78-126">使用以下属性来防止安装 Business Connectivity Services，其中包括 Outlook 2016 会干扰的共享的组件：</span><span class="sxs-lookup"><span data-stu-id="5aa78-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2016:</span></span> <br/>  <span data-ttu-id="5aa78-127">Id ="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="5aa78-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="5aa78-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="5aa78-128">State="Absent"</span></span> <br/>  <span data-ttu-id="5aa78-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="5aa78-129">Children="Force"</span></span> <br/> |
|<span data-ttu-id="5aa78-130">Display</span><span class="sxs-lookup"><span data-stu-id="5aa78-130">Display</span></span>  <br/> | <span data-ttu-id="5aa78-p105">安装程序向用户显示的 UI 级别。典型属性包括：</span><span class="sxs-lookup"><span data-stu-id="5aa78-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="5aa78-133">CompletionNotice ="Yes"</span><span class="sxs-lookup"><span data-stu-id="5aa78-133">CompletionNotice="Yes"</span></span> | <span data-ttu-id="5aa78-134">"No"(default)</span><span class="sxs-lookup"><span data-stu-id="5aa78-134">"No"(default)</span></span> <br/>  <span data-ttu-id="5aa78-135">AcceptEula ="Yes"</span><span class="sxs-lookup"><span data-stu-id="5aa78-135">AcceptEula="Yes"</span></span> | <span data-ttu-id="5aa78-136">"No"(default)</span><span class="sxs-lookup"><span data-stu-id="5aa78-136">"No"(default)</span></span> <br/> |
|<span data-ttu-id="5aa78-137">日志记录</span><span class="sxs-lookup"><span data-stu-id="5aa78-137">Logging</span></span>  <br/> | <span data-ttu-id="5aa78-p106">安装程序执行的日志记录类型的选项。典型属性包括：</span><span class="sxs-lookup"><span data-stu-id="5aa78-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="5aa78-140">类型 ="Off"</span><span class="sxs-lookup"><span data-stu-id="5aa78-140">Type ="Off"</span></span> | <span data-ttu-id="5aa78-141">"Standard"(default)</span><span class="sxs-lookup"><span data-stu-id="5aa78-141">"Standard"(default)</span></span> | <span data-ttu-id="5aa78-142">"Verbose"</span><span class="sxs-lookup"><span data-stu-id="5aa78-142">"Verbose"</span></span> <br/>  <span data-ttu-id="5aa78-143">模板 =" _filename_.txt"（日志文件的名称）</span><span class="sxs-lookup"><span data-stu-id="5aa78-143">Template=" _filename_.txt" (the name of the log file)</span></span>  <br/> |
|<span data-ttu-id="5aa78-144">设置</span><span class="sxs-lookup"><span data-stu-id="5aa78-144">Setting</span></span>  <br/> | <span data-ttu-id="5aa78-p107">指定 Windows Installer 属性的值。典型属性包括：</span><span class="sxs-lookup"><span data-stu-id="5aa78-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="5aa78-147">Setting Id =" _name_"（Windows Installer 属性的名称）</span><span class="sxs-lookup"><span data-stu-id="5aa78-147">Setting Id=" _name_" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="5aa78-148">值 ="_值_"（要分配给属性的值）</span><span class="sxs-lookup"><span data-stu-id="5aa78-148">Value=" _value_" (the value to assign to the property)</span></span>  <br/> |
|<span data-ttu-id="5aa78-149">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="5aa78-149">DistributionPoint</span></span>  <br/> | <span data-ttu-id="5aa78-p108">从该位置运行安装的网络安装点的完全限定路径。包括 Location 属性：</span><span class="sxs-lookup"><span data-stu-id="5aa78-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="5aa78-152">位置 ="_路径_"</span><span class="sxs-lookup"><span data-stu-id="5aa78-152">Location=" _path_"</span></span>  <br/> |
   
<span data-ttu-id="5aa78-153">下面的示例演示 for Business 的 Skype 的典型无提示安装的 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="5aa78-153">The following example shows a Config.xml file for a typical silent installation of Skype for Business.</span></span> 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="5aa78-154">有关使用 Config.xml 文件执行 Office 安装和维护任务的详细的信息，请在[https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)。</span><span class="sxs-lookup"><span data-stu-id="5aa78-154">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>
  
## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="5aa78-155">自定义 Config.xml 文件</span><span class="sxs-lookup"><span data-stu-id="5aa78-155">To customize the Config.xml file</span></span>

1. <span data-ttu-id="5aa78-156">使用文本编辑器工具（例如记事本）打开 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="5aa78-156">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>
    
2. <span data-ttu-id="5aa78-157">找到包含您要更改元素的行。</span><span class="sxs-lookup"><span data-stu-id="5aa78-157">Locate the lines that contain the elements you want to change.</span></span>
    
3. <span data-ttu-id="5aa78-158">使用您需要的静默选项修改元素项。</span><span class="sxs-lookup"><span data-stu-id="5aa78-158">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="5aa78-159">请确保您删除注释分隔符，"\<！-"和"-\>"。</span><span class="sxs-lookup"><span data-stu-id="5aa78-159">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="5aa78-160">例如，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="5aa78-160">For example, use the following syntax:</span></span>
    
  <pre>
  < DistributionPoint Location="\\server\share\Skype15" />
  </pre>

4. <span data-ttu-id="5aa78-161">保存 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="5aa78-161">Save the Config.xml file.</span></span>
    

