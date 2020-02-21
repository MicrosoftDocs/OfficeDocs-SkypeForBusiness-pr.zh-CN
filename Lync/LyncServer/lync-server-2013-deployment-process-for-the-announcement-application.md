---
title: Lync Server 2013：通知应用程序的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44fc32360fe7ffe1924fbc663709dd1f41cf4a36
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中的通知应用程序的部署过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

本节概述了部署通知应用程序所涉及的步骤。 您必须先部署企业语音，然后才能配置通知。 当您部署企业语音时，会安装并启用通知应用程序所需的组件。

### <a name="announcement-deployment-process"></a>通知部署过程

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>角色</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>配置通知设置</p></td>
<td><ul>
<li><p>通过录制并上载音频文件或使用文本到语音转换 (TTS) 来创建通知。</p></li>
<li><p>配置未分配号码表中的未分配号码范围，然后将其与相应的通知关联。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中创建通知</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">在 Lync Server 2013 中配置未分配号码表</a></p></td>
</tr>
<tr class="even">
<td><p>验证通知部署</p></td>
<td><p>通过侦听通知来进行测试以验证配置是否按预期工作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Optional在 Lync Server 2013 中验证通知部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

