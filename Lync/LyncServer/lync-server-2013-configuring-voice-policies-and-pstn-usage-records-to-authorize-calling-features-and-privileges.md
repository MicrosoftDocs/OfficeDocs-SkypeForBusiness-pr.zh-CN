---
title: Lync Server 2013：配置语音策略和 PSTN 用法记录以授权呼叫功能和权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies and PSTN usage records to authorize calling features and privileges
ms:assetid: 63f22010-a3d7-4cbd-86e8-6fc0e13c2b84
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398450(v=OCS.15)
ms:contentKeyID: 48184307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b9f7da3f8560ae0a897211405d686d9ed35101e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="06b20-102">在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限</span><span class="sxs-lookup"><span data-stu-id="06b20-102">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06b20-103">_**主题上次修改时间：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="06b20-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="06b20-104">*语音策略*支持一组呼叫功能，并关联一个或多个 PSTN 使用记录，以定义分配了该策略的用户的呼叫功能和权限。</span><span class="sxs-lookup"><span data-stu-id="06b20-104">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="06b20-105">语音策略作用域可以是*网站*（定义网络站点的默认功能和权限）或*用户*（定义要在每用户或组基础上分配的功能和权限）。</span><span class="sxs-lookup"><span data-stu-id="06b20-105">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis).</span></span> <span data-ttu-id="06b20-106">未分配到语音策略的用户将自动分配给全局策略，该策略是随产品一起安装的默认语音策略。</span><span class="sxs-lookup"><span data-stu-id="06b20-106">Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06b20-107">有关详细信息，请参阅规划文档中<A href="lync-server-2013-voice-policies.md">Lync Server 2013 中的语音策略</A>。</span><span class="sxs-lookup"><span data-stu-id="06b20-107">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="06b20-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="06b20-108">In This Section</span></span>

  - [<span data-ttu-id="06b20-109">在 Lync Server 2013 中创建语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="06b20-109">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="06b20-110">在 Lync Server 2013 中修改语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="06b20-110">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="06b20-111">在 Lync Server 2013 中配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="06b20-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

