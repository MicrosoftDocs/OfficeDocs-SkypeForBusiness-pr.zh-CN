---
title: Lync Server 2013：准备 Active Directory 域服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8abab29930e8b09d0642c84f1e02026d4c554637
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>在 Lync Server 2013 中准备 Active Directory 域服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-19_

在 Lync Server 2013 中，你可以使用 Lync Server 部署向导来准备 Active Directory 域服务，也可以直接使用 Lync Server Management Shell cmdlet。 您还可以直接在域控制器上使用 ldifde 命令行工具，如本主题后面部分所述。

Lync Server 部署向导将指导你完成每个 Active Directory 准备任务。 部署向导运行 Lync Server Management Shell cmdlet。 此工具对于具有单个域和单林拓扑或其他类似拓扑的环境很有用。

<div>


> [!IMPORTANT]  
> 你可以在域控制器运行32位版本的操作系统（有关详细信息，请参阅<A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync Server 2013 的 Active Directory 基础结构要求</A>）的林或域中部署 Lync 服务器。 但是，你无法使用 Lync Server 部署向导在这些环境中运行架构、林和域准备，因为部署向导和支持文件仅为64位。 而是可以在32位域控制器上使用 ldifde 和关联的 .ldf 文件来准备架构、林和域。 请参阅本主题后面部分的 "使用 Cmdlet 和 cscript.exe" 部分。



</div>

你可以使用 Lync Server Management Shell cmdlet 远程运行任务，也可以使用更复杂的环境运行任务。

<div>

## <a name="active-directory-preparation-prerequisites"></a>Active Directory 准备先决条件

必须在运行 Windows Server 2012、Windows Server 2012 R2 或 Windows Server 2008 R2 的计算机上运行 Active Directory 准备步骤（64）。 Active Directory 准备需要 Lync Server 命令行管理程序和 OCSCore。

要运行 Active Directory 准备任务，需要以下组件：

  - Lync Server 核心组件（OCScore）
    
    <div>
    

    > [!NOTE]  
    > 如果您计划将 Lync Server Management Shell 用于 Active Directory 准备，则必须首先运行 Lync Server 部署向导才能安装核心组件。

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > 对于 Windows Server 2012 和 Windows Server 2012 R2，使用服务器管理器安装并激活 .NET Framework 4.5。 有关详细信息，请参阅<A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 的其他软件要求</A>中的 "Microsoft .net Framework 4.5"。 对于 Windows Server&nbsp;2008&nbsp;R2，从 Microsoft 网站下载并安装<A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.net Framework 4.5</A> 。

    
    </div>

  - 远程服务器管理工具（RSAT）
    
    <div>
    

    > [!NOTE]  
    > 如果你在成员服务器上（而不是在域控制器上）运行 Active Directory 准备步骤，则需要一些 RSAT 工具。 从服务器管理器中的 "AD DS" 和 "AD LDS 工具" 节点安装 AD DS 管理单元和命令行工具以及 Windows PowerShell 的 Active Directory 模块。

    
    </div>

  - Microsoft Visual c + + 11 可再发行组件
    
    <div>
    

    > [!NOTE]  
    > 如果计算机上尚未安装此必备组件，则安装程序会提示您安装它。 程序包是为你提供的，你将不需要单独获取它。

    
    </div>

  - Windows PowerShell 3.0 （64位）
    
    对于 Windows Server 2012 和 Windows Server 2012 R2，Windows PowerShell 3.0 应包含在 Lync Server 2013 安装中。 对于 Windows Server 2008 R2，你需要安装或升级到 Windows PowerShell 3.0。 有关详细信息，请参阅[安装 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>管理员权限和角色

下表显示了每个 Active Directory 准备任务所需的管理权限和角色。

### <a name="user-rights-required-for-active-directory-preparation"></a>Active Directory 准备所需的用户权限

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>步</th>
<th>权利或角色</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>架构准备</p></td>
<td><p>林根域的架构管理员组的成员和架构主机上的管理员权限</p></td>
</tr>
<tr class="even">
<td><p>林准备</p></td>
<td><p>林的 "企业管理员" 组的成员</p></td>
</tr>
<tr class="odd">
<td><p>域准备</p></td>
<td><p>指定域的企业管理员或域管理员组的成员</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Active Directory 准备 Cmdlet

下表将用于准备 AD DS 的 Lync Server Management Shell cmdlet 与用于在 Microsoft Office 通信服务器 2007 R2 中准备 AD DS 的 LcsCmd 命令进行比较。

### <a name="cmdlets-compared-to-lcscmd"></a>与 LcsCmd 的比较 cmdlet

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Powershell</th>
<th>确认</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd/forest/action： SchemaPrep/SchemaType： Server</p></td>
</tr>
<tr class="even">
<td><p>CsAdServerSchema</p></td>
<td><p>Lcscmd/forest/action： CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd/forest/action： ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd/forest/action： ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>CsAdForest</p></td>
<td><p>Lcscmd/forest/action： CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd/domain/action：域</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd/domain/action： DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>CsAdDomain</p></td>
<td><p>Lcscmd/domain/action： CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>已锁定 Active Directory 要求

如果已禁用权限继承或已验证用户权限，则必须在你的组织中禁用用户权限，你必须在域准备期间执行其他步骤。 有关详细信息，请参阅[在 Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

</div>

<div>

## <a name="custom-container-permissions"></a>自定义容器权限

如果你的组织使用自定义容器而不是三个内置容器（即用户、计算机和域控制器），则必须向 "已验证用户" 组的自定义容器授予读取访问权限。 域准备需要对容器的读取访问权限。 有关详细信息，请参阅[准备 Lync Server 2013 的域](lync-server-2013-preparing-domains.md)。

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>使用 Cmdlet 和 Ldifde

Lync Server 部署向导中的**准备架构**步骤和**CsAdServerSchema** cmdlet 扩展运行64位操作系统的域控制器上的 Active Directory 架构。 如果需要在运行32位操作系统的域控制器上扩展 Active Directory 架构，则可以从成员服务器远程运行**CsAdServerSchema** cmdlet （推荐方法）。 但是，如果你需要直接在域控制器上运行架构准备，则可以使用 Ldifde 工具导入架构文件。 Ldifde 工具附带了大多数版本的 Windows 操作系统。

如果使用 Ldifde 导入架构文件，则必须导入所有四个文件，无论是从早期版本迁移还是执行全新安装。 必须按以下顺序导入它们：

1.  ExternalSchema

2.  ServerSchema

3.  BackCompatSchema

4.  VersionSchema

<div>


> [!NOTE]  
> 四个 .ldf 文件位于安装媒体或下载的 \Support\Schema 目录中。



</div>

若要使用 Ldifde 导入作为架构主机的域控制器上的四个架构文件，请使用以下格式：

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

例如：

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> 仅当以其他用户身份登录时，才使用 b 参数。 有关所需的用户权限的详细信息，请参阅本主题前面的 "管理员权限和角色" 部分。



</div>

若要使用 Ldifde 导入非架构主机的域控制器上的四个架构文件，请使用以下格式：

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

有关使用 Ldifde 的详细信息，请参阅 Microsoft 知识库文章 237677 "使用 LDIFDE 将目录对象导入和导出到 Active Directory" [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)。

</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中准备 Active Directory 架构](lync-server-2013-preparing-the-active-directory-schema.md)

  - [为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)

  - [为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

