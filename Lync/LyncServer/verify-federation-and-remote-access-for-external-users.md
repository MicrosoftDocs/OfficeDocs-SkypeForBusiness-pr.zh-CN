---
title: 验证联盟和外部用户的远程访问
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a36e92849c59760f831cdebaf59906b546b01d7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="24db0-102">验证联盟和外部用户的远程访问</span><span class="sxs-lookup"><span data-stu-id="24db0-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24db0-103">_**上次修改的主题：** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="24db0-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="24db0-104">将联合身份验证路由转换为 Lync Server 2013 边缘服务器后，应执行一些功能测试，以验证联合身份验证是否按预期执行。</span><span class="sxs-lookup"><span data-stu-id="24db0-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="24db0-105">外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户。</span><span class="sxs-lookup"><span data-stu-id="24db0-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="24db0-106">测试外部用户和外部访问的连接</span><span class="sxs-lookup"><span data-stu-id="24db0-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="24db0-107">至少一个联盟域中的用户、Lync Server 2013 上的内部用户以及 Lync Server 2010 上的用户。</span><span class="sxs-lookup"><span data-stu-id="24db0-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="24db0-108">测试即时消息 (IM)、状态、音频/视频 (A/V) 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="24db0-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="24db0-109">您的组织支持的每个公共 IM 服务提供商的用户（已完成的设置）与 Lync server 2013 上的用户以及 Lync Server 2010 上的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="24db0-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="24db0-110">验证匿名用户是否能够加入会议。</span><span class="sxs-lookup"><span data-stu-id="24db0-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="24db0-111">在 lync server 2010 上托管的用户（使用远程用户访问（从 intranet 外部，但不使用 VPN 登录到 Lync Server 2010）以及 lync server 2013 上的用户以及 Lync Server 2010 上的用户。</span><span class="sxs-lookup"><span data-stu-id="24db0-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="24db0-112">测试 IM、状态、A/V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="24db0-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="24db0-113">在 lync server 2013 上托管的用户（使用远程用户访问（从 intranet 外部，但不使用 VPN 登录到 Lync Server 2013）以及 lync server 2013 上的用户以及 Lync Server 2010 上的用户。</span><span class="sxs-lookup"><span data-stu-id="24db0-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="24db0-114">测试 IM、状态、A/V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="24db0-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

