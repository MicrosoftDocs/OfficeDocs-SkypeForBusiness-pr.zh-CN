---
title: Lync Server 2013：设置 Kerberos 身份验证帐户密码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21ed9f0b5bd8e9aecfb39a7dd9c159857d4b240e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="ed388-102">在 Lync Server 2013 中设置 Kerberos 身份验证帐户密码</span><span class="sxs-lookup"><span data-stu-id="ed388-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed388-103">_**上次修改的主题：** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="ed388-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="ed388-104">为 Kerberos 身份验证帐户创建计算机对象后，即可设置该帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="ed388-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="ed388-105">运行 Windows PowerShell cmdlet 以在一台服务器上设置 Kerberos 帐户密码。</span><span class="sxs-lookup"><span data-stu-id="ed388-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="ed388-106">可以在为 Kerberos 身份验证所创建的对象上设置密码。</span><span class="sxs-lookup"><span data-stu-id="ed388-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="ed388-107">可将密码设置为已知值，但默认情况下为随机密码。</span><span class="sxs-lookup"><span data-stu-id="ed388-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="ed388-108">该密码可用于所有使用该帐户的 Kerberos 身份验证源。</span><span class="sxs-lookup"><span data-stu-id="ed388-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="ed388-109">您可以使用 Windows PowerShell cmdlet 来设置和管理 Kerberos 帐户密码。</span><span class="sxs-lookup"><span data-stu-id="ed388-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed388-110">Kerberos 帐户对象是一个计算机对象，但对 Windows PowerShell cmdlet 中所引用的操作使用 UserAccount 参数。</span><span class="sxs-lookup"><span data-stu-id="ed388-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="ed388-111">请注意，这并非错误，而是 cmdlet 在与 Kerberos 帐户创建和维护结合使用时的预期行为。</span><span class="sxs-lookup"><span data-stu-id="ed388-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed388-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ed388-112">In This Section</span></span>

  - [<span data-ttu-id="ed388-113">在 Lync Server 2013 中的服务器上设置 Kerberos 身份验证帐户密码</span><span class="sxs-lookup"><span data-stu-id="ed388-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="ed388-114">在 Lync Server 2013 中将 Kerberos 身份验证帐户密码同步到 IIS</span><span class="sxs-lookup"><span data-stu-id="ed388-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

