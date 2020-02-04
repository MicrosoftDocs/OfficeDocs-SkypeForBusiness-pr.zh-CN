---
title: Lync Server 2013：部署统一联系人存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d224ec7a9c452c45f9f3471403301460a2a31cc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="ac08a-102">在 Lync Server 2013 中部署统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="ac08a-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac08a-103">_**主题上次修改时间：** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="ac08a-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="ac08a-104">在 Lync Server 2013 中启用统一联系人存储不需要任何拓扑设置。</span><span class="sxs-lookup"><span data-stu-id="ac08a-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="ac08a-105">为用户启用统一联系人存储需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="ac08a-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="ac08a-106">启用统一的联系人存储库策略（将启用默认值）。</span><span class="sxs-lookup"><span data-stu-id="ac08a-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="ac08a-107">用户至少以 Lync 2013 登录。</span><span class="sxs-lookup"><span data-stu-id="ac08a-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="ac08a-108">迁移用户的联系人后，当用户使用 Lync 2013 登录时，该用户可以在 Lync 2013、Outlook 2013 或 Outlook Web Access 中访问和管理其 Lync 联系人。</span><span class="sxs-lookup"><span data-stu-id="ac08a-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="ac08a-109">用户不必登录 Lync 即可从 Outlook 或 Outlook Web Access 管理其联系人。</span><span class="sxs-lookup"><span data-stu-id="ac08a-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ac08a-110">如果用户在迁移后从 Lync 2010 登录，则联系人和组可用且最新，但用户无法管理（即添加、删除、移动、标记、取消标记或修改）这些联系人。</span><span class="sxs-lookup"><span data-stu-id="ac08a-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac08a-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="ac08a-111">In This Section</span></span>

  - [<span data-ttu-id="ac08a-112">在 Lync Server 2013 中为用户启用统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="ac08a-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="ac08a-113">在 Lync Server 2013 中将用户迁移到统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="ac08a-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="ac08a-114">在 Lync Server 2013 中回滚已迁移用户</span><span class="sxs-lookup"><span data-stu-id="ac08a-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

