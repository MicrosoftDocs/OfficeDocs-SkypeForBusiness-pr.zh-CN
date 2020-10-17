---
title: Lync Server 2013：使用 Config.xml 执行安装任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901d95797955c6f545c0d305e2c855829c92addf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535779"
---
# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="c6006-102">使用 Config.xml 在 Lync Server 2013 中执行安装任务</span><span class="sxs-lookup"><span data-stu-id="c6006-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6006-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c6006-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c6006-p101">尽管 Office 自定义工具 (OCT) 是用于自定义安装的主要工具，但管理员可以使用 Config.xml 文件指定在 OCT 中不可用的其他安装说明。下列自定义只能通过 Config.xml 文件来进行：</span><span class="sxs-lookup"><span data-stu-id="c6006-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="c6006-106">指定网络安装点的路径。</span><span class="sxs-lookup"><span data-stu-id="c6006-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="c6006-107">选择要安装的产品。</span><span class="sxs-lookup"><span data-stu-id="c6006-107">Select the products to install.</span></span>

  - <span data-ttu-id="c6006-108">配置日志记录和安装程序自定义文件及软件更新的位置。</span><span class="sxs-lookup"><span data-stu-id="c6006-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="c6006-109">指定安装选项，如用户名。</span><span class="sxs-lookup"><span data-stu-id="c6006-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="c6006-110">无需安装 Office，将本地安装源 (LIS) 复制到用户的计算机上。</span><span class="sxs-lookup"><span data-stu-id="c6006-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="c6006-111">在安装中添加或删除语言。</span><span class="sxs-lookup"><span data-stu-id="c6006-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="c6006-112">建议使用 Config.xml 文件配置 Lync 2013 无提示安装。</span><span class="sxs-lookup"><span data-stu-id="c6006-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="c6006-113">默认情况下，存储在核心产品文件夹中的 Config.xml 文件 (例如 \\ product。WW) 指导安装程序安装该产品。</span><span class="sxs-lookup"><span data-stu-id="c6006-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="c6006-114">例如，以下文件夹中的 Config.xml 文件将安装 Lync 2013：</span><span class="sxs-lookup"><span data-stu-id="c6006-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="c6006-115">\\\\服务器 \\ 共享 \\ Lync15 \\ Lync \\Config.xml</span><span class="sxs-lookup"><span data-stu-id="c6006-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="c6006-116">下表列出了 Lync 2013 安装最常使用的 Config.xml 元素。</span><span class="sxs-lookup"><span data-stu-id="c6006-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="c6006-117">Config.xml 元素</span><span class="sxs-lookup"><span data-stu-id="c6006-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6006-118">元素</span><span class="sxs-lookup"><span data-stu-id="c6006-118">Element</span></span></th>
<th><span data-ttu-id="c6006-119">说明</span><span class="sxs-lookup"><span data-stu-id="c6006-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6006-120">Configuration</span><span class="sxs-lookup"><span data-stu-id="c6006-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="c6006-p103">顶级元素（必需）。包含 Product 属性，例如：Product=Lync</span><span class="sxs-lookup"><span data-stu-id="c6006-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6006-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="c6006-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="c6006-124">指定在安装期间如何处理特定产品功能。</span><span class="sxs-lookup"><span data-stu-id="c6006-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="c6006-125">使用以下属性可阻止安装 Business Connectivity Services，其中包括干扰 Outlook 2010 的共享组件：</span><span class="sxs-lookup"><span data-stu-id="c6006-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6006-126">Id = &quot; LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="c6006-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="c6006-127">State = &quot; 缺少&quot;</span><span class="sxs-lookup"><span data-stu-id="c6006-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="c6006-128">子级 = &quot; 强制&quot;</span><span class="sxs-lookup"><span data-stu-id="c6006-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6006-129">显示</span><span class="sxs-lookup"><span data-stu-id="c6006-129">Display</span></span></p></td>
<td><p><span data-ttu-id="c6006-p105">安装程序向用户显示的 UI 级别。典型属性包括：</span><span class="sxs-lookup"><span data-stu-id="c6006-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6006-132">CompletionNotice = &quot; Yes &quot;  |  &quot; &quot; (不默认值) </span><span class="sxs-lookup"><span data-stu-id="c6006-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="c6006-133">AcceptEula = &quot; Yes &quot;  |  &quot; &quot; (不默认值) </span><span class="sxs-lookup"><span data-stu-id="c6006-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6006-134">日志记录</span><span class="sxs-lookup"><span data-stu-id="c6006-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="c6006-p106">安装程序执行的日志记录类型的选项。典型属性包括：</span><span class="sxs-lookup"><span data-stu-id="c6006-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6006-137">键入 = &quot; Off &quot;  |  &quot; Standard &quot; (默认) | &quot;冗长&quot;</span><span class="sxs-lookup"><span data-stu-id="c6006-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="c6006-138">Template=”filename.txt”（日志文件的名称）</span><span class="sxs-lookup"><span data-stu-id="c6006-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6006-139">设置</span><span class="sxs-lookup"><span data-stu-id="c6006-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="c6006-p107">指定 Windows Installer 属性的值。典型属性包括：</span><span class="sxs-lookup"><span data-stu-id="c6006-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6006-142">设置 Id = &quot; &quot; (Windows Installer 属性名称的名称) </span><span class="sxs-lookup"><span data-stu-id="c6006-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="c6006-143">Value = &quot; value &quot; (要分配给属性的值) </span><span class="sxs-lookup"><span data-stu-id="c6006-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6006-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="c6006-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="c6006-p108">从该位置运行安装的网络安装点的完全限定路径。包括 Location 属性：</span><span class="sxs-lookup"><span data-stu-id="c6006-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6006-147">Location = "path"</span><span class="sxs-lookup"><span data-stu-id="c6006-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6006-148">下面的示例演示了 Lync 2013 典型无提示安装的 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="c6006-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="c6006-149">有关使用 Config.xml 文件执行 Office 安装和维护任务的详细信息，请访问 <https://go.microsoft.com/fwlink/p/?linkid=267514> 。</span><span class="sxs-lookup"><span data-stu-id="c6006-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="c6006-150">自定义 Config.xml 文件</span><span class="sxs-lookup"><span data-stu-id="c6006-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="c6006-151">使用文本编辑器工具（例如记事本）打开 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="c6006-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="c6006-152">找到包含您要更改元素的行。</span><span class="sxs-lookup"><span data-stu-id="c6006-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="c6006-153">使用您需要的静默选项修改元素项。</span><span class="sxs-lookup"><span data-stu-id="c6006-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="c6006-154">请务必删除注释分隔符 " \<\!--" and "--\> "。</span><span class="sxs-lookup"><span data-stu-id="c6006-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="c6006-155">例如，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c6006-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="c6006-156">保存 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="c6006-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

