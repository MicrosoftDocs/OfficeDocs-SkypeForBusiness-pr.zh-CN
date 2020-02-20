---
title: Lync Server 2013：准备林
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f8ff7bbbdd7e1f941b941e2c9446e5890b97dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="4738a-102">准备 Lync Server 2013 的林</span><span class="sxs-lookup"><span data-stu-id="4738a-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4738a-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4738a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4738a-104">林准备创建 Active Directory 全局设置和对象以及由 Lync Server 2013 使用的 Active Directory 通用组，并授予对 Active Directory 对象的适当访问权限。</span><span class="sxs-lookup"><span data-stu-id="4738a-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="4738a-105">有关通用组以及由林准备创建的全局设置和对象的说明，请参阅[Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="4738a-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="4738a-106">林准备还会创建包含由 Lync Server 2013 使用的属性集和显示说明符的对象，并将它们存储在配置容器中。</span><span class="sxs-lookup"><span data-stu-id="4738a-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4738a-107">在执行林准备过程之前，请确保架构准备更改已复制到所有域控制器。</span><span class="sxs-lookup"><span data-stu-id="4738a-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="4738a-108">如果复制尚未完成，则会出错。</span><span class="sxs-lookup"><span data-stu-id="4738a-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="4738a-109">如果您正在执行新的 Lync Server 部署，则必须将全局设置存储在配置容器中。</span><span class="sxs-lookup"><span data-stu-id="4738a-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="4738a-110">如果要从早期版本进行升级，并且仍将全局设置存储在系统容器中，则可以继续使用系统容器。</span><span class="sxs-lookup"><span data-stu-id="4738a-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="4738a-111">只有林根目录域的 Enterprise Admins 组或 Domain Admins 组的成员才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="4738a-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4738a-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="4738a-112">In This Section</span></span>

  - [<span data-ttu-id="4738a-113">为 Lync Server 2013 运行林准备</span><span class="sxs-lookup"><span data-stu-id="4738a-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="4738a-114">使用 cmdlet 对 Lync Server 2013 反向林准备</span><span class="sxs-lookup"><span data-stu-id="4738a-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

