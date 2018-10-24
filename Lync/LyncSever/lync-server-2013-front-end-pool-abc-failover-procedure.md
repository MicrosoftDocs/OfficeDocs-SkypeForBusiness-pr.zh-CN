---
title: Lync Server 2013：前端池 ABC 故障转移过程
TOCTitle: 前端池 ABC 故障转移过程
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945635(v=OCS.15)
ms:contentKeyID: 52061046
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的前端池 ABC 故障转移过程

 

_**上一次修改主题：** 2014-05-22_

使用以下步骤来执行 ABC 故障转移过程。此过程包含每个步骤的概要说明以及要为每个步骤运行的命令和 cmdlet。

若要运行 cmdlet，请使用“以管理员身份运行”打开 Lync Server 命令行管理程序。

## 执行 ABC 故障转移

1.  检查池 A 是否是中央管理服务器 (CMS) 的宿主。
    
      - 运行以下 cmdlet：
        
            Get-CsService -CentralManagement
        
        如果活动 CMS 的“标识”字段指向池 A 的完全限定域名 (FQDN)，则使用此过程的步骤 2 和 3 来首先对中央管理服务器进行故障转移。否则，跳到步骤 4。

2.  通过运行以下 cmdlet 来用灾难恢复模式将 CMS 故障转移到池 B：
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    在执行此操作后，建议您将 CMS 从池 B 移动到其他现有配对池以实现额外的复原。有关详细信息，请参阅 [Move-CsManagementServer](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsManagementServer)。

3.  如果池 A 包含 CMS，请将 LIS 配置从池 A 导入到池 B 的 LIS 数据库 (Lis.mdf) 中。这将仅在您定期备份 LIS 数据时才可行。若要导入 LIS 配置，请运行以下 cmdlet：
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  将备份的 Lync Server 响应组服务工作流从池 A 导入到池 B 中。
    
    > [!NOTE]  
    > 目前， <strong>Import-CsRgsConfiguration</strong> cmdlet 要求池 A 中的队列和工作流名称与池 B 中的队列和工作流名称不同。如果名称相同，则在您运行 <strong>Import-CsRgsConfiguration</strong> cmdlet 时会得到错误，并且将需要重命名池 B 中的队列和工作流，然后才能继续运行 <strong>Import-CsRgsConfiguration</strong> cmdlet。
    
    
    您有两个选项可将响应组配置从池 A 导入到池 B。您使用哪个选项取决于是否要使用池 A 中的应用程序级别设置覆盖池 B 的应用程序级别设置。
    
      - 如果要覆盖池 B 设置，请运行带有 **ReplaceExistingSettings** 选项的 **Import-CsRgsConfiguration** cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 如果不想覆盖池 B 设置，请使用不带 **ReplaceExistingSettings** 选项的 **Import-CsRgsConfiguration** cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    > [!WARNING]
    > 请记住，如果您不想使用主池（池 A）的设置覆盖备份池（池 B）的应用程序级别设置，则池 A 的应用程序级别设置会在池 A 丢失时丢失，因为响应组应用程序只能为每个池存储一组应用程序级别设置。在部署池 C 以替换池 A 时，必须重新配置应用程序级别设置，包括默认的保持音乐音频文件。


5.  通过运行以下 cmdlet 显示导入的响应组来验证响应组配置导入是否成功。请注意，导入的响应组仍为池 A 所拥有。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  对于未分配号码，将使用“通知”作为所选通知服务的未分配号码范围从池 A 移动到池 B。为此：
    
      - 在池 B 中重新创建池 A 中部署的所有通知。如果在池 A 中部署通知时使用了任何音频文件，则在池 B 中重新创建通知将需要这些文件。若要在池 B 中重新创建通知，请使用 **New-CsAnnouncement** cmdlet 并将池 B 作为父服务。
    
      - 将面向池 A 中的通知的所有未分配号码范围重定向到池 B 中新部署的通知。为面向池 A 的通知的每个未分配号码范围运行以下 cmdlet：
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    > [!NOTE]  
    > 使用“Exchange UM”作为所选通知服务的未分配号码范围不需要此步骤。
    


7.  通过运行以下 cmdlet 来以灾难恢复 (DR) 模式将池 A 故障转移到池 B：
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  构建池 C，但不要在池 C 中启动任何服务。
    
    请注意，此步骤可与步骤 5 和 6 同时执行。

9.  通过运行以下 cmdlet 来强制驻留在池 A 中的用户移动到池 C：
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    此时，驻留在池 A 中的用户将开始遇到服务故障。此故障将持续，直到步骤 16，那时，将在池 C 中启动服务。

10. 通过运行以下 cmdlet 来强制池 A 的会议目录移动到池 C：
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. 通过运行以下 cmdlet 来强制会议自动助理 (CAA) 联系人对象从池 A 移动到池 C：
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. 将会议内容从池 B 复制到池 C。

13. 通过运行以下 cmdlet 来从池 B 导出用户数据并将用户数据导入到池 C 中：
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. 将备份的呼叫寄存应用程序数据从池 A 还原到池 C 中并将池 A 的呼叫寄存轨道范围分配到池 C。
    
      - 您可以通过 Lync Server 控制面板或 Lync Server 命令行管理程序将池 A 的呼叫寄存轨道范围重新分配到池 C。对于 Lync Server 命令行管理程序，为分配到池 A 的每个呼叫寄存轨道范围运行以下 cmdlet（请注意，Identity 参数指代属于池 A 的呼叫寄存轨道范围）：
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - 如果在池 A 中为呼叫寄存配置了自定义的保持音乐，请在池 C 中还原呼叫寄存自定义保持音乐文件。
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        例如：
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - 最后，通过使用 **Set-CsCpsConfiguration** cmdlet 来在池 C 中重新配置呼叫寄存设置。呼叫寄存应用程序只能为每个池存储一组设置和一个自定义的保持音乐音频文件，并且在发生灾难时不会备份或保留这些设置。

15. 如果 持久聊天的下一个跃点池指向池 A，请进行拓扑更改并发布这些更改，以便下一个跃点服务器指向池 C。
    
      - 在拓扑生成器中，更改持久聊天池以指向池 C 作为其下一个跃点。为此，请右键单击持久聊天池，然后单击“常规”选项卡，然后在“下一个跃点池”中键入池 C 的名称。
    
      - 通过运行以下 cmdlet 来在池 C 中启动服务：
        
            Start-csWindowsService
    
    此时，原来驻留在池 A 中的用户遇到的服务故障终止。

16. 通过运行以下 cmdlet 来从池 B 导出池 A 拥有的 Lync Server 响应组服务工作流以导入到池 C 中：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. 将 Lync Server 响应组服务工作流从池 B 导入到池 C 中。
    
    您有两个选项可将响应组配置从池 B 导入到池 C。您使用哪个选项取决于是否要使用池 B 中的应用程序级别设置覆盖池 C 的应用程序级别设置。
    
      - 如果要覆盖池 C 设置，请运行带有 **ReplaceExistingSettings** 选项的 **Import-CsRgsConfiguration** cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 如果不想覆盖池 C 设置，请使用不带 **ReplaceExistingSettings** 选项的 **Import-CsRgsConfiguration** cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    > [!WARNING]
    > 请记住，如果您不想使用备份池（池 B）的设置覆盖池 C 的应用程序级别设置，则池 B 的应用程序级别设置会丢失，因为响应组应用程序只能为每个池存储一组应用程序级别设置。


18. 通过运行以下 cmdlet 显示已导入到池 C 的响应组来验证响应组配置导入是否成功。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. 在池 C 中验证了导入的配置后，从池 B 移除主池拥有的响应组。这会最大限度地缩短响应组的停机时间。
    
    此步骤使用导出的配置创建新文件，然后从池 B 移除该文件。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. 将从池 A 移动到池 B 的未分配号码范围移动到池 C。
    
      - 在池 C 中重新创建池 B 中从池 A 重新创建的所有通知。如果在部署要移动的通知时使用了任何音频文件，则您将需要使用这些文件来在池 C 中重新创建通知。若要在池 C 中重新创建通知，请使用 **New-CsAnnouncement** cmdlet 并将池 C 作为父服务。
    
      - 将从池 A 重定向到池 B 的所有未分配号码范围重定向到池 C。为需要重定向的每个未分配号码范围运行以下 cmdlet：
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - （可选）从池 B 移除池 C 中重新创建的通知（如果池 B 中不再使用它们）。若要移除通知，请使用 **Remove-CsAnnouncement** cmdlet。
        
        > [!NOTE]  
		> 使用“Exchange UM”作为通知服务的未分配号码范围不需要此步骤。
        


21. 通过运行以下 cmdlet 来在池 B 中清除池 A 的用户数据：
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. 在拓扑生成器中执行以下操作：
    
      - 取消将池 A 和池 B 配对。将池 B 和池 C 配对。然后从拓扑中移除池 A 并发布它。为此：
        
          - 在拓扑生成器中，右键单击池 B，然后单击“编辑属性”。
        
          - 在左窗格中，单击“复原”。
        
          - 在“关联的备份池”下方的框中，选择“池 C”。请注意，“关联的备份池”选择框最初将显示池 A，因为池 B 以前与此池相关联。
        
          - 选择“语音的自动故障转移和故障回复”，然后单击“确定”。
            
            当您查看该池的详细信息时，关联的池现在显示在“复原”下的右窗格中。
        
          - 在控制台树中，右键单击池 A，然后单击“删除”。
        
          - 发布拓扑。

23. 通过从池 C 中的本地计算机上的部署文件夹中运行以下命令，在池 C 中运行引导应用程序来安装备份服务应用程序，然后启动备份服务应用程序：
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. 通过运行以下 cmdlet 来在池 B 中重新启动备份服务应用程序：
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. 如果池 C 是 Standard Edition (SE) 池，并且池 B 具有 CMS，请通过运行以下 cmdlet 来在池 C 中手动安装 CMS 数据库：
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. 调用备份服务将在将 B 和 C 配对在一起之前所生成的旧会议内容从池 B 同步到池 C，并将在启动池 C 之后、将 B 和 C 配对在一起之前所生成的新会议内容从池 C 同步到池 B。为此，请运行以下 cmdlet：
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. 对于与池 A 关联的每个 Survivable Branch Appliance X：
    
      - 通过运行以下 cmdlet 来关闭 SBA X：
        
            Stop-CsWindowsService
    
      - 创建包含驻留在 SBA X 上的用户列表的文件。在步骤 30 中将用户移回 SBA X 时，将需要此列表。为此，请运行以下 cmdlet：
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - 通过运行以下 cmdlet 来强制驻留在 SBA X 上的用户移动到池 C：
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - 通过首先运行以下 cmdlet 来更新这些用户的数据：
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        然后运行以下脚本：
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        > [!NOTE]  
		> 在与池 A 关联的 SBA 上所驻留的用户移动到池 C 之前，这些用户将遇到服务故障。
        


28. 在拓扑生成器中，为以前与池 A 关联的每个 SBA X，执行以下操作：
    
      - 将关联更改为池 C。为此，单击分支站点，展开“Survivable Branch Appliance”或“Survivable Branch Server”节点，然后单击“Survivable Branch Appliance”。然后选择此 Survivable Branch Appliance 将连接到的 **前端池和用户服务池** 作为池 C，然后单击“下一步”。
    
      - 发布拓扑。为此，在控制台树中，右键单击新的“Survivable Branch Appliance”，单击“拓扑”，然后单击“发布”。

29. 对于现在与池 C 关联的每个 SBA X：
    
      - 通过在 Survivable Branch Appliance 上运行以下 cmdlet 来启动 SBA X：
        
            Start-CsWindowsService
    
      - 通过运行以下 cmdlet 将原来驻留在 SBA X 上的用户从池 C 移动到 SBA X：
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

