---
title: Lync Server 2013 发行说明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f98a19e81ebf52d97b4c6807dbb97dc8110b0f34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536559"
---
# <a name="release-notes-for-lync-server-2013"></a>Lync Server 2013 发行说明

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-12-08_

欢迎使用 Lync Server 2013 发行说明。 有关 Lync Server 2013 的已知问题的信息，请参阅此文件。

<div>

## <a name="about-this-document"></a>关于本文档

本文档包含在部署和使用 Lync Server 2013 之前应了解的重要信息。 有关 Lync Server 2013 的详细信息，请参阅 [Microsoft Lync server 2013](microsoft-lync-server-2013.md) 文档。

本文档包含以下各部分：

  - Lync 2013 客户端

  - Lync Server

  - 安装

  - 移动性

  - 会议

  - 企业语音

  - 状态

  - 响应组应用程序和呼叫寄存应用程序

  - Lync Server 控制面板、拓扑生成器和规划工具

  - 本地化

  - 版权

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Lync 2013 客户端

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>如果文件已在另一个应用程序中打开，则在即时消息中转移文件的操作将失败。

**问题**

如果尝试通过在即时消息中将文件添加到另一个 Lync 用户来传输文件（如 Word 文档），则传输将显示为 "成功"，但实际上可能无法传输该文件。 该文件类型的图标将显示在 Lync 客户端中，但预期的接收器无法打开该文件。 不会显示任何错误消息，通知您传输未成功。

**规避**

若要解决此问题，请先关闭打开的文件或已打开的应用程序，然后再尝试在即时消息中传输该文件。

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>如果 Lync Server 存储服务数据复制失败，管理员将需要检查陈旧存储服务队列项的性能计数器

**问题**

Lync Server Storage Service 使用 Windows Fabric 进行复制。 如果在主前端服务器上删除了数据，但在辅助前端服务器上的删除失败，例如，如果前端服务器上出现意外关闭或错误，则数据可以留下且 "孤立"。 孤立数据会导致性能降低并浪费驱动器空间。

**规避**

若要解决此问题，如果使用的事件 \_ LYSS \_ DB \_ 空间 \_ 错误 (id = 32058) 和 LYSS \_ DB \_ 空间 \_ 使用 \_ 关键 (id = 32059) 在事件日志中生成，管理员应检查前端服务器上前端服务器的性能计数器 **： LYSS-Storage Service API** ，其名称为 **LYSS-当前存储服务陈旧队列项目数**。 如果此性能计数器具有较高的值（例如，大于50000），则管理员应在 Lync Server 2013 资源工具包中运行 CleanuUpStorageServiceData.exe 工具，这将从池中删除所有孤立数据。 有关该工具的详细信息，请参阅 Lync Server 2013 资源工具包文档。

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>每当服务器或池的 IP 地址配置发生更改时，都需要重新启动 Lync Server 服务

**问题**

如果为 Lync Server 2013 部署更改了 IP 地址配置（例如，从 IPv4 更改为双栈或从双堆栈更改为 Ipv6），则并非所有服务器组件都会在重新启动服务之前选取配置更改。

**规避**

若要解决此问题，请在更改部署的 IP 地址配置后重新启动 Lync Server 服务。 若要执行此操作，请在 Lync Server 命令行管理程序中运行以下 cmdlet：

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>Lync Server 2013 管理包中不再提供电话拨入式会议综合事务 cmdlet

**问题**

Lync Server 2013 管理包中不再提供电话拨入式会议综合事务 cmdlet **test-csdialinconferencing** 。

**规避**

仅在企业内部支持使用电话拨入式会议综合事务 cmdlet **test-csdialinconferencing** 。

管理员可继续使用 Lync Server 命令行管理程序中的 cmdlet 进行故障排除。 如果需要，企业还可以开发专用管理包以在内部运行 cmdlet。

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>如果在将日志文件复制到网络共享时网络通信中断，集中日志记录服务将停止

**问题**

将集中日志记录服务配置为使用网络路径时 (**new-csclsconfiguration** Cmdlet 的 CacheFileNetworkFolder 参数的值是有效的 UNC 路径) ，缓存的日志文件将被复制到网络共享。 如果在复制文件时网络流量出现中断，则会发生异常，从而导致集中日志记录服务停止。

该服务配置为自动重新启动三次，因此该服务将从前三个例外中恢复。

**规避**

此问题尚无解决方法。 若要确定问题，请从日志中 "Lync Server 集中式日志记录服务代理" 服务意外终止时日志的 "服务控制管理器" 中监视事件 ID 7031 的事件日志。 如果发生此情况超过三次，请使用 **CsWindowService** cmdlet 手动重新启动该服务。

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>需要手动导入存储服务队列项

**问题**

Lync Server 2013 在每台前端服务器上的数据库上存储有关会议和即时消息的数据，例如存档的邮件和呼叫详细信息记录 (CDR) 。 数据在处理过程中存储在数据库中，然后将其传递到预期的目标。 为了提高性能，Lync Server 2013 定期从本地数据库中导出未在一段较长时间内处理的队列项，并将其保存在文件存储区中。 如果文件存储不可用，项目将存储在每台前端服务器上。 在池故障转移期间，发生相同的操作以防止数据丢失。

在导出操作过程中，Lync Server 存储服务会在事件日志中记录包含 32075 (完全刷新操作的事件日志中的每个阶段。) ，32076 (完全刷新已完成) ，32082 (维护级别刷新已完成) ，32083 (维护级别刷新已完成) ，由于填满数据库 (，32089) 刷新发生。 此数据不会自动导入回系统以进行处理并传递到其最终目标 (SQL Server 或 Exchange Server) 。

**规避**

若要将数据导入系统，管理员需要使用 Lync Server 资源工具包中的 ImportStorageServiceData 工具，该工具会将数据添加回要处理的系统并将其传递到最终目标。

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>如果 UseNormalizationRules 的默认值更改为 False，通讯簿 Web 查询搜索将失败

**问题**

如果 UseNormalizationRules 的默认值更改为 False，通讯簿 Web 查询搜索将失败。 默认值更改后，Lync 客户端用户将无法使用 Lync 通讯簿 web 查询搜索用户。

**规避**

如果 UseNormalizationRules 的默认值设置为 False，以便用户可以使用在没有 Lync Server 2013 的 Active Directory 域服务中定义的电话号码。应用规范化规则，请通过执行以下操作来解决此问题：

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  执行下列操作之一：
    
      - 如果您的部署仅包括 Lync Server 2013 服务器，请在全局级别运行以下 cmdlet，以将 UseNormalizationRules 和 IgnoreGenericRules 的值更改为 True：
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果您的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通信服务器 2007 R2 的组合，请运行以下 cmdlet，并将其分配给拓扑中的每个 Lync Server 2013 池：
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等待 CMS 复制在所有池上进行。

4.  修改适用于您的部署的电话规范化规则文件以清除内容。 文件位于每个 Lync Server 2013 池的文件共享中。 如果文件不存在，则创建一个名为 "公司 \_ 电话 \_ 号码 \_ 规范化Rules.txt" 的空文件 \_ 。

5.  等待几分钟，让所有前端池都能读取新文件。

6.  在部署中的每个 Lync Server 2013 池中运行以下 cmdlet。
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>每个 Lync 2013 池每天生成一次通讯簿服务器错误事件21054

**问题**

在每日执行日常维护时，Lync Server 2013 通讯簿服务器将在每天生成错误事件21054。 每当管理员运行 **csAddressBook** cmdlet 时，也会生成错误，即使更新成功也是如此。 但是，当更新成功时，可以安全地忽略此错误事件。

**规避**

遇到此错误事件时，请运行以下 cmdlet：

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

如果 cmdlet 报告没有未索引或被放弃的对象，则可以安全地忽略错误事件21054。

此外，应在 System Center Operations Manager 中禁用 KHI) "通讯簿用户已正确编制索引" (的关键运行状况指示器。

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>在边缘池上配置 IPv6 时，请求可能会失败

**问题**

在边缘池上配置 IPv6 时，对边缘池的一些请求可能会失败。

**规避**

若要解决此问题，请不要使用 IPv6 配置边缘池。

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>CsPoolFailback cmdlet 可能会在池故障回复期间失败

**问题**

尝试对池进行故障回复时， **csPoolFailback** cmdlet 可能会失败，并出现错误 "未能在重复尝试后完成水合进程"。

**规避**

若要解决此问题，请再次运行 cmdlet，并等待 cmdlet 成功。 请注意，故障回复过程可能需要几分钟才能完成。 对于包含20000用户的池，最长可能需要60分钟的时间。

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>在将前端服务器添加到已建立的池（混合部署、Skype for Business Online）时，可能会发生数据丢失

**问题**

在池具有多台前端服务器的环境中，您可能会遇到此问题，您可以重新启动其中一个前端服务器，也可以添加以前不属于池的新前端服务器。

在为池建立数据存档的稳定分布之前，要存档数据的用户可能会遇到数据丢失的情况。 这一期的潜在数据丢失限制为15分钟的人对人员对话和30分钟内的会议。

**规避**

执行维护时，应将池故障转移到另一个池，然后在服务器上执行维护任务，而不是在池中逐个启动前端服务器。 您还可以在执行维护任务之前使服务不可用，然后在维护完成后还原可用性。

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>管理员不能使用 Get-CsClientAccessLicense cmdlet 获取许可证持有人计数

**问题**

管理员无法使用 **CsClientAccessLicense** cmdlet 获取准确的客户端许可证使用情况。

**规避**

若要检查服务器许可证类型，可以运行 **get-csservice** cmdlet 来检索所有数据库的 FDQNs)  (的完全限定的域名。 如果前端服务器的 FQDN 与后端数据库的 FQDN 相同，则许可证是标准版许可证。 否则，许可证为 Enterprise edition 许可证。

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>客户端许可证持有人计数未准确报告

**问题**

在确定客户端许可证计数时，您可能会遇到以下情况：

1.  **移动用户的许可证计数不准确**
    
    许可证计数基于基于设备的用户的唯一 IP 地址数。 许可证计数将通过以下方式进行限制：
    
      - 如果用户的 IP 地址在 Lync 会话期间发生更改，则许可证将为 overcounted。 当用户从多个位置使用桌面客户端连接到 Lync Server 时，可能会发生这种情况。
    
      - 如果用户连接到移动客户端，则将 undercounted 许可证，因为无法确定设备的 IP 地址。

2.  **对 Lync 客户端的公共交换电话网络 (PSTN) 呼叫（lync 客户端呼叫到 PSTN 线路）计算两次许可证，并将 Lync 呼叫转发到 PSTN 线路**
    
    在以下方案中，将计算两个附加许可证，而不是一个许可证，因为电话号码和 Lync 用户都将进行计数以确定所使用的许可证数量。 若要获取准确的许可数据，请手动删除由电话号码生成的许可证。
    
      - 对 Lync 的 PSTN 电话呼叫
    
      - 对 PSTN 线路的 Lync 呼叫
    
      - 对 Lync 的 PSTN 呼叫，然后 Lync 会将呼叫转发到 PSTN 线路。 其中一个 PSTN 线路将计算在内。

3.  **将不会对登录的 Lync 手机计数许可证**
    
    当用户使用 Lync 认证的电话时，如果电话登录并保持连接（这将保留其登录状态），则不会将电话计为使用许可证（如果在电话登录后进行许可证查询）。

4.  **为 PSTN 电话加入会议而盘点的许可证**
    
    当用户加入带有 PSTN 手机的会议时，将会对加入会议的许可证进行不准确的计数。 但是，使用 PSTN 电话加入会议时无需许可证。

**规避**

1.  **移动用户的许可证计数不准确**
    
      - 您可以手动标识属于同一设备的 IP 地址，然后在许可证计数中删除其中一个。
    
      - 与 Lync 客户端连接的移动设备不存在有关此问题的解决方法。

2.  **对 Lync 客户端的 PSTN 呼叫进行两次许可证计数，Lync 客户端呼叫 PSTN 线路，并将 Lync 呼叫转发到 PSTN 线路**
    
    你将需要手动标识 PSTN 电话号码并删除为其生成的许可证计数。

3.  **许可证不会计数为已登录 Lync 电话**
    
    您可以将 Lync phone 配置为注销，然后在每三个月的定期时间间隔再次登录。

4.  **为 PSTN 电话加入会议而盘点的许可证**
    
    您可以手动标识用于加入会议的 PSTN 电话号码，并删除由电话号码生成的许可证。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>升级到 Silverlight 5 后，Lync Server 控制面板在 VMware 环境中停止工作

**问题**

如果在 VMware 环境中使用 Lync Server 控制面板，则在将 Microsoft Silverlight 升级到版本5后，Lync Server 控制面板可能会停止工作。

**规避**

若要解决此问题，请执行下列操作之一：

  - 卸载 Silverlight 5，并从安装 Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) 。

  - 从不是 VMware 虚拟计算机的计算机访问 Lync Server "控制面板"。
    
    为此，如果在计算机上安装了 Lync Server 管理工具，则可以从服务器上的 Windows " **开始** " 菜单启动 "Lync server 控制面板"。
    
    您还可以使用 web 浏览器访问 Lync Server 控制面板。 该 URL 将类似于 https:// \<frontend\_pool\_fqdn\> /cscp。

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>在 Active Directory 中修改用户的可分辨名称后，通讯簿服务中的用户信息未更新

**问题**

如果用户的可分辨名称 (也称为 DN) 在 Active Directory 域服务中进行了更改，则任何其他更改都不会在通讯簿服务 (ABS) 中进行更新。 这不会影响用户的登录或状态，但如果 SIP 地址也发生更改，则会阻止用户通信，因为搜索将返回过期的 SIP 地址。

**规避**

若要解决此问题，请不要更改用户的 DN。 如果将用户的 DN 还原为以前的值，更新将反映在通讯簿服务中。

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>安装

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>使用非 ASCII 字符可能会导致 Lync server 启动失败

**问题**

如果目标文件夹名称中包含非 ASCII 字符 (包括 UNICODE、双字节字符集 (DBCS) 、UTF-8 和 UTF-16) ，安装程序将失败。 此外，安装程序可能会成功，但如果以下任一情况中包含非 ASCII 字符，则服务器将不会启动：

  - 计算机名称

  - 域名

  - 用户名

  - 用户 SIP URI

  - 服务帐户名称

**规避**

仅在目标文件夹名称、计算机名称、域名、用户名、用户 SIP URI 和服务帐户名称中使用 ASCII 字符。

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>当模块在 IIS 7.5 中调用 InsertEntityBody 方法时，在安装 Lync Server 2013 之前必须安装 "堆损坏" 的修补程序。

**问题**

当模块在 IIS 7.5 " ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)) （Microsoft 知识库文章 264886 () 中所述）中的模块调用了" 堆损坏 "时，在 [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) 安装 Lync Server 2013 之前，必须先安装" 堆损坏 "的修补程序。

**规避**

从 Microsoft 下载中心下载并安装修补程序 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) 。

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 无法在 ITA Windows Server 2012 操作系统 RTM 版本上安装

**问题**

由于 Windows Fabric 安装失败，Lync Server 2013 安装将在 ITA Windows Server 2012 上失败。

由于使用 HH： MM： SS 的时间格式创建 Fabric 跟踪，因此 Windows Fabric 安装将失败。 但是，在 ITA Windows Server 中，时间格式为 HH。MM.SS。

**规避**

若要解决此问题，请在安装 Lync Server 2013 之前更新系统注册表。 需要更新的注册表项为： HKEY \_ 用户 \\ 。默认 \\ 控制面板 \\ 国际 \\ sTimeFormat。 使用 Windows PowerShell 命令行界面将 sTimeFormat 的值更改为 HH： mm： ss，如下所示：

1.  启动 Windows PowerShell 并运行以下 cmdlet：
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  若要查看当前值，请运行以下 cmdlet：
    
        Get-itemproperty $a -Name sTimeFormat
    
    记下 sTimeFormat 的当前值，以便在安装完成后可以对其进行还原。

3.  若要设置为新值，请运行以下 cmdlet：
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  成功安装 Lync Server 2013 后，通过运行以下 cmdlet 还原 sTimeFormat 的原始值：
    
        - Set-ItemProperty 在步骤3中指出的 $a 名称 sTimeFormat "<值。 以上> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>移动性

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>服务器故障转移过程中移动客户端的相关问题

**问题**

当 Lync Server 发生故障且故障转移过程开始时，以下问题可能会影响移动客户端用户：

  - 在故障转移开始后，不会有最长10分钟的传入 Lync 呼叫或信号。

  - 无法接受传入聊天请求

  - 如果出现故障的服务器是用户的主服务器，则无法加入会议

**规避**

此问题尚无解决方法。 故障转移过程完成后，将还原正常功能。

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>如果移动用户拒绝来自另一个 Lync 终结点的传入呼叫，则该呼叫将在 Lync 移动客户端上显示为缺少的转换

**问题**

如果移动用户拒绝传入呼叫，并且该呼叫来自另一个 Lync 终结点，则该呼叫将在 Lync 移动客户端中显示为错过的对话，而不是在设备呼叫列表中的呼叫中显示。

**规避**

此问题尚无解决方法。

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>移动客户端在搜索联系人时可能不显示联合联系人的显示名称

**问题**

联合联系人的显示名称可能不会显示在某些情况下，例如在联系人列表中搜索联合联系人时。 当 Lync 移动客户端没有联系人的活动状态订阅时，可能会发生这种情况。

**规避**

此问题尚无解决方法。

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>在移动客户端中，作为会议邀请的错过对话中缺少被邀请者和时间戳信息

**问题**

在移动客户端中，当错过的对话是会议邀请时，错过的对话邮件中缺少被邀请者和时间戳信息。

**规避**

此问题尚无解决方法。

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>使用 VoIP 进行呼叫的移动客户端用户无法为其语音邮件在 Exchange 2010 或更早版本中配置的用户留下语音邮件

**问题**

如果移动客户端用户使用 VoIP 发出呼叫，则用户将无法为配置为在 Microsoft Exchange Server 2007 或 Microsoft Exchange Server 2010 中使用语音邮件的用户留下语音邮件消息。

**规避**

若要解决此问题，请将 Exchange 2010 与 SP1 或更高版本的 Microsoft Exchange Server 结合使用。

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>对移动客户端上的客户端版本配置使用带 URL 的块时，可能会显示错误消息

**问题**

在移动客户端上为客户端版本配置使用 **带 URL 的块** 时，如果客户端版本不受支持，则可能会显示不正确的错误消息。

**规避**

若要解决此问题，请将客户端版本配置配置为使用 **block** 而不是 **block with URL**。

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>会议

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>在 Lync Server 2013 前端服务器上运行的防病毒软件可能会导致应用程序域回收，这将暂时中断 Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013 客户端的服务

**问题**

防病毒软件可以触发应用程序域重启，这会导致 Lync 移动服务2013和统一通信 (UC) Web API 客户端应用程序 (Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013) 将丢失其状态。

**规避**

若要解决此问题，请从防病毒扫描中排除包含 Web 组件和 .NET framework 的文件夹。 有关详细信息，请参阅 Microsoft 知识库文章 312592 "PRB：在 ASP.NET 中使用应用程序重新启动时的随机应用程序重新启动" 错误 "at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) 。

应排除以下文件夹：

  - % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 组件 \\ Mcx \\ Ext

  - % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 组件 \\ Mcx \\ Int

  - % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 组件 \\ Ucwa \\ Int

  - % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 组件 \\ Ucwa \\ Ext

  - % Windir% \\ Microsoft.NET \\ Framework64 \\ v 4.0.30319 \\ Config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>必须在 Windows Internet Explorer 中启用 ActiveX 控件或本机 XMLHTTP 支持才能成功加入会议

**问题**

如果用户在 Windows Internet Explorer Internet 浏览器设置中禁用了 ActiveX 控件和本机 XMLHTTP 支持，如果选择 Internet Explorer 作为默认浏览器，则该用户将无法加入会议。

**规避**

在 Internet Explorer 中启用 ActiveX 控件或 "本机 XMLHTTP 支持"。

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Lync Server Web 会议服务无法从关键模式恢复

**问题**

如果启用了关键模式进行存档，则在发生系统故障时，关键模式将启动，并且会议将不再适用于参与者。 管理员修复系统故障后 (例如解决数据库问题) ，数据会议服务不会自动恢复，管理员必须手动重新启动会议服务，会议才能继续。

**规避**

修复系统故障后，管理员需要手动重新启动会议服务。

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Web 会议服务忽略外部 Office Web App 服务器的 HTTP 代理

**问题**

如果已将 Office Web Apps Server 外部部署到 Web 会议服务 (也就是说，Internet、外围网络和 Web 会议服务中不包含内部公司网络中) 的服务器，则 Office Web Apps Server 发现将会发生故障。 Web 会议服务忽略 HTTP 代理设置，如在 Office Web Apps Server 安装程序的拓扑生成器中定义的那样。 因此，Lync 客户端将无法与会议中的其他参与者共享 Microsoft PowerPoint 2010。 如果要在内部部署 Lync Server 并在内部网络中配置 Office Web Apps Server 内部部署，则不需要代理配置。

**规避**

唯一的解决方法是不需要使用 HTTP 代理与外部 Office Web Apps Server 进行通信的部署配置。

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>不支持将视频添加到音频会议提供商会议

**问题**

如果用户加入音频会议提供商会议，则不支持添加视频。

**规避**

此问题尚无解决方法。

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>启用了 IPv6 的拓扑强制使用 Lync Web App Silverlight 插件进行自动更新，以确保屏幕共享功能可从 Lync Web App 工作

**问题**

将拓扑配置为启用 IPv6 时，如果已安装早期版本的屏幕共享插件，则用户无法从 Lync Web App 客户端共享其屏幕。

**规避**

若要在通过 Lync Web App 加入会议时强制更新屏幕共享插件的最新版本，请将 **MinSupportedBuildVersion** 的值从 "4.0.7457.0" 修改为以下两个文件中的 "4.0.7577.380"：

  - % ProgramFiles% \\ Microsoft Lync Server 15 \\ Web 组件 \\ 达到 \\ Int \\ 客户端 \\ 插件 \\ReachAppShPluginProperties.xml

  - % ProgramFiles% \\ Microsoft Lync Server 15 \\ Web 组件 \\ 访问 \\ 外部的 \\ 客户端 \\ 插件 \\ReachAppShPluginProperties.xml

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Enterprise Voice

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>在某些情况下，在配置为使用 IPv4 和 IPv6 双堆栈的计算机上运行的 Lync 客户端可能不支持依赖于计算机的 IP 子网的功能，如 E911、媒体旁路、呼叫允许控制和基于位置的路由

<div class="">


> [!NOTE]  
> 本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。



</div>

**问题**

当 Lync 客户端在启用了 IPv4 和 IPv6 双协议的计算机上运行，并且基于代理服务器的 DNS 解析时，客户端可以使用计算机的 IPv6 地址登录。 执行此操作后，Lync 客户端将仅支持 IPv6 支持的功能，这不会排除 E911、媒体旁路、呼叫允许控制和基于位置的路由。

**规避**

若要解决此问题，请在客户端计算机上禁用 IPv6 支持。

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>如果没有为用户配置企业语音，则用户将需要使用 E164 格式从会议拨出

**问题**

如果没有为用户配置企业语音，则该用户将需要使用 E164 格式以成功从会议拨出。 如果未使用 E164 格式，则用户将无法从会议拨出。

**规避**

若要解决此问题，未启用企业语音的用户应使用 E164 格式的号码从会议拨出。

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>状态

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>如果用户在为用户启用统一联系人存储时选择了 "阻止所有邀请和通信"，则状态在应为 "不" 时不会被拒绝

**问题**

如果用户在为用户启用统一联系人存储时选择了 "阻止所有邀请和通信"，则状态在应为时不会被拒绝。

**规避**

若要解决此问题，您可以为用户禁用统一联系人存储。 若要执行此操作，请运行以下 cmdlet：

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

例如：

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office 通信服务器 2007 R2 用户驻留在内部部署中无法查看混合部署中 Skype for Business Online 用户的状态-混合

**问题**

在使用 Lync Server 2013 控制器时，混合部署中可能会发生此问题。

驻留到 Skype for business Online 的用户的状态显示为本地用户的未知状态。 此外，托管到 Skype for Business Online 的用户无法查看 Office 通信服务器 R2 本地用户的状态。

**规避**

若要部分解决此问题，请将 "Home Server (msrtcsip-presencehomeserver) 的 Skype for Business Online 用户更改为指向 Lync Server 2013 本地池，而不是 Lync Server 2013 控制器。 您可以在本地前端服务器上修改此设置。

此替代方法将正确显示托管到 Office 通信服务器 2007 R2 的用户的状态到 Skype for business Online 用户状态。

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>响应组应用程序、呼叫寄存应用程序和组呼叫应答

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>在与检索方建立呼叫的过程中，呼叫者可能会听到一秒的音乐处于保留状态

<div class="">


> [!NOTE]  
> 本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。



</div>

**问题**

通过组呼叫应答检索呼叫时，呼叫者在与检索方之间建立呼叫的过程中，可能会听到一秒的音乐处于保留状态。

**规避**

此问题尚无解决方法。

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>响应组代理可以通过 Lync Server 2010 代理控制台登录并注销，仅适用于 Lync Server 2010 正式代理组

**问题**

Lync Server 2013 响应组代理可以在 Lync server 2010 代理控制台中登录并注销，2010以仅使用正式代理组。 在 Lync Server 2010 代理控制台中，用户只能看到他们所属的 Lync Server 2010 响应组。 他们无法看到它们所属的任何 Lync Server 2013 响应组。

**规避**

如果响应组代理是 Lync Server 2013 用户，并且是 Lync Server 2013 正式代理组的一部分，则用户必须通过浏览器中的 web 链接直接访问 Lync Server 2013 代理控制台，以登录到 Lync Server 2013 代理组并从中注销。

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Lync Server 2010 响应组代理无法代表 Lync Server 2013 响应组发出呼叫

**问题**

作为 Lync Server 2013 响应组代理的 Lync Server 2010 用户不能代表响应组发出呼叫。 Lync Server 2013 响应组将不会在 Lync 客户端中提供以发出呼叫。

**规避**

若要解决此问题，必须将 Lync Server 2010 用户移动到 Lync Server 2013。

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>在将响应组迁移到 Lync Server 2013 之后将其从 Lync 2010 Server 中删除会阻止响应组接受任何传入呼叫

**问题**

如果从 lync server 2010 迁移到 Lync Server 2013 的响应组已从 lync server 2010 通过 Lync Server 控制面板或 Lync Server 命令行管理程序删除，则 Lync Server 2013 中的响应组将停止接收任何传入呼叫。

**规避**

若要解决此问题，请不要从已从 Lync server 2010 迁移到 Lync Server 2013 的 Lync Server 2010 中删除任何响应组。

如果已删除响应组，则应在 Lync Server 2013 中重新部署它。

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>当新的托管工作流在创建时设置为非活动时，工作流的部署将失败

**问题**

当新的托管工作流在创建时设置为非活动时，工作流的部署将失败。 如果工作流在创建时设置为非活动状态，但不会影响在部署后将其设置为非活动状态的工作流，则会遇到此问题。

**规避**

创建和部署工作流时，将工作流设置为活动状态，然后部署它。 成功部署工作流后，可以对工作流进行编辑并将其设置为非活动状态。

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>如果响应组已导入到备份池中，则从所有者池删除响应组将阻止备份池的响应组接受在故障转移期间的任何传入呼叫。

**问题**

如果已将主池拥有的响应组导入到备份池中，而不覆盖所有者，并且从所有者池删除了响应组，则在故障转移过程中，备份池中的响应组将不接受任何传入呼叫。

**规避**

你将需要在主池中重新部署响应组。 然后，您需要从主池导出响应组配置，并再次将其导入备份池。

您还可以在备份池中重新创建响应组。 在这种情况下，备份池将成为响应组的所有者池。

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>如果代表响应组执行了检索请求，则无法从呼叫寄存应用程序检索寄存呼叫

**问题**

如果满足以下条件，则对寄存呼叫的检索请求将失败：

  - 代理是匿名响应组的一部分

  - 代理尝试通过匿名响应组从呼叫寄存应用程序检索寄存的呼叫

  - 代理尝试通过 "代表呼叫" 选项（或通过 Lync 助理客户端中的相同选项）拨打轨道编号来检索呼叫。

**规避**

此问题尚无解决方法。 应检索寄存的呼叫，而无需代表响应组执行此操作。

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Lync Server 控制面板、拓扑生成器和规划工具

<div>

## <a name="planning-tool-limitations"></a>规划工具限制

<div class="">


> [!NOTE]  
> 本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。



</div>

**问题**

规划部署时，规划工具具有以下限制：

  - 最多支持10个中央站点

  - 每个中央站点最多可以有14个分支站点

  - 每个中央站点最多可以有240000个用户

此外，在计算推荐的拓扑时，规划工具不包含以下值：

  - 联机驻留的用户数

  - 为 XMPP 联盟启用的用户所占的百分比

  - 使用 Lync Web App 的用户所占的百分比

**规避**

这些问题没有解决方法。 有关规划工具的详细信息，请参阅 [使用规划工具为 Lync Server 2013 设计拓扑](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)。

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>在更新选项时，规划工具可能不会为边缘网络使用以前定义的 IP 地址

**问题**

使用规划工具完成设计后，如果对边缘网络选项进行了更改，则可能会将其他 IP 地址添加到设计中，而不是更新现有的 IP 地址。 当您查看 Edge 网络图的详细信息时，可能会发生这种情况，请选择 " **单击此处以更新选项**"，然后在 "配置选项" 对话框中选择 "边缘网络 **"。我希望对我的边缘服务器上的边缘服务使用相同的 fqdn 和 IP 地址，而**不是不同的端口。 应用任何更改可能会导致新 IP 地址和边缘服务器添加到设计中。

**规避**

目前尚无解决此问题的方法。

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>在 Lync Server 控制面板中，"将所有用户移动到池" 可能无法按预期工作

**问题**

在使用 Lync Server 控制面板将所有用户从一个池移动到一个复杂的 Active Directory 环境中的另一个池（例如一个具有多个域控制器和父/子域的池）时，可能会返回错误消息 "指定的用户不是旧版用户，请改用 Move-CsUser cmdlet"。 这是在复杂的 Active Directory 环境中复制时间较长的结果。

**规避**

若要解决此问题，请执行下列操作之一：

  - 使用 Lync Server 控制面板中的筛选器搜索旧版用户，选择这些用户，然后使用 " **移动选定用户池" 命令** ，而不是 " **将所有用户移动到池**"。

  - 使用 Lync Server 命令行管理程序通过 Lync Server cmdlet 在批处理中移动旧版用户。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>在将 Microsoft Silverlight 浏览器插件更新到版本5后，Lync Server 控制面板在 VMware 环境中停止工作

**问题**

如果在 VMware 环境中使用 Lync Server 控制面板，则在将 Silverlight 升级到版本5后，Lync Server 控制面板可能会停止工作。

**规避**

若要解决此问题，请执行下列操作之一：

  - 卸载 Silverlight 5，然后从安装 Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) 。

  - 从不是 VMware 虚拟计算机的计算机打开 Lync Server "控制面板"。
    
    若要从远程计算机打开 Lync Server 控制面板，请在计算机上安装 Lync Server 管理工具，然后从 Windows " **开始** " 菜单启动 "Lync server 控制面板"。
    
    您还可以通过在 web 浏览器中输入 URL 来打开 Lync Server "控制面板"。 该 URL 将类似于 https:// \<frontend\_pool\_fqdn\> /cscp。

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>在拓扑生成器中删除镜像数据库后，管理员无法运行 csMirrorDB cmdlet。

**问题**

当管理员在拓扑生成器中禁用镜像数据库，然后在拓扑生成器中删除镜像数据库时，管理员可以在任务列表中显示一条消息，以运行 **csMirrorDatabase** cmdlet 以删除 SQL Server 中的镜像。 当管理员尝试运行 cmdlet 时，它会失败。

**规避**

若要在拓扑生成器中删除池的 SQL 镜像，必须首先使用 cmdlet 删除 SQL Server 中的镜像。 随后，您可使用拓扑生成器删除拓扑中的镜像。 若要删除 SQL Server 中的镜像，请使用以下 cmdlet：

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

例如，若要删除镜像并删除用户数据库的数据库，请键入以下内容：

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

*DropExistingDatabasesOnMirror*参数会导致从镜像中删除受影响的数据库。 然后，若要从拓扑中删除镜像，请执行以下操作：

1.  在拓扑生成器中，右键单击池并单击“编辑属性”****。

2.  清除 " **启用 SQL 存储镜像** "，然后单击 **"确定"**。

3.  发布拓扑。

<div class="">


> [!IMPORTANT]  
> 只要您对后端数据库镜像关系进行了更改，就必须重新启动池中的所有前端服务器。



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>当管理员尝试删除具有关联见证存储的前端池的部署时，会在拓扑生成器中返回验证错误。

**问题**

如果管理员尝试使用拓扑生成器中的 " **删除部署** " 命令来删除包含具有关联见证存储的前端池的部署，则在拓扑生成器中显示验证错误，并且该操作将不会继续。

**规避**

若要解决此问题，请执行下列操作之一：

  - 在尝试删除部署之前，请先删除见证存储。

  - 为前端池添加见证存储，然后将其删除。

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>规划工具和拓扑生成器之间的持久聊天服务器部署信息不一致

**问题**

当启用灾难恢复的情况下，在 Lync Server 2013 中，规划工具会输出持久聊天服务器部署的站点拓扑图，网站拓扑图包含多个 (物理) 站点，在每个站点上均匀分配了持久聊天服务器。 在拓扑生成器中，所有持久聊天服务器都表示为属于单个 (逻辑) 网站，并列在同一个持久聊天服务器池节点下。

**规避**

目前，我们没有解决此问题的方法。 用户应分析持久聊天服务器部署的规划工具的输出，并修改计划以满足其特定需求。

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>本地化

<div>

## <a name="monitoring"></a>监控

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>在某些情况下，在使用 Lync Server 的东亚版时，部署监控报告向导会显示错误的字符

**问题**

在使用东亚语言版本的 Lync Server 2013 时（例如，中文 (简化) 、中文 (传统) 、日语或朝鲜语）在 "系统区域设置" 未设置为东亚语言的操作系统中，"部署监控报告" 向导将显示问号或其他字符，而不是本地化的邮件。

**规避**

若要更正此问题，请将操作系统和 Lync Server 2013 的区域设置为相同的语言，这将正确显示所有邮件。

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync 服务器控制面板

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>在某些情况下，当单击顶部导航栏中的最后一个项目时，Lync Server 控制面板的页面上的第一个项目会消失。

**问题**

在以下三种情况下，在 Lync Server 控制面板的页面上单击顶部导航栏中的最后一项将导致顶部导航栏中的第一个项目消失：

  - 在法语版本中，在页面 "Féderation et accès externe" 中，当单击 "D'accès externe PARTENAIRES" 时，项目 "Stratégie fédérés XMPP" 将消失。

  - 在德语版本中，在 "客户端" 页上，单击 "Pushbenachrichtigungskonfiguration" 时，项目 "Clientversionskonfiguration" 将消失。

  - 在俄语版本中，在 "Конфигурациясети" 页上，单击 "Маршрутрегиона" 时，项目 "Глобально" 将消失。

**规避**

若要解决此问题，请在浏览器中刷新 Lync Server 控制面板的页面。 页面将在浏览器中加载，并显示顶部导航栏中的所有项目。

</div>

</div>

<div>

## <a name="address-book"></a>通讯簿

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>通讯簿中的索引在某些语言中无法按预期工作

<div class="">


> [!NOTE]  
> 本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。



</div>

如果用户的属性包含索引字段，并且该字段只包含无法编制索引的字符，则该用户将不会出现在通讯簿中执行的搜索中。

无法对以下字符和区域编制索引：

  - 大写的西里尔文、希腊语和亚美尼亚字符

  - 大写重音字符

  - 泰语

  - 老挝语

  - 缅甸

  - 梵文

  - 埃塞俄比亚语

  - 藏语

  - 孟加拉语

  - 古吉拉特语

  - 泰卢固语

  - 所有其他印度语脚本

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App、Web 计划程序和 Web 组件

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Lync Web 计划程序中某些语言的语言回退、拨入、加入启动器、持久聊天室管理和 OCTab 可能无法按预期工作

**问题**

在 web 浏览器中选择非特定区域设置时 (在 Internet Explorer 中例如，没有进一步规范的语言名称（如 "挪威 \[ no \] " ) ，而不是指定语言、脚本和区域设置的区域设置 (例如 "挪威语、博克马尔语 (挪威) \[ nb-no \] " ) 可能会在 Lync Web 计划程序、电话拨入、加入启动器、持久聊天室管理和 OCTab 中导致意外的显示行为。 例如，当选择以下任一种语言时，用户可能会看到英语页面：

  - 挪威语

  - 葡萄牙语

  - 塞尔维亚语

**规避**

如果要选择非特定区域设置的语言，请始终确保同时使用脚本和/或国家/地区代码在浏览器语言首选项列表中添加具有特定区域设置 (的语言，) 为其他语言。

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>在某些 Web 浏览器中使用 Lync Web 计划程序、电话拨入、加入启动器、持久聊天室管理和 OCTab 时，对阿泽里语和乌兹别克语区域设置的支持有限

<div class="">


> [!NOTE]  
> 本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。



</div>

**问题**

当您使用 Internet Explorer 8 或 Internet Explorer 9，并将浏览器语言设置为阿塞里语 (拉丁语) 或乌兹别克 (拉丁) 时，将以英语或在浏览器中设置的首选语言显示 "拨入" 和 "联接启动器" 页面。

当您使用 Firefox 或 Chrome 浏览器，并将浏览器语言设置为阿塞拜疆语 (拉丁语) 或乌兹别克 (拉丁) ，Lync Web App、Lync Web 计划程序和 RGS OCTab 将显示为英语或浏览器的首选语言集。

在 Safari 浏览器中不支持乌兹别克 (拉丁语) 区域设置。

**规避**

这些问题尚无解决方法。

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>在 Lync Web App 的罗马尼亚版本中，"加入会议来自" 列表缺少下拉箭头

**问题**

使用罗马尼亚语版本的 Lync Web App 的用户执行以下步骤时，将不会在下拉列表中显示 " **加入会议** " 下拉箭头：

1.  在 "**常规**" 选项卡上选择 "**在此计算机上保存我**"。

2.  选择 " **电话** " 选项卡。

3.  单击中的 " **加入会议**" 下拉列表。
    
    用户将看不到指示具有默认 **Lync Web 应用程序**的更多选项的箭头，其中包括：不在罗马尼亚语中 **加入音频** (，罗马尼亚，"Număr nou" ) 中的 ") 和 **新数字**" (。

**规避**

尽管不显示此下拉列表的箭头，但用户仍可以通过单击默认值来选择列表中的其他设置。

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>使用采用土耳其语版本的 Lync Web 计划程序时，在使用 "谁是演示者" 下使用 "我选择的人员" 选项时无法保存会议

**问题**

在土耳其语版本的 Lync Web 计划程序中创建或编辑会议时，不支持在 "谁是演示者" 下使用 "我选择的人员" 选项。 如果选择此选项，则无法保存会议。 而是显示一条错误消息，指示无法将一个或多个人员变为演示者。

**规避**

若要解决此问题，用户可以使用默认选项 "我的公司的人员" 或任何其他选择，如 "仅组织者" 或 "所有人（包含我的公司之外的人）"。 组织者在加入会议之后，可以降级或将用户提升为正确的角色。

或者，了解其他语言的用户可以将其浏览器中的语言选择更改为其他43支持的语言之一，并尝试使用 "用户选择" 选项。

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>版权

本文档支持软件产品的预发布版本，在最终商业版发布之前可能会有重大更改，并且是 Microsoft Corporation 的机密和专有信息。 本应依照收件人和 Microsoft 之间的保密协议泄露。 本文档仅用于提供信息，Microsoft 不会在本文档中作出任何明示或暗示的担保。 本文档中的信息（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知。 使用本文档的全部风险或结果由用户承担。 除非另有说明，否则此处示例中描述的公司、组织、产品、域名、电子邮件地址、徽标、人员、地点和事件均属虚构。 与任何真实公司、组织、产品、域名、电子邮件地址、徽标、人员、地点或事件无任何关联，也不应进行推断。 遵守所有适用的版权法是用户的责任。 在不限制版权许可的权利的情况下，如果没有得到 Microsoft 公司明确书面许可，本文档的任何部分不可被复制、存储或引进检索系统，或者以任何形式、任何方式（电子、机械、影印、录音或其他）或为任何目的进行传播。

Microsoft 可能对本文档中涉及的主题拥有专利、专利申请、商标、版权或其他知识产权。除非 Microsoft 的任何书面许可协议中明确表示，否则提供本文档并不表示授权您使用这些专利、商标、版权或其他知识产权。

© 2012 Microsoft Corporation。 保留所有权利。

Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook 和 SQL Server 是 Microsoft Corporation 在美国和/或其他国家/地区的注册商标或商标。

其他所有商标均为其各自所有者的财产。

</div>

</div>

<span> </span>

</div>

</div>

</div>

