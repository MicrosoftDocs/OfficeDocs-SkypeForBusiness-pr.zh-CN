---
title: Lync Server 2013：发布对语音路由配置所做的待处理更改
TOCTitle: 发布对语音路由配置所做的待处理更改
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413088(v=OCS.15)
ms:contentKeyID: 49314867
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中发布对语音路由配置所做的待处理更改

 

_**上一次修改主题：** 2012-08-07_

在“语音路由”组的页面中对任何配置设置做出更改后，执行此过程以查看、发布或取消待处理的更改。

> [!IMPORTANT]  
> 确保每次只有一个用户修改语音路由配置设置。<br />
> 必须通过运行“全部提交”命令，同时发布所有待处理的更改。不能选择性地发布待处理的更改。发布待处理的更改前，运行“查看未提交的更改”命令并取消任何不希望发布的配置更改。<br />
> 如果在提交待处理更改前离开“语音路由”组中的页面，所有待处理更改都将丢失。但是，可以将当前配置（包括所有待处理的更改）导出至语音配置文件，然后导入并发布已更新的配置。有关详细信息，请参阅<a href="lync-server-2013-export-a-voice-route-configuration-file.md">在 Lync Server 2013 中导出语音路由配置文件</a>。



## 查看、发布或取消语音路由配置更改

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”。

4.  在“语音路由”组的每个页面中，对设置做出所需的配置更改。

5.  要在不发布更改的情况下查看待处理的更改，请从“提交”菜单中选择“查看未提交的更改”。

6.  如果要取消任何待处理的更改，请执行下列操作之一：
    
      - 从“提交”菜单中选择“取消所有未提交的更改”。
    
      - 导航到包含要取消的待处理更改的“语音路由”页的选项卡，选择包含待处理更改的项目，单击“提交”，然后单击“取消选择的更改”。

7.  查看所有待处理的更改并取消其中不希望发布的更改后，单击“提交”，然后单击“全部提交”。

8.  在“未提交的语音配置设置”对话框（其中显示所有待处理更改的列表）中，单击“确定”。
    
    Lync Server 控制面板提交更改后，将显示消息“已成功发布语音路由配置”。

