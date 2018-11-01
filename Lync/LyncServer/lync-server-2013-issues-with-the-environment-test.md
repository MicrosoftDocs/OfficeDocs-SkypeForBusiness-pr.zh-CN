---
title: 环境测试的问题
TOCTitle: 环境测试的问题
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205421(v=OCS.15)
ms:contentKeyID: 49314848
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 环境测试的问题

 

_**上一次修改主题：** 2012-09-21_

最佳做法分析器为您提供一种方法来验证您的 Lync Server 2013 环境是否为受支持的配置。作为 Active Directory 域服务检查的一部分，最佳做法分析器可执行以下操作：

  - 验证 Active Directory 域服务林和架构准备。

  - 标识部署中 Active Directory 域服务站点和域的数量。

  - 检查林和域级别。

  - 检查域控制器版本。

  - 标识域、配置和架构命名上下文。

  - 标识启用的用户的数量。

  - 检查全局 Active Directory 域服务设置存储的位置。

  - 检查 Lync Server 的服务连接点 (SCP)。

  - 标识数据库版本。

## 解决环境问题

如果环境测试发现您的环境存在问题，则这些问题可能是 Active Directory 配置或特定服务器上运行的软件级别问题造成的。例如，如果最佳做法分析器标识运行 Windows Server 2000 的环境中的任何域控制器，则系统将发出一个警告，且您将需要将这些域控制器升级到受支持的 Windows Server 版本。

