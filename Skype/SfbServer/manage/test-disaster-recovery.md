---
title: Skype for Business 服务器中的灾难恢复测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 为 Skype for business 服务器池服务器执行系统恢复, 以测试已记录的灾难恢复过程
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279212"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Skype for Business 服务器中的灾难恢复测试

为 Skype for business 服务器池服务器执行系统恢复, 以测试已记录的灾难恢复过程。 此测试将模拟一台服务器的完整硬件故障, 并将帮助确保资源、计划和数据可用于恢复。 请尝试每月轮转测试焦点，以便您的组织每次测试不同服务器或其他设备的故障。 

请注意，组织执行灾难恢复测试时所遵循的计划将有所不同。非常重要的是，不得忽略灾难恢复测试。 

将 Skype for Business 服务器拓扑、策略和配置设置导出到文件。 在升级、硬件故障或一些其他问题导致数据丢失后，此文件的功能之一是可用于将该信息恢复到中央管理存储。

将 Skype for Business 服务器拓扑、策略和配置设置导入中央管理存储或本地计算机, 如以下命令所示: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

要备份生产数据, 请执行以下操作:

- 通过使用标准 SQL Server 备份过程来备份 RTC 和 LCSLog 数据库, 以将数据库转储到文件或磁带转储设备。
- 使用第三方备份应用程序将数据备份到文件或磁带。
- 使用 Export-CsUserData cmdlet 创建整个 RTC 数据库的 XML 导出。
- 使用文件系统备份或第三方备份备份会议内容和合规性日志。
- 使用 Export-CsConfiguration 命令行工具备份 Skype for Business 服务器设置。

故障转移过程的第一个步骤包括强制性地将用户从生产池移动到灾难恢复池。 之所以称为强制性移动是因为生产池并不接受用户重新定位。

除了 RTC SQL 数据库上的记录更新之外, Skype for Business 服务器移动用户进程对用户帐户对象上的属性的更改很有效。 通过使用标准 SQL Server 还原过程或使用第三方备份/还原实用工具, 可以从生产 SQL Server 中的原始备份转储设备还原此数据。

还原此数据后, 用户可以有效地连接到灾难恢复池, 并照常运行。 若要使用户能够连接到灾难恢复池, 则需要更改 DNS 记录。

使用以下各项的自动配置和 DNS SRV 记录, 客户端将引用生产版 Skype for Business 池:

- SRV: _sip。 _tls。\<domain>/CNAME: SIP。\<domain>
- CNAME: SIP。\<domain>/cvc-pool-1。\<domain>

为促进故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：

- CNAME: SIP。<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- \<Domain>
- webconf.\<domain>
