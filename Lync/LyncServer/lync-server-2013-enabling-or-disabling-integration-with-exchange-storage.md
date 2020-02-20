---
title: Lync Server 2013：启用或禁用与 Exchange 存储的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a3c51b944032fd871ab6f5372f7f3f8c42fad4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a><span data-ttu-id="d34c7-102">启用或禁用与 Exchange 存储的 Lync Server 2013 集成</span><span class="sxs-lookup"><span data-stu-id="d34c7-102">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d34c7-103">_**上次修改的主题：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="d34c7-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="d34c7-104">在 Lync Server 2013 控制面板中，使用存档配置启用和禁用与 Exchange 存储的集成。</span><span class="sxs-lookup"><span data-stu-id="d34c7-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable integration with Exchange storage.</span></span> <span data-ttu-id="d34c7-105">这包括以下存档配置：</span><span class="sxs-lookup"><span data-stu-id="d34c7-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="d34c7-106">部署 Lync Server 2013 时默认创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="d34c7-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="d34c7-107">您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。</span><span class="sxs-lookup"><span data-stu-id="d34c7-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="d34c7-108">有关如何实施存档配置的详细信息，包括可以指定哪些选项以及存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="d34c7-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="d34c7-109">启用或禁用与 Microsoft Exchange 存储的集成</span><span class="sxs-lookup"><span data-stu-id="d34c7-109">To enable or disable integration with Microsoft Exchange storage</span></span>

1.  <span data-ttu-id="d34c7-110">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d34c7-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d34c7-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="d34c7-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d34c7-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="d34c7-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d34c7-113">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。</span><span class="sxs-lookup"><span data-stu-id="d34c7-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="d34c7-114">单击存档配置列表中相应的全局、站点或池配置的名称，单击“编辑”\*\*\*\*，再单击“显示详细信息”\*\*\*\*，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d34c7-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="d34c7-115">若要启用与 Exchange 2013 存储的集成，请选中 " **Microsoft Exchange 集成**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="d34c7-115">To enable integration with Exchange 2013 storage, select the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="d34c7-116">若要禁用与 Exchange 2013 存储的集成，请清除 " **Microsoft Exchange 集成**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="d34c7-116">To disable integration with Exchange 2013 storage, clear the **Microsoft Exchange integration** check box.</span></span>

5.  <span data-ttu-id="d34c7-117">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d34c7-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d34c7-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d34c7-118">See Also</span></span>


[<span data-ttu-id="d34c7-119">Lync Server 2013 中的存档工作原理</span><span class="sxs-lookup"><span data-stu-id="d34c7-119">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="d34c7-120">在 Lync Server 2013 中管理组织、网站和池的存档配置选项</span><span class="sxs-lookup"><span data-stu-id="d34c7-120">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

