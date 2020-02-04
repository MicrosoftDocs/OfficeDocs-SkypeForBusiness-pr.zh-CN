---
title: Lync Server 2013：删除网络子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c87ca1cfd91344d8f8cbb0b320c70def47bf5ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="76102-102">在 Lync Server 2013 中删除网络子网</span><span class="sxs-lookup"><span data-stu-id="76102-102">Deleting network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76102-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="76102-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="76102-104">可以使用以下过程删除子网。</span><span class="sxs-lookup"><span data-stu-id="76102-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="76102-105">从 Lync Server 控制面板中，您可以创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="76102-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="76102-106">有关创建或修改网络子网的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络子网](lync-server-2013-create-or-modify-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="76102-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="76102-107">在大多数部署呼叫许可控制（CAC）的 Microsoft Lync Server 2013 中，通常会有大量子网。</span><span class="sxs-lookup"><span data-stu-id="76102-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="76102-108">因此，通常最好从 Lync Server 命令行管理程序中配置子网。</span><span class="sxs-lookup"><span data-stu-id="76102-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="76102-109">从这里，你可以将 CsNetworkSubnet 与 Windows PowerShell cmdlet **Import-CSV**结合在一起调用**新的**。</span><span class="sxs-lookup"><span data-stu-id="76102-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="76102-110">通过将这些 cmdlet 结合使用，你可以从逗号分隔值（.csv）文件中读取子网设置，并同时创建多个子网。</span><span class="sxs-lookup"><span data-stu-id="76102-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="76102-111">有关如何从 .csv 文件创建子网的示例，请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="76102-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="76102-112">删除网络子网</span><span class="sxs-lookup"><span data-stu-id="76102-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="76102-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="76102-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="76102-114">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="76102-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="76102-115">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="76102-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="76102-116">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**子网**"。</span><span class="sxs-lookup"><span data-stu-id="76102-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="76102-117">在 "**子网**" 页面上，单击要删除的子网。</span><span class="sxs-lookup"><span data-stu-id="76102-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="76102-118">您可以一次删除多个子网。</span><span class="sxs-lookup"><span data-stu-id="76102-118">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="76102-119">若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个子网。</span><span class="sxs-lookup"><span data-stu-id="76102-119">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="76102-120">或者，若要选择所有子网，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="76102-120">Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="76102-121">在 "**编辑**" 菜单上，单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="76102-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="76102-122">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="76102-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76102-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76102-123">See Also</span></span>


[<span data-ttu-id="76102-124">在 Lync Server 2013 中创建或修改网络子网</span><span class="sxs-lookup"><span data-stu-id="76102-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

