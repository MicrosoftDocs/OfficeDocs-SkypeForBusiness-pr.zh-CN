---
title: 将 Kerberos 身份验证帐户密码同步到 IIS
description: 将 Kerberos 身份验证帐户密码同步到 IIS。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59555fc25088d0d932105f77051f959b4bcebb46
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556348"
---
# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="7a8d4-103">在 Lync Server 2013 中将 Kerberos 身份验证帐户密码同步到 IIS</span><span class="sxs-lookup"><span data-stu-id="7a8d4-103">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a8d4-104">_**上次修改的主题：** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="7a8d4-104">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="7a8d4-105">要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="7a8d4-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="7a8d4-106">在网站中，前端服务器、Standard Edition 服务器和控制器可以使用 Kerberos 身份验证帐户，以对 Web 服务服务的请求进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7a8d4-106">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="7a8d4-107">此过程将查找在已分配 Kerberos 帐户的站点中运行 Web 服务的每台服务器，并将 Internet 信息服务 (IIS) 配置设置更新为使用 Kerberos 帐户。</span><span class="sxs-lookup"><span data-stu-id="7a8d4-107">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="7a8d4-108">有关详细信息，请参阅 [在 Lync server 2013 中的服务器上设置 Kerberos 身份验证帐户密码](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7a8d4-108">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="7a8d4-109">设置和配置 Kerberos 身份验证帐户密码</span><span class="sxs-lookup"><span data-stu-id="7a8d4-109">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="7a8d4-110">以 RTCUniversalServerAdmins 组成员的身份登录到源计算机（例如 fe01.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="7a8d4-110">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="7a8d4-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7a8d4-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7a8d4-112">在 Lync Server 命令行管理程序命令行中，运行以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="7a8d4-112">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="7a8d4-113">例如：</span><span class="sxs-lookup"><span data-stu-id="7a8d4-113">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="7a8d4-p102">源计算机和目标计算机的名称必须是服务器的完全限定域名 (FQDN)。除非池名称与要用作源计算机或目标计算机的计算机名称相同，否则不能使用池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7a8d4-p102">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server. You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="7a8d4-116">在对 Kerberos 身份验证（如添加帐户或删除帐户）进行任何更改之后，您必须从 Lync Server 命令行管理程序命令提示符处运行 <STRONG>Enable-enable-cstopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="7a8d4-116">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

