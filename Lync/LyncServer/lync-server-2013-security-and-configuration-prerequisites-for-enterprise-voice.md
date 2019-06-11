---
title: 企业语音安全性和配置先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d06cdb4c679d1a40eb5c6fa0e8cf837ec8d2e332
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="6fbc2-102">Lync Server 2013 中的企业语音的安全和配置先决条件</span><span class="sxs-lookup"><span data-stu-id="6fbc2-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fbc2-103">_**主题上次修改时间:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6fbc2-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6fbc2-104">验证你的基础结构是否满足以下安全性、用户配置以及特定于方案的硬件先决条件。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="6fbc2-105">管理权限和证书基础结构</span><span class="sxs-lookup"><span data-stu-id="6fbc2-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="6fbc2-106">请确保你的环境配置有以下管理用户组和证书基础结构, 以便在企业语音部署过程中使用。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="6fbc2-107">部署企业语音的管理员应是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="6fbc2-108">执行配置任务的管理员必须具有足够的权限：</span><span class="sxs-lookup"><span data-stu-id="6fbc2-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="6fbc2-109">**CsVoiceAdministrator：** 此管理员角色可以执行语音配置任务、管理语音应用程序以及将语音策略分配给最终用户。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="6fbc2-p101">**CsUserAdministrator：** 此管理员角色可以管理用户属性，如为用户启用企业语音。此管理员角色还可以分配每用户策略（存档策略例外）、移动用户以及管理公用区域电话和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="6fbc2-112">**CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6fbc2-113">委派使更多管理员能够参与 Lync 服务器部署, 而无需打开对资源的不必要的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="6fbc2-114">使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6fbc2-115">有关 Lync Server 中的证书要求的详细信息, 请参阅规划文档中<A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 的证书基础结构要求</A>。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="6fbc2-116">用户配置</span><span class="sxs-lookup"><span data-stu-id="6fbc2-116">User Configuration</span></span>

<span data-ttu-id="6fbc2-117">如果在前端部署期间使用每个前端池或标准版服务器 collocated 中介服务器, 则在安装这些服务器角色的文件期间会自动配置企业语音所需的用户设置。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="6fbc2-118">如果此时你新部署企业语音工作负荷, 则在开始部署过程之前, 请为计划启用企业语音的每个用户指定一个主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="6fbc2-119">作为管理员，应确保此号码是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="6fbc2-120">实现之前, 必须对所有主要电话号码进行标准化 (格式正确), 并使用 Lync Server 控制面板将其复制到每个用户的**行 URI**属性。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6fbc2-121">有关企业语音部署所需的主要电话号码的示例, 请参阅规划文档中的 "lync server 2013 中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">拨号计划和规范规则</A>" 一节中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">拨号计划和规范化2013规则</A>。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="6fbc2-122">后续步骤: 安装文件或配置 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="6fbc2-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="6fbc2-123">验证企业语音的软件和环境先决条件后, 您可以使用以下内容之一:</span><span class="sxs-lookup"><span data-stu-id="6fbc2-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="6fbc2-124">按照在[Lync server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)中所述, 安装中介服务器, 但仅当你希望部署独立的中介服务器或池时, 才需要部署独立的中介服务器或池, 因为已将中介服务器作为前端池或标准的一部分进行安装Collocated 版服务器部署过程。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="6fbc2-125">或者, 开始配置设置以路由企业语音用户的呼叫, 如在[Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="6fbc2-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

