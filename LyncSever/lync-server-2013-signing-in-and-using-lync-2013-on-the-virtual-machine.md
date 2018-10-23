---
title: Lync Server 2013：登录虚拟机并使用 Lync 2013
TOCTitle: 登录虚拟机并使用 Lync 2013
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204948(v=OCS.15)
ms:contentKeyID: 49313008
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 登录虚拟机并使用 Lync 2013

 

_**上一次修改主题：** 2012-10-03_

启用 VDI 插件之后，当用户登录 Lync 2013 时将出现下列步骤。

1.  用户在虚拟机上运行的 Lync 2013 客户端中键入其凭据。

2.  当 Lync 检测到 VDI 插件的可用性后，Lync 会提示用户重新输入其凭据。在此对话框中，建议用户选中“保存我的密码”复选框以在后续登录期间不需要输入凭据。

3.  Lync 开始与 VDI 插件配对。配对完成后，客户端将在 Lync 状态栏中显示两个图标。左下方的图标指示没有可用的音频设备，而右下角的闪烁图标指示 VDI 配对正在进行中，如下所示：
    
    ![显示配对成功的 Lync VDI 图标](images/JJ204713.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "显示配对成功的 Lync VDI 图标")  

4.  VDI 配对成功后，这两个图标将更改为分别指示将用于呼叫的音频设备和 VDI 配对成功：
    
    ![显示成功的 Lync VDI 配对图标](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "显示成功的 Lync VDI 配对图标")  

5.  在 Lync 与 VDI 插件配对后，用户可在连接到本地计算机的 Lync 兼容设备中查看其状态。用户现在可以正常发出和应答呼叫。

