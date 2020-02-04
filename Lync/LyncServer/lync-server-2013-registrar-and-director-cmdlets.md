---
title: Lync Server 2013：注册机构和控制器 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registrar and Director cmdlets
ms:assetid: 327c08ab-7e1e-47c0-b280-a001722c116f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415641(v=OCS.15)
ms:contentKeyID: 48183813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5512b80d5860c94d379c5c5d43e51cdb8ac5177
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registrar-and-director-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6f748-102">Lync Server 2013 中的注册机构和主管 cmdlet</span><span class="sxs-lookup"><span data-stu-id="6f748-102">Registrar and Director cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f748-103">_**主题上次修改时间：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="6f748-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="6f748-104">注册机构和控制器用于对登录请求进行身份验证，并维护有关用户状态和可用性的信息。</span><span class="sxs-lookup"><span data-stu-id="6f748-104">Registrars and Directors are used to authenticate logon requests and to maintain information about user status and availability.</span></span> <span data-ttu-id="6f748-105">注册机构和控制器 cmdlet 使你能够管理这些服务器的配置设置。</span><span class="sxs-lookup"><span data-stu-id="6f748-105">The Registrar and Director cmdlets enable you to manage configuration settings for these servers.</span></span>

<div>

## <a name="registrar-and-director-cmdlets"></a><span data-ttu-id="6f748-106">注册机构和控制器 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6f748-106">Registrar and Director Cmdlets</span></span>

<span data-ttu-id="6f748-107">以下是与管理注册机构和董事直接相关的 cmdlet 的列表：</span><span class="sxs-lookup"><span data-stu-id="6f748-107">The following is a list of cmdlets that relate directly to managing Registrars and Directors:</span></span>

<span data-ttu-id="6f748-108">**注册机构和董事**</span><span class="sxs-lookup"><span data-stu-id="6f748-108">**Registrars and Directors**</span></span>

  - <span></span>  
    <span data-ttu-id="6f748-109">[Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f748-109">[Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f748-110">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/en-us/library/JJ619172(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f748-110">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/en-us/library/JJ619172(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f748-111">[Set-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f748-111">[Set-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f748-112">[CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f748-112">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f748-113">[新-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f748-113">[New-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f748-114">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f748-114">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f748-115">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f748-115">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f748-116">[Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f748-116">[Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f748-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f748-117">See Also</span></span>


[<span data-ttu-id="6f748-118">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="6f748-118">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

