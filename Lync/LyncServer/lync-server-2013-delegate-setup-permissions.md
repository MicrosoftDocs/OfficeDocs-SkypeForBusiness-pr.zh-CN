---
title: Lync Server 2013：委派安装权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="95949-102">Lync Server 2013 中的委派安装权限</span><span class="sxs-lookup"><span data-stu-id="95949-102">Delegate setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95949-103">_**主题上次修改时间：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="95949-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="95949-104">如果你不想向正在部署 lync server 2013 的用户或组授予域管理员组成员身份，你可以启用 RTCUniversalServerAdmins 组的成员在运行 Lync server 2013 的服务器上运行**enable-CsTopology** Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95949-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="95949-105">默认情况下，RTCUniversalServerAdmins 组的成员不具备运行此 cmdlet 的能力。</span><span class="sxs-lookup"><span data-stu-id="95949-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="95949-106">通过使用**CsSetupPermission** cmdlet 授予管理员权限，在运行 lync server 的服务器上运行**CsTopology** ，并指定运行 lync server 2013 的服务器的计算机对象所在的组织单位（OU）。</span><span class="sxs-lookup"><span data-stu-id="95949-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="95949-107">安装 Lync Server 时进行的域准备不会自动添加允许 RTCUniversalServerAdmins 组成员运行 Enable-CsTopology cmdlet 的权限。</span><span class="sxs-lookup"><span data-stu-id="95949-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="95949-108">这意味着，默认情况下，您必须是域管理员才能启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="95949-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="95949-109">若要为 RTCUniversalServerAdmins 组的成员授予启用拓扑的权限，您必须运行 CsSetupPermissions cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95949-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="95949-110">此外，你将需要针对驻留运行 Lync Server 的计算机的每个 Active Directory 容器运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95949-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="95949-111">请记住，此 cmdlet 仅向 RTCUniversalServerAdmins 组授予权限;该 cmdlet 不能用于向其他安全组或单个用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="95949-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95949-112"><STRONG>Enable-CsTopology</STRONG>是允许 RTCUniversalServerAdmins 组成员设置和部署 Lync Server 2013 的关键 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95949-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="95949-113">添加对 RTCUniversalServerAdmins 组运行 Enable-CsTopology 的能力</span><span class="sxs-lookup"><span data-stu-id="95949-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="95949-114">以委派用户将在其上运行的域的域管理员组的成员身份登录到服务器 **-CsTopology**。</span><span class="sxs-lookup"><span data-stu-id="95949-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="95949-115">打开 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="95949-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="95949-116">Lync Server 2013 命令行管理程序自动安装在每个前端服务器或安装了 Lync Server 2013 管理工具的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="95949-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="95949-117">有关 Lync Server 2013 命令行管理程序的详细信息，请参阅操作文档中的[Lync server 2013 管理外壳](lync-server-2013-lync-server-management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="95949-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="95949-118">从 Lync Server 2013 命令行管理程序运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="95949-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="95949-119">如果 OU 不在顶层，则必须提供完整的域名。</span><span class="sxs-lookup"><span data-stu-id="95949-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="95949-120">在以下示例中，OU 是 "Lync 服务器"，它位于 contoso.com 域中。</span><span class="sxs-lookup"><span data-stu-id="95949-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

