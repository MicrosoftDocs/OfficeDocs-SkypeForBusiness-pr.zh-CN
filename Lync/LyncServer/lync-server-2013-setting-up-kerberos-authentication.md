---
title: Lync Server 2013：设置 Kerberos 身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42f2c781b01aaa1ac00793f97067f24233c1e8db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="05078-102">在 Lync Server 2013 中设置 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="05078-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05078-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="05078-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="05078-104">Lync Server 2013 支持对 Web 服务进行 NTLM 和 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="05078-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="05078-105">Office 通信服务器2007和 Office 通信服务器 2007 R2 使用默认的 RTCComponentService 和 RTCService 作为运行 Web 服务应用程序池的用户帐户，从而允许将服务主体名称（SPN）分配给用户帐户并充当身份验证主体。</span><span class="sxs-lookup"><span data-stu-id="05078-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="05078-106">Lync Server 使用 NetworkService 运行 Web 服务，并且 NetworkService 无法为其分配 Spn。</span><span class="sxs-lookup"><span data-stu-id="05078-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="05078-107">为了解决未让 Active Directory 对象保存 Spn 的问题，Lync Server 控制面板可以使用计算机帐户对象来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="05078-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="05078-108">计算机帐户对象可以包含 Spn，不受密码过期的限制，这是在以前版本中使用用户帐户时遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="05078-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="05078-109">您可以使用 Windows PowerShell cmdlet 配置计算机对象，以提供 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="05078-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="05078-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="05078-110">In This Section</span></span>

  - [<span data-ttu-id="05078-111">在 Lync Server 2013 中启用 Kerberos 身份验证的先决条件</span><span class="sxs-lookup"><span data-stu-id="05078-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="05078-112">在 Lync Server 2013 中创建 Kerberos 身份验证帐户</span><span class="sxs-lookup"><span data-stu-id="05078-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="05078-113">在 Lync Server 2013 中向网站分配 Kerberos 身份验证帐户</span><span class="sxs-lookup"><span data-stu-id="05078-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="05078-114">在 Lync Server 2013 中设置 Kerberos 身份验证帐户密码</span><span class="sxs-lookup"><span data-stu-id="05078-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="05078-115">在 Lync Server 2013 中，向其他站点添加 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="05078-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="05078-116">在 Lync Server 2013 中，从站点中删除 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="05078-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="05078-117">在 Lync Server 2013 中测试和报告 Kerberos 身份验证的状态和分配</span><span class="sxs-lookup"><span data-stu-id="05078-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

