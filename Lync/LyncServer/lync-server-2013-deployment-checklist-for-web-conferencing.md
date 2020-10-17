---
title: 适用于 web 会议的 Lync Server 2013 部署清单
description: 适用于 web 会议的 Lync Server 2013 部署清单。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6194cb71af268a45dc5c142c1814d8c1ef15c09e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562178"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 web 会议的部署清单

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-30_

与其他 Lync Server 2013 组件的部署一样，部署 web 会议需要使用拓扑生成器创建并发布包含会议的拓扑。

<div>

## <a name="deployment-sequence"></a>部署顺序

您可以在部署初始拓扑的同时部署会议，也可以在部署了至少一个前端池或 Standard Edition server 之后部署会议。

</div>

<div>

## <a name="conferencing-deployment-process"></a>会议部署过程

下表提供在现有拓扑中部署会议所需步骤的概述。


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
<th>角色和组成员身份</th>
<th>文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安装必备软硬件</strong></p></td>
<td><p>会议在前端池和 Standard Edition 服务器中的前端服务器上运行。 除了需要安装这些服务器外，没有额外的软硬件要求。</p>
<div>

> [!NOTE]  
> Lync Server 2013 使用 Office Web Apps 和 Office Web Apps Server 处理 PowerPoint 演示文稿的共享和呈现。 有关安装和配置 Office Web Apps Server 的信息，请参阅 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">配置与 Office Web Apps server 和 Lync Server 2013 的集成</A>。


</div></td>
<td><p>属于本地 Administrators 组成员的域用户</p></td>
<td><p>可支持性文档中<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a></p>
<p>可支持性文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a></p>
<p>在规划文档中<a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a>。</p>
<p>在规划文档中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中存档的技术要求</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>创建相应的内部拓扑以支持会议</strong></p></td>
<td><p>运行拓扑生成器以将会议添加到拓扑，然后发布拓扑。</p></td>
<td><p>要定义拓扑，需具有本地 Users 组成员的帐户</p>
<p>若要发布拓扑，该帐户是 Domain Admins 组和 RTCUniversalServerAdmins 组的成员，并且具有对用于 Lync Server 2013 文件 (存储的文件共享上的完全控制权限 (读/写/修改) ，以便拓扑生成器可以配置所需的 Dacl) </p></td>
<td><p>在部署文档中<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">的 Lync Server 2013 拓扑生成器中定义和配置拓扑</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>配置会议策略和支持</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序配置会议设置。</p></td>
<td><p>RTCUniversalServerAdmins group ( Windows PowerShell 仅) 或将用户分配到 [] 或 CSAdministrator 角色</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的会议策略</a> 在操作文档中。</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 现在包含 **MaxUploadFileSizeMb** 设置，该设置限制了会议过程中可上载的文件的大小。 此设置的默认值是 500 MB。 您可以使用 **Set-CsConferencingConfiguration** cmdlet 调整 **MaxUploadFileSizeMb**。

**MaxUploadFileSizeMb** 不限制 Lync Web App 的文件上载设置。 将 Lync Web App 的文件大小上传限制设置为大约30MB，并由 IIS web.config 文件：/DataCollabWeb/Int \[ Ext \] /Handler/web.config 进行控制。若要配置 Lync Web App 的文件大小上载限制，请更新 `maxRequestLength` 并 `maxAllowedContentLength` 在 web.config 文件中，如下所示。

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

您必须更新每台前端服务器的 web.config 文件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

