---
title: 将 Kerberos 身份验证帐户密码同步到 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc56da26961caaad236857c88d601676e12cefc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="5b575-102">在 Lync Server 2013 中将 Kerberos 身份验证帐户密码同步到 IIS</span><span class="sxs-lookup"><span data-stu-id="5b575-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b575-103">_**主题上次修改时间:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="5b575-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="5b575-104">若要成功完成此过程, 你应以 RTCUniversalServerAdmins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="5b575-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="5b575-105">在网站、前端服务器、标准版服务器和控制器上, 可以使用 Kerberos 身份验证帐户对 Web 服务服务请求进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5b575-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="5b575-106">此过程将在已分配有 Kerberos 帐户的网站中查找运行 Web 服务的每台服务器, 并将 Internet 信息服务 (IIS) 配置设置更新为使用 Kerberos 帐户。</span><span class="sxs-lookup"><span data-stu-id="5b575-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="5b575-107">有关详细信息, 请参阅[在 Lync server 2013 中的服务器上设置 Kerberos 身份验证帐户密码](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5b575-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="5b575-108">设置和配置 Kerberos 身份验证帐户密码</span><span class="sxs-lookup"><span data-stu-id="5b575-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="5b575-109">以 RTCUniversalServerAdmins 组的成员身份登录源计算机 (如 fe01.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="5b575-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="5b575-110">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="5b575-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5b575-111">在 Lync Server Management Shell 命令行中, 运行以下两个命令:</span><span class="sxs-lookup"><span data-stu-id="5b575-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="5b575-112">例如：</span><span class="sxs-lookup"><span data-stu-id="5b575-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="5b575-113">源计算机和目标计算机的名称必须是服务器的完全限定的域名 (FQDN) 名称。</span><span class="sxs-lookup"><span data-stu-id="5b575-113">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server.</span></span> <span data-ttu-id="5b575-114">除非池名称与用作源计算机或目标计算机的计算机的名称相同, 否则不能使用池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5b575-114">You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="5b575-115">对 Kerberos 身份验证进行任何更改 (如添加帐户或删除帐户) 后, 必须从 Lync Server Management Shell 命令提示符运行<STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="5b575-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

