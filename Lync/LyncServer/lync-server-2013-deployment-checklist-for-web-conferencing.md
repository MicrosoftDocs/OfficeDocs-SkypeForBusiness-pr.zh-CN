---
title: 适用于 web 会议的 Lync Server 2013 部署清单
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
ms.openlocfilehash: 8c20bd593e11f032ba0a0ed852a50b6d417fa604
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531089"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="9b69a-102">Lync Server 2013 中的 web 会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="9b69a-102">Deployment checklist for web conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b69a-103">_**上次修改的主题：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="9b69a-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="9b69a-104">与其他 Lync Server 2013 组件的部署一样，部署 web 会议需要使用拓扑生成器创建并发布包含会议的拓扑。</span><span class="sxs-lookup"><span data-stu-id="9b69a-104">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="9b69a-105">部署顺序</span><span class="sxs-lookup"><span data-stu-id="9b69a-105">Deployment Sequence</span></span>

<span data-ttu-id="9b69a-106">您可以在部署初始拓扑的同时部署会议，也可以在部署了至少一个前端池或 Standard Edition server 之后部署会议。</span><span class="sxs-lookup"><span data-stu-id="9b69a-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="9b69a-107">会议部署过程</span><span class="sxs-lookup"><span data-stu-id="9b69a-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="9b69a-108">下表提供在现有拓扑中部署会议所需步骤的概述。</span><span class="sxs-lookup"><span data-stu-id="9b69a-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b69a-109">阶段</span><span class="sxs-lookup"><span data-stu-id="9b69a-109">Phase</span></span></th>
<th><span data-ttu-id="9b69a-110">步骤</span><span class="sxs-lookup"><span data-stu-id="9b69a-110">Steps</span></span></th>
<th><span data-ttu-id="9b69a-111">角色和组成员身份</span><span class="sxs-lookup"><span data-stu-id="9b69a-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="9b69a-112">文档</span><span class="sxs-lookup"><span data-stu-id="9b69a-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b69a-113"><strong>安装必备软硬件</strong></span><span class="sxs-lookup"><span data-stu-id="9b69a-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="9b69a-114">会议在前端池和 Standard Edition 服务器中的前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="9b69a-114">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="9b69a-115">除了需要安装这些服务器外，没有额外的软硬件要求。</span><span class="sxs-lookup"><span data-stu-id="9b69a-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9b69a-116">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps Server 处理 PowerPoint 演示文稿的共享和呈现。</span><span class="sxs-lookup"><span data-stu-id="9b69a-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="9b69a-117">有关安装和配置 Office Web Apps Server 的信息，请参阅 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">配置与 Office Web Apps server 和 Lync Server 2013 的集成</A>。</span><span class="sxs-lookup"><span data-stu-id="9b69a-117">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="9b69a-118">属于本地 Administrators 组成员的域用户</span><span class="sxs-lookup"><span data-stu-id="9b69a-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="9b69a-119">可支持性文档中<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a></span><span class="sxs-lookup"><span data-stu-id="9b69a-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="9b69a-120">可支持性文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a></span><span class="sxs-lookup"><span data-stu-id="9b69a-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="9b69a-121">在规划文档中<a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a>。</span><span class="sxs-lookup"><span data-stu-id="9b69a-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="9b69a-122">在规划文档中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中存档的技术要求</a>。</span><span class="sxs-lookup"><span data-stu-id="9b69a-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b69a-123"><strong>创建相应的内部拓扑以支持会议</strong></span><span class="sxs-lookup"><span data-stu-id="9b69a-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="9b69a-124">运行拓扑生成器以将会议添加到拓扑，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="9b69a-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="9b69a-125">要定义拓扑，需具有本地 Users 组成员的帐户</span><span class="sxs-lookup"><span data-stu-id="9b69a-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="9b69a-126">若要发布拓扑，该帐户是 Domain Admins 组和 RTCUniversalServerAdmins 组的成员，并且具有对用于 Lync Server 2013 文件 (存储的文件共享上的完全控制权限 (读/写/修改) ，以便拓扑生成器可以配置所需的 Dacl) </span><span class="sxs-lookup"><span data-stu-id="9b69a-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="9b69a-127">在部署文档中<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">的 Lync Server 2013 拓扑生成器中定义和配置拓扑</a>。</span><span class="sxs-lookup"><span data-stu-id="9b69a-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b69a-128"><strong>配置会议策略和支持</strong></span><span class="sxs-lookup"><span data-stu-id="9b69a-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="9b69a-129">使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序配置会议设置。</span><span class="sxs-lookup"><span data-stu-id="9b69a-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="9b69a-130">RTCUniversalServerAdmins group ( Windows PowerShell 仅) 或将用户分配到 [] 或 CSAdministrator 角色</span><span class="sxs-lookup"><span data-stu-id="9b69a-130">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="9b69a-131"><a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的会议策略</a> 在操作文档中。</span><span class="sxs-lookup"><span data-stu-id="9b69a-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9b69a-132">Lync Server 2013 现在包含 **MaxUploadFileSizeMb** 设置，该设置限制了会议过程中可上载的文件的大小。</span><span class="sxs-lookup"><span data-stu-id="9b69a-132">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="9b69a-133">此设置的默认值是 500 MB。</span><span class="sxs-lookup"><span data-stu-id="9b69a-133">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="9b69a-134">您可以使用 **Set-CsConferencingConfiguration** cmdlet 调整 **MaxUploadFileSizeMb**。</span><span class="sxs-lookup"><span data-stu-id="9b69a-134">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="9b69a-135">**MaxUploadFileSizeMb** 不限制 Lync Web App 的文件上载设置。</span><span class="sxs-lookup"><span data-stu-id="9b69a-135">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="9b69a-136">将 Lync Web App 的文件大小上传限制设置为大约30MB，并由 IIS web.config 文件：/DataCollabWeb/Int \[ Ext \] /Handler/web.config 进行控制。若要配置 Lync Web App 的文件大小上载限制，请更新 `maxRequestLength` 并 `maxAllowedContentLength` 在 web.config 文件中，如下所示。</span><span class="sxs-lookup"><span data-stu-id="9b69a-136">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="9b69a-137">您必须更新每台前端服务器的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="9b69a-137">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

