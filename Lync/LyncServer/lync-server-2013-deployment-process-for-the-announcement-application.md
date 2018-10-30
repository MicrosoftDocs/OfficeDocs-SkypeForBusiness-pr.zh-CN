---
title: Lync Server 2013：通知应用程序的部署过程
TOCTitle: 通知应用程序的部署过程
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398545(v=OCS.15)
ms:contentKeyID: 49313233
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中通知应用程序的部署过程

 

_**上一次修改主题：** 2015-03-09_

本节概述 通知应用程序部署中涉及的步骤。必须先部署 企业语音，然后才能配置通知。在部署 企业语音时，将安装并启用 通知应用程序所需的组件。

### 通知部署过程

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
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">（可选）在 Lync Server 2013 中验证通知部署</a></p></td>
</tr>
</tbody>
</table>

