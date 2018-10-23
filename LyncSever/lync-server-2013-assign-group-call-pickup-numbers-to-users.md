---
title: 向用户分配组内呼叫应答号码
TOCTitle: 向用户分配组内呼叫应答号码
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945647(v=OCS.15)
ms:contentKeyID: 52061124
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 向用户分配组内呼叫应答号码

 

_**上一次修改主题：** 2013-01-30_

将组内呼叫应答组号码添加到呼叫寄存轨道表后，可以向用户分配这些组。可使用辅助扩展功能激活 (SEFAUtil) 资源工具包工具向用户分配呼叫应答组。

> [!NOTE]  
> 在混合部署中，不要向在线驻留的用户分配组内呼叫应答组。在线驻留的用户无法参与组内呼叫应答。也就是说，他们的呼叫无法由其他用户应答，他们也无法应答对其他用户的呼叫。



## 向用户分配组内呼叫应答组

1.  使用管理员权限登录安装了 SEFAUtil 工具的计算机。

2.  在该命令行处，运行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## 另请参阅

#### 任务

[为用户启用组内呼叫应答](lync-server-2013-enable-group-call-pickup-for-users.md)  
[为用户禁用组内呼叫应答](lync-server-2013-disable-group-call-pickup-for-users.md)

