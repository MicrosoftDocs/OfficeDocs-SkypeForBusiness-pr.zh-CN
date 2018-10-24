---
title: 手动创建或修改转换规则
TOCTitle: 手动创建或修改转换规则
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398099(v=OCS.15)
ms:contentKeyID: 49311858
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 手动创建或修改转换规则

 

_**上一次修改主题：** 2012-08-06_

如果要通过为匹配模式和转换规则编写正则表达式来定义转换规则，请执行以下步骤。此外，还可以在“构建转换规则”工具中输入一组值，并允许 Lync Server 控制面板生成对应的匹配模式和转换规则。有关详细信息，请参阅[使用“建立转换规则”工具创建或修改转换规则](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)。

## 手动定义转换规则

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  要开始定义转换规则，请执行[在 Lync Server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的前 10 个步骤或执行[在 Lync Server 2013 中配置无媒体旁路功能的中继](lync-server-2013-configure-a-trunk-without-media-bypass.md)中的前 9 个步骤。

4.  在“新建转换规则”或“编辑转换规则”页上的“名称”字段中，键入描述要转换的号码模式的名称。

5.  （可选）在“说明”字段中，键入转换规则的说明，例如，**美国国际长途拨号**。

6.  单击“构建转换规则”部分底部的“编辑”。

7.  在“键入正则表达式”中输入以下内容：
    
      - 在“匹配此模式”中，指定将用于匹配要转换的号码的模式。
    
      - 在“转换规则”中，指定转换号码格式的模式。
    
    例如，如果在“匹配此模式”字段中输入 **^\\+(\\d{9}\\d+)$**，在“转换规则”字段中输入 **011$1**，则该规则会将 +441235551010 转换为 011441235551010。

8.  单击“确定”保存转换规则。

9.  单击“确定”保存 Trunk 配置。

10. 在“Trunk 配置”页上，单击“提交”，然后单击“全部提交”。
    
    > [!NOTE]  
    > 任何时候创建或修改转换规则，都必须运行“全部提交”命令以发布配置更改。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中发布对语音路由配置所做的待处理更改</a>。
    


## 另请参阅

#### 任务

[使用“建立转换规则”工具创建或修改转换规则](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[在 Lync Server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中配置无媒体旁路功能的中继](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[在 Lync Server 2013 中发布对语音路由配置所做的待处理更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### 概念

[全局媒体绕过选项](lync-server-2013-global-media-bypass-options.md)

