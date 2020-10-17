---
title: Lync Server 2013：使用安装程序命令行选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c530387fa9f504120ff3a8f38128eeb07b04e615
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527639"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a>在 Lync Server 2013 中使用安装程序命令行选项

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

Setup.exe 命令行用于 Office 安装中的几个操作。您通常将使用 Office 自定义工具和 Config.xml 文件（而非安装程序命令行选项）来进行产品安装和功能自定义。

Office Setup.exe 命令行识别下表中介绍的命令行选项。

### <a name="office-setup-command-line-options"></a>Office 安装程序命令行选项

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>安装程序命令行选项</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>运行 Office 自定义工具以创建安装程序自定义文件（.msp 文件）。</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [path]</p></td>
<td><p>将指定的安装程序自定义文件应用于安装。您可以指定特定的自定义文件（.msp 文件）的路径或指定存储自定义文件的文件夹的路径。</p></td>
</tr>
<tr class="odd">
<td><p>/config [path]</p></td>
<td><p>指定安装程序在安装过程中使用的 Config.xml 文件。 使用/config 选项可指定为 Lync 2013 安装自定义的 Config.xml 文件，例如： <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>用于修改后的 Config.xml 文件可在维护模式下运行安装程序并对现有 Office 安装进行更改。例如，您可以使用 /modify 选项添加或删除 Lync 功能。</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>从用户的计算机中运行安装程序来修复 Lync。</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>运行安装程序以从用户的计算机中删除 Lync。</p></td>
</tr>
</tbody>
</table>


有关使用安装程序命令行选项的详细信息，请参阅 <https://go.microsoft.com/fwlink/p/?linkid=267515> 。

</div>

<span> </span>

</div>

</div>

</div>

