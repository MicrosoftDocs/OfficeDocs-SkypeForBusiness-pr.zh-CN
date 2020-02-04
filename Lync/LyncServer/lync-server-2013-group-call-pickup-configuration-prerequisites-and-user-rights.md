---
title: 组呼叫装货配置先决条件和用户权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed2a44ccd1730de2ebede4b08c1a4d3d7e0da9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>组呼叫在 Lync Server 2013 中的装货配置先决条件和用户权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-01-30_

组呼叫装货是在部署企业语音时默认安装的通话管理功能。 本主题介绍了在配置组呼叫前需要准备的内容以及执行配置任务所需的用户权限。

本部分假设你已阅读与组呼叫分拣相关的计划文档（请参阅[在 Lync Server 2013 中规划组呼叫装货](lync-server-2013-planning-for-group-call-pickup.md)）。

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>组呼叫装货配置先决条件

群组呼叫分拣需要以下组件：

  - 应用程序服务

  - 呼叫寄存应用程序

部署企业语音时，将自动安装这些组件。

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>组呼叫装货配置用户权限

你可以使用以下管理工具配置组呼叫装货：

  - Lync Server 命令行管理程序

  - SEFAUtil 资源工具包工具

使用 Lync Server Management Shell 在 "呼叫公园轨道" 表中创建和管理呼叫装货组。 使用 SEFAUtil 资源工具包工具分配呼叫装货组，并为用户启用组呼叫分拣，或为用户禁用组呼叫装货。

配置组呼叫分拣需要以下任何管理角色，具体取决于任务：

  - **CsVoiceAdministrator：** 管理员角色可以创建、配置和管理所有语音相关设置和策略。

  - **CsUserAdministrator：** 管理员角色可以为用户启用组呼叫装货。 此管理员角色还具有对所有语音配置的只读视图访问权限。

  - **CsServerAdministrator：** 此管理员角色可以管理和监视服务器和服务并对其进行故障排除。

  - **CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator、CsServerAdministrator 和 CsUserAdministrator 的所有任务。

<div>


> [!NOTE]
> 有关管理权限的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)  


[在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

