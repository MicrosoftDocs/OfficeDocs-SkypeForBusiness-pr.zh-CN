---
title: 启用呼叫允许控制
TOCTitle: 启用呼叫允许控制
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398642(v=OCS.15)
ms:contentKeyID: 49313399
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用呼叫允许控制

 

_**上一次修改主题：** 2012-10-19_

配置完呼叫允许控制部署的网络设置后，必须启用 CAC 来使带宽策略生效。

有关详细信息，请参阅 Lync Server 命令行管理程序文档中有关以下 cmdlet 的内容：

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

## 使用命令行管理程序启用呼叫允许控制

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 Set-CsNetworkConfiguration cmdlet 以在网络中启用 CAC。例如，运行：
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    如果要在网络中禁用 CAC，请运行以下命令：
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

## 使用 Lync Server 控制面板启用呼叫允许控制

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”。

3.  单击“全局”导航按钮。

4.  单击列表中的“全局”，然后在“编辑”菜单中选择“显示详细信息”。

5.  在“编辑全局设置”页上，选中“启用呼叫允许控制”复选框。
    
    > [!NOTE]  
    > 如果要在整个部署中禁用呼叫允许控制，请清除此复选框。
    


6.  单击“提交”。

