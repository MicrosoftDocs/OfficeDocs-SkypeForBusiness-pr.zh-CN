---
title: 配置受信任应用程序服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204c183ad63da3278d10b802d3f2140fa9a86a70
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="c45ca-102">配置受信任应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="c45ca-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c45ca-103">_**上次修改的主题：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="c45ca-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="c45ca-104">在混合环境中，如果创建新的受信任应用程序服务器，则必须将下一个跃点池设置为 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="c45ca-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="c45ca-105">在混合环境中，旧的 Lync Server 2010 池和 Lync Server 2013 池都将显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="c45ca-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="c45ca-106">此环境不支持选择旧池。</span><span class="sxs-lookup"><span data-stu-id="c45ca-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="c45ca-107">**创建受信任的应用程序服务器时，选择 Lync Server 2013 作为下一个跃点**</span><span class="sxs-lookup"><span data-stu-id="c45ca-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="c45ca-108">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="c45ca-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="c45ca-109">在左窗格中，右键单击“受信任的应用程序服务器”\*\*\*\*，然后单击“新建受信任的应用程序池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c45ca-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="c45ca-110">输入受信任应用程序池的“池 FQDN”\*\*\*\*，选择该池是包含一台服务器还是多台服务器。</span><span class="sxs-lookup"><span data-stu-id="c45ca-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="c45ca-111">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c45ca-111">Click **Next**.</span></span>

5.  <span data-ttu-id="c45ca-112">在 "**选择下一个跃点**" 页上的列表中，选择 "Lync Server 2013 前端池"。</span><span class="sxs-lookup"><span data-stu-id="c45ca-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="c45ca-113">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c45ca-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="c45ca-114">选择顶层节点“Lync Server”\*\*\*\*，然后从“操作”\*\*\*\* 窗格中选择“发布”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c45ca-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="c45ca-115">确认“受信任应用程序池”\*\*\*\* 已成功创建并且与正确的前端池关联。</span><span class="sxs-lookup"><span data-stu-id="c45ca-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

