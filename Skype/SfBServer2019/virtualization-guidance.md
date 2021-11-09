---
title: '2019 年 Skype for Business Server 虚拟化支持 '
ms.reviewer: corbinm
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 摘要：了解 Skype for Business Server 2019 的虚拟化支持。
ms.openlocfilehash: 73e9121e2b530e44395aefda50082682fb910e7d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853776"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>2019 年 Skype for Business Server 虚拟化支持

Skype for Business Server虚拟化支持 2019 版本。

尽管支持虚拟化，但需要记住一些要点：

- 保持虚拟 CPU 与物理 CPU 的比例为 1：1。
- 请勿在来宾服务器运行时移动它。
- 不支持迁移实时系统和虚拟机的可移植性。
- 在所有主机上禁用超线程。
- 不要在主机服务器上配置动态内存。
- 使用固定或传递磁盘，而不是动态磁盘。
- 允许虚拟机监控程序超出虚拟来宾需要的 6-10% 的开销。

## <a name="supported-hypervisors"></a>支持的虚拟机监控程序

SfB Server 2019 在 Windows Server 2016 和 Windows Server 2019 上受支持。

对于第三方虚拟机监控程序，你需要一个已通过服务器虚拟化验证计划 (SVVP) 测试的相关操作系统的虚拟机监控程序。

- 请参阅[Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) SVVP 列表中的版本。
- 请参阅 SVVP 列表中的 Windows Server [2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25)版本。

## <a name="stress-and-performance-tool"></a>压力和性能工具

The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019. The Skype for Business Server 2019 Stress and Performance Tool will help you to：

- 简化 2019 Skype for Business Server硬件规划
- 为性能调整提供增强的知识和最佳做法
- 测量 2019 年Skype for Business Server性能
 
你可以从此处下载 [该工具](https://www.microsoft.com/download/details.aspx?id=101447)。
