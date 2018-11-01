---
title: Lync Server 2013：（可选）验证电话拨入式会议设置
TOCTitle: （可选）验证电话拨入式会议设置
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412789(v=OCS.15)
ms:contentKeyID: 49313878
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# （可选）在 Lync Server 2013 中验证电话拨入式会议设置

 

_**上一次修改主题：** 2010-11-02_

最终验证电话拨入式会议配置后，您可以搜索具有尚未被任何访问号码使用的电话拨入式会议区域的拨号计划，还可以搜索未指定电话拨入式会议区域的访问号码。此步骤是可选的。

## 查找具有尚未被访问号码使用的电话拨入式会议区域的拨号计划

1.  以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    此 cmdlet 返回具有尚未被访问号码使用的电话拨入式会议区域的所有拨号计划。

## 查找未分配区域的访问号码

1.  以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    此 cmdlet 返回尚未与区域关联的所有电话拨入式会议访问号码。

