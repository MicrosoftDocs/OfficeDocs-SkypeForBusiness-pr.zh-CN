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
ms.openlocfilehash: 1c156e26a54e9762b1b57d1513f37cb7d7088cee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="fc037-102">在 Lync Server 2013 中设置 Kerberos 身份验证帐户密码</span><span class="sxs-lookup"><span data-stu-id="fc037-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc037-103">_**主题上次修改时间：** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="fc037-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="fc037-104">为 Kerberos 身份验证帐户创建计算机对象后，您可以为该帐户设置密码。</span><span class="sxs-lookup"><span data-stu-id="fc037-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="fc037-105">在一台服务器上运行用于设置 Kerberos 帐户密码的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc037-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="fc037-106">你可以在为 Kerberos 身份验证创建的对象上设置密码。</span><span class="sxs-lookup"><span data-stu-id="fc037-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="fc037-107">密码可以设置为已知值，但默认情况下是随机密码。</span><span class="sxs-lookup"><span data-stu-id="fc037-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="fc037-108">密码可用于使用该帐户的所有 Kerberos 身份验证源。</span><span class="sxs-lookup"><span data-stu-id="fc037-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="fc037-109">你可以使用 Windows PowerShell cmdlet 设置和管理 Kerberos 帐户密码。</span><span class="sxs-lookup"><span data-stu-id="fc037-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc037-110">Kerberos 帐户对象是一个计算机对象，但对所引用的 Windows PowerShell cmdlet 中的操作使用 UserAccount 参数。</span><span class="sxs-lookup"><span data-stu-id="fc037-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="fc037-111">请注意，这不是错误，但在与 Kerberos 帐户创建和维护一起使用时，该 cmdlet 的预期行为。</span><span class="sxs-lookup"><span data-stu-id="fc037-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fc037-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="fc037-112">In This Section</span></span>

  - [<span data-ttu-id="fc037-113">在 Lync Server 2013 中在服务器上设置 Kerberos 身份验证帐户密码</span><span class="sxs-lookup"><span data-stu-id="fc037-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="fc037-114">在 Lync Server 2013 中将 Kerberos 身份验证帐户密码同步到 IIS</span><span class="sxs-lookup"><span data-stu-id="fc037-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

