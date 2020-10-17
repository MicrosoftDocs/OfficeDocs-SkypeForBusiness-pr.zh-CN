---
title: Lync Server 2013：呼叫寄存配置先决条件和用户权限
description: Lync Server 2013：呼叫寄存配置先决条件和用户权限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01187ad32fa7338765c0fa5b409b4e185e8ad35
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563528"
---
# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="3e836-103">在 Lync Server 2013 中呼叫寄存配置先决条件和用户权限</span><span class="sxs-lookup"><span data-stu-id="3e836-103">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e836-104">_**上次修改的主题：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="3e836-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="3e836-105">呼叫寄存是在部署企业语音时默认安装的呼叫管理功能。</span><span class="sxs-lookup"><span data-stu-id="3e836-105">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="3e836-106">本主题介绍在配置呼叫寄存以及执行配置任务所需的用户权限之前，您需要具备的功能。</span><span class="sxs-lookup"><span data-stu-id="3e836-106">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e836-107">在 Lync Server 2013 灾难恢复过程中，不会备份呼叫寄存应用程序的自定义的 "保留时音乐" 文件，如果上载到该池的文件已损坏、损坏或清除，这些文件将会丢失。</span><span class="sxs-lookup"><span data-stu-id="3e836-107">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="3e836-108">始终为已为呼叫寄存上载的自定义的保留音乐文件保留一个单独的备份副本。</span><span class="sxs-lookup"><span data-stu-id="3e836-108">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="3e836-109">本节假定您已阅读与呼叫寄存相关的规划文档 (请参阅 [在 Lync Server 2013) 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md) 。</span><span class="sxs-lookup"><span data-stu-id="3e836-109">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="3e836-110">呼叫寄存配置必备组件</span><span class="sxs-lookup"><span data-stu-id="3e836-110">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="3e836-111">呼叫寄存需要以下组件：</span><span class="sxs-lookup"><span data-stu-id="3e836-111">Call Park requires the following components:</span></span>

  - <span data-ttu-id="3e836-112">应用程序服务</span><span class="sxs-lookup"><span data-stu-id="3e836-112">Application service</span></span>

  - <span data-ttu-id="3e836-113">Call Park 应用程序</span><span class="sxs-lookup"><span data-stu-id="3e836-113">Call Park application</span></span>

<span data-ttu-id="3e836-114">当您部署企业语音时，会自动安装这些组件。</span><span class="sxs-lookup"><span data-stu-id="3e836-114">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="3e836-115">如果希望呼叫者在呼叫寄存时可以听到音乐，还需要保持音乐文件。</span><span class="sxs-lookup"><span data-stu-id="3e836-115">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="3e836-116">在部署企业语音时，会自动安装默认的保持音乐文件。</span><span class="sxs-lookup"><span data-stu-id="3e836-116">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="3e836-117">可以使用自己的保持音乐文件替换默认文件。</span><span class="sxs-lookup"><span data-stu-id="3e836-117">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="3e836-118">呼叫寄存使用文件存储来保存音频文件。</span><span class="sxs-lookup"><span data-stu-id="3e836-118">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="3e836-119">呼叫寄存配置用户权限</span><span class="sxs-lookup"><span data-stu-id="3e836-119">Call Park Configuration User Rights</span></span>

<span data-ttu-id="3e836-120">您可以使用以下管理工具配置呼叫寄存：</span><span class="sxs-lookup"><span data-stu-id="3e836-120">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="3e836-121">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="3e836-121">Lync Server Control Panel</span></span>

  - <span data-ttu-id="3e836-122">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="3e836-122">Lync Server Management Shell</span></span>

<span data-ttu-id="3e836-123">您可以使用这些工具来设置呼叫寄存通道表，并配置呼叫寄存使用的其他设置。</span><span class="sxs-lookup"><span data-stu-id="3e836-123">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="3e836-124">配置呼叫寄存需要以下管理角色中的任何一个，具体取决于任务：</span><span class="sxs-lookup"><span data-stu-id="3e836-124">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="3e836-125">**CsVoiceAdministrator：** 此管理员角色可以创建、配置和管理所有与语音相关的设置和策略。</span><span class="sxs-lookup"><span data-stu-id="3e836-125">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="3e836-126">**CsUserAdministrator：** 此管理员角色可以在语音策略中启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="3e836-126">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="3e836-127">此管理员角色还具有对所有语音配置的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="3e836-127">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="3e836-128">**CsServerAdministrator：** 此管理员角色可以管理和监视服务器和服务并对其进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="3e836-128">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="3e836-129">**CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator、CsServerAdministrator 和 CsUserAdministrator 的所有任务。</span><span class="sxs-lookup"><span data-stu-id="3e836-129">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e836-130">有关管理权限的详细信息，请参阅规划文档中的在 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="3e836-130">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e836-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e836-131">See Also</span></span>


[<span data-ttu-id="3e836-132">在 Lync Server 2013 中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="3e836-132">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="3e836-133">在 Lync Server 2013 中规划呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="3e836-133">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

