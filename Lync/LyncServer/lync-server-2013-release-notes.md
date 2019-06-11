---
title: Lync Server 2013 发行说明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a93fabf10355dcc4ba7873921c0aaf35475927c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Lync Server 2013 发行说明

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2016-12-08_

欢迎使用 Lync Server 2013 发行说明。 有关 Lync Server 2013 的已知问题的信息, 请参阅此文件。

<div>

## <a name="about-this-document"></a>关于此文档

此文档包含在部署和使用 Lync Server 2013 之前应了解的重要信息。 有关 Lync Server 2013 的详细信息, 请参阅[Microsoft Lync server 2013](microsoft-lync-server-2013.md)文档。

本文档包含以下部分:

  - Lync 2013 客户端

  - Lync Server

  - 安装

  - 移动性

  - 网络会议

  - 企业语音

  - 状态

  - 响应组应用程序和呼叫寄存应用程序

  - Lync Server 控制面板、拓扑生成器和规划工具

  - 本地化

  - ©

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Lync 2013 客户端

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>如果文件已在其他应用程序中打开, 则在即时消息中传输文件将失败

**事项**

如果你尝试将文件 (如 Word 文档) 通过在即时消息中包含到另一个 Lync 用户, 则传输将显示为成功, 但实际上可能无法传输该文件。 将在 Lync 客户端中显示文件类型的图标, 但该文件不能由预期的接收方打开。 不会显示任何错误消息, 通知您传送未成功。

**规避**

若要解决此问题, 请先关闭打开的文件或已打开的应用程序, 然后再尝试在即时消息中传输文件。

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>如果 Lync Server 存储服务数据复制失败, 管理员将需要检查陈旧存储服务队列项的性能计数器

**事项**

Lync Server 存储服务使用 Windows Fabric 进行复制。 如果在主前端服务器上删除了数据, 但对辅助前端服务器的删除失败, 例如, 如果前端服务器上出现意外关机或错误, 则数据可以留下并 "孤立"。 孤立数据可能导致性能下降并浪费驱动器空间。

**规避**

若要解决此问题, 如果\_使用\_\_\_的事件 LYSS DB 空间错误 (id = 32058) 和在\_事件\_日志\_中\_生成了关键 (id = 32059) 的 LYSS db 空间, 管理员应检查前端服务器上的性能计数器在**LS: LYSS-** 具有 LYSS 名称的存储服务 API 上 **-当前存储服务陈旧队列项的数量**。 如果此性能计数器具有较高的值 (例如, 大于 50000), 管理员应在 Lync Server 2013 资源工具包中运行 CleanuUpStorageServiceData 工具, 该工具将删除池中的所有孤立数据。 有关该工具的详细信息, 请参阅 Lync Server 2013 资源工具包文档。

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>每当服务器或池中的 IP 地址配置发生更改时, 都需要重新启动 Lync Server 服务

**事项**

当为 Lync Server 2013 部署更改 IP 地址配置时 (例如从 IPv4 更改为双重堆栈或从双堆栈更改到 Ipv6) 时, 并非所有服务器组件都将获取配置更改, 直到重新启动服务。

**规避**

要解决此问题, 请在更改部署的 IP 地址配置后重新启动 Lync Server 服务。 若要执行此操作, 请在 Lync Server 命令行管理程序中运行以下 cmdlet:

   ```
    Stop-CsWindowsService -graceful
   ```

   ```
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>Lync Server 2013 管理包中不再提供电话拨入式会议合成事务 cmdlet

**事项**

Lync Server 2013 管理包中不再提供电话拨入式会议综合事务 cmdlet **CsDialInConferencing** 。

**规避**

仅在企业内部支持使用电话拨入式会议综合事务 cmdlet **Test CsDialInConferencing** 。

管理员可以继续使用 Lync Server Management Shell 中的 cmdlet 进行故障排除。 如果需要, 企业还可以开发专用管理包以在内部运行 cmdlet。

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>如果在将日志文件复制到网络共享时网络流量中断, 集中式日志记录服务将停止

**事项**

将集中式日志记录服务配置为使用网络路径 ( **CsClsConfiguration** Cmdlet 的 CacheFileNetworkFolder 参数的值是有效的 UNC 路径) 时, 缓存的日志文件将被复制到网络共享。 如果复制文件时网络流量中断, 则会发生异常, 导致集中式日志记录服务停止。

该服务配置为自动重启三次, 因此服务将从前三个例外中恢复。

**规避**

此问题没有解决方法。 若要确定此问题, 请从记录 "Lync Server 集中式日志记录服务代理" 服务意外终止的 "服务控制管理器" 监视事件 ID 7031 的事件日志。 如果发生此情况超过三次, 请使用**CsWindowService** cmdlet 手动重启该服务。

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>需要手动导入存储服务队列项

**事项**

Lync Server 2013 存储有关会议和即时消息的数据, 例如已存档的邮件和呼叫详细记录 (CDR), 位于每个前端服务器上的数据库中。 数据在被处理后将存储在数据库中, 然后再传递到预期的目标。 为了提高性能, Lync Server 2013 定期从本地数据库导出未在长时间处理的队列项, 并将其保存在文件存储中。 如果文件存储不可用, 项目将存储在每台前端服务器上。 发生同样的操作以防止池故障转移期间的数据丢失。

在导出操作过程中, Lync Server 存储服务将记录事件日志中的每个阶段, 事件 Id 为 32075 (完全刷新操作已启动)、32076 (完全刷新)、32082 (已启动维护级别刷新)、32083 (维护级别刷新)已完成), 32089 (由于填充数据库而发生刷新)。 此数据不会自动导入回系统以进行处理并传递到其最终目标 (SQL Server 或 Exchange Server)。

**规避**

要将数据导入到系统, 管理员需要使用 Lync Server 资源工具包中的 ImportStorageServiceData 工具, 该工具会将数据重新添加到系统中, 以便进行处理并传递到最终目标。

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>如果 UseNormalizationRules 的默认值更改为 False, 则通讯簿 Web 查询搜索将失败

**事项**

如果 UseNormalizationRules 的默认值更改为 "否", 通讯簿 Web 查询搜索将失败。 默认值更改后, Lync 客户端用户将无法使用 Lync 通讯簿 web 查询搜索用户。

**规避**

如果 UseNormalizationRules 的默认值设置为 False, 以便用户可以使用在没有 Lync Server 2013 的 Active Directory 域服务中定义的电话号码应用规范化规则, 请执行下列操作以解决此问题:

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  请执行下列操作之一：
    
      - 如果你的部署仅包括 Lync Server 2013 服务器, 请在全局级别上运行以下 cmdlet, 将 UseNormalizationRules 和 IgnoreGenericRules 的值更改为 True:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果你的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通信服务器 2007 R2 的组合, 请运行以下 cmdlet, 并将其分配给拓扑中的每个 Lync Server 2013 池:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等待 CMS 复制在所有池上进行。

4.  修改你的部署的电话规范化规则文件以清除内容。 该文件位于每个 Lync Server 2013 池的文件共享中。 如果文件不存在, 则创建一个名为 "\_公司电话\_号码\_规范化\_规则 .txt" 的空文件。

5.  请等待几分钟, 让所有前端池读取新文件。

6.  在部署中的每个 Lync Server 2013 池中运行以下 cmdlet。
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>每个 Lync 2013 池每天生成一个通讯簿服务器错误事件21054

**事项**

在执行日常维护时, Lync Server 2013 通讯簿服务器每天会生成错误事件21054一次。 此错误也会在每次管理员运行**csAddressBook** cmdlet 时生成, 即使更新成功也是如此。 但是, 更新成功后, 可以安全地忽略此错误事件。

**规避**

遇到此错误事件时, 请运行以下 cmdlet:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

如果 cmdlet 报告没有未索引或已放弃的对象, 则可以安全地忽略错误事件21054。

此外, "System Center Operations Manager" 中应关闭 "正确索引的通讯簿用户" 的关键运行状况指示器 (KHI) "。

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>在边缘池上配置 IPv6 时, 请求可能失败

**事项**

在 Edge 池上配置 IPv6 时, 对边缘池的某些请求可能会失败。

**规避**

要解决此问题, 请不要使用 IPv6 配置边缘池。

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>CsPoolFailback cmdlet 在池故障回复期间可能失败

**事项**

尝试故障恢复池时, **csPoolFailback** cmdlet 可能会失败, 出现错误 "无法在重复尝试后完成 hydration 进程"。

**规避**

若要解决此问题, 请再次运行 cmdlet, 然后等到 cmdlet 成功。 请注意, 故障回复过程可能需要几分钟才能完成。 对于包含20000用户的池, 最多可能需要60分钟。

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>将前端服务器添加到已建立的池-混合版、Skype for business Online 时可能会发生数据丢失问题

**事项**

在池具有多个前端服务器的环境中, 你可能会遇到此问题, 你可以重新启动其中一个前端服务器, 或者添加以前不属于该池的新前端服务器。

数据存档的用户可能会在为池建立稳定的数据存档之前遇到数据丢失。 此期的潜在数据丢失时间限制为15分钟, 供人员与人员对话, 而30分钟用于会议。

**规避**

执行维护时, 应将池故障转移到另一个池中, 然后在服务器上执行维护任务, 而不是在池中逐个启动前端服务器。 您也可以在执行维护任务之前使服务不可用, 然后在维护完成后恢复可用性。

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>管理员无法通过使用 CsClientAccessLicense cmdlet 获取许可证持有人的计数

**事项**

管理员无法使用**CsClientAccessLicense** cmdlet 获取准确的客户许可证使用情况。

**规避**

若要检查服务器许可证类型, 可以运行**CsService** cmdlet 以检索所有数据库的完全限定的域名 (FDQNs)。 如果前端服务器的 FQDN 与后端数据库的 FQDN 相同, 则许可证是标准版许可证。 否则, 许可证是企业版许可证。

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>客户许可证持有人计数未准确报告

**事项**

确定客户许可证计数时, 你可能会遇到以下情况:

1.  **移动用户的不准确许可证计数**
    
    许可证计数基于基于设备的用户的唯一 IP 地址的数量。 许可证计数将按以下方式受到限制:
    
      - 如果用户的 IP 地址在 Lync 会话期间发生更改, 将 overcounted 许可证。 当用户使用桌面客户端从多个位置连接到 Lync 服务器时, 可能会发生这种情况。
    
      - 如果用户使用移动客户端连接, 将 undercounted 许可证, 因为无法确定设备的 IP 地址。

2.  **对于 Lync 客户端、Lync 客户端调用 PSTN 线路以及将 Lync 呼叫转发到 PSTN 线路的公共交换电话网络 (PSTN) 呼叫, 许可证均计入两次。**
    
    在以下情况下, 将对两个附加许可证 (而不是一个许可证) 进行计数, 因为将对电话号码和 Lync 用户进行计数以确定所用的许可证数量。 若要获取准确的授权数据, 请手动删除由电话号码生成的许可证。
    
      - 对 Lync 的 PSTN 电话呼叫
    
      - 对 PSTN 线路的 Lync 呼叫
    
      - 对 Lync 的 PSTN 呼叫, 然后 Lync 将呼叫转发到 PSTN 线路。 将对其中一个 PSTN 线路进行计数。

3.  **将不会对已登录 Lync 手机的许可证进行计数**
    
    当用户使用 Lync 认证的电话时, 如果手机登录并保持连接 (这将保留其登录状态), 则不会将手机计为使用许可证 (如果在手机登录后出现许可证的查询)。

4.  **为 PSTN 手机加入会议而计数的许可证**
    
    当用户使用 PSTN 手机加入会议时, 许可证将不准确地计入加入会议的许可证。 但是, 使用 PSTN 手机加入会议时无需许可证。

**规避**

1.  **移动用户的不准确许可证计数**
    
      - 你可以手动标识属于同一设备的 IP 地址, 然后在许可证计数中删除其中一个。
    
      - 与 Lync 客户端连接的移动设备不存在此问题的解决方法。

2.  **对于 Lync 客户端、Lync 客户端调用 PSTN 线路以及将 Lync 呼叫转发到 PSTN 线路, 许可证将计入两次: PSTN 呼叫。**
    
    你将需要手动标识 PSTN 电话号码并删除为其生成的许可证计数。

3.  **不会对已登录 Lync 手机的许可证进行计数**
    
    您可以将 Lync phone 配置为注销, 然后再按常规间隔 (如每3个月) 登录。

4.  **为 PSTN 手机加入会议而计数的许可证**
    
    你可以手动标识用于加入会议的 PSTN 电话号码, 并删除由电话号码生成的许可证。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>升级到 Silverlight 5 后, Lync Server 控制面板在 VMware 环境中停止工作

**事项**

如果在 VMware 环境中使用 Lync Server 控制面板, 则在将 Microsoft Silverlight 升级到版本5后, Lync Server 控制面板可能会停止工作。

**规避**

若要解决此问题, 请执行下列操作之一:

  - 卸载 Silverlight 5, 然后从[https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)安装 silverlight 4。

  - 从不是 VMware 虚拟计算机的计算机访问 Lync Server 控制面板。
    
    为此, 如果在计算机上安装了 Lync Server 管理工具, 则可以从服务器上的 Windows "**开始**" 菜单启动 Lync server 控制面板。
    
    您也可以使用 web 浏览器访问 Lync Server "控制面板"。 该 URL 将类似于\<https://前端\_池\_fqdn/cscp.\>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>在 Active Directory 中修改了用户的识别名后, 通讯簿服务中的用户信息不会更新

**事项**

如果在 Active Directory 域服务中更改了用户的可分辨名称 (也称为 DN), 则不会在通讯簿服务 (ABS) 中更新任何其他更改。 这不会影响用户的登录或状态, 但如果 SIP 地址也发生更改, 它将阻止用户进行通信, 因为搜索将返回过期的 SIP 地址。

**规避**

若要解决此问题, 请不要更改用户的 DN。 如果将用户的 DN 还原为以前的值, 更新将反映在通讯簿服务中。

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>安装

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>使用非 ASCII 字符可能会导致 Lync 服务器启动失败

**事项**

如果目标文件夹名称包含非 ASCII 字符 (包括 UNICODE、双字节字符集 (DBCS)、UTF-8 和 UTF-16), 则安装将失败。 此外, 安装可能会成功, 但如果以下任何一项中包含非 ASCII 字符, 则服务器不会启动:

  - 计算机名

  - 域名

  - 用户名

  - 用户 SIP URI

  - 服务帐户名称

**规避**

仅在目标文件夹名称、计算机名称、域名、用户名、用户 SIP URI 和服务帐户名称中使用 ASCII 字符。

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>当模块调用 IIS 7.5 中的 InsertEntityBody 方法时, 出现堆损坏问题的修复程序必须在安装 Lync Server 2013 之前安装

**事项**

当模块调用 IIS 7.5[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)() 中所述的 InsertEntityBody 方法 (如 Microsoft 知识库文章 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)) 中所述), 在安装 Lync Server 2013 之前, 必须先安装 "堆损坏" 的修复程序。

**规避**

从 Microsoft 下载中心下载并安装修补程序[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)。

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 无法在 ITA Windows Server 2012 操作系统 RTM 版本上安装

**事项**

由于 Windows Fabric 安装失败, Lync Server 2013 安装在 ITA Windows Server 2012 上失败。

由于创建的结构跟踪的时间格式为 HH: MM: SS, 因此 Windows Fabric 安装失败。 但是, 在 ITA Windows Server 中, 时间格式为 HH。MM.SS。

**规避**

要解决此问题, 请在安装 Lync Server 2013 之前更新系统注册表。 需要更新的注册表项为: HKEY\_用户。\\默认\\控制面板\\国际\\sTimeFormat。 使用 Windows PowerShell 命令行界面将 sTimeFormat 的值更改为 HH: mm: ss, 如下所示:

1.  启动 Windows PowerShell 并运行以下 cmdlet:
    
       ```
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  若要查看当前值, 请运行以下 cmdlet:
    
        Get-itemproperty $a -Name sTimeFormat
    
    记下 sTimeFormat 的当前值, 以便在安装完成后可以恢复它。

3.  若要设置为新值, 请运行以下 cmdlet:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  成功安装 Lync Server 2013 后, 通过运行以下 cmdlet 还原 sTimeFormat 的原始值:
    
        - ItemProperty 在步骤3中记下的 "设置-$a 名称" <值。 上方> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>移动性

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>服务器故障转移过程中移动客户端的问题

**事项**

当 Lync 服务器失败并且故障转移过程开始时, 以下问题可能会影响移动客户端用户:

  - 在故障转移开始后, 没有传入 Lync 呼叫或最长10分钟的信号。

  - 无法接受传入的聊天请求

  - 如果故障服务器是用户的主服务器, 则无法加入会议

**规避**

此问题没有解决方法。 故障转移过程完成后, 将恢复正常功能。

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>如果移动用户拒绝来自另一个 Lync 终结点的传入呼叫, 则该呼叫将在 Lync 移动客户端上显示为错过的转换

**事项**

如果移动用户拒绝传入呼叫, 并且该呼叫来自另一个 Lync 终结点, 则该呼叫将在 Lync 移动客户端中显示为错过的对话, 而不是在设备呼叫列表中的呼叫中显示。

**规避**

此问题没有解决方法。

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>在搜索联系人时, 移动客户端可能不会显示联盟联系人的显示名称

**事项**

联盟联系人的显示名称可能不会在某些情况下显示, 例如当在联系人列表中搜索联盟联系人时。 当 Lync 移动客户端没有联系人的活动状态订阅时, 可能会发生这种情况。

**规避**

此问题没有解决方法。

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>在移动客户端中, 错过的对话 (即会议邀请) 缺少被邀请者和时间戳信息

**事项**

在移动客户端中, 当错过的对话是会议邀请时, 错过的对话消息中缺少被邀请者和时间戳信息。

**规避**

此问题没有解决方法。

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>使用 VoIP 进行呼叫的移动客户端用户无法为在 Exchange 2010 或更早版本中配置的用户留下语音邮件

**事项**

如果移动客户端用户使用 VoIP 进行呼叫, 用户将无法为配置为在 Microsoft Exchange Server 2007 或 Microsoft Exchange Server 2010 中使用语音邮件的用户留下语音邮件消息。

**规避**

若要解决此问题, 请将 Exchange 2010 与 SP1 或更高版本的 Microsoft Exchange Server 配合使用。

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>对移动客户端上的客户端版本配置使用带 URL 的块时, 可能会显示错误消息

**事项**

当对移动客户端上的客户端版本配置使用**带 URL 的块**时, 可能会在客户端版本不受支持时显示错误消息。

**规避**

要解决此问题, 请将客户端版本配置配置为使用 "**阻止**", 而不是 "使用**URL 阻止**"。

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>网络会议

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>在 Lync Server 2013 前端服务器上运行的防病毒软件可能会导致应用程序域循环, 这会暂时中断 Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013 客户端的服务

**事项**

防病毒软件可以触发应用程序域重启, 这可能会导致 Lync 移动服务2013和统一通信 (UC) Web API 客户端应用程序 (Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013) 丢失其状态。

**规避**

若要解决此问题, 请从防病毒扫描中排除包含 Web 组件和 .NET framework 的文件夹。 有关详细信息, 请参阅 Microsoft 知识库文章 312592: "PRB: 在 ASP.NET 中重新启动并重新启动应用程序时发生错误" 错误[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)。

应排除下列文件夹:

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web 组件\\Mcx\\Ext

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web 组件\\Mcx\\Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web 组件\\Ucwa\\Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web 组件\\Ucwa\\Ext

  - % Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\Config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>必须在 Windows Internet Explorer 中启用 ActiveX 控件或本机 XMLHTTP 支持才能成功加入会议

**事项**

如果用户在 Windows Internet Explorer Internet 浏览器设置中禁用了 ActiveX 控件和本机 XMLHTTP 支持, 则如果将 Internet Explorer 选作默认浏览器, 用户将无法加入会议。

**规避**

在 Internet Explorer 中启用 ActiveX 控件或 "本机 XMLHTTP 支持"。

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Lync Server Web 会议服务无法从关键模式恢复

**事项**

如果关键模式已启用存档, 则在系统发生故障时, 将启动关键模式, 并且会议将不再适用于参与者。 管理员修复了系统故障 (如修复数据库问题) 后, 数据会议服务不会自动恢复, 管理员必须手动重启会议服务才能继续会议。

**规避**

修复系统故障后, 管理员需要手动重启会议服务。

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>网络会议服务忽略外部 Office Web App 服务器的 HTTP 代理

**事项**

如果你已在 Internet、外围网络和 Web 会议服务中部署了 Web 会议服务外部的 Office Web Apps 服务器 (即不在内部公司网络中的服务器), 则需要 HTTP 代理来连接到该服务器,Office Web Apps 服务器发现将失败。 Web 会议服务忽略 HTTP 代理设置, 如 Office Web App Server 安装程序的拓扑生成器中所定义。 因此, Lync 客户端将无法与会议中的其他参与者共享 Microsoft PowerPoint 2010。 如果你在本地安装 Lync Server, 并且还在内部网络中配置 Office Web Apps 本地服务器, 则不需要代理配置。

**规避**

唯一的解决方法是不需要使用 HTTP 代理与外部 Office Web Apps 服务器通信的部署配置。

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>不支持向音频会议提供商会议添加视频

**事项**

如果用户已加入音频会议提供商会议, 则不支持添加视频。

**规避**

此问题没有解决方法。

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>启用了 IPv6 的拓扑强制使用 Lync Web App Silverlight 插件自动更新, 以确保可以从 Lync Web App 运行屏幕共享功能

**事项**

当拓扑配置为启用 IPv6 时, 如果已安装早期版本的屏幕共享插件, 则用户无法从 Lync Web App 客户端共享其屏幕。

**规避**

若要在通过 Lync Web App 加入会议时强制更新屏幕共享插件的最新版本, 请在以下两个文件中将**MinSupportedBuildVersion**的值从 "4.0.7457.0" 更改为 "4.0.7577.380":

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web 组件\\连接\\到\\Int\\客户\\端插件 ReachAppShPluginProperties

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web 组件\\访问\\外部\\的\\客户\\端插件 ReachAppShPluginProperties

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>企业语音

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>在某些情况下, 在配置为使用 IPv4 和 IPv6 双堆栈的计算机上运行的 Lync 客户端可能不支持依赖于计算机的 IP 子网的功能, 例如 E911、媒体绕过、呼叫许可控制和基于位置的路由

<div class="">


> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



</div>

**事项**

当 Lync 客户端运行在启用了 IPv4 和 IPv6 双堆栈且基于代理服务器的 DNS 解析的计算机上时, 客户端可以使用计算机的 IPv6 地址登录。 执行此操作后, Lync 客户端将仅支持 IPv6 支持的功能, 不包括 E911、媒体旁路、呼叫许可控制和基于位置的路由。

**规避**

若要解决此问题, 请在客户端计算机上禁用 IPv6 支持。

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>如果没有为用户配置企业语音, 用户将需要使用 E164 格式从会议拨出

**事项**

如果没有为用户配置企业语音, 则该用户需要使用 E164 格式成功从会议拨出。 如果未使用 E164 格式, 则用户无法从会议拨出。

**规避**

若要解决此问题, 未启用企业语音的用户应使用 E164 格式的数字拨出会议。

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>状态

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>如果用户已选择 "阻止所有邀请和通信", 而 "统一联系人存储" 为用户打开, 则状态不会被拒绝

**事项**

如果用户已选择 "阻止所有邀请和通信", 而统一联系人存储为用户打开, 则状态不会被拒绝。

**规避**

若要解决此问题, 您可以为用户关闭 "统一联系人存储"。 若要执行此操作, 请运行以下 cmdlet:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

例如：

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office 通信服务器 2007 R2 用户在混合部署中无法看到 Skype for business Online 用户的状态-混合

**事项**

使用 Lync Server 2013 控制器时, 混合部署中可能会出现此问题。

托管到 Skype for business Online 的用户的状态显示为本地用户的未知状态。 此外, 托管到 Skype for Business Online 的用户无法查看 Office 通讯服务器 R2 本地用户的状态。

**规避**

若要解决此问题, 请将 Skype for business Online 用户的主服务器 (msrtcsip-presencehomeserver) 更改为指向 Lync Server 2013 本地池, 而不是 Lync Server 2013 Director。 你可以在本地前端服务器上修改此设置。

此解决方法将正确显示托管到 Office 的 Office 通信服务器 2007 R2 到 Skype for business Online 用户的状态。

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>响应组应用程序、呼叫驻留应用程序和组呼叫装货

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>在与检索方进行通话期间, 呼叫者可能会听到一秒钟的音乐暂停

<div class="">


> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



</div>

**事项**

通过组呼叫拾取检索呼叫时, 呼叫者在与检索方进行通话的过程中, 可能会听到一秒钟的音乐暂停。

**规避**

此问题没有解决方法。

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>响应组代理只能通过 Lync Server 2010 代理2010控制台登录和注销, 仅限正式代理组

**事项**

Lync Server 2013 响应组代理可以通过 Lync Server 2010 代理2010控制台登录并注销, 仅限正式代理组。 在 Lync Server 2010 代理控制台中, 用户只能看到其所属的 Lync Server 2010 响应组。 他们无法看到它们所属的任何 Lync Server 2013 响应组。

**规避**

如果响应组代理是 Lync Server 2013 用户, 并且是 Lync Server 2013 正式代理组的一部分, 则用户必须直接通过浏览器中的 web 链接访问 Lync Server 2013 代理控制台, 以便从 Lync Server 2013 代理组登录和注销。

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Lync Server 2010 响应组代理无法代表 Lync Server 2013 响应组发出呼叫

**事项**

作为 Lync Server 2013 响应组代理的 Lync Server 2010 用户无法代表该响应组发出呼叫。 Lync Server 2013 响应组在 Lync 客户端中将不可用来发出呼叫。

**规避**

若要解决此问题, 必须将 Lync Server 2010 用户移动到 Lync Server 2013。

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>在迁移到 Lync Server 2013 之后从 Lync Server 2010 中删除响应组将会阻止该响应组接受任何传入呼叫

**事项**

如果从 lync server 2010 迁移到 Lync server 2013 的响应组已从 Lync server 2010 通过 Lync Server 控制面板或 Lync Server 管理外壳删除, 则 Lync Server 2013 中的 "响应" 组将停止接收任何传入呼叫。

**规避**

若要解决此问题, 请不要从 lync server 2010 中删除已从 Lync Server 2010 迁移到 Lync Server 2013 的任何响应组。

如果响应组已删除, 则应在 Lync Server 2013 中重新部署它。

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>当新的托管工作流在创建时设置为 "非活动" 时, 工作流的部署将失败

**事项**

当新的托管工作流在创建时设置为 "非活动" 时, 工作流的部署将失败。 当工作流在创建时设置为 "非活动" 时遇到此问题, 但不会影响已编辑的工作流, 以便在部署后将其设置为 "非活动"。

**规避**

创建和部署工作流时, 将工作流设置为 "活动", 然后部署它。 成功部署工作流后, 可以编辑工作流并将其设置为非活动状态。

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>如果响应组已导入到备份池中, 则从所有者池删除响应组将阻止备份池的响应组在故障转移期间接受任何传入调用

**事项**

如果已将主池拥有的响应组导入到备份池中, 而不覆盖所有者, 并且该响应组已从所有者池中删除, 则在故障转移过程中, 备份池中的响应组不会接受任何传入调用。

**规避**

你将需要在主池中重新部署响应组。 然后, 你将需要从主池中导出响应组配置, 并再次将其导入到备份池。

您也可以在备份池中重新创建响应组。 在这种情况下, 备份池将是响应组的所有者池。

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>如果检索请求是代表响应组执行的, 则无法从呼叫寄存应用程序检索寄存通话

**事项**

当满足以下条件时, 对寄存调用的检索请求将失败:

  - 代理是匿名响应组的一部分

  - 工程师尝试通过匿名响应组从呼叫寄存应用程序检索寄存的呼叫

  - 工程师通过在 "代表呼叫" 选项或通过 Lync 助理客户端中的相同选项拨打 "轨道" 编号, 尝试检索呼叫。

**规避**

此问题没有解决方法。 应检索停用呼叫, 而无需代表响应组执行此操作。

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Lync Server 控制面板、拓扑生成器和规划工具

<div>

## <a name="planning-tool-limitations"></a>规划工具限制

<div class="">


> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



</div>

**事项**

规划部署时, 规划工具具有下列限制:

  - 最多支持10个中央站点

  - 每个中心网站最多可以有14个分支网站

  - 每个中心网站最多可以有240000个用户

此外, 在计算推荐的拓扑时, 计划工具不包含以下值:

  - 联机的用户数

  - 为 XMPP 联盟启用的用户百分比

  - 使用 Lync Web App 的用户百分比

**规避**

这些问题没有解决方法。 有关规划工具的详细信息, 请参阅[使用规划工具设计 Lync Server 2013 的拓扑](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)。

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>在更新选项时, 计划工具可能不会使用以前为 Edge 网络定义的 IP 地址

**事项**

使用计划工具完成设计后, 如果对 Edge 网络选项进行了更改, 则可能会将其他 IP 地址添加到设计中, 而不是更新现有的 IP 地址。 如果你查看 Edge 网络图表的详细信息, 请选择 "**单击此处以更新你的选项**", 然后在 "配置选项" 对话框中选择 "边缘网络" 选择 **"我希望使用相同的 fqdn 和 IP 地址", 但边缘服务器上的边缘服务的不同端口**。 如果应用任何更改, 可能会导致新 IP 地址和边缘服务器添加到设计中。

**规避**

目前尚无解决此问题的方法。

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>在 Lync Server 控制面板中, "将所有用户移至池" 可能无法按预期工作

**事项**

使用 Lync Server 控制面板将所有用户从一个池移动到一个复杂的 Active Directory 环境中的另一个池 (如具有多个域控制器和父/子域的一个池) 时, 可能会返回错误消息, 指出 "指定的用户不是旧用户, 请改用 Move-csuser cmdlet。 " 这是在复杂的活动目录环境中复制时间较长的结果。

**规避**

若要解决此问题, 请执行下列操作之一:

  - 在 Lync Server 控制面板中使用筛选器搜索旧版用户, 选择这些用户, 然后使用 "**移动所选用户池" 命令**, 而不是**将所有用户移到 "池**"。

  - 使用 lync server Management Shell, 使用 Lync Server cmdlet 以批处理方式移动旧版用户。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Microsoft Silverlight 浏览器插件更新到版本5后, Lync Server 控制面板在 VMware 环境中停止工作

**事项**

如果您在 VMware 环境中使用 Lync Server 控制面板, 则在将 Silverlight 升级到版本5后, Lync Server 控制面板可能会停止工作。

**规避**

若要解决此问题, 请执行下列操作之一:

  - 卸载 Silverlight 5, 然后从[https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)安装 silverlight 4。

  - 从不是 VMware 虚拟计算机的计算机上打开 Lync Server "控制面板"。
    
    若要从远程计算机打开 Lync Server 控制面板, 请在计算机上安装 Lync Server 管理工具, 然后从 Windows "**开始**" 菜单启动 "lync server" 控制面板。
    
    您也可以通过在 web 浏览器中输入 URL 来打开 Lync Server "控制面板"。 该 URL 将类似于\<https://前端\_池\_fqdn/cscp.\>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>在拓扑生成器中删除镜像数据库后, 管理员无法运行 csMirrorDB cmdlet

**事项**

当管理员在拓扑生成器中禁用镜像数据库, 然后在拓扑生成器中删除镜像数据库时, 管理员的待办事项列表中将显示一条消息以运行**csMirrorDatabase** cmdlet 以删除从 SQL Server 进行镜像。 管理员尝试运行 cmdlet 时失败。

**规避**

若要删除拓扑生成器中的池的 SQL 镜像, 必须首先使用 cmdlet 在 SQL Server 中删除该镜像。 随后，你可以使用拓扑生成器删除拓扑中的镜像。 要删除 SQL Server 中的镜像，请使用以下 cmdlet：

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

例如, 若要删除镜像并除去用户数据库的数据库, 请键入以下内容:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

*DropExistingDatabasesOnMirror*参数会导致将受影响的数据库从镜像中删除。 然后，要从拓扑中删除镜像，请执行以下操作：

1.  在拓扑生成器中，右键单击该池并单击“**编辑属性**”。

2.  清除 "**启用 SQL 应用商店镜像**", 然后单击 **"确定"**。

3.  发布拓扑。

<div class="">


> [!IMPORTANT]  
> 当您对后端数据库镜像关系进行更改时, 您必须重新启动池中的所有前端服务器。



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>当管理员尝试删除具有关联见证存储的前端池的部署时, 将在拓扑生成器中返回验证错误

**事项**

如果管理员尝试使用拓扑生成器中的 "**删除部署**" 命令来删除包含具有关联见证存储的前端池的部署, 则拓扑生成器中将显示一个验证错误, 并且该操作不会继续.

**规避**

若要解决此问题, 请执行下列操作之一:

  - 请先删除见证应用商店, 然后再尝试删除该部署。

  - 为前端池添加见证存储, 然后将其删除。

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>计划工具和拓扑生成器之间的持久聊天服务器部署信息不一致

**事项**

当启用灾难恢复的情况下, 当 Lync Server 2013、计划工具为持久聊天服务器部署输出站点拓扑图时, 网站拓扑图包括多个 (物理) 站点, 每个站点都分配有均匀的持久聊天服务器现场. 在拓扑生成器中, 所有持久聊天服务器都表示为属于单个 (逻辑) 网站, 并在同一个永久聊天服务器池节点下列出。

**规避**

目前, 我们对此问题没有解决方法。 用户应分析持久聊天服务器部署的计划工具的输出, 并修改计划以满足其特定需求。

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>本地化

<div>

## <a name="monitoring"></a>监控

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>在某些情况下, "部署监视报表向导" 显示不正确的字符, 因为使用的是东亚版 Lync Server

**事项**

使用东亚版 Lync Server 2013 (例如, 简体中文)、中文 (繁体)、日语或朝鲜语-在系统区域设置为东亚语言的操作系统上, "部署监视报告" 向导将显示问号或其他字符而不是本地化消息。

**规避**

若要更正此问题, 请将操作系统和 Lync Server 2013 的区域设置设置为相同的语言, 这将正确显示所有消息。

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server 控制面板

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>在某些情况下, 当单击顶部导航栏中的最后一个项目时, "Lync Server 控制面板" 页面上顶部导航栏中的第一个项目将消失

**事项**

在以下三种已知情况下, 在 Lync Server 控制面板的页面上单击顶部导航栏中的最后一个项目将导致顶部导航栏中的第一个项目消失:

  - 在法语版本中, 在 "Féderation et accès externe" 页面上, 当单击 "D'accès externe PARTENAIRES" 时, 项目 "Stratégie fédérés XMPP" 将消失。

  - 在德语版本中的 "客户端" 页面上, 单击 "Pushbenachrichtigungskonfiguration" 时, 项目 "Clientversionskonfiguration" 消失。

  - 在俄语版本中的 "Конфигурациясети" 页面上, 单击 "Маршрутрегиона" 时, 项目 "Глобально" 消失。

**规避**

要解决此问题, 请在浏览器中刷新 Lync Server 控制面板的页面。 将在浏览器中加载页面, 并显示顶部导航栏中的所有项目。

</div>

</div>

<div>

## <a name="address-book"></a>通讯簿

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>在某些语言中, 通讯簿中的索引不会按预期工作

<div class="">


> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



</div>

如果用户的属性包含索引字段, 并且该字段仅包含无法索引的字符, 则该用户将不会出现在通讯簿中执行的搜索中。

以下字符和区域设置无法进行索引:

  - 小写字母、希腊语和亚美尼亚语字符

  - 大写字符

  - 泰语

  - 老挝

  - 缅甸

  - 梵文

  - 文

  - 藏文

  - 孟加拉语

  - 古吉拉特语

  - 泰卢固语

  - 所有其他印度语脚本

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App、Web 计划程序和 Web 组件

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Lync Web 计划程序中某些语言的语言回退、拨入、加入启动器、持久聊天室管理和 OCTab 可能不会按预期工作

**事项**

在 web 浏览器中选择非特定区域设置 (例如, 在 Internet Explorer 中, 在不进一步规范的情况下使用语言\[名称\], 例如 "挪威语 no"), 而不是指定语言、脚本和区域设置的区域设置 (如 "挪威语、博克马尔语 (挪威) \[NB-NO\]") 可能会导致在 Lync Web 计划程序、拨入、加入启动器、持续聊天室管理和 OCTab 中出现意外的显示行为。 例如, 当选择以下语言之一时, 用户可能会看到英语页面:

  - 挪威语

  - 葡萄牙语

  - 塞尔维亚语

**规避**

如果要选择具有非特定区域设置的语言, 请始终确保你还可以在浏览器语言首选项列表中添加具有特定区域设置的语言 (使用脚本和/或国家/地区代码) 作为另一种语言。

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>在某些 Web 浏览器中使用 Lync Web 计划程序、拨入、加入启动器、持续聊天室管理和 OCTab 时, 对阿塞拜疆语和乌兹别克语区域的支持有限。

<div class="">


> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



</div>

**事项**

使用 Internet Explorer 8 或 Internet Explorer 9 并将浏览器语言设置为阿塞拜疆语 (拉丁语) 或乌兹别克语 (拉丁文) 时, 将以英语或在浏览器中设置的首选语言显示 "拨入" 和 "加入" 启动器页面。

使用 Firefox 或 Chrome 浏览器时, 如果将浏览器语言设置为 "阿塞拜疆语 (拉丁语)" 或 "乌兹别克语 (拉丁文)", 则 Lync Web App、Lync Web 计划程序和 RGS OCTab 将显示为英语或浏览器的首选语言集。

在 Safari 浏览器中不支持 "乌兹别克语 (拉丁语)" 区域设置。

**规避**

这些问题没有解决方法。

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>Lync Web App 的罗马尼亚语版本中的 "加入会议来自" 列表缺少下拉箭头

**事项**

当使用罗马尼亚语版本的 Lync Web App 的用户执行以下步骤时, 下拉列表中不显示 "**加入会议**" 下拉箭头:

1.  在 "**常规**" 选项卡上选择 "**在此计算机上保存我**"。

2.  选择 "**电话**" 选项卡。

3.  单击 "**加入会议**" 下拉列表。
    
    用户将看不到指示有比默认**Lync Web 应用**更多的选项, 其中包括:**不加入音频**(在罗马尼亚语、"Nu se asociaža la componenta 音频") 和**新号码**"(在罗马尼亚语中," Număr nou ")。

**规避**

即使不显示此下拉列表的箭头, 用户仍然可以通过单击默认值来选择列表中的其他设置。

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>使用使用土耳其版本的 Lync Web 计划程序时, 当使用 "谁是演示者" 下的 "用户选择" 选项时, 无法保存会议

**事项**

在土耳其语版本的 Lync Web 计划程序中创建或编辑会议时, 不支持 "谁是演示者" 下的选项 "我选择的人员"。 选中此选项时, 无法保存会议。 而是显示一条错误消息, 指示无法将一个或多个人员变为演示者。

**规避**

若要解决此问题, 用户可以使用默认选项 "来自我的公司的人员" 或任何其他选择, 如 "仅组织者" 或 "每个人 (包括我的公司外的人)"。 稍后, 组织者可以在加入会议后降级或将其提升到其正确的角色。

或者, 了解其他语言的用户可以将其浏览器中的语言选择更改为其他43支持的语言之一, 并尝试使用 "我选择的人员" 选项。

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>©

本文档支持软件产品的预发布版本, 该版本可能会在最终商业版发布之前显著更改, 并且是 Microsoft Corporation 的机密和专有信息。 本协议依照收件人和 Microsoft 之间的保密协议披露。 本文档仅供提供信息之用, Microsoft 对本文档不作任何明示或暗示的担保。 本文档中的信息 (包括 URL 和其他互联网网站参考) 如有更改, 恕不另行通知。 使用本文档的全部风险或结果由用户承担。 除非另有说明, 否则此处的示例中所描述的公司、组织、产品、域名、电子邮件地址、徽标、人员、地点和事件均属虚构。 无意与任何真实公司、组织、产品、域名、电子邮件地址、徽标、人员、地点或事件相关联, 也不应进行推断。 遵守所有适用的著作权法是用户的责任。 在不限制版权所辖权利的情况下, 本文档的任何部分均不得被复制、存储或引入检索系统, 或者以任何形式或通过任何形式 (电子、机械、影印、录音或其他方式) 进行传输, 或者出于任何目的而进行传播。没有 Microsoft Corporation 的明确书面许可。

Microsoft 可能拥有本文档中所涉及主题的专利、专利应用程序、商标、版权或其他知识产权权利。 除非 Microsoft 的任何书面许可协议中明确提供, 否则提供本文档不会向您提供这些专利、商标、版权或其他知识产权的任何许可证。

© 2012 Microsoft Corporation。 保留所有权利。

Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook 和 SQL Server 是 Microsoft Corporation 在美国和/或其他国家/地区的注册商标或商标。

所有其他商标均为其各自所有者的财产。

</div>

</div>

<span> </span>

</div>

</div>

</div>

