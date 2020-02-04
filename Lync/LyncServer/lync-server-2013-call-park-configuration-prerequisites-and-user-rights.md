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
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013 中的呼叫寄存配置先决条件和用户权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-10_

呼叫寄存是在部署企业语音时默认安装的通话管理功能。 本主题介绍了在配置呼叫寄存以及执行配置任务所需的用户权限之前需要具备的准备工作。

<div>


> [!IMPORTANT]  
> Lync Server 2013 灾难恢复过程中不会备份呼叫寄存应用程序的自定义音乐保留文件，如果上载到该池的文件已损坏、损坏或清除，这些文件将会丢失。 始终保留已为呼叫寄存上载的自定义的保持音乐文件的单独备份副本。



</div>

本部分假设你已阅读与呼叫寄存有关的计划文档（请参阅[在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)）。

<div>

## <a name="call-park-configuration-prerequisites"></a>呼叫寄存配置先决条件

呼叫寄存需要以下组件：

  - 应用程序服务

  - 呼叫寄存应用程序

部署企业语音时，将自动安装这些组件。

如果希望呼叫者在呼叫暂停时听到音乐，也需要使用 "音乐保留" 文件。 部署企业语音时，将自动安装默认的 "保留音乐" 文件。 你可以将默认文件替换为你自己的保留音乐的文件。 通话寄存使用文件存储来保存音频文件。

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>呼叫寄存配置用户权限

可以使用以下管理工具配置呼叫寄存：

  - Lync Server 控制面板

  - Lync Server 命令行管理程序

使用这些工具设置 "呼叫驻留轨道" 表，并配置呼叫寄存使用的其他设置。

配置呼叫寄存需要以下任何管理角色，具体取决于任务：

  - **CsVoiceAdministrator：** 管理员角色可以创建、配置和管理所有语音相关设置和策略。

  - **CsUserAdministrator：** 管理员角色可以在语音策略中启用呼叫寄存。 此管理员角色还具有对所有语音配置的只读视图访问权限。

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

