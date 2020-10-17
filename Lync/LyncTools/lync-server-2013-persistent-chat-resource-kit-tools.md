---
title: Lync Server 2013 持久聊天资源工具包工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80a9116374914c212d305ef2e55d0b8c4fecb782
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533665"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Lync Server 2013 持久聊天资源工具包工具

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-24_

Lync Server 2013 持久聊天资源工具包工具有助于为部署和管理 Lync Server 2013 持久聊天服务器的 IT 管理员更轻松地执行日常任务。 除了安装说明之外，本主题还介绍了每个工具的用途及其用法示例。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>资源工具包工具的安装

若要安装 Lync Server 2013、资源工具包工具，请下载 **PersistentChatReskit.msi**。 运行 **PersistentChatReskit.msi** 以执行简单安装。 .Msi 在以下路径中安装所有工具： \\ **Program Files \\ Microsoft Lync Server 2013 \\ Persistent Chat server 资源工具包**。 包含自包含可执行文件的工具位于此文件夹中。 还包含文件的工具位于自己的子文件夹中。

<div>


> [!IMPORTANT]  
> 安装 Lync Server 2013 （资源工具包工具）后，必须安装<STRONG>PsExec.exe</STRONG>并将<STRONG>PsExec.exe</STRONG>复制到以下路径： \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ Persistent Chat server Resource Kit\ChatStressTool</STRONG>。 如果不复制 <STRONG>PsExec.exe</STRONG>，持久聊天工具将引发错误异常，且不能正常运行。 在运行该工具之前，请确保满足此先决条件要求。 有关安装 <STRONG>PsExec.exe</STRONG>的详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> 。



</div>

</div>

<div>

## <a name="supported-environments"></a>支持的环境

为了获得最佳性能，Lync Server 2013，资源工具包工具应安装在相同的环境中，并且具有与 Lync Server 2013 所需的相同规范。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>资源工具包工具概述

以下是 Lync Server 2013 持久聊天资源工具包中提供的工具。 下一节提供了每个工具的说明，包括要求和示例用法。

  - AffCheck

  - ChatMonitoringSummary

  - ChatStress 工具

  - ChatUpgradeVerifier

  - ChatUsageReport

  - ScheduleADSyncforPrincipal

</div>

<div>

## <a name="affcheck"></a>AffCheck

<div>

## <a name="description"></a>说明

AffCheck 工具确认持久聊天后端数据库用户和组附属记录与 Active Directory 域服务的记录相匹配。

</div>

<div>

## <a name="requirements"></a>要求

该工具随加入域的计算机上的 PersistentChatResKit 安装程序一起安装。

运行该工具所使用的用户帐户必须具有对持久聊天后端数据库和 Active Directory 域服务的读取访问权限。

</div>

<div>

## <a name="usage"></a>用法

根据配置文件中的说明配置 AffCheck.exe.config 文件，并运行不带命令行参数的 AffCheck 工具。 以下是默认 AffCheck.exe.config 的内容。

**AffCheck.exe.config：**

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a>ChatMonitoringSummary

<div>

## <a name="description"></a>说明

PersistentChatMonitoringSummary 工具将持久聊天监视信息从监控数据库移动到指定的 CSV 日志文件中。

CSV 文件将包含按会话总数、成功会话、意外故障、预期失败次数以及诊断 ID、失败次数和失败说明细分意外故障的连续聊天会话的细目。

</div>

<div>

## <a name="requirements"></a>要求

在有权访问监控数据库的加入域的计算机上安装持久聊天资源工具包工具。

运行该工具所使用的用户帐户必须具有对监控数据库的读取权限。

PersistentChatMonitoringSummary.exe.config 的文件中，必须包含一个 \<connectionStrings\> 定义监控数据库的连接字符串的节。 它还必须包含将为其收集监控数据的 PersistentChatEndpointUri 的键，以及将生成的 CSV 文件的位置的文件路径。 有关示例，请参阅已安装的配置文件。 文件必须与工具位于同一目录中。

</div>

<div>

## <a name="usage"></a>用法

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

这些参数定义数据的选择：

**StartDateTime：** （可选）指定选择期的开始日期。 默认值： 1/1/1753 12:00:00 AM

**EndDateTime：** （可选）指定选择期的结束日期。 默认值： Now

</div>

<div>

## <a name="example"></a>示例

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a>持久聊天应力工具

<div>

## <a name="description"></a>说明

持久聊天压力工具提供了一种简单的方法来模拟持久聊天的使用情况，以测试实际性能，包括各种用户模型以更好地适合预期的使用方案。

</div>

<div>

## <a name="requirements"></a>要求

将持久聊天资源工具包工具安装到可访问持久聊天后端数据库的加入域的计算机上。

除了此 *控制器* 计算机之外，还需要多个 *加载程序* 计算机。 对于用户模型中的每个10K 用户，加载项计算机上至少需要4GB 的可用 RAM。 例如，运行80K 用户将需要在所有加载程序计算机上分配 32 GB RAM。 建议您至少具有三个加载程序计算机，而不考虑预期的负载。

加载程序计算机必须安装 .NET 4.5 Framework 以及安装的 Visual c + + 2012 可再发行组件。

</div>

<div>

## <a name="configuration"></a>配置

将 ChatStressTool 文件复制到可从所有加载程序计算机访问的共享文件夹中。

创建在压力运行中使用的用户和频道：

  - 为您的用户模型调用创建任意多个用户，为 Lync 启用它们，并将其持久聊天策略设置为 "启用"。

  - 为您的压力通道创建一个类别，然后根据该类别的需要创建任意多个会议室。 类别应将所有压力用户放在其 **允许** 列表中 (通过添加其 OU) 的方式，并且压力会议室应具有 **开放**的隐私设置。

  - 我们建议创建额外的压力房间。 您可以使用以下 Windows PowerShell 命令行界面命令创建50000聊天室：
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

编辑配置文件以适用于您的拓扑：

在 **LoaderProcess.exe.config**中，将 "controller.contoso.com" 更改为控制器计算机的完全限定的域名 (FQDN) 。

在 **StressLauncher.exe.config 中：**

1.  将 "LoaderBinary" 设置值更改为共享文件夹的路径。

2.  将 "AdminUser"/"AdminPassword" 更改为具有对加载程序计算机的管理员访问权限的凭据。

3.  将 "ChannelCategory" 更改为在其下创建了压力通道的类别的名称。

4.  将 "UserNamePattern" 和 "UserPasswordPattern" 更改为与你的压力用户凭据相匹配的模板。 {0} 将替换为用户的索引号。

5.  将 "域" 更改为测试拓扑的 SIP 域。

6.  将 "ConnectionString" 更改为持久聊天后端数据库的连接字符串。

7.  将 "UserIndexStart" 更改为第一个压力用户的索引。

8.  将 "LyncFQDN" 更改为前端池的 FQDN。

9.  修改 "计算机" 列表，以包含所有加载程序计算机的计算机名称。

10. 更改服务终结 (点的 baseAddress 默认值为 "controller.contoso.com" ) 到控制器计算机的 FQDN。

</div>

<div>

## <a name="usage"></a>用法

配置完成后，在控制器计算机上打开 StressLauncher.exe。 您可以以任何用户的形式启动 StressLauncher。 必须在配置文件中指定用于在加载程序计算机上启动加载程序进程的凭据。 此外，还必须为连接字符串提供对持久聊天后端数据库的读取访问权限。 如果此连接字符串使用集成的 Windows 身份验证，则必须以具有此访问权限的用户身份启动 StressLauncher。

根据需要更改用户模型设置。 单击 " **开始加载** " 以启动运行。 一分钟后，用户将开始登录，进度栏将开始填充。 在这种情况下，您可能可以运行控制器计算机并采用性能度量。

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>说明

ChatUpgradeVerifier 是一种持久的聊天特定数据库比较工具。 该工具将组聊天 2007 R2 或组聊天2010数据库 (2007/2010Db) 与持久聊天2013数据库 (2013Db) 进行比较。

该工具将逐个检查、每个类别、持久聊天室和外接程序在 2007/2010Db 中进行检查，以查看它是否出现在2013Db 中。 比较包括检查类别、聊天室或外接中的所有设置、类别中的任何主体以及类别或聊天室上的角色中的任何主体。 如果类别或聊天室未在2013Db 中正确显示，则这些差异将输出到冲突文件中。 如果在升级后进行了升级，则会更改 2007/2010Db，然后运行此工具时，冲突文件的输出将会有所不同。 请注意，此应用程序仅为数据库比较工具，不会验证升级过程。

</div>

<div>

## <a name="requirements"></a>要求

在已加入域的计算机上安装持久聊天资源工具包工具，该计算机可访问持久聊天) 的旧版本和当前版本的现有聊天后端数据库 (。

运行该工具所使用的用户帐户必须具有对持久聊天数据库的读取权限。

ChatUpgradeVerifier.exe.config 文件必须包含 GroupChat2007R2Db 参数或 GroupChat2010Db 参数，并将连接字符串指向相应的 Group Chat 数据库 (Groupchat 2007R2 或 2010) 。 它还必须包含 PersistentChat2013Db 参数，并将连接字符串连接到持久聊天2013数据库。

</div>

<div>

## <a name="usage"></a>用法

运行不带任何参数的 **ChatUpgradeVerifier** 。

</div>

<div>

## <a name="example"></a>示例

![正在运行 ChatUpgradeVerifier.exe。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "正在运行 ChatUpgradeVerifier.exe。")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>持久聊天使用情况报告

<div>

## <a name="description"></a>说明

ChatUsageReport 工具生成持久聊天服务使用情况的 HTML 报告。

</div>

<div>

## <a name="requirements"></a>要求

在有权访问持久聊天后端数据库的加入域的计算机上安装持久聊天资源工具包工具。

运行该工具所使用的用户帐户必须具有对持久聊天后端数据库的读取访问权限。

ChatUsageReport.exe.config 的文件中，必须包含 \<connectionStrings\> 定义持久聊天后端数据库的连接字符串的节。 默认配置文件的内容包含在此处，供您参考。

</div>

<div>

## <a name="usage"></a>用法

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
这些参数定义数据的选择：

**起始日期：** （可选）指定选择期的 UTC 开始日期。 默认：最早日期

**结束日期：** （可选）指定选择期的 UTC 结束日期。 默认值： Now

这些参数定义了显示数据的方式和方式：

**TopActiveUsers：** 如果指定此值，则报告将包含 n 个最活跃的用户，这取决于用户在所选时段内已在聊天室中发布的邮件数。 默认值：10

**TopActiveRooms：** 如果指定此值，则报告将包含 n 个最活跃的聊天室，这取决于所选时段的会议室中投递的邮件数。 默认值：10

**LeastActiveRooms：** 如果指定此值，则报告将包含 n 个最小活动聊天室，条件是在所选时段的聊天室中发布的邮件数。 聊天室将至少发布一封邮件。 默认值：10

**RoomsInactiveSince：** 如果指定此类型，报告将包含自指定日期后处于非活动状态的聊天室的列表。 默认值：整个时间

**OutputFolder：** 将在其中放置 ChatUsageReport.html 和 graph 图像的文件夹。 这必须在配置文件或命令行中进行定义。

此外，还可以在与工具位于同一目录中的 ChatUsageReport.exe.config 文件中指定所有命令行参数值。 如果在配置文件和命令行中指定了任何值，则命令行值将替代 config 文件值。

</div>

<div>

## <a name="output"></a>Output

报告将始终包含以下输出：

  - 前 n 个最活跃聊天室（按所选时间段的邮件投递数表示）。

  - 按所选时间段的邮件投递次数排名前 n 个的最活跃的用户。

  - 前 n 个最小活动聊天室（按选定时间段内的邮件投递数表示）。

  - 在数据库的整个生命周期中或自指定的日期起处于非活动状态的聊天室。

  - 选定时间段内的每日邮件投递趋势。

  - 选定时段的每周邮件投递趋势。

  - 选定时段的每月邮件投递趋势。

  - 选定时间段内的邮件投递总数。

  - 已启用的会议室总数。

</div>

<div>

## <a name="example"></a>示例

下面的示例将生成2001年的使用率报告，并将报告放置在 ChatUsageReport.exe.config 中指定的 OutputFolder 中。

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport.exe.config：

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a>ScheduleADSyncForPrincipal

<div>

## <a name="description"></a>说明

ScheduleADSyncForPrincipal 是 Microsoft SQL Server 2012 脚本，它必须在连接到持久聊天后端数据库时直接从 SQL Server Management Studio 中运行。 通过此脚本，您可以强制持久聊天将用户的记录与 Active Directory 域服务的记录同步，而不是等待计划的同步时间。

</div>

<div>

## <a name="requirements"></a>要求

运行脚本所使用的用户帐户必须具有对持久聊天后端数据库的所有者访问权限。

</div>

<div>

## <a name="usage"></a>用法

以下是默认脚本的内容：

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

