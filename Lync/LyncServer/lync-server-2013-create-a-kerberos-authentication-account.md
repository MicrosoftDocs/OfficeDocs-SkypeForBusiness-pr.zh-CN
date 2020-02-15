---
title: Lync Server 2013：创建 Kerberos 身份验证帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e59703328fad7c8763bc1a6cc018c2cbc585c3ed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="8b16a-102">在 Lync Server 2013 中创建 Kerberos 身份验证帐户</span><span class="sxs-lookup"><span data-stu-id="8b16a-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b16a-103">_**上次修改的主题：** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="8b16a-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="8b16a-104">要成功完成此过程，至少应以 Domain Admins 组成员身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="8b16a-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="8b16a-105">可以为每个站点创建多个 Kerberos 身份验证帐户，或者创建一个 Kerberos 身份验证帐户，然后将其用于所有站点。</span><span class="sxs-lookup"><span data-stu-id="8b16a-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="8b16a-106">您可以使用 Windows PowerShell cmdlet 来创建和管理帐户，包括标识分配给每个网站的帐户。</span><span class="sxs-lookup"><span data-stu-id="8b16a-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="8b16a-107">拓扑生成器和 Lync Server 2013 控制面板不显示 Kerberos 身份验证帐户。</span><span class="sxs-lookup"><span data-stu-id="8b16a-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="8b16a-108">使用以下过程创建一个或多个要用于 Kerberos 身份验证的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8b16a-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="8b16a-109">创建 Kerberos 帐户</span><span class="sxs-lookup"><span data-stu-id="8b16a-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="8b16a-110">作为 Domain Admins 组的成员，请登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b16a-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="8b16a-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b16a-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8b16a-112">在命令行中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8b16a-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="8b16a-113">例如：</span><span class="sxs-lookup"><span data-stu-id="8b16a-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="8b16a-114">通过打开“Active Directory 用户和计算机”确认是否已创建计算机对象，展开“用户”\*\*\*\* 容器，然后确认容器中存在此用户帐户的计算机对象。</span><span class="sxs-lookup"><span data-stu-id="8b16a-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

