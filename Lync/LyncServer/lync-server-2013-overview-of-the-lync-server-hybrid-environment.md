---
title: Lync Server 2013：Lync Server 混合环境概述
TOCTitle: Lync Server 2013 混合环境概述
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204669(v=OCS.15)
ms:contentKeyID: 49311984
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 混合环境概述

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 混合环境指的是一种部署，在该部署中，某些用户由本地 Lync Server 2013 进行托管，而其他用户则由 Lync Online 进行托管，但是这些用户共享同一域，如 user@contoso.com。

## 关于本指南

本指南介绍配置 Lync Server 2013 环境以与 Lync Online 进行互操作，然后将用户从本地部署迁移为使用 Lync Online 所需完成的任务。

## 先决条件

您将需要安装以下应用程序和实用程序才能完成配置混合部署的任务。这些文件的安装程序位于针对您的部署提供的安装介质上，以及下表提供的链接中。

  - [Active Directory 联合身份验证服务 (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft 目录同步工具 9.1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [安装 Windows PowerShell 以便使用 AD FS 进行单一登录](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Office 365 桌面设置中随附 Microsoft Online Services 登录助手 (msoidcli-7.0.msi)，可通过链接至 Office 365 管理门户的下载页面获得。

## 管理员凭据

当要求您提供管理员凭据时，请使用为您创建的 Office 365 租户管理员帐户的用户名和密码。在配置 Active Directory 联合身份验证服务 (AD FS) 2.0、目录同步、单一登录、联合身份验证以及将用户移至 Lync Online 时也需要用到这些凭据。

## 连接到 Lync Online PowerShell

管理员现在可以使用 Windows PowerShell 管理 Lync Online 及其 Lync Online 用户帐户。为此，您必须首先从 Microsoft 下载中心下载和安装 Lync Online 连接器模块 (http://go.microsoft.com/fwlink/?LinkId=294688)。有关下载、安装和使用 Lync Online 连接器模块的详细信息，以及使用 Windows PowerShell 管理 Lync Online 的详细信息，请参阅 [使用 Windows PowerShell 管理 Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

