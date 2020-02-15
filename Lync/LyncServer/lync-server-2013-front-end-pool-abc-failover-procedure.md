---
title: Lync Server 2013：前端池 ABC 故障转移过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2f3798dbe49b9da0e76810d1ea8e6619a4e9b6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Lync Server 2013 中的前端池 ABC 故障转移过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-22_

使用以下步骤执行 ABC 故障转移过程。 此过程包含每个步骤的简要说明，以及要针对每个步骤运行的命令和 cmdlet。

若要运行 cmdlet，请使用 "以管理员身份运行" 打开 Lync Server 命令行管理程序。

<div>

## <a name="to-perform-an-abc-failover"></a>执行 ABC 故障转移

1.  检查池 A 是否是中央管理服务器（CMS）的主机。
    
      - 运行以下 cmdlet：
        
            Get-CsService -CentralManagement
        
        如果活动 CMS 的 Identity 字段指向池 A 的完全限定的域名（FQDN），则使用此过程中的步骤2和步骤3先对中央管理服务器进行故障转移。 否则，请跳到步骤4。

2.  通过运行以下 cmdlet，在灾难恢复模式下将 CMS 故障转移到 Pool B：
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    执行此操作后，我们建议您将 CMS 从池 B 移到另一个现有配对池，以实现额外的恢复。 有关详细信息，请参阅[move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)。。

3.  如果池 A 包含 CMS，则将 .LIS 配置从池 A 导入到池 B 的 .LIS 数据库（.Lis .mdf）中。 仅当您定期备份 IIS 数据时，这才有效。 若要导入 .LIS 配置，请运行以下 cmdlet：
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  将已备份的 Lync Server 响应组服务工作流从池 A 导入到池 B。
    
    <div>
    

    > [!NOTE]  
    > 目前， <STRONG>CsRgsConfiguration</STRONG> cmdlet 要求池 A 上的队列和工作流名称与池 B 上的队列和工作流名称不同。如果名称不是唯一的，您将在运行<STRONG>CsRgsConfiguration</STRONG> cmdlet 时收到错误，在继续执行<STRONG>CsRgsConfiguration</STRONG> cmdlet 之前，将需要在 pool B 中重命名队列和工作流。

    
    </div>
    
    有两种方法可将响应组配置从池 A 导入到池 B。使用哪个选项取决于是否要使用 pool A 中的应用程序级设置覆盖池 B 的应用程序级别设置。
    
      - 如果要覆盖 Pool B 设置，请运行带**ReplaceExistingSettings**选项的**CsRgsConfiguration** cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 如果您不想覆盖池 B 设置，请使用不带**ReplaceExistingSettings**选项的**CsRgsConfiguration** cmdlet。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 请注意，如果您不想使用主池（池 B）的设置覆盖备份池（池 B）的应用程序级别设置，池 A 的应用程序级别设置将会丢失（如果池 A 丢失），因为响应组应用程序可以每个池仅存储一组应用程序级设置。 部署池 C 以替换池 A 时，必须重新配置应用程序级别的设置，包括默认的保持音乐的音频文件。

    
    </div>

5.  运行以下 cmdlet 以验证响应组配置是否成功，并显示导入的响应组。 请注意，导入的响应组仍然归池 A 所有。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  对于未分配号码，请将使用 "公告" 的未分配号码范围作为选定的宣告服务从池 A 移动到 pool B。为此，请执行以下操作：
    
      - 重新创建在池 B 上的池 A 中部署的所有通知。如果在池 A 中部署通知时使用了任何音频文件，则需要这些文件来重新创建池 B 中的通知。若要在 pool B 中重新创建通知，请使用**CsAnnouncement** cmdlet，并将 pool b 用作父服务。
    
      - 将作为池 A 中的公告的所有未分配号码范围重新设定为 pool B 中新部署的宣告。为目标为池 A 的公告的每个未分配号码范围运行以下 cmdlet：
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > 如果未分配的号码范围将 "Exchange UM" 用作选定的通知服务，则不需要执行此步骤。

    
    </div>

7.  通过运行以下 cmdlet，将池 A 故障转移到灾难恢复（DR）模式中的 Pool B：
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  构建池 C，但不启动池 C 上的任何服务。
    
    请注意，可以使用步骤5和6同时执行此步骤。

9.  通过运行以下 cmdlet 强制驻留在池 A 上的用户移动到池 C：
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    在这种情况下，驻留在池 A 上的用户将开始遇到服务中断。 此中断将持续到第16步，在此期间启动池 C 上的点服务。

10. 通过运行以下 cmdlet 强制池 A 的会议目录移动到池 C：
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. 通过运行以下 cmdlet，强制会议自动助理（CAA） Contact 对象从池 A 移到池 C：
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. 将会议内容从池 B 复制到池 C。

13. 从 pool B 导出用户数据，并通过运行以下 cmdlet 将用户数据导入到池 C 中：
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. 将已备份的呼叫寄存应用程序数据从池 A 还原到池 C，并将池 A 的呼叫寄存轨道范围分配给 pool C。
    
      - 您可以通过 Lync Server 控制面板或 Lync Server 命令行管理程序，将池 A 的呼叫寄存轨道范围重新分配到池 C。 对于 Lync Server 命令行管理程序，请为分配到池 A 的每个呼叫寄存通道范围运行以下 cmdlet （请注意，Identity 参数引用属于池 A 的呼叫寄存通道范围）：
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - 如果已为池 A 中的呼叫寄存配置了自定义的已保留音乐，请在池 C 中还原呼叫寄存自定义的保留音乐文件。
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        例如：
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - 最后，使用**CsCpsConfiguration** cmdlet 在 pool C 上重新配置呼叫寄存设置。 呼叫寄存应用程序只能为每个池存储一组设置和一个自定义的音乐保留音频文件，并且在发生灾难时不会备份或保留这些设置。

15. 如果用于持久聊天的下一个跃点池指向池 A，请发出并发布拓扑更改，以便下一个跃点服务器指向池 C。
    
      - 在拓扑生成器中，将持久聊天池更改为指向池 C 作为其下一个跃点。 为此，请右键单击 "持久聊天" 池，然后单击 "**常规**" 选项卡，然后在 "**下一个跃点池**" 中键入 pool C 的名称。
    
      - 通过运行以下 cmdlet 启动 pool C 上的服务：
        
            Start-csWindowsService
    
    在这种情况下，用户最初驻留在池 A 上的服务中断会结束。

16. 通过运行以下 cmdlet，导出来自 pool A 的 pool B 所拥有的 Lync Server 响应组服务工作流，以将其导入到 pool C 中：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. 将 Lync Server 响应组服务工作流从池 B 导入池 C。
    
    有两种方法可用于将响应组配置从池 B 导入池 C。使用哪个选项取决于您是否要使用池 B 中的应用程序级设置覆盖池 C 的应用程序级别设置。
    
      - 如果要覆盖 Pool C 设置，请运行带**ReplaceExistingSettings**选项的**CsRgsConfiguration** cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 如果您不想覆盖 Pool C 设置，请使用不带**ReplaceExistingSettings**选项的**CsRgsConfiguration** cmdlet。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 请注意，如果您不想使用备份池（池 B）的设置覆盖池 C 的应用程序级别设置，则池 B 的应用程序级别设置将会丢失，因为响应组应用程序只能存储一组应用程序级别每个池的设置。

    
    </div>

18. 运行以下 cmdlet 以验证响应组配置导入是否成功，以显示已导入到池 C 的响应组。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. 在池 C 中验证导入的配置后，从池 B 中删除主池拥有的响应组。这将最大限度地减少响应组的停机时间。
    
    此步骤将使用导出的配置创建一个新文件，然后从池 B 中删除该文件。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. 移动到池 C 从池 A 移至池 B 的未分配号码范围。
    
      - 在池 C 中重新创建从池 B 中的池 A 重新创建的所有通知。如果在部署要移动的通知时使用了任何音频文件，则需要使用这些文件在 pool C 中重新创建通知。若要在 pool C 中重新创建通知，请使用**CsAnnouncement** cmdlet，将 pool c 用作父服务。
    
      - 从池 C 重新定位到池 B 的所有未分配号码范围。为需要重定目标的每个未分配号码范围运行以下 cmdlet：
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Optional从池 B 中删除如果已不再在池 B 中使用，则在池 C 中重新创建的通知。若要删除通知，请使用**CsAnnouncement** cmdlet。
        
        <div>
        

        > [!NOTE]  
        > 如果未分配的号码范围将 "Exchange UM" 用作通知服务，则不需要执行此步骤。

        
        </div>

21. 通过运行以下 cmdlet 清除 pool A 中的 pool A 的用户数据：
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. 在拓扑生成器中执行以下操作：
    
      - Unpair 池 A 和池 B 对池 B 和池 C。然后，从拓扑中删除池 A 并发布它。 为此，请执行以下操作：
        
          - 在拓扑生成器中，右键单击 "池 B"，然后单击 "**编辑属性**"。
        
          - 在左窗格中单击 "**弹性**"。
        
          - 在 "关联的**备份池**" 下面的框中，选择 "池 C"。请注意，"关联的备份池" 选择框最初将显示池 A，这是因为以前与此池相关联的池 B。
        
          - 选择“语音的自动故障转移和故障回复”****，然后单击“确定”****。
            
            当您查看该池的详细信息时，关联的池现在显示在“复原”**** 下的右窗格中。
        
          - 在控制台树中，右键单击 "池 A"，然后单击 "删除"。
        
          - 发布拓扑。

23. 运行 pool C 上的引导应用程序以安装备份服务应用程序，然后通过从池中的本地计算机上的部署文件夹中运行以下命令来启动 backup service 应用程序：
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. 运行以下 cmdlet，在池 B 上重新启动备份服务应用程序：
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. 如果 pool C 是标准版（SE）池，并且 pool B 有 CMS，请运行以下 cmdlet，在池 C 上手动安装 CMS 数据库：
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. 调用备份服务，将旧会议内容从池 B 同步到配对 B 和 C 之前生成的池 C，并将新的会议内容从池 C 同步到在启动池 C 之后生成的池 B，并将 B 和 C 结合在一起。 若要执行此操作，请运行以下 cmdlet：
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. 对于与池 A 关联的每个 Survivable 分支装置 X：
    
      - 运行以下 cmdlet 以关闭 SBA X：
        
            Stop-CsWindowsService
    
      - 创建一个文件，其中包含驻留在 SBA X 上的用户的列表。当用户移回步骤30中的 SBA X 时，将需要此列表。 若要执行此操作，请运行以下 cmdlet：
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - 通过运行以下 cmdlet 强制驻留在 SBA X 上的用户移动到池 C：
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - 通过先运行以下 cmdlet 来更新这些用户的数据：
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        然后运行以下脚本：
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > 对于驻留在 Sba 上且与池 A 关联的用户，如果将这些用户移动到池 C，则会发生服务中断。

        
        </div>

28. 在拓扑生成器中，对于之前与池 A 关联的每个 SBA X，请执行以下操作：
    
      - 将关联更改为池 C。为此，请单击分支站点，展开 "Survivable Branch 器具" 或 "Servers" 节点，然后单击 " **Survivable Branch 设备**"。 然后选择 "Survivable" 分支设备将作为池 C 连接到的 "**用户服务" 池**，然后单击 "**下一步**"。
    
      - 发布拓扑。 若要执行此操作，请在控制台树中，右键单击新的**Survivable 分支设备**，单击 "**拓扑**"，然后单击 "**发布**"。

29. 对于现在与池 C 关联的每个 SBA X：
    
      - 通过在 survivable 分支设备上运行以下 cmdlet 来启动 SBA X：
        
            Start-CsWindowsService
    
      - 通过运行以下 cmdlet，将最初驻留在 SBA X 上的用户从池 C 转移到 SBA X。
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

