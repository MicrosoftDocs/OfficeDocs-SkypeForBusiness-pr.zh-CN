---
title: Lync Server 2013：委派安装程序权限
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
ms.openlocfilehash: 394200b21d3720f288fc89780c6ff193bd278cec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="770f2-102">在 Lync Server 2013 中委派安装程序权限</span><span class="sxs-lookup"><span data-stu-id="770f2-102">Delegate setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="770f2-103">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="770f2-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="770f2-104">如果您不想向正在部署 lync server 2013 的用户或组授予 Domain Admins 组成员身份，则可以启用 RTCUniversalServerAdmins 组的成员，以便在运行 Lync server 2013 的服务器上运行**enable-cstopology** Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="770f2-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="770f2-105">默认情况下，RTCUniversalServerAdmins 组的成员无法运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="770f2-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="770f2-106">通过使用**CsSetupPermission** cmdlet 并指定运行 lync server 2013 的服务器的计算机对象所在的组织单位（OU），您可以授予管理员对运行 lync server 的服务器上运行**enable-cstopology**的权限。</span><span class="sxs-lookup"><span data-stu-id="770f2-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="770f2-107">在安装 Lync Server 时进行的域准备不会自动添加允许 RTCUniversalServerAdmins 组成员运行 Enable-cstopology cmdlet 的权限。</span><span class="sxs-lookup"><span data-stu-id="770f2-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="770f2-108">这意味着，默认情况下，只有域管理员才能启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="770f2-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="770f2-109">要授予 RTCUniversalServerAdmins 组的成员启用拓扑的权限，必须运行 Grant-CsSetupPermissions cmdlet。</span><span class="sxs-lookup"><span data-stu-id="770f2-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="770f2-110">此外，还需要对驻留运行 Lync Server 的计算机的每个 Active Directory 容器运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="770f2-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="770f2-111">请记住，此 cmdlet 仅向 RTCUniversalServerAdmins 组授予权限；此 cmdlet 不能用于向其他安全组或向单个用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="770f2-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="770f2-112"><STRONG>Enable-enable-cstopology</STRONG>是允许 RTCUniversalServerAdmins 组成员设置和部署 Lync Server 2013 的关键 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="770f2-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="770f2-113">向 RTCUniversalServerAdmins 组添加运行 Enable-CsTopology 的权限</span><span class="sxs-lookup"><span data-stu-id="770f2-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="770f2-114">以委派用户将在其上运行 **Enable-CsTopology** 的域的 Domain Admins 组成员身份登录服务器。</span><span class="sxs-lookup"><span data-stu-id="770f2-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="770f2-115">打开 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="770f2-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="770f2-116">Lync Server 2013 命令行管理程序将自动安装在每台前端服务器或安装了 Lync Server 2013 管理工具的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="770f2-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="770f2-117">有关 Lync Server 2013 命令行管理程序的详细信息，请参阅操作文档中的[Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序。</span><span class="sxs-lookup"><span data-stu-id="770f2-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="770f2-118">从 Lync Server 2013 命令行管理程序运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="770f2-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="770f2-119">如果 OU 不是最高级别，则必须提供完整的域名。</span><span class="sxs-lookup"><span data-stu-id="770f2-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="770f2-120">在以下示例中，OU 是位于 contoso.com 域中的“Lync Servers”。</span><span class="sxs-lookup"><span data-stu-id="770f2-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

