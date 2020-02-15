---
title: 配置受信任应用程序服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e74cba866a7353890bb47de745e5e525d43963
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="9d51d-102">配置受信任应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="9d51d-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d51d-103">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="9d51d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="9d51d-104">在混合环境中，如果在将旧版 Office 通信服务器拓扑与 Lync Server 2013 合并之后创建新的受信任应用程序服务器，并使用拓扑生成器定义新的受信任应用程序服务器，则必须将下一个跃点池设置为Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="9d51d-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="9d51d-105">在合并环境中，旧版 Office 通信服务器池和 Lync Server 2013 池都显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="9d51d-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="9d51d-106">此环境*不* 支持选择旧池。</span><span class="sxs-lookup"><span data-stu-id="9d51d-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="9d51d-107">在创建受信任的应用程序服务器时选择 Lync Server 2013 作为下一个跃点</span><span class="sxs-lookup"><span data-stu-id="9d51d-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="9d51d-108">在拓扑生成器中打开现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="9d51d-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="9d51d-109">在左窗格中，右键单击“受信任的应用程序服务器”\*\*\*\*，然后单击“新建受信任的应用程序池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d51d-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="9d51d-110">输入受信任的应用程序池的**池 FQDN** ，并选择它是单服务器部署还是多服务器部署。</span><span class="sxs-lookup"><span data-stu-id="9d51d-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="9d51d-111">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9d51d-111">Click **Next**.</span></span>

5.  <span data-ttu-id="9d51d-112">在 "**选择下一个跃点**" 页上的列表中，选择 "Lync Server 2013 前端池"。</span><span class="sxs-lookup"><span data-stu-id="9d51d-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="9d51d-113">!["定义新的受信任应用程序池" 对话框](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg ""定义新的受信任应用程序池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="9d51d-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="9d51d-114">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d51d-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="9d51d-115">选择顶部节点**Lync Server** ，然后从 "**操作**" 窗格中选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="9d51d-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="9d51d-116">验证**受信任的应用程序池**是否已成功创建并与正确的前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="9d51d-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

