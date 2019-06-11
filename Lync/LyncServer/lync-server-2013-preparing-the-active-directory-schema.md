---
title: Lync Server 2013：准备 Active Directory 架构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="59184-102">在 Lync Server 2013 中准备 Active Directory 架构</span><span class="sxs-lookup"><span data-stu-id="59184-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59184-103">_**主题上次修改时间:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="59184-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="59184-104">在开始准备 Active Directory 域服务之前, 可以使用文本编辑器 (如 Windows 记事本) 打开架构文件, 或者查看[由 Lync Server 2013 使用的 Active Directory 架构扩展、类和属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)以查看所有活动将针对 Lync Server 2013 进行修改的 Directory 域服务架构扩展。</span><span class="sxs-lookup"><span data-stu-id="59184-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="59184-105">Lync 服务器使用四个架构文件:</span><span class="sxs-lookup"><span data-stu-id="59184-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="59184-106">ExternalSchema 用于与 Microsoft Exchange Server 的互操作性</span><span class="sxs-lookup"><span data-stu-id="59184-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="59184-107">ServerSchema, 它是主 Lync Server 2013 架构文件</span><span class="sxs-lookup"><span data-stu-id="59184-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="59184-108">BackCompatSchema 用于与以前版本中的任何组件的互操作性</span><span class="sxs-lookup"><span data-stu-id="59184-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="59184-109">VersionSchema 用于预准备架构的版本信息</span><span class="sxs-lookup"><span data-stu-id="59184-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="59184-110">无论是从以前的版本迁移还是执行全新安装, 都将在架构准备期间安装所有 .ldf 文件。</span><span class="sxs-lookup"><span data-stu-id="59184-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="59184-111">这些架构文件按照前面列表中显示的顺序安装, 位于安装媒体上的 " \\支持\\架构" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="59184-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="59184-112">Lync Server 架构扩展跨所有域复制, 这会影响网络流量。</span><span class="sxs-lookup"><span data-stu-id="59184-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="59184-113">当网络使用率较低时, 请一次运行架构准备。</span><span class="sxs-lookup"><span data-stu-id="59184-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59184-114">如果需要将 Microsoft® Office Communicator Mobile 2007 R2 for Java 和 Microsoft® Office Communicator Mobile for Nokia 1.0 移动客户端的支持添加到 Lync Server 2013 部署, 你需要准备 Active Directory 架构 for Microsoft Office在安装 Lync Server 2013 期间通信服务器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="59184-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="59184-115">有关必需的软件和文档, 请<A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>参阅。</span><span class="sxs-lookup"><span data-stu-id="59184-115">For the necessary software and documentation, see <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="59184-116">ADSI 编辑器</span><span class="sxs-lookup"><span data-stu-id="59184-116">ADSI Edit</span></span>

<span data-ttu-id="59184-117">Active Directory 服务界面编辑器 (ADSI Edit) 是一个 AD DS 管理工具, 可用于验证架构准备和复制。</span><span class="sxs-lookup"><span data-stu-id="59184-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="59184-118">安装 AD DS 角色以使服务器成为域控制器时, 默认情况下会安装 "ADSI 编辑"。</span><span class="sxs-lookup"><span data-stu-id="59184-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="59184-119">对于 Windows Server 2008 和 Windows Server 2008 R2, "ADSI 编辑" (adsiedit) 将包含在远程服务器管理工具 (RSAT) 中。</span><span class="sxs-lookup"><span data-stu-id="59184-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="59184-120">您也可以在域成员服务器或独立服务器上安装 RSAT。</span><span class="sxs-lookup"><span data-stu-id="59184-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="59184-121">默认情况下, 将在安装 Windows 时将 RSAT 程序包复制到这些服务器, 但默认情况下不会安装该程序包。</span><span class="sxs-lookup"><span data-stu-id="59184-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="59184-122">使用服务器管理器安装单个工具。</span><span class="sxs-lookup"><span data-stu-id="59184-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="59184-123">"**角色管理工具**"、" **Active Directory 域服务工具**"、" **active directory 域控制器工具**" 下包含 "ADSI 编辑"。</span><span class="sxs-lookup"><span data-stu-id="59184-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="59184-124">对于 Windows Server 2003, "支持工具" 中附带了 "ADSI 编辑"。</span><span class="sxs-lookup"><span data-stu-id="59184-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="59184-125">支持工具可从 Windows Server 2003 CD 的 "支持\\\\工具" 文件夹中获得, 也可从 "Windows server 2003 Service Pack 2 32 位支持工具" 下载。 [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)</span><span class="sxs-lookup"><span data-stu-id="59184-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="59184-126">有关从产品 CD 安装支持工具的说明, 请访问 "安装 Windows 支持工具" [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)。</span><span class="sxs-lookup"><span data-stu-id="59184-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="59184-127">在安装支持工具时, 将自动注册 Adsiedit。</span><span class="sxs-lookup"><span data-stu-id="59184-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="59184-128">但是, 如果您已将文件复制到计算机, 则必须运行**regsvr32**命令来注册 adsiedit .dll 文件, 然后才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="59184-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="59184-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="59184-129">In This Section</span></span>

  - [<span data-ttu-id="59184-130">在 Lync Server 2013 中运行 Active Directory 架构准备</span><span class="sxs-lookup"><span data-stu-id="59184-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="59184-131">在 Lync Server 2013 中验证 Active Directory 架构复制</span><span class="sxs-lookup"><span data-stu-id="59184-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59184-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59184-132">See Also</span></span>


[<span data-ttu-id="59184-133">为 Lync Server 2013 准备林</span><span class="sxs-lookup"><span data-stu-id="59184-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="59184-134">为 Lync Server 2013 准备域</span><span class="sxs-lookup"><span data-stu-id="59184-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

