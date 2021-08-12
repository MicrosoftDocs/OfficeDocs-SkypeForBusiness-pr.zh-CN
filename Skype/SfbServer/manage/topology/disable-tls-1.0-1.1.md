---
title: 在 2015 年 10 月禁用 TLS 1.0/1.1 Skype for Business Server TLS
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 准备并实施在环境中禁用 TLS 1.0 和 1.1。
ms.openlocfilehash: 9bb737466595420770c4374d7d1b76bcc0319e38d188f550fb284b686df7e19f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337770"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>在 2015 年 10 月禁用 TLS 1.0/1.1 Skype for Business Server TLS

本文帮助你准备和实施在环境中禁用 TLS 1.0 和 1.1。 此过程需要进行广泛的规划和准备。 当您制定为组织禁用 TLS 1.0 和 1.1 的计划时，请仔细查看本文中所有的信息。 禁用 TLS 1.0/1.1 可能会影响许多外部依赖项和连接条件，因此，需要进行广泛的规划和测试。

- [背景和范围](#background-and-scope)
- [先决条件和过程](#prerequisites-and-process)
- [高级部署方案](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a>背景和范围

提供对 Skype for Business Server 本地 TLS 1.0 和 1.1 禁用支持的主要驱动因素是支付卡行业 (PCI) 安全标准委员会和联邦信息处理标准要求。 有关 PCI 要求详细信息，请参阅 [此处](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。  Microsoft 无法提供有关你的组织是否需要遵守这些要求或其他要求的指导。 必须确定是否需要在你的环境中禁用 TLS 1.0 和/或 1.1。

Microsoft 已制作一份有关此处提供的[](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)TLS 的白皮书，我们还建议在此博客中提供Exchange[阅读](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)。

## <a name="supportability-scope"></a>可支持性范围

*范围* 是指可支持性边界。 *完全测试和支持* 意味着我们完全支持并已经针对列出的产品版本禁用 TLS 1.0 和 1.1。 *当前正在调查* 意味着这一点;我们正在积极调查将这些产品引入 TLS 禁用支持的范围。 *超出范围* 意味着这些产品版本不支持禁用 TLS 1.0 或 1.1，并且将不起作用，但已指出的例外情况除外。

### <a name="fully-tested-and-supported-servers"></a>经过完全测试且受支持的服务器

- Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年 6 月或) 更高版本
- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 日或更高版本Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新) 、2012 R2 或 2016。
- ) 年 5 月或更高版本的 Windows Server 2008 R2、2012 (KB 3140245 或取代更新) 或 2012 R2 上的 CU9 6.0.9319.548 (就地升级[Skype for Business Server](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 2015 或更高版本。
- Exchange有关与 Outlook Web App 2010 SP3 RU19 Exchange Server或更高版本的连接和连接[，请在此处](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)提供指导
- Survivable Branch Appliance (SBA) 与 Skype for Business Server 2015 CU6 (或更高版本 (请与供应商确认他们打包了相应的更新，并且已可用于你的) 
- Survivable Branch Server (SBS) 2015 CU6 SKYPE FOR BUSINESS SERVER 2 或更高版本
- 仅 Lync Server 2013 边缘角色 ，这是因为边缘角色在 1.0 上Windows Fabric依赖关系。

### <a name="fully-tested-and-supported-clients"></a>经过完全测试且受支持的客户端

- Lync 2013 (Skype for Business) 桌面客户端、MSI 和 C2R，包括基本[15.0.5023.1000 或更高版本](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype for Business 2016 桌面客户端、MSI [16.0.4678.1000 或更高版本](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)，包括基本
- Skype for Business 2016 年 4 月单击以运行需要[2018 年 4 月](/officeupdates/release-notes-office365-proplus)更新： 
    - 每月和Semi-Annual定向，16 \. \. 0 9126 \. 2152 或更高版本
    - Semi-Annual和延期频道，16 \. \. 0 8431 \. 2242 或更高版本
- Skype for Business Mac 16.15 或更高版本上
- Skype for Business iOS 和 Android 6.19 或更高版本
- Microsoft Teams 会议室 (2018 年 12 月Skype 4.0.64. (0) 4.0.64.0 或更高版本) 会议室系统 V2 SRS V2
- Surface Hub KB4499162 (2019 年 5 月操作系统内部版本 15063.1835 或更高版本) 更新
- SkypeServer) 中附带 Web App 2015 CU6 (或更高版本

### <a name="currently-being-investigated"></a>当前正在调查

- 呼叫质量仪表板 (TLS 1.0、1.1 禁用后的新安装，请参阅下面的) *
 
### <a name="out-of-scope"></a>超出范围

除非特别说明，否则以下产品不在 TLS 1.0/1.1 范围内禁用支持，并且不会在 TLS 1.0 和 1.1 已禁用的环境中运行。 这意味着：如果仍使用作用域外服务器或客户端，则必须更新或删除这些服务器或客户端（如果需要在 Skype for Business Server 本地部署中的任何位置禁用 TLS 1.0/1.1）。

- Lync Server 2013
- Lync Server 2010
- WindowsServer 2008 或更低
- Lync for Mac 2011
- Lync 2013 移动版 - iOS、iPad、Android 或 Windows Phone
- Lync"MX"Windows Store 客户端
- Lync 会议室 (。。 SRSv1) 。 LRS 于 2018 年 10 月 9 日终止支持，不会进行更新以支持 TLS 1.2。
- 所有 Lync 2010 客户端
- Lync 电话 Edition - 此处更新[了指南](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)。
- 基于 2013 的 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS) 
- 云连接器版本 (CCE) 
- Windows Phone版Skype for Business

### <a name="exceptions"></a>例外

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 依赖于 1.0 Windows Fabric版本。  在 Lync Server 2013 的设计阶段，选择 Windows Fabric 1.0 作为其引人注目的新分布式体系结构，以提供复制、高可用性和容错。  随着时间的推移，Skype for Business Server和Windows Fabric都大大改进了这种联合体系结构，在后续版本中进行重大重新设计。  例如Skype for Business 2015 Server Windows Fabric 3.0。

遗憾的是，Windows Fabric 1.0 **不支持 TLS 1.2。 但是，我们将更新 Lync Server 2013 以使用 TLS 1.2。** 这将在 Lync Server 2013 的下一个累积更新中发布。  我们提供 TLS 1.2 支持，以实现共存、迁移、联合和混合方案。

如果您的组织需要禁用 TLS 1.0 和 1.1，并且您当前使用 Lync Server 2013，我们建议您开始规划过程，您可能必须就地升级或并行迁移 (新池，将用户) 移动到 Skype for Business Server 2015 或更高版本。  或者，你可能希望加速迁移到 Skype for Business Online。

#### <a name="call-quality-dashboard"></a>通话质量仪表板

内部部署呼叫质量仪表板当前依赖于新安装期间 TLS 1.0 (首次安装到本地环境) 。  我们目前正在调查此问题，并计划在近期发布修补程序。  如果计划安装 CQD 并同时禁用 TLS 1.0，我们建议您首先完成 CQD 安装，然后继续禁用 TLS 1.0。

#### <a name="skype-for-business-sdn-manager"></a>Skype for BusinessSDN 管理器

Skype for Business使用 SDN 管理器SQL安装期间，数据库依赖于 TLS 1.0。 如果计划使用 SQL 数据库安装 Skype for Business SDN 管理器并禁用 TLS 1.0，我们建议您首先完成 Skype for Business SDN 管理器，然后继续禁用 TLS 1.0。 如果 TLS 1.0 在安装之前被禁用，应在将用于托管 Skype for Business SDN 管理器 SQL 数据库的 SQL Server 后端服务器中临时启用 TLS 1.0。

#### <a name="third-party-devices"></a>第三方设备

在 3PIP 电话、视频会议、反向代理和负载平衡器等第三方设备上，请务必验证 TLS 1.2 可支持性、仔细测试并根据需要与供应商联系。

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>在边缘服务器上禁用 TLS 1.0/1.1 时联盟注意事项

必须仔细规划并考虑禁用 TLS 1.0/1.1 对边缘服务器的影响。  禁用 TLS 1.0 和 1.1 后，您可能会发现其他组织无法再与您的组织联盟。

您可以选择在边缘服务器上保持启用 TLS 1.0/1.1，以保持与非修补的 (SfB 2015、Lync 2013) 或 (2010) 外部系统的向后兼容性。

Microsoft 无法提供有关边缘网络网络或任何 (网络是否) PCI 标准的建议或建议;必须由单个公司确定。

Skype for Business目前，Online 支持 TLS 1.2，因此不会影响与 Online 的混合/联合身份验证。

PIC (Public IM Connectivity) to Skype Consumer Service：我们预计禁用 TLS 1.0/1.1 不会影响 Skype[连接](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 网关已经支持 TLS 1.2。

## <a name="prerequisites-and-process"></a>先决条件和过程

除非如上所述，一旦禁用了 TLS 1.0 和 1.1 的作用域外服务器，客户端和设备将可以正常运行，或者甚至会一切正常。 这可能意味着你需要暂停并等待 Microsoft 的更新指导。 一旦满足所有要求并计划解决差距，请继续。

在高级别上，尽管 Skype for Business Server 2019 已准备好进行安装过程，但 Skype for Business Server 2015 将要求您安装 CU9，将先决条件更新应用到 .NET 和 SQL，部署必备注册表项，最后是单独一轮操作系统配置更新 (即通过注册表文件导入) 禁用 TLS 1.0 和 1.1。 在环境中的任何服务器上禁用 TLS 1.0 和 1.1 之前，必须完成所有必备组件（包括 Skype for Business Server 2015 CU6 SKYPE FOR BUSINESS SERVER 2）的安装，这一点非常重要。 每个Skype for Business服务器（包括边缘角色SQL后端）都需要更新。 此外，请确保所有 (范围内) 客户端已更新为所需的最低版本。 不要忘记更新管理工作站。

我们希望按照"内部到外部"的常规操作顺序来升级Skype for Business服务器。 以通常相同的方式处理控制器池、持久聊天和配对池。 此处和此处介绍了升级[的顺序](topology.md)[和方法](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。

### <a name="high-level-process"></a>高级流程

1. 在配置生产服务器之前，测试实验室中的所有步骤。
2. 在每个要更新的每台服务器上备份和保留导出的注册表副本。 不能在服务器之间共享注册表;它们包含基于计算机的唯一密钥。
3. 将所有 Skype for Business 2015 服务器升级到 CU9 或更高版本。 对于 Skype for Business Server 2019，请升级到 CU1 或更高版本。
4. 将所有必备组件安装到所有服务器。
5. 部署必备注册表项。
6. 确保所有范围内客户端已更新。
7. 通过注册表导入禁用 TLS 1.0 和 1.1。
8. 验证工作负荷是否正常工作。
    - 如果遇到问题，请进行故障排除和解决，或者
    - 从步骤 2 还原注册表以重新启用 TLS 1.0 和 1.1
9. 验证是否仅使用了 TLS 1.2。

### <a name="install-prerequisites-to-all-servers"></a>将必备组件安装到所有服务器

在开始在 Skype for Business Server 2015 部署的操作系统级别禁用 TLS 1.0 和 1.1 之前，需要进行大量依赖更新。 以下是可以支持 TLS 1.2 的最低版本。 在开始禁用 TLS 1.0 和 1.1 之前，Skype for Business部署环境中每个服务器的所有必备组件更新。

- Skype for Business Server 2019 年 5 月或更高版本的 2015 CU9 6.0.9319.548 (2019) 更高版本
- .NET Framework注册表中启用了 SchUseStrongCrypto， ([4.7](https://www.microsoft.com/download/details.aspx?id=55167)或更高版本) 
- SQL 2015 Skype for Business和后端上必须更新此配置。 首先Enterprise Edition池SQL，然后更新其各自的 FES。 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)或更高版本 / SQL Server 2012 SP2 + CU16 或更高版本 / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)或更高版本 / SQL Server 2014 SP2
     - [SQL Server Native Client 2012 SQL Server](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)或更高版本
     - [SQL Server 2014 SP2 的共享管理对象](https://www.microsoft.com/download/details.aspx?id=53164)
     - [sqlSysClrTypes for SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>按建议的操作顺序安装先决条件的基本步骤

1. 将 Skype for Business Server CU9 更新安装到所有服务器。 
    1. 使用更新程序将更新安装到组件。
    2. 根据记录的过程更新数据库。 有关 Skype for Business Server 2015，请参阅 KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。
    3. 在推进任何其他更改之前，验证部署中的产品功能。
2. 下载 .NET 4.7 脱机安装程序。 
    1. 引用：[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. 确保Skype for Business Server前端服务器上停止 2015 服务。
    3. 引用：[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. 例如 (Standard Edition) ：```Stop-CsWindowsService```
    5. 例如 (Enterprise Edition) ：```Invoke-CsComputerFailover```
    6. 运行安装程序程序包。
    7. 请重新启动服务器。
3. 在所有SQL更新 SQL Express 2014。 
    1. 引用：[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. 下载 SQL 2014 SP2 
        - 引用：[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. 将安装媒体复制到服务器上文件夹 (例如：C：\01_2014SqlSp2) 
    4. 确保Skype for Business Server前端服务器上停止 2015 服务 
        - 例如 (Standard Edition) ：```Stop-CsWindowsService```
        - 例如 (Enterprise Edition) ：```Invoke-CsComputerFailover```
    5. 打开管理员命令提示符，并升级所有已安装的组件和实例 
        - 示例：C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. 更新SQL Native Client。 
    1. 参考 [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) ：。
    2. 下载自 [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. 确保Skype for Business Server前端服务器上停止 2015 服务。 
        - 例如 (Standard Edition) ：```Stop-CsWindowsServices```
        - 例如 (Enterprise Edition) ：```Invoke-CsComputerFailover```
    4. 停止SQL实例运行 
        - 例如： ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 例如： ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - 例如 (Standard Edition仅) ：```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 安装该更新。
5. 更新 ODBC Driver 11 for SQL Server以包含对 TLS 1.2 (KB [3135244) 。](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    1. 下载[ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)。
    2. 确保Skype for Business Server前端服务器上停止 2015 服务。
        - 示例 (Standard Edition) ：```Stop-CsWindowsService```
        - 示例 (Enterprise Edition) ：```Invoke-CsComputerFailover```
    3. 安装该更新。
6. 部署必备注册表项。

### <a name="pre-requisite-registry-keys"></a>先决条件注册表项

将以下测试复制/粘贴到记事本并重命名 TLSPreReq.reg 或你选择的名称，然后导入：

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

对于SQL池Enterprise Edition后端，先决条件和 TLS 禁用应视为任何SQL或操作系统更新;引用：[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)

尽管必备组件应用程序和 TLS 禁用步骤可以组合使用，但我们强烈建议先应用所有先决条件，然后再在操作系统级别禁用 TLS 1.0 和 1.1。 最佳实践方法是：部署所有必备组件，验证工作负荷是否按预期正常运行，然后稍后继续禁用 TLS 1.0/1.1。

### <a name="disable-tls-10-and-11-via-registry-import"></a>通过注册表导入禁用 TLS 1.0 和 1.1

在继续执行下一步骤之前，请确保已完成所有先决条件并更新Skype for Business *服务器。*

将以下文本复制到一个记事本文件，并将其重命名为 **TLSDisable.reg**：

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

在要禁用 TLS 1.0 和 1.1 的每个服务器上导入 .reg 文件。 请重新启动服务器。 服务重新联机后，移动到下一台服务器。 池Enterprise Edition方法与针对任何操作系统更新采用的方法相同。

你可能已经注意到，我们所做的不仅仅是在此处禁用 TLS 1.0 和 1.1。 我们支持加密套件重新排序 (如上所示) 禁用一些旧的弱密码。 这是我们第一次正式支持对 Skype for Business Server 上的 SCHANNEL 和加密 API 的这些更改，需要注意的是，这些更改是唯一支持并且目前已经过测试的更改。 我们将来可能会考虑其他配置，但现在请不要在你的实现中修改注册表导入文件。

### <a name="validate-that-workloads-are-functioning-as-expected"></a>验证工作负荷是否正常工作

在环境中禁用 TLS 1.0 和 1.1 后，请确保所有主工作负荷均正常运行，如 IM & Presence、P2P 呼叫、企业语音 等。

**仅验证是否使用了 TLS 1.2**

让安全团队对 Skype for Business 通信执行新的审核，以确保不再使用较早的协议 TLS 1.0 和 1.1。

或者，您可以使用 Internet Explorer 在 TLS 1.0 和 TLS 1.1 被禁用后测试从 Skype for Business Server 2015 到 Web 服务的 TLS 连接。

1. 启动Internet Explorer。
2. 选择 **"工具**  >  **""Internet 选项"。**
3. 选择“高级”选项卡。
4. 在 **设置** 下，滚动到底部。
5. 验证是否已启用 TLS 1.0、TLS 1.1 和 TLS 1.2。
6. 浏览 SfB 2015 池的内部 Web 服务 URL， (连接成功) 。
7. 返回到"Internet Explorer并禁用"仅 **使用 TLS 1.2"** 选项。
8. 再次浏览 SfB 2015 池的内部 Web 服务 URL， (无法连接到) 。

![Internet 选项](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>高级部署方案

由于支持 Skype for Business Server 2015 中的 TLS 1.2 需要某些依赖项先决条件，因此在已禁用 TLS 1.0 和 1.1 的任何系统上，从 RTM 媒体进行安装将失败。

**在环境中Standard Edition TLS 1.0 和 1.1 Enterprise Edition部署新的服务器或池。**

**选项 1：** 使用 [SmartSetup](../../deploy/install/install-skype-for-business-server.md)。 请注意，我们将更新 SmartSetup 以适应更新SQL CU 中的二进制文件，并在将来更新本文。

**选项 2：** 在 RTCLOCAL SQL LYNCLOCAL (预安装本地) 

1. 下载并复制 SQL Express 2014 SP2 (SQLEXPR_x64.exe) FE 上的本地文件夹。 假设文件夹路径为 <SQL_FOLDER_PATH>。
2. 启动 PowerShell 或命令提示符并导航到 <SQL_FOLDER_PATH>。
3. 通过运行以下SQL创建 RTCLOCAL 实例。 请等待SQLEXPR_x64.exe完成，然后再继续：

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine，Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT=1 "NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. 通过运行SQL创建 LYNCLOCAL 实例。 请等待SQLEXPR_x64.exe完成，然后再继续下一步：

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine，Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT=1 "NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. 运行 Skype for Business Server 2015 RTM 安装程序。
2. 按照上述先决条件部分中的其余步骤操作。

**选项 3：** 还可以手动替换本地安装媒体目录中的二进制文件，如下所示：

1. [安装用于安装Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. 安装 .NET 4.7： 
      - **注意：** 我们首先在 Skype for Business Server 2015 CU5 (6.0.9319.281) 中引入了对 .NET 4.7 的支持。 因此，在下面的步骤中，我们将在主要安装之前更新核心组件。
      - 下载 https://www.microsoft.com/download/details.aspx?id=55167 ：。 
      - 参考[：应在部署 Skype for Business Server 2015 之前安装的软件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. 复制 ISO 文件/文件夹： 
    - 附加 Skype for Business Server 2015 ISO 后，在文件资源管理器中打开它作为 (Ex： D： 连接的驱动器 \) 的根目录。
    - 将所有文件夹和文件复制到本地磁盘上的文件夹 (例如：C：\SkypeForBusiness2015ISO) 。
    - **注意：** 在安装组件之前，需要更新某些文件以支持 TLS 1.2。
4. 替换 MSI/EXE 包： 
    - 替换本地计算机上安装媒体的 /Setup/amd64/ 文件夹中的现有 MSI 和 EXE 包。
    - SQL 2014 SP2 Express：https://www.microsoft.com/download/details.aspx?id=53167 
        - 重命名为SQLEXPR_x64本地计算机上，并替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。
    - SQL Native Client：https://www.microsoft.com/download/details.aspx?id=50402 
        - **注意：** 如有必要，重命名sqlncli.msi，然后替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。
    - SQL管理对象：https://www.microsoft.com/download/details.aspx?id=53164 
        - **注意：** 功能包中将包含许多可下载的项目。 选择以仅SharedManagementObjects.msi下载。
        - **注意：** 替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。
    - SQLCLR 类型：https://www.microsoft.com/download/details.aspx?id=53164 
        - **注意：** 功能包中将包含许多可下载的项目。 选择以仅CQLSysClrTypes.msi下载
        - **注意**：替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。
5. 安装核心组件： 
    - 从Setup.exe的 Setup/amd64/ 文件夹中运行安装程序。 按照说明安装核心组件
    - 关闭核心组件。
6. 更新核心组件： 
    - 下载 Skype for Business Update Installer。
    - 运行安装程序以更新核心组件并安装性能计数器。
    - **注意：** 自 CU6HF2 发布起，自动更新功能当前仅安装 CU6。 因此，更新程序必须单独运行，以将核心组件更新为 6.0.9319.516。
    - 参考： https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. 安装管理工具 (可选) ： 
    - 这将使用更新的文件安装 Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64) 和 Microsoft System CLR Types for SQL Server 2014 (x64) 。 此外，Skype for Business Server 2015 拓扑生成器和控制面板将在本地计算机上可用。
8. 安装本地配置存储 (步骤 1) ： 
     - 打开部署向导，单击"安装或更新Skype for Business Server"，然后单击"步骤 1： 安装本地配置存储"中的"运行"。 
     - 在 **"安装** 本地配置 **存储"对话框中单击"下一** 步"。
     !["安装本地配置存储"对话框](../../media/local-configuration-store.png)
     - 查看结果，并确保"任务状态"已完成。 通过单击"查看日志文件查看生成的 **记录**。
     ![任务状态将显示为"已完成"](../../media/local-configuration-task-completed.png)
     - 单击“完成”。
9. 在步骤 2 Skype for Business Server中 (或删除) ：
    - 打开部署向导，单击 **安装或Skype for Business Server系统"，** 然后单击"步骤 2： 设置或删除部署组件Skype for Business Server运行
    - 单击 **"** 设置组件Skype for Business Server中的"下一步"。
    !["设置Skype for Business Server组件"窗口](../../media/set-up-skype-for-business-server-components-window.png)
    - 使用"查看日志"查看日志，并验证安装是否已完成且没有问题。 
    - 单击“完成”。
10. 如果需要，请继续进行其他安装和配置 (此时您可以恢复正常的安装) 。