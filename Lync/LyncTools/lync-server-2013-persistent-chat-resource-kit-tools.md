---
title: Lync Server 2013 持久聊天资源工具包工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c851be7bb7046021cc2d37c88ef03bdea60c95a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Lync Server 2013 持久聊天资源工具包工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-24_

Lync Server 2013 持久聊天资源工具包工具可帮助部署和管理 Lync Server 2013 持久聊天服务器的 IT 管理员更轻松地执行日常任务。 除了安装说明, 本主题还介绍了每个工具的用途以及它的使用示例。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>安装资源管理包工具

若要安装 Lync Server 2013、资源工具包工具, 请下载**PersistentChatReskit**。 运行**PersistentChatReskit**以执行简单安装。 .Msi 将在以下路径中安装所有工具: \\**程序\\文件 Microsoft Lync Server 2013\\持久聊天服务器资源工具包**。 属于自包含可执行文件的工具位于此文件夹中。 也有文件的工具位于它们自己的子文件夹中。

<div>


> [!IMPORTANT]  
> 安装 Lync Server 2013 和资源工具包工具后, 必须安装<STRONG>psexec</STRONG>并将<STRONG>psexec</STRONG>复制到以下路径: \\<STRONG>程序文件 \ Microsoft Lync server 2013 \ 持久聊天服务器资源 Kit\ChatStressTool</STRONG>. 如果不复制<STRONG>PsExec</STRONG>, 持久聊天应力工具将引发错误异常, 并且不能正确执行。 在运行该工具之前, 请确保满足此先决条件要求。 有关安装<STRONG>PsExec</STRONG>的详细信息, 请参阅<A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>。



</div>

</div>

<div>

## <a name="supported-environments"></a>支持的环境

为获得最佳性能, Lync Server 2013、资源工具包工具应安装在相同的环境中, 并具有 Lync Server 2013 所需的相同规范。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>资源管理包工具概述

下面是 Lync Server 2013 持久聊天资源工具包中提供的工具。 下节提供了每个工具的说明, 包括要求和示例用法。

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

AffCheck 工具可确认持久的聊天后端数据库用户和组从属记录是否与 Active Directory 域服务的记录相匹配。

</div>

<div>

## <a name="requirements"></a>要求

该工具随加入域的计算机上的 PersistentChatResKit 安装程序一起安装。

运行该工具的用户帐户必须对持久的聊天后端数据库和 Active Directory 域服务具有读取访问权限。

</div>

<div>

## <a name="usage"></a>用法

根据配置文件中的说明配置 AffCheck 文件, 并运行 AffCheck 工具 (不带命令行参数)。 以下是默认 AffCheck 的内容。

**AffCheck:**

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

PersistentChatMonitoringSummary 工具将持久聊天监视信息从监视数据库移动到指定的 CSV 日志文件中。

CSV 文件将包含按会话总数、成功会话、意外失败、预期失败和意外故障 (如诊断 ID、失败数和失败说明) 细分的持久聊天会话的细目。

</div>

<div>

## <a name="requirements"></a>要求

在有权访问监视数据库的已加入域的计算机上安装持久聊天资源工具包工具。

运行该工具的用户帐户必须具有对监视数据库的读取访问权限。

文件 (PersistentChatMonitoringSummary) 必须包含一个\<connectionStrings\>部分, 用于定义监视数据库的连接字符串。 它还必须包含将为其收集监视数据的 PersistentChatEndpointUri 的键, 以及将生成的 CSV 文件的位置的文件路径。 有关示例, 请参阅已安装的配置文件。 文件必须与工具位于同一目录中。

</div>

<div>

## <a name="usage"></a>用法

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

这些参数定义数据的选择:

**StartDateTime:**(可选) 指定选择期的开始日期。 默认: 1/1/1753 12:00:00 AM

**EndDateTime:**(可选) 指定选择期的最后一个日期。 默认: 现在

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

持久聊天功能强大的工具提供了一种简单的方法来模拟持久聊天的使用, 以测试实际性能, 包括各种用户模型以更好地适应预期的使用方案。

</div>

<div>

## <a name="requirements"></a>要求

在有权访问持久的聊天后端数据库的已加入域的计算机上安装持久聊天资源工具包工具。

除了此*控制器*计算机外, 你还需要多个*加载程序*计算机。 对于用户模型中的每个10K 用户, 加载程序计算机上至少需要4GB 的可用内存。 例如, 80K 用户的运行将需要跨所有加载程序计算机的 RAM 的32GB。 建议您至少拥有三个加载器计算机, 而不考虑预期的负载。

加载程序计算机必须安装 .NET 4.5 框架以及安装 Visual c + + 2012 可再发行组件。

</div>

<div>

## <a name="configuration"></a>配置

将 ChatStressTool 文件复制到可从所有加载程序计算机访问的共享文件夹中。

创建要在压力运行中使用的用户和频道:

  - 创建任意多个用户作为你的用户模型调用, 为 Lync 启用它们, 并将其持久聊天策略设置为 "已启用"。

  - 为您的压力信道创建一个类别, 然后根据该类别的需要创建任意多个房间。 该类别应在其**允许**列表中包含所有压力用户 (通过添加其 OU), 并且压力房间应具有 "**打开**" 隐私设置。

  - 我们建议您创建额外的压力房间。 你可以通过以下 Windows PowerShell 命令行界面命令创建50000聊天室:
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

编辑配置文件以适合你的拓扑:

在**LoaderProcess**中, 将 "controller.contoso.com" 更改为控制器计算机的完全限定的域名 (FQDN)。

在**StressLauncher 中:**

1.  将 "LoaderBinary" 设置值更改为共享文件夹的路径。

2.  将 "AdminUser"/"AdminPassword" 更改为具有对加载程序计算机的管理员访问权限的凭据。

3.  将 "ChannelCategory" 更改为在其下创建了应力信道的类别的名称。

4.  将 "UserNamePattern" 和 "UserPasswordPattern" 更改为与你的压力用户凭据匹配的模板。 {0}将替换为用户的索引号。

5.  将 "域" 更改为测试拓扑的 SIP 域。

6.  将 "ConnectionString" 更改为持久的聊天后端数据库的连接字符串。

7.  将 "UserIndexStart" 更改为第一个压力用户的索引。

8.  将 "LyncFQDN" 更改为你的前端池的 FQDN。

9.  修改 "计算机" 列表以包括所有加载程序计算机的计算机名称。

10. 将服务终结点的 baseAddress (默认为 "controller.contoso.com") 更改为控制器计算机的 FQDN。

</div>

<div>

## <a name="usage"></a>用法

完成配置后, 在控制器计算机上打开 StressLauncher。 您可以以任何用户的身份启动 StressLauncher。 在加载程序计算机上启动的加载程序进程所下的凭据必须在配置文件中指定。 你还必须提供对持久的聊天后端数据库具有读取访问权限的连接字符串。 如果此连接字符串使用集成的 Windows 身份验证, 则必须以具有此访问权限的用户的身份启动 StressLauncher。

根据需要更改用户模型设置。 单击 "**开始加载**" 以启动 "运行"。 一分钟后, 用户将开始登录, 进度栏将开始填充。 此时, 控制器计算机可以正常工作并采取性能测量。

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>说明

ChatUpgradeVerifier 是一种持久的聊天特定数据库比较工具。 该工具将组聊天 2007 R2 或群组聊天2010数据库 (2007/2010Db) 与持久聊天2013数据库 (2013Db) 进行比较。

在 2007/2010Db 中, 该工具将逐个检查、每个类别、持久聊天室和外接程序, 以查看它是否出现在2013Db 中。 比较包括检查类别、聊天室或外接程序上的所有设置、类别范围内的任何主体, 以及类别或聊天室上某个角色中的任何主体。 如果2013Db 中未正确显示某个类别或聊天室, 则差异将输出到冲突文件。 如果在升级后, 将更改 2007/2010Db, 然后此工具运行, 则会有一个与冲突文件的差异输出。 请注意, 此应用程序仅是数据库比较工具, 不会验证升级过程。

</div>

<div>

## <a name="requirements"></a>要求

在有权访问持久聊天后端数据库的已加入域的计算机上安装持久聊天资源工具包工具 (以前版本和当前版本以便永久聊天)。

运行该工具的用户帐户必须具有对持久聊天数据库的读取访问权限。

ChatUpgradeVerifier 文件必须包含 GroupChat2007R2Db 参数或 GroupChat2010Db 参数, 并将连接字符串指向相应的群组聊天数据库 (Groupchat 2007R2 或 2010)。 它还必须包含 PersistentChat2013Db 参数, 并将连接字符串连接到持久聊天2013数据库。

</div>

<div>

## <a name="usage"></a>用法

不带任何参数运行**ChatUpgradeVerifier** 。

</div>

<div>

## <a name="example"></a>示例

![运行 ChatUpgradeVerifier。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "运行 ChatUpgradeVerifier。")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>持续聊天使用情况报告

<div>

## <a name="description"></a>说明

ChatUsageReport 工具生成持久聊天服务使用的 HTML 报告。

</div>

<div>

## <a name="requirements"></a>要求

在有权访问持久聊天后端数据库的已加入域的计算机上安装持久聊天资源工具包工具。

运行该工具的用户帐户必须具有对持久聊天后端数据库的读取访问权限。

文件 ChatUsageReport 必须包含一个\<connectionStrings\>部分, 用于定义与持久的聊天后端数据库的连接字符串。 默认配置文件的内容包含在此处, 供你参考。

</div>

<div>

## <a name="usage"></a>用法

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
这些参数定义数据的选择:

开始**日期:**(可选) 指定选择期的 UTC 开始日期。 默认: 最早日期

**结束日期:**(可选) 指定选择期的 UTC 结束日期。 默认: 现在

这些参数定义数据的显示方式和显示方式:

**TopActiveUsers:** 如果指定此选项, 则报表将包括 n 个最活跃的用户, 包括用户在所选期间的聊天室中发布的消息数。 默认值:10

**TopActiveRooms:** 如果指定此选项, 则报表将包含 n 个最活跃的聊天室, 其中包含在所选期间的会议室中发布的消息数。 默认值:10

**LeastActiveRooms:** 如果指定此选项, 则报告将包括 n 个最少活动聊天室, 条件是所选期间的聊天室中发布的消息数。 会议室将至少发布一封邮件。 默认值:10

**RoomsInactiveSince:** 如果指定此项, 报表将包含自指定日期后处于非活动状态的聊天室的列表。 默认: 整个时间

**OutputFolder:** 将放置 ChatUsageReport 和 graph 图像的文件夹。 这必须在配置文件或命令行中定义。

所有命令行参数值也可以在与工具位于同一目录中的 ChatUsageReport 文件中指定。 如果在配置文件和命令行中均指定了任何值, 则命令行值将替代配置文件值。

</div>

<div>

## <a name="output"></a>输出

报表将始终包含以下输出:

  - 按所选期间的邮件投递次数排名前 n 位的最活跃聊天室。

  - 按所选期间的邮件投递次数排名前 n 位的最活跃的用户。

  - 按所选期间的邮件投递次数, 最少有 n 个活动聊天室。

  - 在数据库的整个生命周期内或自指定日期起不活动的聊天室。

  - 所选期间的每日消息发布趋势。

  - 所选期间的每周邮件发布趋势。

  - 所选期间的每月消息发布趋势。

  - 所选期间的总邮件帖子。

  - 已启用的会议室的总数。

</div>

<div>

## <a name="example"></a>示例

下面的示例为2001生成一个完整的使用报表, 并将报表放置在 ChatUsageReport 中指定的 OutputFolder 中。

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport:

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

ScheduleADSyncForPrincipal 是 Microsoft SQL Server 2012 脚本, 当连接到持久的聊天后端数据库时, 必须直接在 SQL Server Management Studio 内运行。 此脚本使你能够强制持久聊天将用户的记录与 Active Directory 域服务的记录同步, 而不是等待计划的同步时间。

</div>

<div>

## <a name="requirements"></a>要求

运行脚本的用户帐户必须具有对持久的聊天后端数据库的所有者访问权限。

</div>

<div>

## <a name="usage"></a>用法

以下是默认脚本的内容:

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

