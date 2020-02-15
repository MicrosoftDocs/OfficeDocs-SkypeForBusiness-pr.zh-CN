---
title: Lync Server 2013：呼叫寄存配置先决条件和用户权限
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
ms.openlocfilehash: 19a677b7b1a76c0956b5edc663e8932716ce5fb6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="8412a-102">在 Lync Server 2013 中呼叫寄存配置先决条件和用户权限</span><span class="sxs-lookup"><span data-stu-id="8412a-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8412a-103">_**上次修改的主题：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="8412a-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="8412a-104">呼叫寄存是在部署企业语音时默认安装的呼叫管理功能。</span><span class="sxs-lookup"><span data-stu-id="8412a-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="8412a-105">本主题介绍在配置呼叫寄存以及执行配置任务所需的用户权限之前，您需要具备的功能。</span><span class="sxs-lookup"><span data-stu-id="8412a-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8412a-106">在 Lync Server 2013 灾难恢复过程中，不会备份呼叫寄存应用程序的自定义的 "保留时音乐" 文件，如果上载到该池的文件已损坏、损坏或清除，这些文件将会丢失。</span><span class="sxs-lookup"><span data-stu-id="8412a-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="8412a-107">始终为已为呼叫寄存上载的自定义的保留音乐文件保留一个单独的备份副本。</span><span class="sxs-lookup"><span data-stu-id="8412a-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="8412a-108">本节假定您已阅读与呼叫寄存相关的规划文档（请参阅[在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)）。</span><span class="sxs-lookup"><span data-stu-id="8412a-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="8412a-109">呼叫寄存配置必备组件</span><span class="sxs-lookup"><span data-stu-id="8412a-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="8412a-110">呼叫寄存需要以下组件：</span><span class="sxs-lookup"><span data-stu-id="8412a-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="8412a-111">应用程序服务</span><span class="sxs-lookup"><span data-stu-id="8412a-111">Application service</span></span>

  - <span data-ttu-id="8412a-112">Call Park 应用程序</span><span class="sxs-lookup"><span data-stu-id="8412a-112">Call Park application</span></span>

<span data-ttu-id="8412a-113">当您部署企业语音时，会自动安装这些组件。</span><span class="sxs-lookup"><span data-stu-id="8412a-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="8412a-114">如果希望呼叫者在呼叫寄存时可以听到音乐，还需要保持音乐文件。</span><span class="sxs-lookup"><span data-stu-id="8412a-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="8412a-115">在部署企业语音时，会自动安装默认的保持音乐文件。</span><span class="sxs-lookup"><span data-stu-id="8412a-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="8412a-116">可以使用自己的保持音乐文件替换默认文件。</span><span class="sxs-lookup"><span data-stu-id="8412a-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="8412a-117">呼叫寄存使用文件存储来保存音频文件。</span><span class="sxs-lookup"><span data-stu-id="8412a-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="8412a-118">呼叫寄存配置用户权限</span><span class="sxs-lookup"><span data-stu-id="8412a-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="8412a-119">您可以使用以下管理工具配置呼叫寄存：</span><span class="sxs-lookup"><span data-stu-id="8412a-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="8412a-120">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="8412a-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="8412a-121">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="8412a-121">Lync Server Management Shell</span></span>

<span data-ttu-id="8412a-122">您可以使用这些工具来设置呼叫寄存通道表，并配置呼叫寄存使用的其他设置。</span><span class="sxs-lookup"><span data-stu-id="8412a-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="8412a-123">配置呼叫寄存需要以下管理角色中的任何一个，具体取决于任务：</span><span class="sxs-lookup"><span data-stu-id="8412a-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="8412a-124">**CsVoiceAdministrator：** 此管理员角色可以创建、配置和管理所有与语音相关的设置和策略。</span><span class="sxs-lookup"><span data-stu-id="8412a-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="8412a-125">**CsUserAdministrator：** 此管理员角色可以在语音策略中启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="8412a-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="8412a-126">此管理员角色还具有对所有语音配置的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="8412a-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="8412a-127">**CsServerAdministrator：** 此管理员角色可以管理和监视服务器和服务并对其进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="8412a-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="8412a-128">**CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator、CsServerAdministrator 和 CsUserAdministrator 的所有任务。</span><span class="sxs-lookup"><span data-stu-id="8412a-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8412a-129">有关管理权限的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。</span><span class="sxs-lookup"><span data-stu-id="8412a-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8412a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8412a-130">See Also</span></span>


[<span data-ttu-id="8412a-131">在 Lync Server 2013 中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="8412a-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="8412a-132">在 Lync Server 2013 中规划呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="8412a-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

