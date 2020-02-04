---
title: Lync Server 2013：会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d1d9ed6fc0ad75e316a41ef7939f36ecaba354
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="44439-102">Lync Server 2013 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="44439-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44439-103">_**主题上次修改时间：** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="44439-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="44439-104">会议策略定义用户在会议（也称为会议）期间可用的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="44439-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="44439-105">会议策略设置包含各种安排和参与选项，包括从会议能否包括 IP 音频和视频，到可参与会议的最大人数。</span><span class="sxs-lookup"><span data-stu-id="44439-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="44439-106">管理员可以使用会议策略来管理会议的安全、带宽和法律方面。</span><span class="sxs-lookup"><span data-stu-id="44439-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="44439-107">可以在三个级别定义会议策略：全局作用域、站点作用域和用户作用域。</span><span class="sxs-lookup"><span data-stu-id="44439-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="44439-108">可以为不同范围的作用域中的特定用户应用设置。</span><span class="sxs-lookup"><span data-stu-id="44439-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="44439-109">如果向用户分配用户策略，这些设置优先。</span><span class="sxs-lookup"><span data-stu-id="44439-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="44439-110">如果未分配用户策略，则应用站点设置。</span><span class="sxs-lookup"><span data-stu-id="44439-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="44439-111">如果未应用用户策略或站点策略，则全局策略会提供默认设置。</span><span class="sxs-lookup"><span data-stu-id="44439-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="44439-112">默认情况下，全局策略已存在，因此不能创建新的全局策略。</span><span class="sxs-lookup"><span data-stu-id="44439-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="44439-113">也不能删除现有全局策略，但可以更改现有全局策略以自定义默认设置。</span><span class="sxs-lookup"><span data-stu-id="44439-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="44439-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="44439-114">In This Section</span></span>

  - [<span data-ttu-id="44439-115">在 Lync Server 2013 中查看会议策略信息</span><span class="sxs-lookup"><span data-stu-id="44439-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="44439-116">在 Lync Server 2013 中创建或修改会议策略</span><span class="sxs-lookup"><span data-stu-id="44439-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="44439-117">在 Lync Server 2013 中删除现有会议策略</span><span class="sxs-lookup"><span data-stu-id="44439-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="44439-118">Lync Server 2013 的会议策略设置参考</span><span class="sxs-lookup"><span data-stu-id="44439-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

