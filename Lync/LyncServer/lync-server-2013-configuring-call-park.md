---
title: Lync Server 2013：配置呼叫寄存
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
ms.openlocfilehash: 750ea65da2b5507099f097b31044673c474bfc7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="ddc00-102">在 Lync Server 2013 中配置呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="ddc00-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddc00-103">_**主题上次修改时间：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="ddc00-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="ddc00-104">"呼叫驻留" 使企业语音用户可以通过一条电话将呼叫置于保持状态，然后通过从任何电话拨入内部号码（称为呼叫公园*轨道*），稍后检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="ddc00-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="ddc00-105">当部署企业语音时，将在前端服务器或标准版服务器上自动安装和启用调用寄存使用的组件。</span><span class="sxs-lookup"><span data-stu-id="ddc00-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ddc00-106">但是，你必须先配置呼叫寄存，然后才能向用户提供。</span><span class="sxs-lookup"><span data-stu-id="ddc00-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="ddc00-107">本部分将指导你完成通话寄存的配置。</span><span class="sxs-lookup"><span data-stu-id="ddc00-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ddc00-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="ddc00-108">In This Section</span></span>

  - [<span data-ttu-id="ddc00-109">Lync Server 2013 中的呼叫寄存配置先决条件和用户权限</span><span class="sxs-lookup"><span data-stu-id="ddc00-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="ddc00-110">Lync Server 2013 中的呼叫寄存的部署过程</span><span class="sxs-lookup"><span data-stu-id="ddc00-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="ddc00-111">在 Lync Server 2013 中配置呼叫寄存通道表</span><span class="sxs-lookup"><span data-stu-id="ddc00-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="ddc00-112">在 Lync Server 2013 中配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="ddc00-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="ddc00-113">在 Lync Server 2013 中自定义呼叫寄存音乐处于暂停状态</span><span class="sxs-lookup"><span data-stu-id="ddc00-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="ddc00-114">在 Lync Server 2013 中为用户启用呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="ddc00-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="ddc00-115">在 Lync Server 2013 中验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="ddc00-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="ddc00-116">可选在 Lync Server 2013 中验证呼叫寄存部署</span><span class="sxs-lookup"><span data-stu-id="ddc00-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

