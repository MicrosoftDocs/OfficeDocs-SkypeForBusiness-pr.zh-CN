---
title: Lync Server 2013 发行说明
TOCTitle: 发行说明
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205120(v=OCS.15)
ms:contentKeyID: 49313765
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 发行说明

 

_**上一次修改主题：** 2016-12-08_

欢迎使用 Lync Server 2013 发行说明。请参阅本文档以了解有关 Lync Server 2013 的已知问题的信息。

## 关于本文档

本文档包含在部署和使用 Lync Server 2013 之前所应了解的重要信息。有关 Lync Server 2013 的详细信息，请参阅 [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 文档。

本文档包含以下各节：

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

  - 版权信息

## Lync 2013 客户端

## 如果文件中另一个应用程序中打开，则通过即时消息传输文件会失败 (1920369)

**问题：**

如果您尝试通过在发送给另一个 Lync 用户的即时消息中包括文件（如 Word 文档）来传输文件，则传输表面上成功，但是可能实际上无法传输文件。文件类型的图标将显示在 Lync 客户端中，但是预期收件人无法打开文件。不会显示错误消息来通知您传输不成功。

**解决方法：**

要解决此问题，请在尝试通过即时消息传输文件之前关闭打开的文件或打开文件的应用程序。

## Lync Server

## 如果 Lync Server 存储服务数据复制失败，管理员将需要在性能计数器中查看过时的存储服务队列项 (3225121)

**问题：**

Lync Server 存储服务使用 Windows Fabric 进行复制。如果在主前端服务器上删除了数据，但在辅助前端服务器上的删除失败 - 例如，如果前端服务器意外关闭或出错 - 数据可以保留并保持“孤立”。孤立的数据可能会导致性能降低和驱动器空间浪费。

**解决方法：**

若要解决此问题，如果事件日志中生成了事件 LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) 和 LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059)，管理员应在前端服务器上查看“LS:LYSS - 存储服务 API”下方的名为“LYSS - 当前存储服务过时队列项数”的性能计数器。如果此性能计数器具有一个较大的值 - 例如，50,000 以上的值 - 则管理员应运行 Lync Server 2013 资源工具包中的 CleanuUpStorageServiceData.exe 工具，这将删除池中所有孤立的数据。有关该工具的详细信息，请参阅 Lync Server 2013 资源工具包文档。

## 只要为服务器或池更改 IP 地址配置，就需要重新启动 Lync Server 服务 (3212447)

**问题：**

如果为 Lync Server 2013 部署更改 IP 地址配置（如从 IPv4 更改为双协议栈或从双协议栈更改为 Ipv6），则在重新启动这些服务之前，并非所有服务器组件都会采用该配置更改。

**解决方法：**

若要解决此问题，请在为部署更改 IP 地址配置后重新启动 Lync Server 服务。为此，请在 Lync Server 命令行管理程序中运行以下 cmdlet：

  ```
  Stop-CsWindowsService -graceful
  ```
  ```
  Start-CsWindowsService
  ```

## Lync Server 2013 管理包中不再提供电话拨入式会议综合事务 cmdlet (3212342)

**问题：**

Lync Server 2013 管理包中不再提供电话拨入式会议综合事务 cmdlet **Test-CsDialInConferencing**。

**解决方法：**

仅支持在企业内部使用电话拨入式会议综合事务 cmdlet **Test-CsDialInConferencing**。

管理员可继续在 Lync Server 命令行管理程序中使用 cmdlet 以进行故障排除。如果需要，企业还可以开发专用管理包以便内部运行 cmdlet。

## 如果网络流量在将日志文件复制到网络共享时中断，则集中式日志记录服务将停止 (3212464)

**问题：**

在将集中式日志记录服务配置为使用网络路径（ **Get-CsClsConfiguration** cmdlet 的 CacheFileNetworkFolder 参数的值是有效的 UNC 路径）时，缓存的日志文件将复制到网络共享中。如果在复制文件时发生网络流量中断，则将引发一个异常，从而导致集中式日志记录服务停止。

该服务将配置为最多自动重新启动三次，因此该服务将从前三次异常中恢复。

**解决方法：**

没有解决此问题的方法。若要标识此问题，请从“服务控制管理器”监视事件 ID 为 7031 的事件日志，该日志记录了“Lync Server 集中式日志记录服务代理”服务意外终止的时间。如果此情况出现了 3 次以上，请使用 **Start-CsWindowService** cmdlet 手动重新启动该服务。

## 需要手动导入存储服务队列项 (3211368)

**问题：**

Lync Server 2013 在每个前端服务器上的数据库中存储有关会议和即时消息的数据，如存档的消息和呼叫详细记录 (CDR)。此数据存储在数据库中，会先对其进行处理，然后再将其交付给指定目标。为了改进性能，Lync Server 2013 会定期从本地数据库中导出较长时间内未处理的队列项，并将这些项保存到文件存储中。如果文件存储不可用，则这些项将存储到每个前端服务器上。在池故障转移期间，将执行相同的操作来防止数据丢失。

在导出操作期间，Lync Server 存储服务在事件日志中记录每个阶段，这些阶段的事件 ID 分别为 32075（完全刷新操作已开始）、32076（完全刷新已完成）、32082（维护级别刷新已开始）、32083（维护级别刷新已完成）、32089（因数据库已填满执行刷新）。此数据不会自动导入回系统以供处理且不会交付给其最终目标（SQL Server 或 Exchange Server）。

**解决方法：**

若要将数据导入系统，管理员需要使用 Lync Server 资源工具包中的 ImportStorageServiceData 工具，这会将该数据添加回系统以进行处理，然后交付给其最终目标。

## 如果 UseNormalizationRules 的默认值更改为 False，则通讯簿 Web 查询搜索将失败 (3175514)

**问题：**

如果 UseNormalizationRules 的默认值更改为 False，则通讯簿 Web 查询搜索将失败。在更改默认值之后，Lync 客户端用户将无法使用 Lync 通讯簿 Web 查询搜索用户。

**解决方法：**

如果将 UseNormalizationRules 的默认值设置为 False，以便用户能够使用 Active Directory 域服务 中定义的电话号码而无需 Lync Server 2013 应用规范化规则，则可通过执行以下操作来解决此问题：

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  执行下列操作之一：
    
      - 如果您的部署仅包括 Lync Server 2013 服务器，则在全局级别运行以下 cmdlet 以将 UseNormalizationRules 和 IgnoreGenericRules 的值更改为 True：
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果您的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office Communications Server 2007 R2 的组合，则运行以下 cmdlet 并将其分配给拓扑中的每个 Lync Server 2013 池：
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等待在所有池上执行 CMS 复制。

4.  修改部署的电话规范化规则文件以清除内容。该文件位于每个 Lync Server 2013 池的文件共享中。如果该文件未提供，则创建一个名为“Company\_Phone\_Number\_Normalization\_Rules.txt”的空文件。

5.  等待几分钟，以便所有前端池读取新文件。

6.  在部署中的每个 Lync Server 2013 池上运行以下 cmdlet。
    
        Update-csAddressBook

## 每天为每个 Lync 2013 池生成一次通讯簿服务器错误事件 21054 (3195918)

**问题：**

Lync Server 2013 通讯簿服务器每天在执行日常维护时都会生成一次错误事件 21054。该错误还将在管理员每次运行 **Update-csAddressBook** cmdlet 时生成，即使已成功更新也是如此。但在更新成功时可安全忽略此错误事件。

**解决方法：**

在遇到此错误时，请运行以下 cmdlet：

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

如果 cmdlet 报告没有未编制索引的对象或已放弃的对象，则可安全忽略错误事件 21054。

此外，应在 System Center Operations Manager 中关闭关键运行状况指示器 (KHI)“已为通讯簿用户正确编制索引”。

## 在边缘池上配置 IPv6 时，请求可能失败 (3205810)

**问题：**

在边缘池上配置 IPv6 时，对边缘池的一些请求可能会失败。

**解决方法：**

若要解决此问题，请不要使用 IPv6 配置边缘池。

## 在池故障转移期间，invoke-csPoolFailback cmdlet 可能会失败 (3206153)

**问题：**

在尝试对池进行故障转移时，**invoke-csPoolFailback** cmdlet 可能失败，并出现错误“多次尝试后仍无法完成水化过程”。

**解决方法：**

若要解决此问题，请再次运行 cmdlet，并等待直到 cmdlet 成功。请注意，故障转移过程可能要花几分钟时间才能完成。对于具有 20,000 个用户的池，此过程可能要花费最多 60 分钟时间才能完成。

## 在向已建立的池添加前端服务器时，可能出现数据丢失 (3015990) – 混合，Skype for Business Online

**问题：**

您可能会在以下环节中遇到此问题：包含一个具有多个 前端服务器的池，并且您重新启动这些 前端服务器之一或添加之前未作为池的一部分的新 前端服务器。

在为池建立稳定的数据存档分发之前，其数据已存档的用户可能遇到数据丢失。对于面对面会话，此可能数据丢失时段最长为 15 分钟，而对于会议为 30 分钟。

**解决方法：**

在执行维护时，您应从一个池故障转移到另一个池，然后在服务器上执行维护任务，而不是在池中逐个启动 前端服务器。您还可以在执行维护任务之前禁用该服务，然后在维护完成后还原其可用性。

## 管理员无法使用 Get-CsClientAccessLicense cmdlet 获取许可接受方计数 (3012255)

**问题：**

管理员无法使用 **Get-CsClientAccessLicense** cmdlet 获取准确的客户端许可证使用情况。

**解决方法：**

若要检查服务器许可证类型，您可以运行 **Get-CsService** cmdlet 来检索所有数据库的完全限定域名 (FDQN)。如果 前端服务器的 FQDN 与后端数据库的 FQDN 相同，则该许可证为标准版许可证。否则，该许可证为企业版许可证。

## 未准确报告客户端许可证接受方计数 (3010175)

**问题：**

在确定客户端许可证计数时，您可能遇到以下情况：

1.  **移动用户的许可证计数不正确**
    
    许可证计数将基于基于设备的用户的唯一 IP 地址数。将通过以下方式限制许可证计数：
    
      - 如果用户的 IP 地址在 Lync 会话期间发生更改，则对许可证的计数将过量。当用户从具有桌面客户端的多个位置连接到 Lync Server 时会出现此情况。
    
      - 如果用户使用移动客户端进行连接，则对许可证的计数将不足，因为无法确定设备的 IP 地址。

2.  **对用于针对 Lync 客户端的公用电话交换网 (PSTN) 呼叫、针对 PSTN 线路的 Lync 客户端呼叫和转接到 PSTN 线路的 Lync 呼叫的许可证计数两次**
    
    在以下方案中，将对两个而不是一个额外的许可证计数，因为将对电话号码和 Lync 用户计数以确定使用的许可证数。若要获得准确的许可数据，请手动删除通过电话号码生成的许可证。
    
      - 针对 Lync 的 PSTN 电话呼叫
    
      - 针对 PSTN 线路的 Lync 呼叫
    
      - 针对 Lync 的 PSTN 呼叫，然后 Lync 将该呼叫转接到 PSTN 线路。其中一个 PSTN 线路将被计数。

3.  **不对已登录的 Lync 电话的许可证计数**
    
    在用户使用经 Lync 认证的电话时，如果该电话登录并保持连接（这将使其保持登录状态），则在电话登录后查询许可证的情况下，不会将电话视为使用了许可证。

4.  **对加入会议的 PSTN 电话的许可证计数**
    
    在用户通过 PSTN 电话加入会议时，无法对加入会议所需的许可证准确计数。但是，通过 PSTN 电话加入会议无需许可证。

**解决方法：**

1.  **移动用户的许可证计数不正确**
    
      - 您可以手动标识属于同一设备的 IP 地址，然后在许可证计数中删除其中一个 IP 地址。
    
      - 对于与连接到 Lync 客户端的移动设备相关的此问题，没有解决方法。

2.  **对用于针对 Lync 客户端的 PSTN 呼叫、针对 PSTN 线路的 Lync 客户端呼叫和转接到 PSTN 线路的 Lync 呼叫的许可证计数两次**
    
    您将需要手动标识确定 PSTN 电话号码并删除为其生成的许可证计数。

3.  **不对已登录的 Lync 电话的许可证计数**
    
    您可以将 Lync 电话配置为定期（如每 3 个月）注销，然后重新登录。

4.  **对加入会议的 PSTN 电话的许可证计数**
    
    您可以手动标识用于加入会议的 PSTN 电话号码并删除通过该电话号码生成的许可证。

## 在升级到 Silverlight 5 后， Lync Server 控制面板在 VMware 环境中停止工作 (3010077)

**问题：**

如果您在 VMware 环境中使用 Lync Server 控制面板，则 Lync Server 控制面板在您将 Microsoft Silverlight 升级到版本 5 后可能会停止工作。

**解决方法：**

要解决该问题，请执行下列操作之一：

  - 卸载 Silverlight 5 并从 [http://go.microsoft.com/fwlink/p/?LinkID=149156](http://go.microsoft.com/fwlink/p/?linkid=149156) 安装 Silverlight 4。

  - 从不是 VMware 虚拟机的计算机访问 Lync Server 控制面板。
    
    为此，如果计算机上安装了 Lync Server 管理工具，则可从服务器上的 Windows“开始”菜单启动 Lync Server 控制面板。
    
    还可以使用 Web 浏览器访问 Lync Server 控制面板。URL 将类似于 https://\<frontend\_pool\_fqdn\>/cscp。

## 在 Active Directory 中修改用户的可分辨名称后不更新通讯簿服务中的用户信息 (3211549)

**问题：**

如果在 Active Directory 域服务 中更改用户的可分辨名称（也称作 DN），则不会在通讯簿服务 (ABS) 中更新任何其他更改。这不会影响用户的登录或状态，但如果 SIP 地址也被更改了，这将阻止用户通信，因为搜索将返回过期的 SIP 地址。

**解决方法：**

若要解决此问题，请不要更改用户的 DN。如果您将用户的 DN 还原为之前的值，则更新将反映在通讯簿服务中。

## 安装

## 使用非 ASCII 字符可能导致 Lync 服务器无法启动

**问题：**

如果目标文件夹名称包括非 ASCII 字符（包括 UNICODE、双字节字符集 (DBCS)、UTF-8 和 UTF-16），则安装将失败。此外，如果以下任何内容中包含非 ASCII 字符，则安装可能会成功但不会启动：

  - 计算机名称

  - 域名

  - 用户名

  - 用户 SIP URI

  - 服务帐户名称

**解决方法：**

请在目标文件夹名称、计算机名称、域名、用户名、用户 SIP URI 以及服务帐户名称中仅使用 ASCII 字符。

## 在安装 Lync Server 2013 之前，必须先安装针对“在 IIS 7.5 中，当模块调用 InsertEntityBody 方法时发生堆损坏”的修补程序

**问题：**

在安装 Lync Server 2013 之前，必须先安装针对“在 IIS 7.5 中，当模块调用 InsertEntityBody 方法时发生堆损坏”的修补程序 ([http://go.microsoft.com/fwlink/?linkid=268602\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268602%26clcid=0x804))，如 Microsoft 知识库文章 264886 ([http://go.microsoft.com/fwlink/?linkid=268603\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268603%26clcid=0x804)) 中所述。

**解决方法：**

从 Microsoft 下载中心下载并安装该修补程序，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=268602](http://go.microsoft.com/fwlink/p/?linkid=268602)。

## 在 ITA Windows Server 2012 OS RTM 版本上安装 Lync Server 2013 失败 (3179467)

**问题：**

在 ITA Windows Server 2012 上安装 Lync Server 2013 失败，因为 Windows Fabric 的安装未成功。

Windows Fabric 安装失败，因为 Fabric 跟踪是采用时间格式 HH:MM:SS 创建的。但在 ITA Windows Server 中，时间格式为 HH.MM.SS。

**解决方法：**

若要解决此问题，请先更新系统注册表，然后再安装 Lync Server 2013。需要更新的注册表项为：HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat。使用 Windows PowerShell 命令行接口 将 sTimeFormat 的值更改为 HH:mm:ss，如下所示：

1.  启动 Windows PowerShell 并返回以下 cmdlet：
    
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS

       &nbsp;
    
        $a="HKU:\.Default\Control Panel\International"

2.  若要查看当前值，请运行以下 cmdlet：
    
        Get-itemproperty $a -Name sTimeFormat
    
    记下 sTimeFormat 的当前值，以便在安装完成后还原为该值。

3.  若要设置新值，请运行以下 cmdlet：
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  在成功安装 Lync Server 2013 之后，使用以下 cmdlet 还原 sTimeFormat 的初始值：
    
        - Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3. above>"

## 移动性

## 服务器故障转移过程中移动客户端的问题 (3345992)

**问题：**

当 Lync Server 出现故障并开始执行故障转移过程时，以下问题可能会影响移动客户端用户：

  - 故障转移开始的多达 10 分钟内无传入 Lync 呼叫或信号。

  - 无法接受传入聊天请求

  - 如果出现故障的服务器是用户的主服务器，则无法加入会议

**解决方法：**

没有解决此问题的方法。故障转移过程完成时将恢复正常功能。

## 如果移动用户拒绝来自其他 Lync 终结点的传入呼叫，则该呼叫将在 Lync 移动客户端上显示为错过的会话 (3346251)

**问题：**

如果移动用户拒绝传入呼叫，而该呼叫来自其他 Lync 终结点，则该呼叫将在 Lync 移动客户端上显示为错过的会话，而不是在设备呼叫列表中显示为一个呼叫。

**解决方法：**

没有解决此问题的方法。

## 当搜索联系人时，移动客户端可能无法显示联盟联系人的显示名称 (3346256)

**问题：**

联盟联系人的显示名称在某些情况下可能无法显示，例如当搜索联系人列表中的联盟联系人时。当 Lync 移动客户端中的联系人没有活动的状态订阅时，可能会发生这种情况。

**解决方法：**

没有解决此问题的方法。

## 在移动客户端中，属于会议邀请的错过对话中缺少被邀请者和时间戳信息 (3346265)

**问题：**

在移动客户端中，当错过的对话是会议邀请时，错过的对话消息中缺少被邀请者和时间戳信息。

**解决方法：**

没有解决此问题的方法。

## 使用 VoIP 进行呼叫的移动客户端用户无法为在 Exchange 2010 或较早版本中配置了语音邮件的用户留语音邮件消息 (3346260)

**问题：**

如果移动客户端用户使用 VoIP 进行呼叫，则该用户不能为配置为在 Microsoft Exchange Server 2007 或 Microsoft Exchange Server 2010 中使用语音邮件的用户留语音邮件消息。

**解决方法：**

若要解决此问题，请使用 Exchange 2010 SP1 或 Microsoft Exchange Server 的更高版本。

## 当对移动客户端上的客户端版本配置使用“使用 URL 阻止”时，可能会显示不正确的错误消息 (3346258)

**问题：**

如果对移动客户端上的客户端版本配置使用“使用 URL 阻止”，当不支持客户端版本时，可能会显示不正确的错误消息。

**解决方法：**

若要解决此问题，请将客户端版本配置配置为使用“阻止”而不是“使用 URL 阻止”。

## 会议

## 在 Lync Server 2013前端服务器上运行的防病毒软件可能会导致应用程序域回收，这将临时中断 Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013 客户端的服务 (3212531)

**问题：**

防病毒软件可触发应用程序域重新启动，这会导致 Lync Mobility Service 2013 和统一通信 (UC) Web API 客户端应用程序（ Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013）丢失其状态。

**解决方法：**

若要解决此问题，请从防病毒扫描中排除包含 Web 组件和 .NET Framework 的文件夹。有关详细信息，请参阅 Microsoft 知识库文章 312592“PRB：在 ASP.NET 中出现应用程序随机重新启动并伴随‘应用程序正在重新启动’错误”，网址为 [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x804)。

应排除以下文件夹：

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext

  - %Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config

## 必须在 Windows Internet Explorer 中启用 ActiveX 控件或本机 XMLHTTP 支持以便成功加入会议 (2798163)

**问题：**

如果某个用户在 Windows Internet Explorer 的 Internet 浏览器设置中同时禁用了 ActiveX 控件和本机 XMLHTTP 支持，则该用户在 Internet Explorer 被选作默认浏览器时将无法加入会议。

**解决方法：**

在 Internet Explorer 中启用 ActiveX 控件或“本机 XMLHTTP 支持”。

## Lync Server Web 会议服务无法从临界模式恢复 (2788663)

**问题：**

如果将临界模式用于存档，则在系统出现故障时，临界模式将启动且会议不再对参与者可用。在管理员修复系统故障（如修复数据库问题）之后，数据会议服务不会自动恢复，管理员必须手动重新启动会议服务才能将其恢复。

**解决方法：**

管理员需要在系统故障修复后手动重新启动会议服务。

## Web 会议服务忽略外部 Office Web App 服务器的 HTTP 代理 (2602182)

**问题：**

如果您已在 Internet 和外围网络中部署 Web 会议服务的外部 Office Web Apps Server（即未在内部企业网络中的服务器），并且 Web 会议服务需要一个 HTTP 代理才能连接到它，则 Office Web Apps Server 发现将失败。Web 会议服务将忽略 Office Web Apps Server 安装程序的 拓扑生成器中定义的 HTTP 代理设置。因此，Lync 客户端无法与会议中的其他参与者进行 Microsoft PowerPoint 2010 共享。如果您本地安装 Lync Server 并在内部网络中本地配置 Office Web Apps Server，则无需代理配置。

**解决方法：**

唯一的解决办法是，不采用需要使用 HTTP 代理与外部 Office Web Apps Server 进行通信的部署配置。

## 不支持向音频会议提供商会议添加视频 (2603861)

**问题：**

如果用户加入音频会议提供商会议以进行音频会议，则不支持添加视频。

**解决方法：**

没有解决此问题的方法。

## 已启用 IPv6 的拓扑会强制进行 Lync Web App Silverlight 插件自动更新以确保屏幕共享功能可从 Lync Web App 运行 (2604634)

**问题：**

在启用 IPv6 的情况下配置拓扑时，如果已安装早期版本的屏幕共享插件，则用户无法从 Lync Web App 客户端共享其屏幕。

**解决方法：**

若要在通过 Lync Web App 加入会议时强制更新到最新版本的屏幕共享插件，请同时在以下两个文件中将 **MinSupportedBuildVersion** 的值从“4.0.7457.0”更改为“4.0.7577.380”：

  - %ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml

  - %ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml

## 企业语音

## 在某些情况下，配置为使用 IPv4 和 IPv6 双协议栈的计算机上运行的 Lync 客户端可能不支持依赖计算机的 IP 子网的功能，例如 E911、媒体绕过、呼叫允许控制和基于位置的路由 (3335508)

> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



**问题：**

当 Lync 客户端在启用了 IPv4 和 IPv6 双协议栈并且基于代理服务器的 DNS 解析的计算机上运行时，客户端可能会使用计算机的 IPv6 地址登录。这样做之后，Lync 客户端将仅支持 IPv6 支持的功能，这些功能不包括 E911、媒体绕过、呼叫允许控制和基于位置的路由。

**解决方法：**

若要解决此问题，请在客户端计算机上禁用 IPv6 支持。

## 如果未为用户配置 企业语音，则用户将需要使用 E164 格式从会议发起电话拨出 (3215342)

**问题：**

如果未为用户配置 企业语音，则用户将需要使用 E164 格式才能从会议成功发起电话拔出。如果不使用 E164 格式，则用户无法从会议发起电话拨出。

**解决方法：**

若要解决此问题，未启用 企业语音的用户应使用 E164 格式的号码从会议发起电话拨出。

## 状态

## 如果用户在为其启用统一的联系人存储库时选择“阻止所有邀请和通信”，则在需要时不会拒绝当前状态 (3204526)

**问题：**

如果用户在为其启用统一的联系人存储库时选择“阻止所有邀请和通信”，则在需要时不会拒绝当前状态。

**解决方法：**

若要解决此问题，您可以为用户禁用统一的联系人存储库。为此，请运行以下 cmdlet：

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

例如：

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

## 在混合部署中，本地驻留的 Office Communications Server 2007 R2 用户无法查看 Skype for Business Online 用户的当前状态 (3014624) - 混合

**问题：**

在使用 Lync Server 2013 控制器时，混合部署中可能会出现此问题。

向本地用户显示的驻留到 Skype for Business Online 的用户的当前状态为“显示状态未知”。此外，驻留到 Skype for Business Online 的用户无法查看 Office Communications Server R2 本地用户的当前状态。

**解决方法：**

若要部分解决此问题，请将 Skype for Business Online 用户的主服务器 (msrtcsip-presencehomeserver) 更改为指向 Lync Server 2013 本地池而不是 Lync Server 2013 控制器。您可以在本地 前端服务器上修改此设置。

此解决方法会向 Skype for Business Online 用户正确显示驻留到 Office Communications Server 2007 R2 的用户的当前状态。

## 响应组应用程序、呼叫寄存应用程序和组内呼叫应答

## 与取回方建立呼叫期间，呼叫者可能会听到一秒的保持音乐 (3334097)

> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



**问题：**

当通过组内呼叫应答取回呼叫时，在与取回方建立呼叫期间，呼叫者可能会听到一秒的保持音乐。

**解决方法：**

没有解决此问题的方法。

## 响应组代理只能通过 Lync Server 2010 代理控制台登录和注销 Lync Server 2010 正式代理组 (2773455)

**问题：**

Lync Server 2013响应组代理只能通过 Lync Server 2010 代理控制台登录和注销 Lync Server 2010 正式代理组。在 Lync Server 2010 代理控制台中，用户只能查看他们所属的 Lync Server 2010响应组，而无法查看其所属的任一 Lync Server 2013 响应组。

**解决方法：**

如果 响应组代理是一个 Lync Server 2013 用户且为 Lync Server 2013 正式代理组的一部分，则该用户必须通过浏览器中的 Web 链接直接访问 Lync Server 2013 代理控制台来登录或注销 Lync Server 2013 代理组。

## Lync Server 2010响应组代理无法代表 Lync Server 2013响应组发出呼叫 (2773471)

**问题：**

作为 Lync Server 2013响应组的代理的 Lync Server 2010 用户无法代表 响应组发出呼叫。 Lync Server 2013响应组将不可用于在 Lync 客户端中发出呼叫。

**解决方法：**

若要解决此问题，您必须将 Lync Server 2010 用户移至 Lync Server 2013。

## 在 响应组迁移到 Lync Server 2013 后将其从 Lync Server 2010 中删除将会阻止 响应组接受任何传入呼叫 (3016227)

**问题：**

如果通过 Lync Server 控制面板或 Lync Server 命令行管理程序从 Lync Server 2010 中删除已从 Lync Server 2010 迁移到 Lync Server 2013 的 响应组，则 Lync Server 2013 中的 响应组将停止接收任何传入呼叫。

**解决方法：**

若要解决此问题，请不要从 Lync Server 2010 中删除已从 Lync Server 2010 迁移到 Lync Server 2013 的任何响应组。

如果 响应组已被删除，您应在 Lync Server 2013 中重新部署它。

## 如果在创建新的托管工作流时将其设置为非活动状态，则该工作流的部署将失败 (3207527)

**问题：**

如果在创建新的托管工作流时将其设置为非活动状态，则该工作流的部署将失败。如果在创建工作流时将其设置为非活动状态，则会遇到此问题，但不会影响已编辑为在部署后设置为非活动状态的工作流。

**解决方法：**

在创建和部署工作流时，将工作流设置为活动状态，然后部署它。在成功部署工作流后，可以编辑工作流并将其设置为非活动状态。

## 如果已将 响应组导入备份池，则从所有者池中删除 响应组将阻止备份池的 响应组在故障转移期间接受任何传入呼叫 (3016214)

**问题：**

如果将主池所拥有的 响应组导入备份池而不覆盖所有者，并从所有者池中删除 响应组，则备份池中的响应组在故障转移期间不会接受任何传入呼叫。

**解决方法：**

您将需要在主池中重新部署 响应组。然后，您需要从主池中导出 响应组配置并将其重新导入到备份池中。

您还可以在备份池中重新创建 响应组。在此情况下，备份池将是 响应组的所有者池。

## 如果代表 响应组发出检索请求，则无法从 呼叫寄存应用程序中检索寄存呼叫 (3211798)

**问题：**

在满足以下条件时，寄存呼叫的检索请求将失败：

  - 代理是匿名 响应组的一部分

  - 代理尝试通过匿名 响应组从 呼叫寄存应用程序中检索寄存呼叫

  - 代理尝试通过“代表呼叫”选项或通过 Lync 助理客户端中的同一选项拨打通道号来检索呼叫

**解决方法：**

没有解决此问题的办法。应在未代表 响应组执行此操作的情况下检索寄存呼叫。

## Lync Server 控制面板、 拓扑生成器和规划工具

## 规划工具限制（3331056 和 3331059）

> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



**问题：**

规划您的部署时，规划工具具有以下限制：

  - 最多支持 10 个中央站点

  - 每个中央站点最多可以有 14 个分支站点

  - 每个中央站点最多可以有 240,000 个用户

此外，当计算推荐的拓扑时，规划工具不包括以下内容的值：

  - 以联机方式驻留的用户数

  - 启用了 XMPP 联盟的用户的百分比

  - 使用 Lync Web App 的用户的百分比

**解决方法：**

这些问题没有解决办法。有关规划工具的详细信息，请参阅[使用规划工具设计适用于 Lync Server 2013 的拓扑](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)。

## 当更新选项时，规划工具可能不会使用以前为边缘网络定义的 IP 地址

**问题：**

使用规划工具完成您的设计之后，如果您对边缘网络选项进行更改，则可以向设计添加其他 IP 地址，而不必更新现有 IP 地址。当您查看边缘网络图的详细信息时可能会发生这种情形，请选择“单击此处更新选项”，然后在“配置选项”对话框上选择“我希望使用相同的 FQDN 和 IP 地址，但是为我的边缘服务器上的边缘服务使用不同端口”。应用任何更改可能会导致新的 IP 地址和边缘服务器添加到设计。

**解决方法：**

此问题此时没有解决办法。

## 在 Lync Server 控制面板中，“将所有用户移动到池”无法按预期工作 (3199270)

**问题：**

在复杂的 Active Directory 环境（如包含多个域控制器和父/子域的环境）中，使用 Lync Server 控制面板将一个池中的所有用户移动到另一个池时，可能会返回一条错误消息，指明“指定用户不是旧用户，请改用 Move-CsUser cmdlet”。此情况是由于复杂的 Active Directory 环境中的复制时间较长导致的。

**解决方法：**

要解决该问题，请执行下列操作之一：

  - 在 Lync Server 控制面板中使用筛选器搜索旧用户，选择这些用户，然后使用“将所选用户移动到池”命令而不是“将所有用户移动到池”。

  - 使用 Lync Server 命令行管理程序通过 Lync Server cmdlet 批量移动旧用户。

## 在将 Microsoft Silverlight 浏览器插件 更新为版本 5 后， Lync Server 控制面板在 VMware 环境中停止工作 (3199270)

**问题：**

如果您在 VMware 环境中使用 Lync Server 控制面板，则 Lync Server 控制面板在您将 Silverlight 升级到版本 5 后可能会停止工作。

**解决方法：**

要解决该问题，请执行下列操作之一：

  - 卸载 Silverlight 5，然后从 [http://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](http://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) 中安装 Silverlight 4。

  - 从不是 VMware 虚拟机的计算机中打开 Lync Server 控制面板。
    
    若要从远程计算机中打开 Lync Server 控制面板，请在该计算机上安装 Lync Server 管理工具，然后从 Windows“开始”菜单启动 Lync Server 控制面板。
    
    还可以通过在 Web 浏览器中输入 URL 来打开 Lync Server 控制面板。URL 将类似于 https://\<frontend\_pool\_fqdn\>/cscp。

## 在 拓扑生成器中删除镜像数据库后，管理员无法运行 Uninstall-csMirrorDB cmdlet (3199266)

**问题：**

当管理员在 拓扑生成器中禁用某个镜像数据库，然后将该数据库从 拓扑生成器中删除时，待办事项列表中将显示一条消息，指示管理员运行 **Uninstall-csMirrorDatabase** cmdlet 以从 SQL Server 中删除镜像。在管理员尝试运行此 cmdlet 时发生失败。

**解决方法：**

若要从 拓扑生成器中删除某个池的 SQL 镜像，您必须先使用 cmdlet 删除 SQL Server 中的镜像，然后使用 拓扑生成器删除拓扑中的镜像。若要删除 SQL Server 中的镜像，请使用以下 cmdlet：

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

例如，若要删除镜像并删除针对用户数据库的数据库，请键入：

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

*DropExistingDatabasesOnMirror* 参数可促使从镜像中删除受影响的数据库。然后，若要从拓扑中删除镜像，请执行以下操作：

1.  在拓扑生成器中，右键单击池，然后单击“编辑属性”。

2.  清除“启用 SQL 存储镜像”，然后单击“确定”。

3.  发布拓扑。

> [!IMPORTANT]
> 只要更改后端数据库镜像关系，就必须重新启动池中的所有 前端服务器。


## 管理员尝试删除包含具有关联的见证存储的前端池的部署时， 拓扑生成器中返回验证错误 (3199266)

**问题：**

如果管理员尝试在拓扑生成器中使用“删除部署”命令删除包含具有关联的见证存储的前端池的部署时，拓扑生成器中显示一条验证错误，并且操作将无法继续进行。

**解决方法：**

要解决该问题，请执行下列操作之一：

  - 尝试删除部署之前先删除见证存储。

  - 为前端池添加见证存储，然后将其删除。

## 持久聊天服务器部署信息在规划工具与 拓扑生成器之间不一致 (3012228)

**问题：**

在 Lync Server 2013 规划工具输出已启用灾难恢复的 持久聊天服务器部署的站点拓扑图时，该站点拓扑图包括多个（物理）站点，并且在每个站点上均匀分配了 持久聊天服务器。在 拓扑生成器中，所有 持久聊天服务器都表示为属于一个（逻辑）站点，并在同一个 持久聊天服务器池节点下列出。

**解决方法：**

目前，我们没有解决此问题的方法。用户应分析 持久聊天服务器部署的 规划工具的输出，并修改计划以满足其特定需求。

## 本地化

## 监控

## 在使用东亚版本的 Lync Server 时，部署监控报告向导在特定情况下会显示不正确的字符 (3113565)

**问题：**

在系统区域设置未设置为东亚语言的操作系统上使用东亚版本的 Lync Server 2013（例如，中文（简体）、中文（繁体）、日语或朝鲜语）时，部署监控报告向导将显示问号或其他字符而不是本地化的消息。

**解决方法：**

若要纠正此问题，请将操作系统的区域设置和 Lync Server 2013 设置为同一语言，这将正确显示所有消息。

## Lync Server 控制面板

## 在某些情况下，当单击 Lync Server 控制面板的页面的顶部导航栏中的最后一个项时，该栏中的第一个项将消失 (3158118)

**问题：**

通过单击 Lync Server 控制面板的页面上顶部导航栏中的最后一个项将导致该顶部导航栏中的第一个项消失的已知情况有三种：

  - 在法语版本中，在“Féderation et accès externe”页面上，在单击“Partenaires fédérés XMPP”时，项“Stratégie d'accès externe”将消失。

  - 在德语版本中，在“Clients”页上，在单击“Pushbenachrichtigungskonfiguration”时，项“Clientversionskonfiguration”将消失。

  - 在俄语版本中，在“Конфигурация сети”页上，在单击“Маршрут региона”时，项“Глобально”将消失。

**解决方法：**

若要解决此问题，请刷新浏览器中的 Lync Server 控制面板的页面。将在浏览器中加载该页面，其中将显示顶部导航栏中的所有项。

## 通讯簿

## 通讯簿中的索引在某些语言中未按预期工作 (3336047)

> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



如果用户的属性包含索引字段，并且该字段仅包含无法编制索引的字符，则该用户不会显示在通讯簿中执行的搜索中。

以下字符和区域设置无法编制索引：

  - 大写西里尔文、希腊语和亚美尼亚语字符

  - 大写重音符号

  - 泰语

  - 老挝语

  - 缅甸

  - 梵文

  - 埃塞俄比亚文

  - 藏语

  - 孟加拉语

  - 古吉拉特语

  - 泰卢固语

  - 所有其他印度语脚本

## Lync Web App、Web Scheduler 和 Web 组件

## 针对 Lync Web Scheduler、Dial-In、Join Launcher、持久聊天聊天室管理和 OCTab 中的特定语言的语言回滚无法按预期运行 (3079700)

**问题：**

如果在 Web 浏览器中选择中性区域设置（例如，在 Internet Explorer 中，未进一步规范的语言名称，如“Norwegian \[no\]”）而不是选择指定语言的局域设置，则脚本和区域设置（如“Norwegian, Bokm?l (Norway) \[nb-NO\]”）可能会导致针对 Lync Web Scheduler、Dial-In、Join Launcher、持久聊天聊天室管理和 OCTab 中的特定语言的意外显示行为。例如，在选择下列语言之一时，用户可能会看到英文页面：

  - 挪威语

  - 葡萄牙语

  - 塞尔维亚语

**解决方法：**

若要选择具有中性区域设置的语言，请始终确保您还在浏览器的语言首选项列表中添加带特定区域设置（包括脚本和/或国家/地区代码）的语言作为附加语言。

## 在某些 Web 浏览器中使用 Lync Web Scheduler、Dial-In、Join Launcher、持久聊天聊天室管理和 OCTab 时，对阿塞拜疆语和乌兹别克语区域设置的支持是有限的 (3336748)

> [!NOTE]  
> 本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。



**问题：**

当您使用 Internet Explorer 8 或 Internet Explorer 9，并将浏览器语言设置为阿塞拜疆语（拉丁文）或乌兹别克语（拉丁文）时，Dial-in 和 Join Launcher 页面将以英语或浏览器中设置的首选语言显示。

当您使用 Firefox 或 Chrome 浏览器，并将浏览器语言设置为阿塞拜疆语（拉丁文）或乌兹别克语（拉丁文）时，Lync Web App、Lync Web Scheduler 和 RGS OCTab 将以英语或为浏览器设置的首选语言显示。

Safari 浏览器中不支持乌兹别克语（拉丁文）区域设置。

**解决方法：**

这些问题没有解决办法。

## 罗马尼亚语版本的 Lync Web App 中的“从以下位置加入会议”列表中缺少下拉箭头 (3154899)

**问题：**

在使用罗马尼亚语版本的 Lync Web App 的用户执行以下步骤时，下拉列表中未显示“加入会议”的下拉箭头：

1.  在“常规”选项卡上，选择“在此计算机上保留我的信息”。

2.  选择“电话”选项卡。

3.  单击“从以下位置加入会议”的下拉列表。
    
    用户将看不到一个指示存在除默认“Lync Web App”之外的更多选项的箭头，这包括“不加入音频”（在罗马尼亚语版本中，为“Nu se asocia?a la componenta audio”）和“新号码”（在罗马尼亚语版本中，为“Num?r nou”）。

**解决方法：**

即时未显示此下拉列表的箭头，用户仍可以通过单击默认值来选择此列表中的其他设置。

## 如果使用的是土耳其语版本的 Lync Web Scheduler，则在使用“演示者身份”下的“我选择的人员”选项时，将无法保存会议 (3169483)

**问题：**

在土耳其语版本的 Lync Web Scheduler 中创建或编辑会议时，不支持“演示者身份”下的“我选择的人员”选项。在选择此选项时，无法保存会议。相反，将显示一条错误消息，该消息指示无法将一个或多个人员作为演示者。

**解决方法：**

若要解决此问题，用户可使用默认选项“我公司的人员”或任何其他选项，如“仅组织者”或“包括我公司之外的人员在内的每个人”。组织者可在人员加入会议后将人员降级或升级到其正确角色。

或者，了解其他语言的用户可将其浏览器中的语言选择更改为其他 43 种受支持的语言之一，并尝试使用“我选择的人员”选项。

## 版权信息

本文档支持预发行版的软件产品，它是 Microsoft Corporation 的机密和专有信息，并可能会在最终商业发行版之前进行重大更改。将依据接收方与 Microsoft 之间签订的保密协议披露本文档。本文档提供的信息仅供参考，Microsoft 不对本文档中的内容作任何明示或默示的保证。本文档中的信息（包括 URL 和其他 Internet 网站引用）如发生更改，恕不另行通知。使用本文档的全部风险或因使用本文档而导致的各种后果均由用户承担。除非另行说明，否则本文档示例中所提及的公司、组织、产品、域名、电子邮件地址、徽标、人物、地点和事件纯属虚构。不应据此联想或推断到任何真实的公司、组织、产品、域名、电子邮件地址、徽标、人物、地点或事件。用户有责任遵守所有适用的版权法。在不限制版权许可权利的情况下，未经 Microsoft Corporation 的明确书面许可，不得出于任何目的、以任何形式或通过任何手段（电子、机械、复印、录制或其他方式）复制本文档的任何部分或将其存储到或引入检索系统中或进行传播。

本文档所涵盖的主题可能涉及到 Microsoft 的专利、专利申请、商标、版权或其他知识产权权利。除非 Microsoft 的任何书面许可协议中明确规定，否则提供本文档并不代表向您授予上述任何专利、商标、版权或其他知识产权许可。

© 2012 Microsoft Corporation。保留所有权利。

Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook 和 SQL Server 是 Microsoft Corporation 在美国和/或其他国家/地区的注册商标或商标。

所有其他商标归其各自的所有者所有。
