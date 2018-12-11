---
title: 业务服务器中 Skype 测试的灾难恢复
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 为业务服务器池服务器 Skype 测试您的记录的灾难恢复过程中执行系统恢复
ms.openlocfilehash: d401d27c1cc0f5b04c6e256a1e55f6847c9c35ba
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222721"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>业务服务器中 Skype 测试的灾难恢复

为业务服务器池服务器 Skype 测试您的记录的灾难恢复过程中执行系统恢复。 此测试将模拟一台服务器的完整的硬件故障，有助于保证可用于恢复资源、 计划和数据。 请尝试每月轮转测试焦点，以便您的组织每次测试不同服务器或其他设备的故障。 

请注意，组织执行灾难恢复测试时所遵循的计划将有所不同。非常重要的是，不得忽略灾难恢复测试。 

将您的企业服务器拓扑、 策略和配置设置的 Skype 导出到文件。 在升级、硬件故障或一些其他问题导致数据丢失后，此文件的功能之一是可用于将该信息恢复到中央管理存储。

导入您的企业服务器拓扑、 策略和配置设置的 Skype 到中央管理存储或本地计算机示以下命令： 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

若要备份生产数据：

- 备份 RTC 和 LCSLog 数据库使用标准的 SQL Server 备份过程能够转储文件或磁带转储设备的数据库。
- 使用第三方备份应用程序将数据备份到文件或磁带。
- 使用 Export-CsUserData cmdlet 创建整个 RTC 数据库的 XML 导出。
- 使用文件系统备份或第三方备份 to back up 会议内容和合规性日志。
- 使用 Export-csconfiguration 命令行工具备份 Skype 的业务服务器设置。

故障转移过程的第一个步骤包括强制性地将用户从生产池移动到灾难恢复池。 之所以称为强制性移动是因为生产池并不接受用户重新定位。

业务服务器移动用户进程的 Skype 实际上是对除了上的 RTC SQL 数据库的记录更新此用户帐户对象的属性的更改。 可以还原此数据从原始备份转储设备从生产使用标准的 SQL Server 还原进程，或使用第三方 SQL Server 备份/还原实用程序。

在还原此数据后，用户可以有效地连接到灾难恢复池，并像往常一样运行。 若要使用户能够连接到灾难恢复池，还将需要的 DNS 记录的更改。

生产 Skype 业务池将使用客户端自动配置和 DNS SRV 记录的引用：

- SRV: _sip._tls。\<域 > /CNAME: SIP。\<域 >
- CNAME: SIP。\<域 > /cvc-pool-1。\<域 >

为促进故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：

- CNAME: SIP。<domain> / DROCSPool。\<域 >
- Sip。\<域 >
- AV.\<域 >
- webconf。\<域 >
