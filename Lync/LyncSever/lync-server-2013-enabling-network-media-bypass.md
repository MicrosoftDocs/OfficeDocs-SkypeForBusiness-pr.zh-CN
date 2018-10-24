---
title: 启用网络媒体绕过
TOCTitle: 启用网络媒体绕过
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182552(v=OCS.15)
ms:contentKeyID: 49313646
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用网络媒体绕过

 

_**上一次修改主题：** 2012-11-01_

媒体旁路设置会全局应用到整个 Microsoft Lync Server 2013 部署。媒体旁路功能允许呼叫绕过中介服务器。有关何时使用媒体旁路的详细信息，请参阅规划一节中的[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)。

可以通过 Lync Server 控制面板启用和配置媒体旁路。

## 启用和配置媒体旁路

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“全局”。

4.  在“全局”页上，单击“全局”配置。始终只有一个配置，且始终命名为“全局”。

5.  在“编辑”菜单上，单击“查看详细信息”。

6.  在“编辑全局设置”页上，单击“启用媒体旁路”复选框。

7.  选择下列选项之一：
    
      - **始终绕过** 选择此选项可对所有呼叫尝试媒体旁路。如果启用呼叫允许控制 (CAC)，则此选项将不可用。如果未启用 CAC，则在出现下列情况时选择此选项：
        
          - 不需要带宽控制。
        
          - 不需要精确的配置以确定何时发生旁路。
        
          - 网关与客户端之间有完全连接。
    
      - **使用站点和区域配置** 如果已启用 CAC，则默认情况下选择此选项，且无法更改。如果选择了此选项，则将使用网络配置站点和区域来确定何时可能发生媒体旁路。如果选择此选项，则可以选择为尚未映射的站点启用绕过。仅在具有一个或多个与没有带宽限制的同一区域关联的大型站点（例如大型中央站点），并且具有一些与有带宽限制的同一区域关联的分支站点时，单击“为非映射站点启用旁路”复选框。为未映射的站点启用绕过时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了 CAC，则建议您不要选中“为非映射站点启用旁路”复选框。

8.  单击“提交”保存所做的更改。

## 另请参阅

#### 任务

[禁用网络媒体旁路](lync-server-2013-disabling-network-media-bypass.md)  

#### 概念

[全局媒体绕过选项](lync-server-2013-global-media-bypass-options.md)  

#### 其他资源

[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)

