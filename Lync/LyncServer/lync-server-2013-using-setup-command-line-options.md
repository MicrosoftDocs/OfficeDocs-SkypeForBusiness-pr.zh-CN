---
title: 使用安装命令行选项
TOCTitle: 使用安装命令行选项
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205129(v=OCS.15)
ms:contentKeyID: 49313706
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用安装命令行选项

 

_**上一次修改主题：** 2016-12-08_

Setup.exe 命令行用于 Office 安装中的几个操作。您通常将使用 Office 自定义工具和 Config.xml 文件（而非安装程序命令行选项）来进行产品安装和功能自定义。

Office Setup.exe 命令行识别下表中介绍的命令行选项。

### Office 安装程序命令行选项

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>安装程序命令行选项</th>
<th>描述</th>
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
<td><p>指定安装程序在安装过程中使用的 Config.xml 文件。使用 /config 选项可指定针对 Lync 2013 安装自定义的 Config.xml 文件，例如：<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
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


有关使用安装程序命令行选项的详细信息，请参阅 [http://go.microsoft.com/fwlink/?linkid=267515\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=267515%26clcid=0x804)。

