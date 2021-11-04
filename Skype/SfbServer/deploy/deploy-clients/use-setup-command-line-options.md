---
title: 将安装程序命令行选项用于Skype for Business客户端
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要：了解Setup.exe安装程序中的命令行Office操作。
ms.openlocfilehash: 00d76dddef6a2cc8ba1bcda87ceadb22f7269dcb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742928"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>将安装程序命令行选项用于Skype for Business客户端
 
**摘要：** 了解Setup.exe安装程序中的命令行Office操作。
  
Setup.exe 命令行用于 Office 安装中的几个操作。 通常，你将使用 Office 自定义工具和 Config.xml 文件进行产品安装和功能自定义，而不是使用安装程序命令行选项。
  
Office Setup.exe 命令行识别下表中介绍的命令行选项。
  
**Office 安装程序命令行选项**

|**安装程序命令行选项**|**说明**|
|:-----|:-----|
|/admin  <br/> |运行 Office 自定义工具以创建安装程序自定义文件（.msp 文件）。  <br/> |
|/adminfile [path]  <br/> |将指定的安装程序自定义文件应用于安装。您可以指定特定的自定义文件（.msp 文件）的路径或指定存储自定义文件的文件夹的路径。  <br/> |
|/config [path]  <br/> |指定安装程序在安装过程中使用的 Config.xml 文件。 使用 /config 选项指定Config.xml安装自定义的Skype for Business文件，例如：`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |用于修改后的 Config.xml 文件可在维护模式下运行安装程序并对现有 Office 安装进行更改。 例如，您可以使用 /modify 选项添加或删除Skype for Business功能。  <br/> |
|/repair Skype  <br/> |从用户的计算机运行安装程序以修复Skype for Business。  <br/> |
|/uninstall Skype  <br/> |运行安装程序Skype for Business用户计算机中删除用户的计算机。  <br/> |
   


