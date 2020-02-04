---
title: 企业语音安全性和配置先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的企业语音的安全和配置先决条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-18_

验证你的基础结构是否满足以下安全性、用户配置以及特定于方案的硬件先决条件。

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>管理权限和证书基础结构

请确保你的环境配置有以下管理用户组和证书基础结构，以便在企业语音部署过程中使用。

  - 部署企业语音的管理员应是 RTCUniversalServerAdmins 组的成员。

  - 执行配置任务的管理员必须具有足够的权限：
    
      - **CsVoiceAdministrator：** 此管理员角色可以执行语音配置任务、管理语音应用程序以及将语音策略分配给最终用户。
    
      - **CsUserAdministrator：** 此管理员角色可以管理用户属性，如为用户启用企业语音。此管理员角色还可以分配每用户策略（存档策略例外）、移动用户以及管理公用区域电话和模拟设备。
    
      - **CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。
    
    <div>
    

    > [!NOTE]
    > 委派使更多管理员能够参与 Lync 服务器部署，而无需打开对资源的不必要的访问权限。

    
    </div>

  - 使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。
    
    <div>
    

    > [!NOTE]
    > 有关 Lync Server 中的证书要求的详细信息，请参阅规划文档中<A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 的证书基础结构要求</A>。

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>用户配置

如果在前端部署期间使用每个前端池或标准版服务器 collocated 中介服务器，则在安装这些服务器角色的文件期间会自动配置企业语音所需的用户设置。

如果此时你新部署企业语音工作负荷，则在开始部署过程之前，请为计划启用企业语音的每个用户指定一个主要电话号码。 作为管理员，应确保此号码是唯一的。 实现之前，必须对所有主要电话号码进行标准化（格式正确），并使用 Lync Server 控制面板将其复制到每个用户的**行 URI**属性。

<div>


> [!NOTE]
> 有关企业语音部署所需的主要电话号码的示例，请参阅规划文档中的 "lync server 2013 中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">拨号计划和规范规则</A>" 一节中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">拨号计划和规范化2013规则</A>。



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>后续步骤：安装文件或配置 PSTN 连接

验证企业语音的软件和环境先决条件后，您可以使用以下内容之一：

  - 安装中介服务器，如在[Lync server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)中所述，但仅当你希望部署独立的中介服务器或池时，因为在 collocated 时，将中介服务器作为前端池或标准版服务器部署过程的一部分安装。

  - 或者，开始配置设置以路由企业语音用户的呼叫，如在[Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)中所述。

</div>

</div>

<span> </span>

</div>

</div>

</div>

