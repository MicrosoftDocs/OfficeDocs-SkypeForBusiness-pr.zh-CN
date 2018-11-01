---
title: Lync Server 2013：导入语音路由配置文件
TOCTitle: 导入语音路由配置文件
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398301(v=OCS.15)
ms:contentKeyID: 49312784
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中导入语音路由配置文件

 

_**上一次修改主题：** 2012-11-01_

如果要在未发布语音路由配置的情况下保存该配置，请按照本主题中的步骤使用 Lync Server 控制面板配置导出和导入命令来保存和检索语音路由配置快照。导入语音路由配置文件 (.vcfg) 时，如果已更改服务器上的语音路由配置，则会在 Lync Server 控制面板的“语音路由”组的页面中指明有尚未提交的语音路由更改。这些未提交的更改是两种需要调节的配置之间的差异。

如果对此组内的任何页上的设置进行更改后未提交，则会将更改保存到导出语音配置文件 (.vcfg) 中。这样，您就可以在发布更改之前的多个会话期间进行语音路由配置更改。

## 导入语音路由配置

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”。

4.  在“操作”菜单上，单击“导入配置”。

5.  找到要导入的配置文件，然后单击“打开”。

6.  单击“提交”，然后单击“全部提交”。
    
    > [!NOTE]  
    > 任何时候导入语音配置文件，都必须运行“全部提交”命令以发布配置更改。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中发布对语音路由配置所做的待处理更改</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中导出语音路由配置文件](lync-server-2013-export-a-voice-route-configuration-file.md)  
[在 Lync Server 2013 中发布对语音路由配置所做的待处理更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

