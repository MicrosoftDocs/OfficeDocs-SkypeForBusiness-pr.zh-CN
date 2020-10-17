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
ms.openlocfilehash: 46b15be02b48c5e3f95a9b05475bea42284ec275
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498789"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013 中的组内呼叫装货配置先决条件和用户权限

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

组呼叫装货是在部署企业语音时默认安装的呼叫管理功能。 本主题介绍在配置组内呼叫应答和执行配置任务所需的用户权限之前，您需要进行的操作。

本节假定您已阅读与组内呼叫应答相关的规划文档 (请参阅 [在 Lync Server 2013) 中规划组内呼叫装货](lync-server-2013-planning-for-group-call-pickup.md) 。

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>组呼叫装货配置先决条件

组呼叫应答需要以下组件：

  - 应用程序服务

  - Call Park 应用程序

当您部署企业语音时，会自动安装这些组件。

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>组呼叫装货配置用户权限

您可以使用以下管理工具配置组呼叫装货：

  - Lync Server 命令行管理程序

  - SEFAUtil 资源工具包工具

使用 Lync Server 命令行管理程序可以在呼叫寄存通道表中创建和管理呼叫应答组。 使用 SEFAUtil 资源工具包工具分配呼叫应答组并为用户启用组呼叫应答，或为用户禁用组呼叫挑选。

配置组呼叫应答需要以下管理角色中的任何一个，具体取决于任务：

  - **CsVoiceAdministrator：** 此管理员角色可以创建、配置和管理所有与语音相关的设置和策略。

  - **CsUserAdministrator：** 此管理员角色可以为用户启用组呼叫装货。 此管理员角色还具有对所有语音配置的只读访问权限。

  - **CsServerAdministrator：** 此管理员角色可以管理和监视服务器和服务并对其进行故障排除。

  - **CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator、CsServerAdministrator 和 CsUserAdministrator 的所有任务。

<div>


> [!NOTE]
> 有关管理权限的详细信息，请参阅规划文档中的在 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A> 。



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

