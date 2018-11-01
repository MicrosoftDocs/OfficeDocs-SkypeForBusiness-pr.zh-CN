---
title: 为用户配置电话
TOCTitle: 为用户配置电话
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520988(v=OCS.15)
ms:contentKeyID: 49312700
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为用户配置电话

 

_**上一次修改主题：** 2012-11-01_

电话设置是可在 Lync Server 控制面板中为用户配置的用户帐户的各项设置中的一部分（前提是单个用户已启用 Lync Server 2013 且组织支持电话技术）。

Lync Server 用户电话选项包括以下几项：

  - **禁用音频/视频** 用户无法发出音频和视频呼叫。

  - **仅限 PC 到 PC** 用户只能发出 PC 到 PC 音频或视频呼叫。

  - **企业语音** 用户可以使用 Lync Server 2013 基础结构路由所有传入和传出呼叫。用户还可以发出 PC 到 PC 呼叫。

  - **远程呼叫控制** 用户可以使用 Lync Server 2013 控制桌面电话，还可以发出 PC 到 PC 呼叫。

有关为组织配置电话的详细信息，请参阅部署文档中的[为用户配置电话](lync-server-2013-configure-telephony-for-a-user.md)和[在 Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)。

## 为特定用户帐户配置电话

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  在“搜索用户”框中，键入所需用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。

5.  在表中，单击要修改的用户帐户。

6.  在“编辑”菜单上，单击“修改”。

7.  在“电话”中，执行下列操作：
    
      - 要为用户禁用音频和视频呼叫，请单击“禁用音频/视频”。
    
      - 要为用户启用 PC 到 PC 音频通信，但不启用远程呼叫控制或企业语音，请单击“仅限 PC 到 PC”。为用户用于进行 PC 到 PC 音频通信的电话指定“线路 URI”值。
    
      - 要使用符合服务策略类的 Lync Server 2010 基础结构路由用户的电话呼叫（包括 PC 到 PC 音频通信），请单击“企业语音”。在“线路 URI”中，指定用于企业语音的电话号码。在“拨号计划策略”和“语音策略”中，为用户指定相应的策略。要指定用于将用户拨打的电话号码转换为 E.164 格式的规范化规则，请在“位置策略”中选择相应的位置配置文件。
    
      - 要启用远程呼叫控制，使用户可以从 Lync Server 2013 控制其桌面电话线路以发出 PC 到 PC 呼叫和 PC 到电话呼叫，请单击“远程呼叫控制”。在“线路 URI”中，指定用于远程呼叫控制的电话号码。要进行呼叫路由，用户必须具有桌面电话和专用交换机 (PBX) 连接。

## 另请参阅

#### 其他资源

[修改用户帐户属性](lync-server-2013-modifying-user-account-properties.md)

