---
title: 在 Skype for Business Server 2015 中禁用 TLS 1.0/1。1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：在你的环境中准备和实现禁用 TLS 1.0 和1.1。
ms.openlocfilehash: 691dcc170830b3efa6129d23401930fcf1c149cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817143"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中禁用 TLS 1.0/1。1

本文旨在为你提供必要的指南，以便你准备和实现在你的环境中禁用 TLS 1.0 和1.1。 此过程需要广泛的规划和准备。 请仔细查看本文中的所有信息，确保你的计划能够为你的组织禁用 TLS 1.0 和1.1。 请注意，有许多外部依赖项和连接条件可能会受到禁用 TLS 1.0/1.1 的影响，因此需要进行大量的计划和测试。

## <a name="in-this-article"></a>在本文中

- [背景和作用域](#background)
- [先决条件和过程](#prerequisites-and-process)
- [高级部署方案](#advanced-deployment-scenarios)

## <a name="background"></a>背景

提供 TLS 1.0 和1.1 的主要驱动程序对本地 Skype for business 服务器禁用支持是支付卡行业（PCI）安全标准委员会和联邦信息处理标准的要求。 可[在此处](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)找到有关 PCI 要求的详细信息。  Microsoft 无法提供有关您的组织是否需要遵守这些或其他要求的指导。 你必须确定是否需要在你的环境中禁用 TLS 1.0 和/或1.1。

Microsoft 在[此处](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)提供了有关 TLS 的白皮书，我们还建议在此[Exchange 博客](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)中提供的后台阅读功能。

## <a name="supportability-scope"></a>支持范围

*范围*指的是可支持性边界。 *经完全测试和支持*意味着我们完全支持并针对列出的产品版本对 TLS 1.0 和1.1 的禁用进行了测试。 *目前正在调查*的是，这一点是指我们正在积极调查如何将这些产品带入 TLS 禁用支持的范围内。 *超出范围*意味着这些产品版本不支持禁用 TLS 1.0 或1.1，并且将无法正常工作，但所注明的例外情况除外。

### <a name="fully-tested-and-supported-servers"></a>经过充分测试和支持的服务器

- Skype for Business Server 2019 CU1 17.0.2046.123 （6月2019日）或更高版本
- Skype for Business Server 2015 CU9 6.0.9319.548 （五月2019）或更高版本在 Windows Server 2012 上（有 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新），2012 R2 或2016。
- 就地升级的 Skype for business Server 2015，CU9 6.0.9319.548 （五月2019）或更高版本的 Windows Server 2008 R2、2012（包含 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新）或 2012 r2。
- Exchange 连接和 Outlook Web App 与 Exchange Server 2010 SP3 RU19 或更高版本，请参阅[此处](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)的指南
- Survivable 分支装置（SBA）使用 Skype for Business Server 2015 CU6 HF2 或更高版本（请向您的供应商确认他们已将 appropiate 更新打包，并已为你的设备提供）
- Survivable 分支服务器（SBS）与 Skype for Business Server 2015 CU6 HF2 或更高版本
- Lync Server 2013 **Edge 角色**，这是因为 edge 角色不依赖于 Windows Fabric 1.0。

### <a name="fully-tested-and-supported-clients"></a>经过充分测试和支持的客户端

- Lync 2013 （Skype for Business）桌面客户端、MSI 和 C2R，包括基本[15.0.5023.1000 或更高版本](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype for Business 2016 桌面客户端、MSI [16.0.4678.1000 或更高版本](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)，包括基本
- Skype for Business 2016 单击以运行时需要[2018 年4月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)更新： 
    - 每月和半年度目标、16\.0\.9126\.2152 或更高版本
    - 半年和延期频道，16\.0\.8431\.2242 或更高版本
- Mac 16.15 或更高版本上的 Skype for Business
- 适用于 iOS 和 Android 6.19 或更高版本的 Skype for business
- Microsoft 团队聊天室（以前称为 Skype 会议室 System V2 SRS V2）4.0.64.0 （2018年12月）或更高版本
- 基于 KB4499162 （可能是2019、操作系统内部版本15063.1835）或更高版本的 Team edition 的 Surface Hub 更新
- Skype Web App 2015 CU6 HF2 或更高版本（随服务器一起提供）

### <a name="currently-being-investigated"></a>当前正在调查

- 通话质量仪表板（TLS 1.0 后的全新安装，1.1 已禁用，请参阅下文） *
 
### <a name="out-of-scope"></a>超出范围

除非另有说明，否则以下产品不在 TLS 1.0/1.1 禁用支持的范围内，在禁用 TLS 1.0 和1.1 的环境中将不起作用。 这意味着：如果仍在使用超出范围的服务器或客户，则必须在 Skype for Business Server 内部部署中的任意位置禁用 TLS 1.0/1.1，否则必须更新或删除它们。

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 或更低
- Lync for Mac 2011
- 适用于移动版的 Lync 2013-iOS、iPad、Android 或 Windows Phone
- Lync "MX" Windows 应用商店客户端
- Lync 会议室系统（a.k.a。 SRSv1). LRS 已达到2018年10月9日的支持结束，并且不会更新为支持 TLS 1.2。
- 所有 Lync 2010 客户端
- Lync Phone Edition-更新的[指南。](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)
- 基于2013的 Survivable 分支装置（SBA）或 Survivable 分支服务器（SBS）
- 云连接器版（CCE）
- Windows Phone 版 Skype for Business

### <a name="exceptions"></a>异常

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 依赖于 Windows Fabric 版本1.0。  在 Lync Server 2013 的设计阶段，为其引人注目的和新的分布式体系结构选择了 Windows Fabric 1.0 以提供复制、高可用性和容错。  随着时间的推移，Skype for business 服务器和 Windows Fabric 在后续版本中大大提高了这种联合体系结构的显著重新设计。  例如，当前 Skype for Business 2015 服务器使用的是 Windows Fabric 3.0。

很遗憾，Windows Fabric 1.0 不**支持 TLS 1.2。 但是，我们将更新 Lync Server 2013 以与 TLS 1.2 配合工作**。 这将进入 Lync Server 2013 的下一个累积更新。  我们提供了 TLS 1.2 支持以启用共存、迁移、联盟和混合方案。

如果你的组织需要禁用 TLS 1.0 和1.1，并且你当前使用的是 Lync Server 2013，我们建议你开始计划过程，但你可能需要就地升级或并行迁移（新的池、移动用户）到 Skype for Business企业服务器2015或更高版本。  或者，您可能希望加速迁移到 Skype for business Online。

#### <a name="call-quality-dashboard"></a>呼叫质量仪表板

在全新安装期间，本地呼叫质量仪表板当前对 TLS 1.0 有依赖性（首次安装到本地环境）。  我们目前正在调查此问题，并计划在不久的将来发布修补程序。  如果你计划安装 CQD 并禁用 TLS 1.0，我们建议你先完成 CQD 安装，然后再继续 TLS 1.0 禁用。

#### <a name="third-party-devices"></a>第三方设备

在第三方设备（如3PIP 电话、视频会议、反向代理和负载平衡器）上，确保验证 TLS 1.2 可支持性，仔细测试，如果需要，请与供应商联系。

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>在边缘服务器上禁用 TLS 1.0/1.1 时的联合注意事项

您必须仔细规划并考虑在边缘服务器上禁用 TLS 1.0/1.1 的影响。  一旦 TLS 1.0 和1.1 被禁用，你可能会发现其他组织无法再与你的组织联盟。

你可以选择将 TLS 1.0/1.1 保留在 Edge 服务器上，以保持与非修补（SfB 2015、Lync 2013）或较早（2010）外部系统的向后兼容性。

Microsoft 无法提供有关您的 Edge 网络（或任何网络）是否属于 PCI 标准的建议或建议。必须由单个公司确定。

Skype for Business Online 目前支持 TLS 1.2，因此不需要与在线的混合/联盟产生任何影响。

PIC （公共 IM 连接）到 Skype 消费者服务：我们不希望禁用 TLS 1.0/1.1 来影响[Skype 连接](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 网关已经支持支持 TLS 1.2。

## <a name="prerequisites-and-process"></a>先决条件和过程

除了上面提到的情况，一旦 TLS 1.0 和1.1 禁用了超出范围的服务器，客户和设备将继续正常运行，或者完全正常。 这可能意味着你需要暂停并等待来自 Microsoft 的更新指南。 一旦您满意满足所有要求并制定一个计划来解决缺口，请继续操作。

在较高级别，虽然 Skype for business Server 2019 已准备好进行安装过程，但 Skype for business Server 2015 将要求你安装 CU9、将必备更新应用到 .NET 和 SQL、部署必备注册表项以及最后一个单独的一轮操作系统配置更新（例如，通过注册表文件导入禁用 TLS 1.0 和1.1）。 在你环境中的任何服务器上禁用 TLS 1.0 和1.1 之前，必须先完成安装所有先决条件（包括 Skype for Business Server 2015 CU6 HF2），这一点至关重要。 每个 Skype for Business 服务器（包括边缘角色和 SQL Backends）都需要更新。 还要确保所有受支持的（范围内）客户端已更新为所需的最低版本。 不要忘记更新管理工作站。

我们希望按照通常的 "内部" 操作顺序来升级 Skype for Business 服务器。 按照正常方式处理控制器池、持久聊天和配对的池。 升级的订单和方法在[此处](topology.md)和[此处](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)介绍。

### <a name="high-level-process"></a>高级别流程

1. 在配置生产服务器之前测试实验室中的所有步骤。
2. 在要更新的每台服务器和每台服务器上备份和保留导出注册表的副本。 不能在服务器之间共享注册表;它们包含基于计算机的唯一密钥。
3. 将所有 Skype for business 2015 服务器升级到 CU9 或更高版本。 对于 Skype for business Server 2019，请升级到 CU1 或更高版本。
4. 将所有先决条件安装到所有服务器。
5. 部署必备注册表项。
6. 确保更新所有范围内客户端。
7. 通过注册表导入禁用 TLS 1.0 和1.1。
8. 验证工作负荷是否按预期运行。
    - 如果遇到问题、排除和解决问题，或者
    - 从步骤2还原注册表以重新启用 TLS 1.0 和1。1
9. 验证是否仅使用 TLS 1.2。

### <a name="install-prerequisites-to-all-servers"></a>将先决条件安装到所有服务器

在开始在 Skype for Business Server 2015 部署中的操作系统级别禁用 TLS 1.0 和1.1 之前，需要进行广泛的依赖项更新。 以下是可支持 TLS 1.2 的最低版本。 在开始禁用 TLS 1.0 和1.1 之前，在你的环境中的每个 Skype for Business 服务器上部署所有先决条件更新。

- Skype for Business Server 2015 CU9 6.0.9319.548 （五月2019）或更高版本
- [.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)或更高版本在注册表中启用了 SchUseStrongCrypto （如下所示）
- 必须在所有 Skype for Business 2015 服务器和 backends 上更新 SQL。 首先更新企业版池 SQL Backends，然后再更新其各自的 FEs。 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)或更高版本/sql SERVER 2012 SP2 + CU16 或更高版本/ [SQL server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)或更高版本/sql server 2014 SP2
     - [SQL server 的 SQL Server Native Client 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [MICROSOFT ODBC Driver 11 FOR SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)或更高版本
     - [SQL Server 2014 SP2 的共享管理对象](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQL server 2014 SP2 的 SQLSysClrTypes](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>安装先决条件的基本步骤，以推荐的操作顺序

1. 将 Skype for business Server CU9 更新安装到所有服务器。 
    1. 使用更新程序安装对组件的更新。
    2. 根据已记录的过程更新数据库。 对于 Skype for business 服务器2015，请参阅 KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。
    3. 在迁移之前先验证部署中的产品功能，然后再进行任何其他更改。
2. 下载 .NET 4.7 脱机安装程序。 
    1. 参阅[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. 确保在前端服务器上停止 Skype for business Server 2015 服务。
    3. 参阅[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex （标准版）：```Stop-CsWindowsService```
    5. Ex （企业版）：```Invoke-CsComputerFailover```
    6. 运行安装程序包。
    7. 重新启动服务器。
3. 在所有服务器上更新 SQL Express 2014。 
    1. 参阅[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. 下载 SQL 2014 SP2 
        - 参阅[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. 将安装媒体复制到服务器上的文件夹（例如： C：\ 01_2014SqlSp2）
    4. 确保在前端服务器上停止 Skype for business 服务器2015服务 
        - Ex （标准版）：```Stop-CsWindowsService```
        - Ex （企业版）：```Invoke-CsComputerFailover```
    5. 打开管理员命令提示符，并升级所有已安装的组件和实例 
        - 示例： C：\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances
4. 更新 SQL Native 客户端。 
    1. 参考： [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)。
    2. 下载自[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. 确保前端服务器上的 Skype for business Server 2015 服务已停止。 
        - Ex （标准版）：```Stop-CsWindowsServices```
        - Ex （企业版）：```Invoke-CsComputerFailover```
    4. 停止运行已安装的 SQL 实例 
        - 例如```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 例如```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex （仅适用于标准版）：```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 安装该更新。
5. 更新 ODBC Driver 11 for SQL Server 以包括对 TLS 1.2 （KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)）的支持。
    1. 下载[SQL Server 的 ODBC 驱动程序 11-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)。
    2. 确保在前端服务器上停止 Skype for business Server 2015 服务。
        - 示例（标准版）：```Stop-CsWindowsService```
        - 示例（企业版）：```Invoke-CsComputerFailover```
    3. 安装该更新。
6. 部署必备注册表项。

### <a name="pre-requisite-registry-keys"></a>预必备注册表项

将以下测试复制/粘贴到记事本中并重命名 TLSPreReq 或您选择的名称，然后导入：

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

对于适用于企业版池的 SQL 后端，应将先决条件和 TLS disable 视为任何 SQL 或 OS 更新。请参阅：[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

虽然必备的应用程序和 TLS 禁用步骤都可以合并，但我们强烈建议在操作系统级别继续禁用 TLS 1.0 和1.1 之前应用所有先决条件。 最佳做法做法是通过部署所有先决条件来准备环境、验证工作负荷是否正常运行和预期，然后在以后继续执行 TLS 1.0/1.1。

### <a name="disable-tls-10-and-11-via-registry-import"></a>通过注册表导入禁用 TLS 1.0 和1。1

在继续下一步操作之前，*请确保已完成所有先决条件和更新的 Skype for Business 服务器*。

将以下文本复制到记事本文件中，然后将其重命名**TLSDisable**：

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

在要禁用 TLS 1.0 和1.1 的每台服务器上导入 .reg 文件。 重新启动服务器。 服务重新联机后，移动到下一台服务器。 适用于企业版池的方法与进行任何操作系统更新所需的方法相同。

你可能已注意到，我们执行的操作不仅仅是在此处禁用 TLS 1.0 和1.1。 我们支持密码套件重新排序（如上所示）和禁用某些较旧的弱密码。 这是我们首次在 Skype for Business 服务器上对 SCHANNEL 和加密 API 的这些更改的首次支持，请务必注意，这些更改是我们支持且现在已测试的唯一这些更改。 我们将来可能会考虑到其他配置，但目前请不要在你的实现中修改注册表导入文件。

### <a name="validate-that-workloads-are-functioning-as-expected"></a>验证工作负荷是否按预期运行

一旦 TLS 1.0 和1.1 在你的环境中被禁用，请确保你的所有主工作负荷正常运行，例如 IM & 状态、P2P 呼叫、企业语音等。

**仅验证正在使用的 TLS 1。2**

让你的安全团队执行新的 Skype for business 通信审核，以确保不再使用 TLS 1.0 和1.1 的较旧协议。

或者，你可以使用 Internet Explorer 从 Skype for Business Server 2015 中的 Skype for Business Server 测试 TLS 连接，然后禁用 TLS 1.0 和 TLS 1.1。

1. 启动 Internet Explorer。
2. 选择**工具** > "**Internet 选项**"。
3. 选择 "**高级**" 选项卡。
4. 在 "**设置**" 下，滚动到底部。
5. 验证 TLS 1.0、TLS 1.1 和 TLS 1.2 是否已启用。
6. 浏览 SfB 2015 池的内部 Web 服务 URL （应成功连接）。
7. 返回到 Internet Explorer 并禁用仅**使用 TLS 1.2**的选项。
8. 再次浏览 SfB 2015 池的内部 Web 服务 URL （应该无法连接）。

![Internet 选项](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>高级部署方案

由于需要某些依赖项先决条件来支持 Skype for Business Ser 2015 中的 TLS 1.2，因此在禁用 TLS 1.0 和1.1 的任何系统上都将无法使用 RTM 介质进行安装。

**在你的环境中禁用了 TLS 1.0 和1.1 后部署新的标准版服务器或企业版池。**

**选项1：** 使用[SmartSetup](../../deploy/install/install-skype-for-business-server.md)。 请注意，我们正在更新 SmartSetup 以在将来的 CU 中容纳已更新的 SQL 二进制文件，并将在将来更新本文。

**选项2：** 预安装本地 SQL 实例（RTCLOCAL 和 LYNCLOCAL）

1. 下载 SQL Express 2014 SP2 （SQLEXPR_x64）并将其复制到 FE 上的本地文件夹。 假设 "文件夹路径" <SQL_FOLDER_PATH>。
2. 启动 PowerShell 或命令提示符并导航到 <SQL_FOLDER_PATH>。
3. 通过运行下面的命令创建 RTCLOCAL SQL 实例。 请等到 SQLEXPR_x64 完成，然后再继续操作：

    SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安装/FEATURES = SQLEngine，Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "/AGTSVCACCOUNT" NTAUTHORITY\NetworkService = "/SQLSVCSTARTUPTYPE" Automati =
1. 通过运行下面的命令创建 LYNCLOCAL SQL 实例。 等到 SQLEXPR_x64 完成后再继续下一步操作：

    SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安装/FEATURES = SQLEngine，Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE =" "=" "= 自动
1. 运行 Skype for Business Server 2015 RTM 设置。
2. 按照上面的 "先决条件" 部分中的其余步骤操作。

**选项3：** 您也可以手动替换本地安装媒体目录中的二进制文件，如下所示：

1. [安装 Skype for business 服务器的先决条件](../../deploy/install/install-prerequisites.md)  
2. 安装 .NET 4.7： 
      - **注意：** 我们首先在 Skype for business Server 2015 CU5 （6.0.9319.281）中引入了对 .NET 4.7 的支持。 因此，在后面的步骤中，我们将在主安装之前更新核心组件。
      - 下载： https://www.microsoft.com/download/details.aspx?id=55167。 
      - 参考：[应在 Skype For Business Server 2015 部署之前安装的软件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. 复制 ISO 文件/文件夹： 
    - 通过附加 Skype for Business Server 2015 ISO，打开它所附加的驱动器的根目录（例如：\)在文件资源管理器中）。
    - 将所有文件夹和文件复制到本地磁盘上的文件夹（例如： C:\SkypeForBusiness2015ISO）。
    - **注意：** 安装组件之前，需要更新某些文件，以支持 TLS 1.2。
4. 替换 MSI/EXE 程序包： 
    - 替换本地计算机上安装媒体的/Setup/amd64/文件夹中的现有 MSI 和 EXE 程序包。
    - SQL 2014 SP2 Express：https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - 在本地计算机上重命名为 SQLEXPR_x64，并替换安装媒体的 Setup/amd64/文件夹中的现有文件。
    - SQL Native 客户端：https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **注意：** 如有必要，请将其重命名为 sqlncli，然后替换安装媒体的 Setup/amd64/文件夹中存在的现有文件。
    - SQL 管理对象：https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **注意：** 功能包将有大量可供下载的项目。 选择仅下载 SharedManagementObjects。
        - **注意：** 替换安装媒体的 Setup/amd64/文件夹中存在的现有文件。
    - SQL CLR 类型：https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **注意：** 功能包将有大量可供下载的项目。 选择仅下载 CQLSysClrTypes
        - **注意**：替换安装媒体的 Setup/amd64/文件夹中存在的现有文件。
5. 安装核心组件： 
    - 从安装媒体的 Setup/amd64/文件夹运行 Setup.exe。 按照说明安装核心组件
    - 关闭核心组件。
6. 更新核心组件： 
    - 下载 Skype for Business 更新安装程序。
    - 运行安装程序以更新核心组件并安装性能计数器。
    - **注意：** 从 CU6HF2 发布开始，"自动更新" 功能目前仅安装最多 CU6。 因此，必须单独运行更新程序，以将核心组件更新到6.0.9319.516。
    - 参阅https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. 安装管理工具（可选）： 
    - 这将使用已更新的文件安装 Microsoft SQL Server 2012 本机客户端、SQL Server 2014 管理对象（x64）和 Microsoft System CLR 类型（x64）和 SQL Server 2014 （x64）。 此外，Skype for Business Server 2015 拓扑生成器和控制面板将在本地计算机上可用。
8. 安装本地配置存储（步骤1）： 
     - 打开部署向导，单击 "安装或更新 Skype for business 服务器系统"，然后单击步骤1中的 "**运行**"： "安装本地配置存储"。
     - 单击 "**安装本地配置存储**" 对话框中的 "**下一步**"。
     !["安装本地配置存储" 对话框](../../media/local-configuration-store.png)
     - 查看结果，确保任务状态为 "已完成"。 通过单击 "**查看日志**" 查看生成的日志文件。
     ![任务状态显示为已完成](../../media/local-configuration-task-completed.png)
     - 单击“**完成**”。
9. 设置或删除 Skype for business 服务器组件（步骤2）：
    - 打开部署向导，单击 "**安装或更新 skype for Business 服务器系统**"，然后单击步骤2中的 "**运行**"：设置或删除 Skype for business 服务器组件
    - 在 "设置 Skype for Business 服务器组件" 对话框中，单击 "**下一步**"。
    !["设置 Skype for Business 服务器组件" 窗口](../../media/set-up-skype-for-business-server-components-window.png)
    - 使用 "查看日志" 查看日志，并验证安装程序是否未出现问题。 
    - 单击“**完成**”。
10. 根据需要继续执行其他安装和配置（此时可以恢复正常的安装过程）。
