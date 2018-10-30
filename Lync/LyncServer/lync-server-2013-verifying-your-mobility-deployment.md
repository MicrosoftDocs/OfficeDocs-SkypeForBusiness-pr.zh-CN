---
title: Lync Server 2013：验证您的移动功能部署
TOCTitle: 验证您的移动功能部署
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690024(v=OCS.15)
ms:contentKeyID: 49313237
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中验证您的移动功能部署

 

_**上一次修改主题：** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

部署 Lync Server Mobility Service 和 Lync Server 自动发现服务后，运行测试事务来验证您的部署是否正常工作。您可以运行 **Test-CsUcwaConference** 来测试两个使用 Lync 2013 Mobile 客户端的用户能否创建和加入会议以及在会议中通信。若要使用此测试事务，您需要两个实际或测试用户及其完整凭据。

可以使用 **Test-CsMcxP2PIM** 测试两个使用 Lync 2010 Mobile 的用户之间发送即时消息的情况。与 **Test-CsUcwaConference** 类似，您需要使用两个实际用户或两个预定义的测试用户。

## 测试 Lync 2013 Mobile 客户端的会议功能

1.  以 CsAdministrator 角色的成员身份登录任何安装了 Lync Server 命令行管理程序和 Ocscore 的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中键入：
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    您可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。例如：
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

## 测试 Lync 2010 Mobile 的个人到个人即时消息 (IM)

1.  以 CsAdministrator 角色的成员身份登录任何安装了 Lync Server 命令行管理程序和 Ocscore 的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中键入：
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    您可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。例如：
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

## 另请参阅

#### 其他资源

[Test-CsMcxP2PIM](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference)

