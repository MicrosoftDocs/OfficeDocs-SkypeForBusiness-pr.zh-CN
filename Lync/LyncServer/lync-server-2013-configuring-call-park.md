---
title: Lync Server 2013：配置呼叫寄存
description: Lync Server 2013：配置呼叫寄存。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2708f26fae5706afc31aa195b9fdb82536247b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568748"
---
# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="a3ba1-103">在 Lync Server 2013 中配置呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="a3ba1-103">Configuring Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3ba1-104">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="a3ba1-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="a3ba1-105">通过呼叫寄存，企业语音用户可以将呼叫置于保持状态，然后在稍后通过拨打来自任何电话的呼叫寄存 *轨道*)  (的内部号码来检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="a3ba1-105">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="a3ba1-106">在部署企业语音时，会自动在前端服务器或 Standard Edition 服务器上安装和启用呼叫寄存使用的组件。</span><span class="sxs-lookup"><span data-stu-id="a3ba1-106">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a3ba1-107">但是，您必须先配置呼叫寄存，然后才可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="a3ba1-107">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="a3ba1-108">本部分将指导您完成呼叫寄存的配置。</span><span class="sxs-lookup"><span data-stu-id="a3ba1-108">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a3ba1-109">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a3ba1-109">In This Section</span></span>

  - [<span data-ttu-id="a3ba1-110">在 Lync Server 2013 中呼叫寄存配置先决条件和用户权限</span><span class="sxs-lookup"><span data-stu-id="a3ba1-110">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="a3ba1-111">Lync Server 2013 中呼叫寄存的部署过程</span><span class="sxs-lookup"><span data-stu-id="a3ba1-111">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="a3ba1-112">在 Lync Server 2013 中配置呼叫寄存通道表</span><span class="sxs-lookup"><span data-stu-id="a3ba1-112">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="a3ba1-113">在 Lync Server 2013 中配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="a3ba1-113">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="a3ba1-114">在 Lync Server 2013 中自定义呼叫寄存暂停音乐</span><span class="sxs-lookup"><span data-stu-id="a3ba1-114">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="a3ba1-115">在 Lync Server 2013 中为用户启用呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="a3ba1-115">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="a3ba1-116">在 Lync Server 2013 中验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="a3ba1-116">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="a3ba1-117"> (可选) 在 Lync Server 2013 中验证呼叫寄存部署</span><span class="sxs-lookup"><span data-stu-id="a3ba1-117">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

