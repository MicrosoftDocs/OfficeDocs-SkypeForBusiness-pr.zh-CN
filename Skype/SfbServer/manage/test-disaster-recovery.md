---
title: Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 对 Skype for Business Server 服务器执行系统恢复，以测试记录灾难恢复过程
ms.openlocfilehash: 87b76e958ed35896921791406759e58ce2ee1635
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390104"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Skype for Business Server

对池服务器执行Skype for Business Server恢复，以测试记录灾难恢复过程。 此测试将模拟一台服务器的完整硬件故障，并帮助保证资源、计划和数据可用于恢复。 尝试每月轮换测试的焦点，以便组织每次测试不同服务器或其他设备的故障。 

请注意，组织执行灾难恢复测试的计划将有所不同。 不要忽略或忽略灾难恢复测试，这一点非常重要。 

将Skype for Business Server拓扑、策略和配置设置导出到文件中。 此外，在升级、硬件故障或其他一些问题导致数据丢失后，此文件还可用于将此信息还原到中央管理存储。

将Skype for Business Server拓扑、策略和配置设置导入中央管理存储或本地计算机，如以下命令所示： 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

备份生产数据：

- 使用标准备份过程备份 RTC 和 LCSLog 数据库SQL Server将数据库转储到文件或磁带转储设备。
- 使用第三方备份应用程序将数据备份到文件或磁带。
- 使用 Export-CsUserData cmdlet 创建整个 RTC 数据库的 XML 导出。
- 使用文件系统备份或第三方备份来备份会议内容和合规性日志。
- 使用 Export-CsConfiguration 命令行工具来备份Skype for Business Server设置。

故障转移过程中的第一步包括强制将用户从生产池移动到灾难恢复池。 这是强制移动，因为生产池将不能接受用户重定位。

除了Skype for Business Server RTC 数据库上的记录更新之外，移动用户过程实际上是更改用户帐户SQL更改。 可以使用 SQL Server标准 SQL Server 还原过程，或者使用第三方备份/还原实用工具，从生产环境中从原始备份转储设备还原此数据。

还原此数据后，用户可以有效地连接到灾难恢复池，并像往常一样运行。 若要使用户能够连接到灾难恢复池，需要更改 DNS 记录。

客户端Skype for Business配置和 DNS SRV 记录引用生产池：

- SRV：_sip._tls。\<domain> /CNAME：SIP。\<domain>
- CNAME：SIP。\<domain> /cvc-pool-1。\<domain>

为了便于进行故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：

- CNAME：SIP。\<domain> /DROCSPool。\<domain>
- Sip。\<domain>
- AV。\<domain>
- webconf。\<domain>
