---
title: 在 Lync Server 2013 中查看设备的软件更新
TOCTitle: 在 Lync Server 2013 中查看设备的软件更新
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182592(v=OCS.15)
ms:contentKeyID: 49314331
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中查看设备的软件更新

 

_**上一次修改主题：** 2016-12-08_

通过 Lync Server 2013，可使用设备更新 Web 服务查看和管理组织设备的软件更新。Microsoft 支持网站 ([http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0x804)) 上的 .cab (CAB) 文件中提供了这些更新。下载 .cab 文件后，运行 **Import-CSdeviceUpdate** cmdlet 可从该 .cab 文件中导入设备更新规则。有关 **Import-CSdeviceUpdate** cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档中的 [Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate)。

> [!TIP]
> 将新的更新部署到组织之前，请验证其在测试设备上是否正常工作。


## 查看 UC 设备的软件更新

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从 Microsoft 支持网站 ([http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0x804)) 上将 .cab 文件下载到 Lync Server 2013 计算机上的某个位置（例如，C:\\Updates\\UCUpdates.cab）。

3.  通过运行以下 cmdlet 之一从 C:\\Updates\\UCUpdates.cab 文件导入设备更新规则：
    
      - 如果 .cab 文件位于运行要更新的服务 (service:Redmond-websvc-2) 的计算机上，请运行以下 cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - 如果 .cab 文件不在运行要更新的服务 (service:Redmond-websvc-3) 的计算机上，请运行以下 cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

5.  在左侧导航栏中，单击“客户端”，然后单击“设备更新”。

6.  在“设备更新”页上，单击列表中的更新，然后执行下列操作之一：
    
      - **取消待处理的更新。** 要阻止将所选更新部署到组织的设备，请单击“操作”菜单，然后单击“取消待处理的更新”。
    
      - **批准更新。** 要允许将所选更新部署到组织的设备，请单击“操作”菜单，然后单击“批准”。
    
      - **还原更新。** 要允许将先前批准的更新部署到组织的设备，请单击“操作”菜单，然后单击“还原”。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)

