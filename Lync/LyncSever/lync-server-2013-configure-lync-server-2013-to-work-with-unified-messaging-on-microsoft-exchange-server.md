---
title: Lync Server 2013：配置 Lync Server 2013 以使用 Microsoft Exchange Server 统一消息
TOCTitle: 配置 Lync Server 2013 以使用 Microsoft Exchange Server 统一消息
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398193(v=OCS.15)
ms:contentKeyID: 49312029
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Lync Server 2013 以使用 Microsoft Exchange Server 统一消息

 

_**上一次修改主题：** 2016-12-08_

此步骤需要使用 Exchange UM 集成实用程序 (OcsUmUtil.exe)。此工具位于 Lync Server 2013 服务器上的 ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support 文件夹中。

## 运行 Exchange UM 集成实用程序

必须通过具有以下特征的用户帐户运行 Exchange UM 集成实用程序：

  - RTCUniversalServerAdmins 和 RtcUniversalUserAdmins 组中的成员身份（包含读取 Exchange Server 统一消息设置的权限）。

  - 域中可在指定的组织单位 (OU) 容器中创建联系对象的用户权限。

运行 Exchange UM 集成实用程序时，该实用程序将执行以下任务：

  - 为要由 企业语音用户使用的每个自动助理和订阅者访问号码创建联系对象。

  - 确保每个 企业语音拨号计划的名称与其对应的统一消息 (UM) 拨号计划的电话上下文匹配。仅当 UM 拨号计划在 *低于* Exchange 2010 Service Pack 1 (SP1) 的 Exchange 版本上运行时，才需要此匹配。

> [!IMPORTANT]  
> 运行 Exchange UM 集成实用程序之前，请确保已执行以下操作：
> <ul><li><p>创建一个或多个 Exchange UM 拨号计划，如 Exchange 产品文档中所述。</p>
> <p>对于 Microsoft Exchange Server 2010，请参阅“创建 UM 拨号计划”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>。</p>
> <p>对于 Microsoft Exchange Server 2007 Service Pack 1 (SP1)，请参阅“如何创建统一消息 SIP URI 拨号计划”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>。</p></li>
> <li><p>创建一个或多个相应的 Lync Server 拨号计划，如<a href="lync-server-2013-create-a-dial-plan.md">在 Lync Server 2013 中创建拨号计划</a>中所述。</p></li>
> <ul><li>如果使用的 Exchange 版本低于 Microsoft Exchange Server 2010 SP1，则必须在 Lync Server 2013 拨号计划的“简单名称”字段中输入相应 Exchange 统一消息 (UM) SIP 拨号计划的完全限定的域名 (FQDN)。如果使用的是 Microsoft Exchange Server 2010 SP1 或最新的 Service Pack，则不需要此拨号计划名称匹配。</li></ul>
> <li><p>创建自动助理，并确保订阅者访问号码和自动助理号码的格式为 E.164。</p></li></ul>


## 运行 Exchange UM 集成实用程序

1.  在 前端服务器上，打开命令提示符，键入 **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support** ，然后按 Enter。

2.  键入 **OcsUmUtil.exe**，然后按 Enter。

3.  单击“加载数据”以查找所有受信任的 Exchange 林。

4.  在“SIP 拨号计划”列表中，选择要为其创建联系对象的 UM SIP 拨号计划，然后单击“添加”。

5.  在“联系人”框中接受默认的组织单位，或单击“浏览”，从而启动“OU 选取器”。在“OU 选取器”框中，可以选择 OU 并单击“确定”，也可以单击“新建 OU”，在域中的根或任何其他 OU 下创建新的组织单位（例如“OU=RTC Special Accounts,DC=fourthcoffee,DC=com”），然后单击“确定”。
    
    > [!NOTE]  
    > 已选择或创建的 OU 的可分辨名称 (DN) 此时将显示在“组织单位”框中。
    


6.  在“名称”框中接受默认的拨号计划名称，或为要创建的联系对象键入新的显示名称。
    
    > [!NOTE]  
    > 例如，如果要创建订阅者访问联系对象，则可能只需简单地将其命名为“订阅者访问”。
    


7.  在“SIP 地址”框中，接受默认 SIP 地址或键入新的 SIP 地址。
    
    > [!NOTE]  
    > 如果键入新的 SIP 地址，该地址必须以 <strong>SIP:</strong> 开头（即“SIP:”，包括冒号）。
    


8.  在“服务器或池”列表中，选择要在其中启用该联系对象的 Standard Edition 服务器或前端池。
    
    > [!NOTE]  
    > 选择的池最好是部署启用了企业语音和 Exchange UM 的用户的同一个池。
    


9.  在“电话号码”列表中，选择“输入电话号码”或“使用 Exchange UM 中的引导号码”，然后输入电话号码。

10. 在“联系人类型”列表中，选择要创建的联系人类型，然后单击“确定”。

11. 对于要创建的其他联系对象，重复步骤 1 到 10。
    
    > [!NOTE]  
    > 为每个自动助理应至少创建一个联系人。如果希望允许外部访问，还需要一个订阅者访问联系人并指定外线直拨分机 (DID) 号码。
    


要验证是否已创建联系对象，请打开“Active Directory 用户和计算机”，并选择在其中创建对象的 OU。联系对象应在详细信息窗格中出现。

