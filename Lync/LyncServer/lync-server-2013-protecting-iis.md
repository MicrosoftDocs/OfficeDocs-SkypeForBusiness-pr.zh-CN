---
title: Lync Server 2013：保护 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d0f3e736284970bf22fe813093e0e54accd29e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="3c373-102">在 Lync Server 2013 中保护 IIS</span><span class="sxs-lookup"><span data-stu-id="3c373-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c373-103">_**主题上次修改时间：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="3c373-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="3c373-104">在 Microsoft Office 通信服务器2007和 Microsoft Office 通信服务器 2007 R2 中，Internet Information Services （IIS）在标准用户帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="3c373-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="3c373-105">这可能会导致问题：如果该密码已过期，则可能会丢失 Web 服务，这种问题通常很难诊断。</span><span class="sxs-lookup"><span data-stu-id="3c373-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="3c373-106">为了帮助避免密码过期，Microsoft Lync Server 2013 允许你创建一个计算机帐户（对于实际上不存在的计算机），该帐户可以充当运行 IIS 的网站中的所有计算机的身份验证主体。</span><span class="sxs-lookup"><span data-stu-id="3c373-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="3c373-107">由于这些帐户使用 Kerberos 身份验证协议，因此称为 Kerberos 帐户，并且新的身份验证过程称为 Kerberos Web 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c373-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="3c373-108">使您可以使用单个帐户管理所有 IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="3c373-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="3c373-109">若要在此身份验证主体下运行服务器，必须首先使用 CsKerberosAccount cmdlet 创建计算机帐户;然后，将此帐户分配给一个或多个网站。</span><span class="sxs-lookup"><span data-stu-id="3c373-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="3c373-110">执行分配后，将通过运行 CsTopology cmdlet 启用帐户与 Lync Server 2013 网站之间的关联。</span><span class="sxs-lookup"><span data-stu-id="3c373-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="3c373-111">在其他操作中，这将在 Active Directory 域服务（AD DS）中创建所需的服务主体名称（SPN）。</span><span class="sxs-lookup"><span data-stu-id="3c373-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="3c373-112">SPN 为客户端应用程序提供了一种查找特定服务的方法。</span><span class="sxs-lookup"><span data-stu-id="3c373-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="3c373-113">有关详细信息，请参阅操作文档中的 "[新建-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) "。</span><span class="sxs-lookup"><span data-stu-id="3c373-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="3c373-114">最佳做法</span><span class="sxs-lookup"><span data-stu-id="3c373-114">Best Practices</span></span>

<span data-ttu-id="3c373-115">为了帮助提高 IIS 的安全性，我们建议你为 IIS 实现 Kerberos 帐户。</span><span class="sxs-lookup"><span data-stu-id="3c373-115">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS.</span></span> <span data-ttu-id="3c373-116">如果不实现 Kerberos 帐户，IIS 将在标准用户帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="3c373-116">If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

