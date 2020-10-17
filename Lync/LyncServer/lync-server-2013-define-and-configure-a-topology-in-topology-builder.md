---
title: Lync Server 2013：在拓扑生成器中定义和配置拓扑
description: Lync Server 2013：在拓扑生成器中定义和配置拓扑。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a1f29ec78cf7cfd3856d3f1aa87a22dc0bbe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569938"
---
# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="9d27b-103">在 Lync Server 2013 拓扑生成器中定义和配置拓扑</span><span class="sxs-lookup"><span data-stu-id="9d27b-103">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d27b-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9d27b-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9d27b-105">运行拓扑生成器以定义新的拓扑或修改现有拓扑不需要本地管理员或有权限的域组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="9d27b-105">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="9d27b-106">拓扑生成器将指导您完成定义您的企业版前端池或标准版的拓扑所需的步骤，具体取决于您的配置要求。</span><span class="sxs-lookup"><span data-stu-id="9d27b-106">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="9d27b-107">您必须使用拓扑生成器完成并发布拓扑，然后才能在服务器上安装 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9d27b-107">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="9d27b-108">以下过程包括定义新拓扑所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="9d27b-108">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="9d27b-109">定义拓扑</span><span class="sxs-lookup"><span data-stu-id="9d27b-109">To define a topology</span></span>

1.  <span data-ttu-id="9d27b-110">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="9d27b-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9d27b-111">在拓扑生成器中，选择 " **新建拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="9d27b-111">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="9d27b-112">系统将提示您输入用于保存拓扑的位置和文件名。</span><span class="sxs-lookup"><span data-stu-id="9d27b-112">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="9d27b-113">为拓扑文件指定一个有意义的名称，并接受默认扩展名 tbxml。</span><span class="sxs-lookup"><span data-stu-id="9d27b-113">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="9d27b-114">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d27b-114">Click **OK**.</span></span>

3.  <span data-ttu-id="9d27b-115">导航到要在其中保存新的拓扑 XML 文件的位置，输入该文件的名称，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="9d27b-115">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="9d27b-116">在 " **定义主域"** 页面上，输入您的组织的主要 SIP 域的名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9d27b-116">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="9d27b-117">在 " **指定其他支持的域** " 页上，输入其他域的名称（如果有），然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9d27b-117">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="9d27b-118">在 " **定义第一张网站** " 页上，为第一个网站输入名称和说明，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9d27b-118">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="9d27b-119">在 " **指定网站详细信息** " 页上，输入网站的位置信息，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9d27b-119">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="9d27b-120">在 " **已成功定义新拓扑** " 页上，确保选中了 " **关闭此向导时打开新的前端向导** " 复选框，然后单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="9d27b-120">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="9d27b-121">定义并保存拓扑之后，使用新的前端向导为网站定义前端池或 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="9d27b-121">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="9d27b-122">有关详细信息，请参阅 [在 Lync server 2013 中定义和配置前端池或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9d27b-122">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

