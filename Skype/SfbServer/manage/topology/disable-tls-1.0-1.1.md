---
title: 在 Skype for Business Server 2015 中禁用 TLS 1.0/1.1
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
description: 摘要：准备和实施在环境中禁用 TLS 1.0 和 1.1。
ms.openlocfilehash: da76280540f9d18435ed929aace6cf6fc439a4cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826392"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中禁用 TLS 1.0/1.1

本文的目的是为准备和实施环境中禁用 TLS 1.0 和 1.1 提供必要的指导。 此过程需要进行广泛的规划和准备。 在计划为组织禁用 TLS 1.0 和 1.1 时，请仔细检查本文中所有的信息。 请注意，禁用 TLS 1.0/1.1 可能会影响许多外部依赖项和连接条件，因此需要进行广泛的规划和测试。

## <a name="in-this-article"></a>本文内容

- [背景和范围](#background)
- [先决条件和过程](#prerequisites-and-process)
- [高级部署方案](#advanced-deployment-scenarios)

## <a name="background"></a>背景

提供 TLS 1.0 和 1.1 禁用对 Skype for Business Server 本地支持的主要驱动因素是支付卡行业 (PCI) 安全标准委员会和联邦信息处理标准要求。 有关 PCI 要求详细信息，请参阅 [此处](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。  Microsoft 无法提供有关组织是否需要遵守这些或其他要求的指导。 您必须确定在环境中禁用 TLS 1.0 和/或 1.1 是否是必需的。

Microsoft 已制作一份有关此处提供的[](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)TLS 的白皮书，我们还建议在此 Exchange 博客中提供背景[阅读](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)。

## <a name="supportability-scope"></a>可支持性范围

*范围* 是指可支持性边界。 *完全测试和支持* 意味着我们完全支持并已针对列出的产品版本禁用 TLS 1.0 和 1.1。 *当前正在调查* 意味着这一点;我们正在积极调查将这些产品引入 TLS 禁用支持的范围。 *超出范围* 意味着这些产品版本不支持禁用 TLS 1.0 或 1.1，并且将不起作用，但已指出的例外情况。

### <a name="fully-tested-and-supported-servers"></a>经过完全测试且受支持的服务器

- Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年 6 月) 或更高版本
- skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseded update) ， 2012 R2 or 2016.
- 在 Windows Server 2008 R2、2012)  (KB [为 3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 或取代更新) 或 2012 R2 的 Windows Server 2008 R2、2012 (中，CU9 6.0.9319.548 (2019 年 5 月或更高版本就地升级的 Skype for Business Server 2015。
- Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher， guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Survivable Branch Appliance (SBA) With Skype for Business Server 2015 CU6 版 (或更高版本向供应商确认他们打包了相应的更新，并且已可用于你的) 
- Survivable Branch Server (SBS) Skype for Business Server 2015 CU6 版</) 或更高版本
- 仅 Lync Server 2013 边缘角色，这是因为边缘角色对 Windows Fabric 1.0 没有依赖关系。

### <a name="fully-tested-and-supported-clients"></a>经过完全测试且受支持的客户端

- Lync 2013 (Skype for Business) 桌面客户端、MSI 和 C2R，包括基本 [15.0.5023.1000 或更高版本](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype for Business 2016 桌面客户端、MSI [16.0.4678.1000 或更高版本](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)，包括基本
- Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates: 
    - 每月和Semi-Annual定向、16 \. 0 \. 9126 \. 2152 或更高版本
    - Semi-Annual和延期频道，16 \. 0 \. 8431 \. 2242 或更高版本
- Mac 16.15 或更高版本上的 Skype for Business
- 适用于 iOS 和 Android 6.19 或更高版本的 Skype for Business
- Microsoft Teams 会议室 (2018 年 12 月或更高版本) Skype 会议室系统 V2 SRS V2 (4.0.64.0) 
- 基于 KB4499162 的 Surface Hub 更新 (2019 年 5 月操作系统版本 15063.1835) 或更高版本
- Server 2015 附带 Skype Web App 2015 CU6 (或更高版本) 

### <a name="currently-being-investigated"></a>当前正在调查

- 呼叫质量仪表板 (TLS 1.0、1.1 后的新安装，请参阅下面的) *
 
### <a name="out-of-scope"></a>超出范围

除非说明，以下产品不在 TLS 1.0/1.1 禁用支持范围内，并且不会在 TLS 1.0 和 1.1 已禁用的环境中运行。 这意味着：如果仍使用作用域外服务器或客户端，则必须更新或删除这些服务器或客户端（如果需要在 Skype for Business Server 本地部署中的任意位置禁用 TLS 1.0/1.1）。

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 或更低版本
- Lync for Mac 2011
- Lync 2013 移动版 - iOS、iPad、Android 或 Windows Phone
- Lync "MX" Windows 应用商店客户端
- Lync Room System (.k.a. SRSv1) 。 LRS 于 2018 年 10 月 9 日终止支持，不会进行更新以支持 TLS 1.2。
- 所有 Lync 2010 客户端
- Lync Phone Edition - 此处更新 [了指南](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)。
- 基于 2013 的 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS) 
- 云连接器版本 (CCE) 
- Skype for Business for Windows Phone

### <a name="exceptions"></a>Exceptions

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 依赖 Windows Fabric 1.0 版。  在 Lync Server 2013 的设计阶段，为 Windows Fabric 1.0 选择了具有吸引力的新分布式体系结构，以提供复制、高可用性和容错。  随着时间的推移，Skype for Business Server 和 Windows Fabric 已显著改进此联合体系结构，在后续版本中进行重大重新设计。  例如，当前 Skype for Business 2015 Server 使用 Windows Fabric 3.0。

遗憾的是，Windows Fabric 1.0 **不支持 TLS 1.2。 但是，我们将更新 Lync Server 2013 以使用 TLS 1.2。** 这将在 Lync Server 2013 的下一次累积更新中提供。  我们提供 TLS 1.2 支持，以实现共存、迁移、联合和混合方案。

如果你的组织需要禁用 TLS 1.0 和 1.1，并且你当前使用 Lync Server 2013，我们建议你开始规划过程，你可能必须就地升级或并行迁移 (新池，将用户) 移动到 Skype for Business Server 2015 或更高版本。  或者，你可能想要加速迁移到 Skype for Business Online。

#### <a name="call-quality-dashboard"></a>通话质量仪表板

本地呼叫质量仪表板当前依赖于新安装期间 TLS 1.0 (首次安装到本地环境时) 。  我们目前正在调查此问题，并计划在近期发布修补程序。  如果计划安装 CQD 并同时禁用 TLS 1.0，我们建议您首先完成 CQD 安装，然后继续禁用 TLS 1.0。

#### <a name="skype-for-business-sdn-manager"></a>Skype for Business SDN 管理器

使用 Skype for Business SDN 管理器SQL新安装期间，数据库依赖于 TLS 1.0。 如果计划使用 SQL 数据库安装 Skype for Business SDN 管理器并禁用 TLS 1.0，我们建议您首先完成 Skype for Business SDN 管理器，然后继续禁用 TLS 1.0。 如果 TLS 1.0 在安装之前已被禁用，应在将用于托管 Skype for Business SDN 管理器 SQL 数据库的 SQL Server 后端服务器中临时启用 TLS 1.0。

#### <a name="third-party-devices"></a>第三方设备

在 3PIP 电话、视频会议、反向代理和负载平衡器等第三方设备上，请务必验证 TLS 1.2 可支持性，仔细测试，并根据需要与供应商联系。

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>在边缘服务器上禁用 TLS 1.0/1.1 时联合身份验证注意事项

必须仔细规划并考虑禁用 TLS 1.0/1.1 对边缘服务器的影响。  禁用 TLS 1.0 和 1.1 后，您可能会发现其他组织无法再与您的组织联盟。

您可以选择在边缘服务器上保持启用 TLS 1.0/1.1，以保持与非修补的 (SfB 2015、Lync 2013) 或 (2010) 外部系统的向后兼容性。

Microsoft 无法提供有关边缘网络网络或 (网络网络是否) PCI 标准的建议或建议;必须由单个公司确定。

Skype for Business Online 现在支持 TLS 1.2，因此对与 Online 的混合/联盟没有影响。

PIC (公共 IM) Skype 消费者服务：我们预计禁用 TLS 1.0/1.1 不会影响 Skype [连接](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 网关已经支持 TLS 1.2。

## <a name="prerequisites-and-process"></a>先决条件和过程

除非如上所述，一旦禁用了 TLS 1.0 和 1.1 的作用域外服务器，客户端和设备将更长地正常运行，或一切正常。 这可能意味着你需要暂停并等待来自 Microsoft 的更新指导。 一旦满足所有要求并计划解决差距，请继续。

在高级别上，虽然 Skype for Business Server 2019 已做好安装过程准备，但 Skype for Business Server 2015 将要求您安装 CU9，将先决条件更新应用到 .NET 和 SQL，部署必备注册表项，最后是单独一轮操作系统配置更新 (即通过注册表文件导入) 禁用 TLS 1.0 和 1.1。 在环境中的任何服务器上禁用 TLS 1.0 和 1.1 之前，必须完成所有必备组件（包括 Skype for Business Server 2015 CU6 IBM2）的安装，这一点至关重要。 每个 Skype for Business 服务器（包括边缘角色SQL后端）都需要更新。 此外，请确保所有 (范围内) 客户端已更新为所需的最低版本。 不要忘记更新管理工作站。

我们希望遵循"从内到外"的常规操作顺序来升级 Skype for Business 服务器。 以通常相同的方式处理控制器池、持久聊天和配对池。 此处和此处介绍了升级[的顺序](topology.md)[和方法](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。

### <a name="high-level-process"></a>高级流程

1. 在配置生产服务器之前，测试实验室中的所有步骤。
2. 在每台要更新的每台服务器上备份并保留导出的注册表副本。 不能在服务器之间共享注册表;它们包含基于计算机的唯一密钥。
3. 将所有 Skype for Business 2015 服务器升级到 CU9 或更高版本。 对于 Skype for Business Server 2019，请升级到 CU1 或更高版本。
4. 将所有必备组件安装到所有服务器。
5. 部署必备注册表项。
6. 确保所有作用域内客户端已更新。
7. 通过注册表导入禁用 TLS 1.0 和 1.1。
8. 验证工作负荷是否正常工作。
    - 如果遇到问题，则进行故障排除和解决，或者
    - 从步骤 2 还原注册表以重新启用 TLS 1.0 和 1.1
9. 验证是否仅使用了 TLS 1.2。

### <a name="install-prerequisites-to-all-servers"></a>将必备组件安装到所有服务器

在开始在 Skype for Business Server 2015 部署的操作系统级别禁用 TLS 1.0 和 1.1 之前，需要进行广泛的依赖更新。 以下是支持 TLS 1.2 的最低版本。 在开始禁用 TLS 1.0 和 1.1 之前，在环境中每个 Skype for Business 服务器上部署所有必备组件更新。

- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 或更高版本
- [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) 或更高版本，在注册表中启用 SchUseStrongCrypto， (提供如下) 
- SQL必须在所有 Skype for Business 2015 服务器和后端上进行更新。 首先更新 Enterprise Edition Pool SQL后端，然后更新其各自的 FES。 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)或更高版本/ SQL Server 2012 SP2 + CU16 或更高版本/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)或更高版本/ SQL Server 2014 SP2
     - [SQL Server 2012 SQL Server Native Client](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)或更高版本
     - [SQL Server 2014 SP2 的共享管理对象](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes for SQL server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>按建议的操作顺序安装先决条件的基本步骤

1. 将 Skype for Business Server CU9 更新安装到所有服务器。 
    1. 使用更新程序将更新安装到组件。
    2. 根据记录的过程更新数据库。 对于 Skype for Business Server 2015，请参阅 KB [3061064。](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    3. 在推进任何其他更改之前，验证部署中的产品功能。
2. 下载 .NET 4.7 脱机安装程序。 
    1. 参考： [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. 确保前端服务器上已停止 Skype for Business Server 2015 服务。
    3. 参考： [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. 例如 (Standard Edition) ： ```Stop-CsWindowsService```
    5. 例如 (Enterprise Edition) ： ```Invoke-CsComputerFailover```
    6. 运行安装程序程序包。
    7. 请重新启动服务器。
3. 在所有SQL更新 Express 2014。 
    1. 参考： [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. 下载 SQL 2014 SP2 
        - 参考： [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. 将安装媒体复制到服务器上文件夹 (例如：C：\01_2014SqlSp2) 
    4. 确保前端服务器上已停止 Skype for Business Server 2015 服务 
        - 例如 (Standard Edition) ： ```Stop-CsWindowsService```
        - 例如 (Enterprise Edition) ： ```Invoke-CsComputerFailover```
    5. 打开管理命令提示符，并升级所有已安装的组件和实例 
        - 示例：C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. 更新SQL客户端。 
    1. 参考 [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) ：。
    2. 下载自 [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. 确保前端服务器上已停止 Skype for Business Server 2015 服务。 
        - 例如 (Standard Edition) ： ```Stop-CsWindowsServices```
        - 例如 (Enterprise Edition) ： ```Invoke-CsComputerFailover```
    4. 停止SQL实例运行 
        - 例如： ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 例如： ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - 例如 (Standard Edition) ： ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 安装该更新。
5. 更新 ODBC Driver 11 for SQL Server以包含对 TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)) 。
    1. 下载 [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)。
    2. 确保前端服务器上已停止 Skype for Business Server 2015 服务。
        - Standard Edition (示例) ： ```Stop-CsWindowsService```
        - Enterprise Edition (示例) ： ```Invoke-CsComputerFailover```
    3. 安装该更新。
6. 部署必备注册表项。

### <a name="pre-requisite-registry-keys"></a>先决条件注册表项

将以下测试复制/粘贴到记事本中，重命名 TLSPreReq.reg 或您所选择的名称，然后导入：

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

对于SQL池的后端，必备组件和 TLS 禁用应视为任何SQL操作系统更新;请参阅： [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

尽管必备应用程序和 TLS 禁用步骤都可以组合使用，但我们强烈建议先应用所有必备组件，然后再在操作系统级别继续禁用 TLS 1.0 和 1.1。 最佳做法是准备环境，方法是部署所有必备组件，验证工作负荷是否按预期正常运行，然后稍后继续禁用 TLS 1.0/1.1。

### <a name="disable-tls-10-and-11-via-registry-import"></a>通过注册表导入禁用 TLS 1.0 和 1.1

在继续执行下一步之前，请确保已完成所有先决条件和更新 *的 Skype for Business 服务器*。

将以下文本复制到记事本文件中，并将其重命名 **为 TLSDisable.reg：**

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

在要禁用 TLS 1.0 和 1.1 的每个服务器上导入 .reg 文件。 请重新启动服务器。 服务重新联机后，移动到下一台服务器。 Enterprise Edition Pools 的方法与任何操作系统更新的方法相同。

你可能已经注意到，我们所做的不仅仅是禁用 TLS 1.0 和 1.1。 我们支持加密套件重新排序 (如上所示) 禁用一些旧的弱密码。 这是我们第一次正式支持对 Skype for Business Server 上的 SCHANNEL 和加密 API 的这些更改，必须注意，这些更改是唯一支持并且目前已经过测试的更改。 我们将来可能会考虑其他配置，但现在请不要在你的实现中修改注册表导入文件。

### <a name="validate-that-workloads-are-functioning-as-expected"></a>验证工作负荷是否正常工作

在环境中禁用 TLS 1.0 和 1.1 后，请确保所有主工作负荷均正常运行，例如 IM & 状态、P2P 呼叫、企业语音等。

**仅验证是否使用了 TLS 1.2**

让安全团队对 Skype for Business 流量执行新的审核，以确保不再使用较旧的协议 TLS 1.0 和 1.1。

或者，在 TLS 1.0 和 TLS 1.1 被禁用后，可以使用 Internet Explorer 测试从 Skype for Business Server 2015 到 Web 服务的 TLS 连接。

1. 启动Internet Explorer。
2. 选择 **工具**  >  **Internet 选项**。
3. 选择 **"高级"** 选项卡。
4. 在 **"设置**"下，滚动到底部。
5. 验证是否已启用 TLS 1.0、TLS 1.1 和 TLS 1.2。
6. 浏览 SfB 2015 池的内部 Web 服务 URL， (连接成功) 。
7. 返回到Internet Explorer并禁用"仅使用 **TLS 1.2"** 选项。
8. 再次浏览 SfB 2015 池的内部 Web 服务 URL， (连接失败) 。

![Internet 选项](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>高级部署方案

由于在 Skype for Business Server 2015 中支持 TLS 1.2 需要一些依赖先决条件，因此从 RTM 媒体安装将在已禁用 TLS 1.0 和 1.1 的任何系统上失败。

**在环境中禁用 TLS 1.0 和 1.1 后部署新的 Standard Edition Servers 或 Enterprise Edition 池。**

**选项 1：** 使用 [SmartSetup](../../deploy/install/install-skype-for-business-server.md)。 请注意，我们将更新 SmartSetup 以适应SQL CU 中更新的二进制文件，并在将来更新本文。

**选项 2：** 在 RTCLOCAL SQL LYNCLOCAL (预安装本地实例) 

1. 下载 Express 2014 SP2 SQL， (SQLEXPR_x64.exe) 复制到 FE 上的本地文件夹。 假设文件夹路径为 <SQL_FOLDER_PATH>。
2. 启动 PowerShell 或命令提示符并导航到 <SQL_FOLDER_PATH>。
3. 通过运行以下SQL创建 RTCLOCAL 实例。 请等待SQLEXPR_x64.exe完成，然后再继续：

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine，Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. 通过运行以下SQL创建 LYNCLOCAL 实例。 请等待SQLEXPR_x64.exe完成，然后再继续下一步：

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine，Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT=1 "NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. 运行 Skype for Business Server 2015 RTM 安装程序。
2. 按照上述先决条件部分的剩余步骤操作。

**选项 3：** 还可以手动替换本地安装媒体目录中的二进制文件，如下所示：

1. [安装 Skype for Business Server 的先决条件](../../deploy/install/install-prerequisites.md)  
2. 安装 .NET 4.7： 
      - **注意：** 我们首先在 Skype for Business Server 2015 CU5 (6.0.9319.281) 中引入了对 .NET 4.7 的支持。 因此，在下面的步骤中，我们将在主要安装之前更新核心组件。
      - 下载： https://www.microsoft.com/download/details.aspx?id=55167 。 
      - 参考[：应在 Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)部署之前安装的软件
3. 复制 ISO 文件/文件夹： 
    - 附加 Skype for Business Server 2015 ISO 后，在文件资源管理器中打开它作为 (Ex： D： 连接的驱动器 \) 的根目录。
    - 将所有文件夹和文件复制到本地磁盘上的文件夹 (例如：C：\SkypeForBusiness2015ISO) 。
    - **注意：** 在安装组件之前，需要更新某些文件以支持 TLS 1.2。
4. 替换 MSI/EXE 包： 
    - 替换本地计算机上安装媒体的 /Setup/amd64/ 文件夹中的现有 MSI 和 EXE 包。
    - SQL 2014 SP2 Express： https://www.microsoft.com/download/details.aspx?id=53167 
        - 重命名为SQLEXPR_x64计算机上的名称，并替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。
    - SQL本机客户端： https://www.microsoft.com/download/details.aspx?id=50402 
        - **注意：** 如有必要，请重命名sqlncli.msi，然后替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。
    - SQL管理对象： https://www.microsoft.com/download/details.aspx?id=53164 
        - **注意：** 功能包将有很多可下载的项目。 选择以仅SharedManagementObjects.msi下载。
        - **注意：** 替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。
    - SQL CLR 类型： https://www.microsoft.com/download/details.aspx?id=53164 
        - **注意：** 功能包将有很多可下载的项目。 选择仅CQLSysClrTypes.msi下载
        - **注意**：替换安装媒体的 Setup/amd64/ 文件夹中的现有文件。
5. 安装核心组件： 
    - 从Setup.exe的 Setup/amd64/ 文件夹中运行安装程序。 按照说明安装核心组件
    - 关闭核心组件。
6. 更新核心组件： 
    - 下载 Skype for Business 更新安装程序。
    - 运行安装程序以更新核心组件并安装性能计数器。
    - **注意：** 自 CU6HF2 发布起，自动更新功能当前最多只能安装 CU6。 因此，更新程序必须单独运行，以将核心组件更新为 6.0.9319.516。
    - 参考： https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. 安装管理工具 (可选) ： 
    - 这将使用更新的文件安装 Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64) 和 Microsoft System CLR Types for SQL Server 2014 (x64) 。 此外，本地计算机上还将提供 Skype for Business Server 2015 拓扑生成器和控制面板。
8. 安装本地配置存储 (步骤 1) ： 
     - 打开部署向导，单击"安装或更新 Skype for Business Server系统"，然后单击"步骤 1：安装本地配置存储"中的"运行"。
     - 在 **"** 安装本地配置 **存储"对话框中单击"下一** 步"。
     !["安装本地配置存储"对话框](../../media/local-configuration-store.png)
     - 查看结果，并确保任务状态已完成。 通过单击"日志文件日志 **"查看生成的结果**。
     ![任务状态将显示为"已完成"](../../media/local-configuration-task-completed.png)
     - 单击“完成”。
9. 在步骤 2 中设置 (或删除 Skype for Business Server) ：
    - 打开部署向导，单击 **"安装或** 更新 Skype for Business Server系统"，然后单击"步骤 2：设置或删除 Skype for Business Server 组件"中的"运行"
    - 在 **"** 设置 Skype for Business Server 组件"对话框中单击"下一步"。
    !["设置 Skype for Business Server 组件"窗口](../../media/set-up-skype-for-business-server-components-window.png)
    - 使用视图日志查看日志，并验证安装程序是否已完成且没有问题。 
    - 单击“完成”。
10. 如果需要，请继续其他安装和配置 (此时可以恢复正常安装) 。
