---
title: Lync Server 2013：导入语音路由测试用例
TOCTitle: 导入语音路由测试用例
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398460(v=OCS.15)
ms:contentKeyID: 49313065
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中导入语音路由测试用例

 

_**上一次修改主题：** 2013-02-21_

测试用例为您提供了在您的组织中测试语音路由的方法：将某些内容定义为要拨打的号码以及要使用的拨号计划和语音策略，之后 Lync Server 2013 便可验证，提供的号码在给定的条件下是否能成功路由到 PSTN 网络。

可使用 Lync Server 控制面板创建的测试用例一般仅保存在用例最初创建和运行的服务器上。但是，这些测试用例可导出为 XML 文件（使用 .vtest 扩展名），然后在其他服务器上导入。这使您可在位于拓扑中的不同点上的不同计算机上运行相同的测试。

## 导入语音路由测试用例

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”。

4.  在“操作”菜单上，单击“导入测试用例”。

5.  找到要导入的测试用例文件 (.vtest)，然后单击“打开”。

6.  单击“提交”，然后单击“全部提交”。
    
    > [!NOTE]  
    > 任何时候导入 .vtest 文件，都必须运行“全部提交”命令才能发布测试用例。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中发布对语音路由配置所做的待处理更改</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中导出语音路由测试用例](lync-server-2013-export-voice-routing-test-cases.md)

