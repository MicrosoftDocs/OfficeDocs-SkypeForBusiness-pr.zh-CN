---
title: 管理类别
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b161ab9dce464bdab96432ed909ed48b7df19d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-categories"></a><span data-ttu-id="72a06-102">管理类别</span><span class="sxs-lookup"><span data-stu-id="72a06-102">Manage categories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72a06-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="72a06-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="72a06-104">创建新的持久聊天服务器类别</span><span class="sxs-lookup"><span data-stu-id="72a06-104">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="72a06-105">仅当存在多个持久聊天服务器池时，才需要 PersistentChatPoolFqdn。</span><span class="sxs-lookup"><span data-stu-id="72a06-105">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="72a06-106">对现有的持久聊天服务器类别进行更改</span><span class="sxs-lookup"><span data-stu-id="72a06-106">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="72a06-107">Windows PowerShell：可以同时设置 AllowedMembers、DeniedMembers 和创建者。</span><span class="sxs-lookup"><span data-stu-id="72a06-107">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="72a06-108">Creators 应该是 AllowedMembers 减去 DeniedMembers 的子集。</span><span class="sxs-lookup"><span data-stu-id="72a06-108">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="72a06-109">还可以在设置成员和创建者的同时设置类别的属性。</span><span class="sxs-lookup"><span data-stu-id="72a06-109">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="72a06-110">创建、获取、设置或删除类别</span><span class="sxs-lookup"><span data-stu-id="72a06-110">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="72a06-111">创建新类别</span><span class="sxs-lookup"><span data-stu-id="72a06-111">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="72a06-112">获取类别</span><span class="sxs-lookup"><span data-stu-id="72a06-112">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="72a06-113">或</span><span class="sxs-lookup"><span data-stu-id="72a06-113">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="72a06-114">设置类别</span><span class="sxs-lookup"><span data-stu-id="72a06-114">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="72a06-115">或</span><span class="sxs-lookup"><span data-stu-id="72a06-115">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="72a06-116">删除类别</span><span class="sxs-lookup"><span data-stu-id="72a06-116">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="72a06-117">或</span><span class="sxs-lookup"><span data-stu-id="72a06-117">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

