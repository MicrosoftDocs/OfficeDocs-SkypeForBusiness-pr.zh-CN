---
title: 在 Skype for Business Server 2015 中使用安装程序命令行选项
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要： 了解有关 Office 安装程序中的 Setup.exe 命令行操作。
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中使用安装程序命令行选项
 
**摘要：**了解有关 Office 安装程序中的 Setup.exe 命令行操作。
  
Setup.exe 命令行用于 Office 安装中的几个操作。 而不是使用安装程序命令行选项，您通常使用 Office 自定义工具和 Config.xml 文件为产品安装和功能自定义。
  
Office Setup.exe 命令行识别下表中介绍的命令行选项。
  
**Office 安装程序命令行选项**

|**安装程序命令行选项**|**说明**|
|:-----|:-----|
|/admin  <br/> |运行 Office 自定义工具以创建安装程序自定义文件（.msp 文件）。  <br/> |
|/adminfile [path]  <br/> |将指定的安装程序自定义文件应用于安装。您可以指定特定的自定义文件（.msp 文件）的路径或指定存储自定义文件的文件夹的路径。  <br/> |
|/config [path]  <br/> |指定安装程序在安装过程中使用的 Config.xml 文件。 /Config 选项用于指定您为自定义 Skype 对于企业安装，例如 Config.xml 文件：`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |用于修改后的 Config.xml 文件可在维护模式下运行安装程序并对现有 Office 安装进行更改。 例如，您可以使用 / 修改选项添加或删除 Skype 业务功能。  <br/> |
|/repair Skype  <br/> |从用户的计算机以修复 Skype 业务运行安装程序。  <br/> |
|/uninstall Skype  <br/> |运行安装程序在用户的计算机上删除 Skype 业务。  <br/> |
   
有关使用安装程序命令行选项的详细信息，请参阅[https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515)。 
  

