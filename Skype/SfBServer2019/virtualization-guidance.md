---
title: 'Skype for business Server 2019 的虚拟化支持 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：了解 Skype for business Server 2019 的虚拟化支持。
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509029"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Skype for business Server 2019 的虚拟化支持

Skype for business Server 2019 在虚拟化中受支持。

虽然虚拟化受支持，但有一些要点需要注意：

- 将虚拟 CPU 的1:1 比率维护为物理 CPU。
- 请勿在来宾服务器运行时移动它。
- 不支持迁移实时系统和虚拟机的可移植性。
- 在所有主机上禁用超线程。
- 不要在主机服务器上配置动态内存。
- 使用固定磁盘或传递磁盘，而不是动态磁盘。
- 允许不超过虚拟来宾所需的虚拟机监控程序6-10% 的开销。

## <a name="supported-hypervisors"></a>支持的虚拟机监控程序

Windows Server 2016 和 Windows Server 2019 支持 SfB Server 2019。

对于第三方虚拟机管理程序，您需要一个已通过服务器虚拟化验证程序的虚拟机监控程序 (SVVP) 测试相关操作系统。

- 请参阅 SVVP 列表中的 [Windows Server 2016 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) 。
- 请参阅 SVVP 列表中的 [Windows Server 2019 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) 。

## <a name="stress-and-performance-tool"></a>压力和性能工具

Skype for Business Server 2019 压力和性能工具包括简化 Skype for business Server 2019 容量规划的工具。 Skype for Business Server 2019 的压力和性能工具将帮助你执行以下操作：

- 简化对 Skype for Business Server 2019 的硬件规划
- 为您提供更多的知识和最佳做法以优化性能
- 衡量预期的 Skype for business Server 2019 部署的性能
 
您可以从 [此处](https://www.microsoft.com/download/details.aspx?id=101447)下载该工具。
