---
title: Lync Server 2013：准备 Active Directory 域服务
TOCTitle: 准备 Active Directory 域服务
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398607(v=OCS.15)
ms:contentKeyID: 49313334
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中准备 Active Directory 域服务

 

_**上一次修改主题：** 2016-12-08_

在 Lync Server 2013 中，可以使用 Lync Server 部署向导准备 Active Directory 域服务，或者直接使用 Lync Server 命令行管理程序 cmdlet。也可以直接在域控制器上使用 ldifde.exe 命令行工具，相关信息将在本主题后面的内容中进行介绍。

Lync Server 部署向导可指导您完成每一项 Active Directory 准备任务。部署向导运行 Lync Server 命令行管理程序 cmdlet。对于单域、单林拓扑或其他类似拓扑的环境，此工具很有用。

> [!IMPORTANT]
> 可以在域控制器运行某些 32 位版本操作系统的林或域中部署 Lync Server（有关详细信息，请参阅 <a href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync Server 2013 的 Active Directory 基础结构要求</a>）。但是，不能在这些环境中使用 Lync Server 部署向导运行架构、林和域准备，因为部署向导和支持文件仅提供了 64 位版本。可以改为在 32 位域控制器上使用 ldifde.exe 和 associated .ldf 文件来准备架构、林和域。请参阅本主题稍后的“使用 Cmdlet 和 Ldifde.exe”一节。


可以使用 Lync Server 命令行管理程序 cmdlet 远程运行任务，也可以将其用于更为复杂的环境。

## Active Directory 准备先决条件

必须在运行 Windows Server 2012、Windows Server 2012 R2 或 Windows Server 2008 R2 SP1（64 位）的计算机上运行 Active Directory 准备步骤。Active Directory 准备需要使用 Lync Server 命令行管理程序 和 OCSCore。

运行 Active Directory 准备任务需要以下组件：

  - Lync Server 核心组件 (OCScore.msi)
    
    > [!NOTE]  
	> 如果计划使用 Lync Server 命令行管理程序 执行 Active Directory 准备，则必须先运行 Lync Server 部署向导以安装核心组件。
    


  - Microsoft .NET Framework 4.5
    
    > [!NOTE]  
	> 对于 Windows Server 2012 和 Windows Server 2012 R2，将使用服务器管理器安装和激活 .NET Framework 4.5。有关详细信息，请参阅<a href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 的其他软件要求</a>中的“Microsoft .NET Framework 4.5”。对于 Windows Server 2008 R2，请从 Microsoft 网站下载 <a href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</a> 并安装。
    


  - 远程服务器管理工具 (RSAT)
    
    > [!NOTE]  
	> 如果在成员服务器而不是域控制器上运行 Active Directory 准备步骤，则需要使用某些 RSAT 工具。从服务器管理器中的“AD DS 和 AD LDS 工具”节点安装 AD DS 管理单元、命令行工具和 Windows PowerShell 的 Active Directory 模块。
    


  - Microsoft Visual C++ 11 可再发行软件包
    
    > [!NOTE]  
	> 如果计算机中尚未安装此必备软件，安装程序会提示您进行安装。将为您提供此软件包，不需要单独购买。
    


  - Windows PowerShell 3.0（64 位）
    
    对于 Windows Server 2012 和 Windows Server 2012 R2，Windows PowerShell 3.0 应包含在 Lync Server 2013 安装中。对于 Windows Server 2008 R2，需要安装 Windows PowerShell 3.0 或升级到该版本。有关详细信息，请参阅[为 Lync Server 2013 安装 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)

## 管理员权限和角色

下表显示了每个 Active Directory 准备任务需要的管理权限和角色。

### Active Directory 准备任务需要的用户权限

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>过程</th>
<th>权限或角色</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>架构准备</p></td>
<td><p>架构主机上目录林根级域的 Schema Admins 组成员和管理员权限</p></td>
</tr>
<tr class="even">
<td><p>林准备</p></td>
<td><p>林的 Enterprise Admins 组成员</p></td>
</tr>
<tr class="odd">
<td><p>域准备</p></td>
<td><p>指定域的 Enterprise Admins 或 Domain Admins 组成员</p></td>
</tr>
</tbody>
</table>


## Active Directory 准备 Cmdlet

下表将 Microsoft Office Communications Server 2007 R2 中用于准备 AD DS 的 Lync Server 命令行管理程序 cmdlet 与用于准备 AD DS 的 LcsCmd 命令进行了比较。

### Cmdlet 与 LcsCmd 比较

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


## 锁定的 Active Directory 要求

如果在组织中禁用了权限继承，或者必须禁用通过身份验证的用户权限，则在域准备期间还必须执行其他步骤。有关详细信息，请参阅 [在 Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

## 自定义容器权限

如果组织使用自定义容器代替三个内置容器（即“用户”、“计算机”和“域控制器”），则必须为 Authenticated Users 组授予自定义容器的读取权限。域准备需要具有容器的读取权限。有关详细信息，请参阅[为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)。

## 使用 Cmdlet 和 Ldifde.exe

Lync Server 部署向导中的“准备架构”步骤和 **Install-CsAdServerSchema** cmdlet 用于在运行 64 位操作系统的域控制器上扩展 Active Directory 架构。如果需要在运行 32 位操作系统的域控制器上扩展 Active Directory 架构，可以从成员服务器远程运行 **Install-CsAdServerSchema** cmdlet（推荐方法）。但是，如果需要直接在域控制器上运行架构准备，可以使用 Ldifde.exe 工具导入架构文件。Windows 操作系统的大多数版本均附带 Ldifde.exe 工具。

如果使用 Ldifde.exe 导入架构文件，则不管是从以前的版本迁移还是执行全新安装，都必须导入所有四个文件。必须按以下顺序导入这些文件：

1.  ExternalSchema.ldf

2.  ServerSchema.ldf

3.  BackCompatSchema.ldf

4.  VersionSchema.ldf

> [!NOTE]  
> 这四个 .ldf 文件位于安装介质或下载的 \Support\Schema 目录中。



要在充当架构主机的域控制器上使用 Ldifde.exe 导入这四个架构文件，请使用以下格式：

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

例如：

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

> [!NOTE]  
> 仅当以其他用户身份登录时才使用 b 参数。有关所需用户权限的详细信息，请参阅本主题前面的“管理员权限和角色”一节。



要在架构主机以外的域控制器上使用 Ldifde.exe 导入这四个架构文件，请使用以下格式：

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

有关使用 Ldifde 的详细信息，请参阅 Microsoft 知识库文章 237677“使用 LDIFDE 将目录对象导入或导出到 Active Directory”，网址为 [http://go.microsoft.com/fwlink/?linkid=132204\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=132204%26clcid=0x804)。

## 本节内容

  - [在 Lync Server 2013 中准备 Active Directory 架构](lync-server-2013-preparing-the-active-directory-schema.md)

  - [为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)

  - [为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)

