---
title: 管理加载项
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef4586d0d84d53173f5e27fc504a9911905f1dd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-add-ins"></a><span data-ttu-id="dda60-102">管理加载项</span><span class="sxs-lookup"><span data-stu-id="dda60-102">Manage add-ins</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dda60-103">_**主题上次修改时间:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="dda60-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="dda60-104">创建新的持久聊天服务器外接程序</span><span class="sxs-lookup"><span data-stu-id="dda60-104">To create a new Persistent Chat Server Add-in</span></span>

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a><span data-ttu-id="dda60-105">创建、获取、设置或删除加载项</span><span class="sxs-lookup"><span data-stu-id="dda60-105">Create, Get, Set, or Remove an Add-in</span></span>

<span data-ttu-id="dda60-106">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="dda60-106">To create a new Add-in</span></span>

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dda60-107">仅&lt;当&gt;存在多个持久聊天服务器池时, 才需要 PersistentChatPoolFqdn 字符串。</span><span class="sxs-lookup"><span data-stu-id="dda60-107">PersistentChatPoolFqdn &lt;String&gt; is required only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="dda60-108">获取加载项</span><span class="sxs-lookup"><span data-stu-id="dda60-108">To get an Add-in</span></span>

    Get-CsPersistentChatAddin -Identity <String>]

<span data-ttu-id="dda60-109">或者</span><span class="sxs-lookup"><span data-stu-id="dda60-109">or</span></span>

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

<span data-ttu-id="dda60-110">设置加载项</span><span class="sxs-lookup"><span data-stu-id="dda60-110">To set an Add-in</span></span>

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="dda60-111">或者</span><span class="sxs-lookup"><span data-stu-id="dda60-111">or</span></span>

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="dda60-112">删除加载项</span><span class="sxs-lookup"><span data-stu-id="dda60-112">To remove an Add-in</span></span>

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="dda60-113">或者</span><span class="sxs-lookup"><span data-stu-id="dda60-113">or</span></span>

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

