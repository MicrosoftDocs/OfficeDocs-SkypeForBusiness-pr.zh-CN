---
title: Lync Server 2013：响应组配置权限和先决条件
TOCTitle: 响应组配置权限和先决条件
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204840(v=OCS.15)
ms:contentKeyID: 49312667
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的响应组配置权限和先决条件

 

_**上一次修改主题：** 2016-12-08_

响应组是一种 企业语音呼叫管理功能。本主题介绍了在配置 响应组之前您需要拥有的工具以及执行配置任务所需的管理凭据和权限。

本节假定您已阅读与 响应组相关的规划文档。有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)。

## 配置工具和管理角色

可以使用以下管理工具配置 响应组：

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
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
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
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
<td><p>    √    </p></td>
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


> [!NOTE]  
> <strong>(1)</strong> Active Directory 域服务 用户对象必须是所列的指定 Active Directory 安全组的成员。管理员或其他具有向安全组中添加用户的适当权限的委托 Active Directory 组成员（例如，管理员、帐户操作员）必须向所列安全组或组中添加用户对象，用户才能执行所列功能。<strong>(2)</strong> 仅对于 CsResponseGroupAdministrator 已分派给 CsResponseGroupManager 的工作流。<strong>(3)</strong> 响应组管理员可将 CsResponseGroupManager 的其他成员分派给当前管理员已管理的工作流。<strong>(4)</strong> CsViewOnlyAdministrator 只能运行谓词“Get”Lync Server 命令行管理程序 cmdlet。



## 响应组配置先决条件

响应组需要以下组件：

  - 应用程序服务

  - 响应组应用程序

  - 语言包

  - 文件存储（用于保存音频文件）

  - Web 服务（包括 响应组配置工具和代理的登录和注销控制台）

在部署 企业语音时，默认情况下将安装所有这些组件。

在配置 响应组之前，您可能需要执行以下任务：

  - 为用户启用 Lync Server 2013 和 企业语音。

  - 修改配置文件以符合联邦信息处理标准 (FIPS)。

  - 修改数据库排序规则以支持队列名称和代理组名称的 Yi、Meng 和 Zang 字符。

## 启用用户

配置 响应组的第一步是创建代理组。在创建代理组之前，必须对即将成为 响应组代理的用户启用 Lync Server 2013 和 企业语音。为用户启用 Lync Server 2013 通常是 Enterprise Edition Server 或 Standard Edition Server 部署中的一个步骤。有关为用户启用 Lync Server 2013 的详细信息，请参阅 [禁用或重新启用 Lync Server 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。为用户启用 企业语音通常是 企业语音部署中的一个步骤。有关详细信息，请参阅 [在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)。

## 符合 FIPS 要求

仅当您的组织需要符合联邦信息处理标准 (FIPS) 时，本节才适用。

要符合 FIPS，安装 Web 服务后需要修改应用程序级别 Web.config 文件，以使用不同的加密算法。需要指定 ASP.NET 使用三重数据加密标准 (3DES) 算法，来处理视图状态数据。对于 响应组应用程序，此要求适用于 响应组配置工具以及代理登录和注销控制台。有关此要求的详细信息，请参阅 Microsoft 知识库文章 911722“从 ASP.NET 1.1 升级到 ASP.NET 2.0 后，访问启用了 ViewState 的 ASP.NET 网页时可能会收到错误消息”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)。

若要修改 Web.config 文件，请执行以下操作：

1.  在文本编辑器（如记事本）中，打开应用程序级别 Web.config 文件。

2.  在 Web.config 文件中，查找 `<system.web>` 部分。

3.  将以下 `<machineKey>` 部分添加到 `<system.web>` 部分：
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  保存 Web.config 文件。

5.  通过在命令提示符处运行以下命令来重新启动 Internet Information Services (IIS) 服务：
    
        iisreset

## 支持 Yi、Meng 和 Zang 字符

仅当您的组织需要支持 Yi、Meng 或 Zang 字符时，本节才适用。

> [!NOTE]  
> 有关 Yi、Meng 和 Zang 字符是什么以及它们对部署非常重要的原因的信息，请参阅有关 GB18030 字符集的信息 <a href="http://go.microsoft.com/fwlink/?linkid=240223%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=240223&amp;clcid=0x804</a>。



要支持 Yi、Meng 或 Zang 字符，需要修改 Rgsconfig 数据库的排序规则。在每个 Rgsconfig 数据库的下列各表中更改“Name”列的排序规则：

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

对于 SQL Server 2008 R2 或 SQL Server 2012，使用 Latin\_General\_100（区分重音）。如果使用此排序规则，则所有对象名称不区分大小写。

可以使用 Microsoft SQL Server Management Studio 来更改排序规则。有关使用此工具的详细信息，请参阅“使用 SQL Server Management Studio”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)。执行下列步骤可更改排序规则：

1.  确保 SQL Server Management Studio 配置为允许要求重新创建表的更改。有关详细信息，请参阅“"保存" （不允许）对话框”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)。有关设置列排序规则的详细信息，请参阅“如何设置列排序规则 (Visual Database Tools)”，网址为[http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)。

2.  使用 Microsoft SQL Server Management Studio 连接到 Rgsconfig 数据库。

3.  在 Rgsconfig 数据库中查找要更改的表，右键单击该表，然后单击 “设计”。

4.  更改 “名称”列的排序规则并保存该表。

