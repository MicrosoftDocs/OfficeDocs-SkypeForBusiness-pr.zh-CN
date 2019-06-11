---
title: Lync Server 2013：响应组配置权限和先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Lync Server 2013 中的响应组配置权限和先决条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-05_

响应组是企业语音呼叫管理功能。 本主题介绍了在可以配置响应组以及执行配置任务所需的管理凭据和权限之前需要具备的准备工作。

本部分假设你已阅读与响应组相关的计划文档。 有关详细信息, 请参阅规划文档中[Lync Server 2013 中的 "规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)"。

<div>

## <a name="configuration-tools-and-administrative-roles"></a>配置工具和管理角色

可以使用以下管理工具配置响应组:

  - Lync Server 控制面板

  - 响应组配置工具

  - Lync Server 命令行管理程序

若要配置响应组，您必须至少成为以下管理角色之一的成员：


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Active Directory 安全组 (1)</strong></p></td>
<td><p>创建工作流</p></td>
<td><p>分派管理者</p></td>
<td><p>创建/分派代理、队列</p></td>
<td><p>创建/管理假日和工作时间</p></td>
<td><p>激活/停用工作流</p></td>
<td><p>配置工作流（IVR 或智能寻线）</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√(2)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> Active Directory 域服务用户对象必须是所列的指定 Active directory 安全组的成员。 具有将用户添加到安全组的相应权限的管理员或其他委派的 Active Directory 组成员 (例如管理员、帐户操作员) 必须将用户对象添加到列出的安全组或组中, 以便用户能够执行列出的函数。 <STRONG>(2)</STRONG>仅适用于 CsResponseGroupAdministrator 分配给 CsResponseGroupManager 的工作流。 <STRONG>(3)</STRONG>响应组管理器可以将 CsResponseGroupManager 的另一个成员分配给当前管理器已管理的工作流。 <STRONG>(4)</STRONG> CsViewOnlyAdministrator 仅可运行动词 "Get" Lync Server Management Shell cmdlet。



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>响应组配置先决条件

响应组需要以下组件:

  - 应用程序服务

  - 响应组应用程序

  - 语言包

  - 文件存储（用于保存音频文件）

  - Web 服务 (包括响应组配置工具和代理的登录和注销控制台)

在部署企业语音时, 默认情况下会安装所有这些组件。

在配置响应组之前, 可能需要执行以下任务:

  - 为 Lync Server 2013 和企业语音启用用户。

  - 修改配置文件以符合联邦信息处理标准 (FIPS)。

  - 修改数据库排序规则以支持队列名称和代理组名称的 Yi、Meng 和 Zang 字符。

<div>

## <a name="enabling-users"></a>启用用户

配置响应组的第一步是创建代理组。 在创建代理组之前, 必须启用将用作 Lync Server 2013 和企业语音的 "响应" 组的代理用户。 为 Lync Server 2013 启用用户通常是企业版 server 或标准版服务器部署中的一个步骤。 有关为 Lync Server 2013 启用用户的详细信息, 请参阅[禁用或重新启用 Lync server 2013 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。 为企业语音启用用户通常是企业语音部署中的一个步骤。 有关详细信息, 请参阅[在 Lync Server 2013 中启用企业语音用户](lync-server-2013-enable-users-for-enterprise-voice.md)。

</div>

<div>

## <a name="complying-with-fips-requirements"></a>符合 FIPS 要求

仅当您的组织需要符合联邦信息处理标准 (FIPS) 时，本节才适用。

要符合 FIPS，安装 Web 服务后需要修改应用程序级别 Web.config 文件，以使用不同的加密算法。 需要指定 ASP.NET 使用三重数据加密标准 (3DES) 算法，来处理视图状态数据。 对于响应组应用程序, 此要求适用于响应组配置工具和代理登录和注销控制台。 有关此要求的详细信息, 请参阅 Microsoft 知识库文章 911722, 当你访问在从 ASP.NET 1.1 升级到 ASP.NET 2.0 后启用了 ViewState 的 ASP.NET 网页时, 你可能会收到错误消息[http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)。

若要修改 Web.config 文件，请执行以下操作：

1.  在文本编辑器（如记事本）中，打开应用程序级别 Web.config 文件。

2.  在 web.config 文件中, 找到相应的`<system.web>`部分。

3.  将以下`<machineKey>`部分添加到 "" `<system.web>`部分中:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  保存 Web.config 文件。

5.  通过在命令提示符处运行以下命令, 重启 Internet 信息服务 (IIS) 服务:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>支持 Yi、Meng 和 Zang 字符

仅当您的组织需要支持 Yi、Meng 或 Zang 字符时，本节才适用。

<div>


> [!NOTE]  
> 有关 Yi、Meng 和 Zang 字符的内容以及它们对部署很重要的原因的信息, 请参阅 GB18030 字符集<A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>的相关信息。



</div>

要支持 Yi、Meng 或 Zang 字符，需要修改 Rgsconfig 数据库的排序规则。在每个 Rgsconfig 数据库的下列各表中更改“Name”**** 列的排序规则：

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

对于 SQL Server 2008 R2 和 SQL Server 2012, 请使用拉丁文\_常规\_100 (区分重音) 排序规则。 如果使用此排序规则，则所有对象名称不区分大小写。

可以使用 Microsoft SQL Server Management Studio 来更改排序规则。 有关使用此工具的详细信息, 请参阅 "使用 SQL Server Management Studio [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)"。 执行下列步骤可更改排序规则：

1.  确保 SQL Server Management Studio 配置为允许要求重新创建表的更改。 有关详细信息, 请参阅 "保存 (不允许)" 对话框[http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)。 有关设置列排序规则的详细信息, 请参阅 "如何: 设置列排序规则 (可视化数据库工具) [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)"。

2.  使用 Microsoft SQL Server Management Studio 连接到 Rgsconfig 数据库。

3.  在 Rgsconfig 数据库中查找要更改的表，右键单击该表，然后单击“设计”****。

4.  更改“名称”列**** 的排序规则并保存该表。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

