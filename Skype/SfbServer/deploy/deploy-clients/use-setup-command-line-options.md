---
title: 将安装程序命令行选项与 Skype for Business 客户端一同使用
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要：了解Setup.exe Office 安装程序中的命令行操作。
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837202"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>将安装程序命令行选项与 Skype for Business 客户端一同使用
 
**摘要：** 了解 office Setup.exe中的命令行操作。
  
Setup.exe 命令行用于 Office 安装中的几个操作。 您通常使用 Office 自定义工具和 Config.xml 文件进行产品安装和功能自定义，而不是使用安装程序命令行选项。
  
Office Setup.exe 命令行识别下表中介绍的命令行选项。
  
**Office 安装程序命令行选项**

|**安装程序命令行选项**|**说明**|
|:-----|:-----|
|/admin  <br/> |运行 Office 自定义工具以创建安装程序自定义文件（.msp 文件）。  <br/> |
|/adminfile [path]  <br/> |将指定的安装程序自定义文件应用于安装。您可以指定特定的自定义文件（.msp 文件）的路径或指定存储自定义文件的文件夹的路径。  <br/> |
|/config [path]  <br/> |指定安装程序在安装过程中使用的 Config.xml 文件。 使用 /config 选项指定Config.xml Skype for Business 安装自定义的文件，例如：  `/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |用于修改后的 Config.xml 文件可在维护模式下运行安装程序并对现有 Office 安装进行更改。 例如，可以使用 /modify 选项添加或删除 Skype for Business 功能。  <br/> |
|/repair Skype  <br/> |从用户的计算机运行安装程序以修复 Skype for Business。  <br/> |
|/uninstall Skype  <br/> |运行安装程序以从用户计算机中删除 Skype for Business。  <br/> |
   


