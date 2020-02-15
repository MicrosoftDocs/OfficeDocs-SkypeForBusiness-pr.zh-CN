---
title: Lync Server 2013：准备 Active Directory 架构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d98f7ba4ac0f2efe8a78ebcaacdc966ac5fdf3a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="42e57-102">在 Lync Server 2013 中准备 Active Directory 架构</span><span class="sxs-lookup"><span data-stu-id="42e57-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42e57-103">_**上次修改的主题：** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="42e57-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="42e57-104">在开始准备 Active Directory 域服务之前，可以使用文本编辑器（如 Windows 记事本）打开架构文件，或者查看[Lync server 2013 使用的 Active directory 架构扩展、类和属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)，以检查将为 Lync server 2013 修改的所有 Active Directory 域服务架构扩展。</span><span class="sxs-lookup"><span data-stu-id="42e57-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="42e57-105">Lync Server 使用四个架构文件：</span><span class="sxs-lookup"><span data-stu-id="42e57-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="42e57-106">ExternalSchema 用于与 Microsoft Exchange Server 的互操作性</span><span class="sxs-lookup"><span data-stu-id="42e57-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="42e57-107">ServerSchema，它是主 Lync Server 2013 架构文件</span><span class="sxs-lookup"><span data-stu-id="42e57-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="42e57-108">BackCompatSchema.ldf，用于实现与以前版本中任何组件的互操作性</span><span class="sxs-lookup"><span data-stu-id="42e57-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="42e57-109">VersionSchema.ldf，用于所准备架构的版本信息</span><span class="sxs-lookup"><span data-stu-id="42e57-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="42e57-110">所有 .ldf 文件都是在架构准备期间安装的，无论是从以前的版本中进行迁移还是执行全新安装。</span><span class="sxs-lookup"><span data-stu-id="42e57-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="42e57-111">这些架构文件按上列表中显示的顺序安装，位于安装媒体上的 " \\支持\\架构" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="42e57-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="42e57-112">Lync Server 架构扩展在所有域之间进行复制，这会影响网络流量。</span><span class="sxs-lookup"><span data-stu-id="42e57-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="42e57-113">请在网络利用率较低时运行架构准备。</span><span class="sxs-lookup"><span data-stu-id="42e57-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42e57-114">如果需要将 Microsoft® Office Communicator Mobile 2007 R2 for Java 和 Microsoft® Office Communicator Mobile for Nokia 1.0 移动客户端添加到 Lync Server 2013 部署的支持，您需要为 Microsoft Office 准备 Active Directory 架构在安装 Lync Server 2013 期间通信服务器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="42e57-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="42e57-115">有关必需的软件和文档，请<A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>参阅。</span><span class="sxs-lookup"><span data-stu-id="42e57-115">For the necessary software and documentation, see <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="42e57-116">ADSI Edit</span><span class="sxs-lookup"><span data-stu-id="42e57-116">ADSI Edit</span></span>

<span data-ttu-id="42e57-117">Active Directory Service Interfaces Editor (ADSI Edit) 是一个 AD DS 管理工具，可以用来验证架构准备和复制。</span><span class="sxs-lookup"><span data-stu-id="42e57-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="42e57-118">安装 AD DS 角色以使服务器成为域控制器时，会默认安装 ADSI Edit。</span><span class="sxs-lookup"><span data-stu-id="42e57-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="42e57-119">对于 Windows Server 2008 和 Windows Server 2008 R2，ADSI 编辑（adsiedit）包含在远程服务器管理工具（RSAT）中。</span><span class="sxs-lookup"><span data-stu-id="42e57-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="42e57-120">还可以在域成员服务器或独立服务器上安装 RSAT。</span><span class="sxs-lookup"><span data-stu-id="42e57-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="42e57-121">默认情况下，RSAT 包会在安装 Windows 时复制到这些服务器，但默认情况下不安装该包。</span><span class="sxs-lookup"><span data-stu-id="42e57-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="42e57-122">请使用服务器管理器安装各个工具。</span><span class="sxs-lookup"><span data-stu-id="42e57-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="42e57-123">ADSI Edit 包括在 **“角色管理工具”**、**“Active Directory 域服务工具”**、**“Active Directory 域控制器工具”** 下。</span><span class="sxs-lookup"><span data-stu-id="42e57-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="42e57-124">对于 Windows Server 2003，ADSI Edit 随附在支持工具中。</span><span class="sxs-lookup"><span data-stu-id="42e57-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="42e57-125">支持工具可从 Windows Server 2003 CD 中的 "支持\\\\工具" 文件夹中获取，也可从 "Windows server 2003 Service Pack 2 32-位支持工具" 下载。 [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)</span><span class="sxs-lookup"><span data-stu-id="42e57-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="42e57-126">有关从产品 CD 安装支持工具的说明，可参阅 "安装 Windows 支持工具" [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)。</span><span class="sxs-lookup"><span data-stu-id="42e57-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="42e57-127">安装支持工具时，Adsiedit.dll 会自动注册。</span><span class="sxs-lookup"><span data-stu-id="42e57-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="42e57-128">但是，如果已经将文件复制到您的计算机，则您必须在您可运行工具之前运行 **regsvr32** 命令注册 adsiedit.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="42e57-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42e57-129">本部分内容</span><span class="sxs-lookup"><span data-stu-id="42e57-129">In This Section</span></span>

  - [<span data-ttu-id="42e57-130">在 Lync Server 2013 中运行 Active Directory 架构准备</span><span class="sxs-lookup"><span data-stu-id="42e57-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="42e57-131">在 Lync Server 2013 中验证 Active Directory 架构复制</span><span class="sxs-lookup"><span data-stu-id="42e57-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="42e57-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42e57-132">See Also</span></span>


[<span data-ttu-id="42e57-133">准备 Lync Server 2013 的林</span><span class="sxs-lookup"><span data-stu-id="42e57-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="42e57-134">准备 Lync Server 2013 的域</span><span class="sxs-lookup"><span data-stu-id="42e57-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

