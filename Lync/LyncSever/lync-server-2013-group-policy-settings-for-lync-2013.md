---
title: Lync 2013 的组策略设置
TOCTitle: Lync 2013 的组策略设置
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204924(v=OCS.15)
ms:contentKeyID: 49312923
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync 2013 的组策略设置

 

_**上一次修改主题：** 2016-12-08_

在以前版本的 Lync 和 Office Communicator 中，独立的 Communicator.adm 管理模板可用于配置客户端组策略设置。对于 Lync 2013，新的管理模板文件（.admx 和 .adml 文件）与 Office 组策略管理模板包含在一起。如果 Lync 2013 .admx 和 .adml 文件可用，您便可以下载模板和集中管理所有 Office 程序和语言包的组策略设置。有关详细信息，请参阅 Office 2013 文档中的“Office 2013 管理模板文件（ADMX、ADML）”，网址为 [http://go.microsoft.com/fwlink/?linkid=267516\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=267516%26clcid=0x804)。

## 客户端引导策略

在用户首次登录到服务器之前，应该配置几个客户端引导策略。由于这些策略在客户端登录并开始接收带内设置前生效，因此您可以使用组策略配置它们。有关详细信息，请参阅部署文档中的[在 Lync Server 2013 中配置客户端引导策略](lync-server-2013-configuring-client-bootstrapping-policies.md)。

