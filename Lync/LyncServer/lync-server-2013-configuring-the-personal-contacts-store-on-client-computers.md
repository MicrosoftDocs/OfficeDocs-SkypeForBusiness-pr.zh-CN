---
title: 在客户端计算机上配置个人联系人存储
TOCTitle: 在客户端计算机上配置个人联系人存储
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49888658
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在客户端计算机上配置个人联系人存储

 

_**上一次修改主题：** 2016-12-08_

如果您正在集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013，则建议您在所有运行 Microsoft Lync 2010 的客户端计算机上配置个人联系人存储库。特别是应该配置 Lync 以将 Exchange 用作个人联系人存储库，同时确保用户无法覆盖该决策。这可以通过在每个客户端计算机上创建和配置注册表值来完成。

注意，在运行 Lync 2013 的计算机上没有此要求。

要在单个计算机上配置此值，请完成下列过程：

1.  在客户端计算机上，单击“开始”，然后单击“运行”。

2.  在“运行” 对话框中，键入 regedit，然后按 Enter。

3.  在注册表编辑器中，依次展开“HKEY\_LOCAL\_MACHINE”、“Software”、“Policies”、“Microsoft”和“Communicator”。

4.  右键单击“Communicator”，指向“新建”，然后单击“DWORD（32 位）值”。

5.  创建新值后，键入 **PersonalContactStoreOverride**，然后按 Enter 来重命名该值。

6.  验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。

如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。有关详细信息，请参阅“组策略”文档，网址为：[http://go.microsoft.com/fwlink/?linkid=268543\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268543%26clcid=0x804)。

