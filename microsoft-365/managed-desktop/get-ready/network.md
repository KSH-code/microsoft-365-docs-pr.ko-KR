---
title: Microsoft Managed Desktop의 네트워크 구성
description: Proxies 및 필요한 끝점을 설정하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: cf9b1e1a485000bee7bf672690af5979767fb34b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215572"
---
#  <a name="network-configuration-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 네트워크 구성

<!--Proxy config -->


## <a name="proxy-configuration"></a>프록시 구성

Microsoft Managed Desktop 클라우드 관리 서비스입니다. 서비스에서 도달할 수 Microsoft Managed Desktop 끝점이 있습니다. 이 섹션에서는 Microsoft Managed Desktop 서비스에서 다양한 측면에 대해 허용해야 하는 끝점을 나열합니다. 

고객은 방화벽 또는 프록시를 통해 모든 신뢰할 수 있는 Microsoft 365 네트워크 요청을 직접 전송하고 인증 및 모든 추가 패킷 수준 검사 또는 처리를 우회하여 네트워크를 최적화할 수 있습니다. 이렇게 하면 대기 시간 및 경계 용량 요구 사항이 줄어듭니다. 

또한 클라우드 기반 서비스를 Microsoft Managed Desktop 성능을 최적화하기 위해 이러한 끝점은 고객 클라이언트 브라우저 및 에지 네트워크의 장치를 통해 특별한 처리가 필요합니다. 이러한 장치에는 방화벽, SSL 중단 및 검사, 패킷 검사 장치 및 데이터 손실 방지 시스템이 포함됩니다.

### <a name="proxy-requirement"></a>프록시 요구 사항

프록시 또는 방화벽은 TLS 1.2를 지원해야 합니다. 그렇지 않으면 프로토콜 검색을 사용하지 않도록 설정해야 할 수 있습니다.

### <a name="endpoints-allowed-that-are-necessary-for-microsoft-managed-desktop"></a>끝점 사용이 허용되는 데 필요한 끝점은 Microsoft Managed Desktop

Microsoft Managed Desktop Azure Portal을 사용하여 웹 콘솔을 호스트합니다. 다음 URL은 프록시 및 방화벽의 허용 목록에 있어야 Microsoft Managed Desktop Microsoft 서비스와 통신할 수 있습니다.  

이 Microsoft Managed Desktop URL은 고객 API에서 서비스가 실행되는 모든 서비스에 사용됩니다. 회사 네트워크에서 이 URL에 항상 액세스할 수 있도록 해야 합니다.

Microsoft 서비스  | 허용 목록에 필요한 URL 
--- | ---
Microsoft Managed Desktop | prod-mwaas-services-customerapi.azurewebsites.net
도움말 | \*.support.services.microsoft.com  <br>inprod.support.services.microsoft.com  <br>supportchannels.services.microsoft.com  <br>graph.windows.net  <br>login.windows.net  <br>prod-mwaas-services-customerapi.azurewebsites.net  <br>concierge.live.com
빠른 지원 | remoteassistance.support.services.microsoft.com <br>relay.support.services.microsoft.com <br>channelwebsdks.azureedge.net  <br>web.vortex.data.microsoft.com  <br>gateway.channelservices.microsoft.com <br>\*.lync.com
Microsoft 지원 및 복구 도우미 | \*.apibasic.diagnostics.office.com  <br>\*.api.diagnostics.office.com
 

### <a name="endpoints-allowed-used-by-other-microsoft-products"></a>다른 Microsoft 제품에서 사용할 수 있는 끝점

허용 목록에 여러 Microsoft 제품의 URL이 있으므로 Microsoft Managed Desktop Microsoft 서비스와 통신할 수 있습니다. 링크를 사용하여 각 제품에 대한 전체 목록을 볼 수 있습니다. 

Microsoft 서비스 | 설명서
--- | ---
Windows 10 Enterprise 업데이트 Windows 포함 | [버전 Windows 10 1803에 대한 연결 끝점 관리](/windows/privacy/manage-windows-1803-endpoints)<br><br>[연결에 대한 연결 끝점 Windows 10, 버전 1809](/windows/privacy/manage-windows-1809-endpoints)<br><br>[1903 버전 Windows 10 연결 끝점 관리](/windows/privacy/manage-windows-1903-endpoints)<br><br>[버전 2004의 Windows 10 끝점 관리](/windows/privacy/manage-windows-2004-endpoints)
배달 최적화 | [업데이트 업데이트에 Windows 10 최적화 구성](/windows/deployment/update/waas-delivery-optimization)
Microsoft 365 | [Microsoft 365 URL 및 IP 주소 범위](../../enterprise/urls-and-ip-address-ranges.md)
Azure Active Directory | [하이브리드 ID에는 포트 및 프로토콜이 필요하고](/azure/active-directory/hybrid/reference-connect-ports) [Active Directory 및 Active Directory 도메인 서비스 포트 요구 사항](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd772723(v=ws.10)) 
Microsoft Intune | [Intune 네트워크 구성 요구 사항](/intune/network-bandwidth-use)<br>[네트워크 끝점에 대한 Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)
엔드포인트용 Microsoft Defender | [끝점용 Microsoft Defender 요구 사항](/windows/security/threat-protection/windows-defender-atp/configure-proxy-internet-windows-defender-advanced-threat-protection#enable-access-to-windows-defender-atp-service-urls-in-the-proxy-server)
Windows Autopilot | [Windows Autopilot 네트워킹 요구 사항](/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)

Microsoft 서비스  | 허용 목록에 필요한 URL | 설명서 원본
--- | --- | ---
Windows 비즈니스용 업데이트(WUfB) | update.microsoft.com<br>\*.update.microsoft.com<br>download.windowsupdate.com<br>\*.download.windowsupdate.com<br>download.microsoft.com<br>\*.download.microsoft.com<br>windowsupdate.com<br>\*.windowsupdate.com<br>ntservicepack.microsoft.com<br>wustat.windows.com<br>login.live.com <br>mp.microsoft.com<br>\*.mp.microsoft.com | [Windows 비즈니스 방화벽 및 프록시 요구 사항 업데이트](https://support.microsoft.com/help/3084568/can-t-download-updates-from-windows-update-from-behind-a-firewall-or-p)
배달 최적화 | \*.do.dsp.mp.microsoft.com<br>\*.dl.delivery.mp.microsoft.com <br>\*.emdl.ws.microsoft.com<br>\*.download.windowsupdate.com <br>\*.windowsupdate.com   | [Windows 프록시 요구 사항 업데이트](https://support.microsoft.com/help/3175743/proxy-requirements-for-windows-update)
비즈니스용 Microsoft Store | login.live.com <br>account.live.com <br>clientconfig.passport.net <br>wustat.windows.com <br>\*.windowsupdate.com <br>\*.wns.windows.com <br>\*.hotmail.com <br>\*.outlook.com <br>\*.microsoft.com <br>\*.msftncsi.com/ncsi.txt   | [Microsoft Store 허용 목록](https://support.microsoft.com/help/2778122/using-authenticated-proxy-servers-together-with-windows-8)
Microsoft 365 | \*.office365.com<br>\*.office.com<br>\*.office.net<br>\*.live.com<br>\*.portal.cloudappsecurity.com<br>\*.portal.cloudappsecurity.com<br>\*.us.portal.cloudappsecurity.com<br>\*.eu.portal.cloudappsecurity.com<br>\*.us2.portal.cloudappsecurity.com<br><tenant>.onmicrosoft.com<br>account.office.net<br>agent.office.net<br>apc.delve.office.com<br>aus.delve.office.com<br>can.delve.office.com<br>delve.office.com<br>eur.delve.office.com<br>gbr.delve.office.com<br>home.office.com<br>ind.delve.office.com<br>jpn.delve.office.com<br>kor.delve.office.com<br>lam.delve.office.com<br>nam.delve.office.com<br>admin.microsoft.com<br>outlook.office365.com<br>suite.office.net<br>webshell.suite.office.com<br>www.office.com<br>\*.aria.microsoft.com<br>browser.pipe.aria.microsoft.com<br>mobile.pipe.aria.microsoft.com<br>portal.microsoftonline.com<br>clientlog.admin.microsoft.com<br>nexus.officeapps.live.com<br>nexusrules.officeapps.live.com<br>amp.azure.net<br>\*.o365weve.com<br>auth.gfx.ms<br>appsforoffice.microsoft.com<br>assets.onestore.ms<br>az826701.vo.msecnd.net<br>c.microsoft.com<br>c1.microsoft.com<br>client.hip.live.com<br>contentstorage.osi.office.net<br>dgps.support.microsoft.com<br>docs.microsoft.com<br>groupsapi-<br>rod.outlookgroups.ms<br>groupsapi2-prod.outlookgroups.ms<br>groupsapi3-prod.outlookgroups.ms<br>groupsapi4-prod.outlookgroups.ms<br>msdn.microsoft.com<br>platform.linkedin.com<br>products.office.com<br>prod.msocdn.com<br>r1.res.office365.com<br>r4.res.office365.com<br>res.delve.office.com<br>shellprod.msocdn.com<br>support.content.office.net<br>support.microsoft.com<br>support.office.com<br>technet.microsoft.com<br>templates.office.com<br>video.osi.office.net<br>videocontent.osi.office.net<br>videoplayercdn.osi.office.net<br>\*.manage.office.com<br>\*.protection.office.com<br>manage.office.com<br>Protection.office.com<br>diagnostics.office.com | [Microsoft 365 URL 및 IP 주소 범위](../../enterprise/urls-and-ip-address-ranges.md)
Azure Active Directory | api.login.microsoftonline.com<br>api.passwordreset.microsoftonline.com<br>autologon.microsoftazuread-sso.com<br>becws.microsoftonline.com<br>clientconfig.microsoftonline-p.net <br>companymanager.microsoftonline.com <br>device.login.microsoftonline.com <br>hip.microsoftonline-p.net <br>hipservice.microsoftonline.com <br>login.microsoft.com<br>login.microsoftonline.com <br>logincert.microsoftonline.com <br>loginex.microsoftonline.com<br>login-us.microsoftonline.com <br>login.microsoftonline-p.com <br>login.windows.net <br>nexus.microsoftonline-p.com <br>passwordreset.microsoftonline.com <br>provisioningapi.microsoftonline.com<br>stamp2.login.microsoftonline.com<br>\*.msappproxy.net<br>ccs.login.microsoftonline.com<br>ccs-sdf.login.microsoftonline.com<br>accounts.accesscontrol.windows.net<br>secure.aadcdn.microsoftonline-p.com<br>\*.phonefactor.net<br>account.activedirectory.windowsazure.com<br>secure.aadcdn.microsoftonline-p.com<br>graph.microsoft.com | [하이브리드 ID에는 포트 및 프로토콜이 필요하고](/azure/active-directory/connect/active-directory-aadconnect-ports) [Active Directory 및 Active Directory 도메인 서비스 포트 요구 사항](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd772723(v=ws.10)) 
Microsoft Intune | login.microsoftonline.com<br>portal.manage.microsoft.com<br>m.manage.microsoft.com<br>sts.manage.microsoft.com<br>Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com<br>fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com<br>fef.msua01.manage.microsoft.com<br>fef.msua02.manage.microsoft.com<br>fef.msua04.manage.microsoft.com<br>fef.msua05.manage.microsoft.com<br>fef.msua06.manage.microsoft.com<br>fef.msua07.manage.microsoft.com<br>fef.msub01.manage.microsoft.com<br>fef.msub02.manage.microsoft.com<br>fef.msub03.manage.microsoft.com<br>fef.msub05.manage.microsoft.com<br>fef.msuc01.manage.microsoft.com<br>fef.msuc02.manage.microsoft.com<br>fef.msuc03.manage.microsoft.com<br>fef.msuc05.manage.microsoft.com |  [Intune 네트워크 구성 요구 사항](/intune/network-bandwidth-use)
비즈니스용 OneDrive | onedrive.com <br> <br>\*.onedrive.com <br>onedrive.live.com <br>login.live.com <br>spoprod-a.akamaihd.net <br>\*.mesh.com <br>p.sfx.ms <br>\*.microsoft.com <br>fabric.io <br>\*.crashlytics.com <br>vortex.data.microsoft.com <br>https://posarprodcssservice.accesscontrol.windows.net <br>redemptionservices.accesscontrol.windows.net  <br>token.cp.microsoft.com/ <br>tokensit.cp.microsoft-tst.com/ <br>\*.office.com <br>\*.officeapps.live.com <br>\*.aria.microsoft.com <br>\*.mobileengagement.windows.net <br>\*.branch.io <br>\*.adjust.com <br>\*.servicebus.windows.net <br>vas.samsungapps.com <br>odc.officeapps.live.com <br>login.windows.net <br>login.microsoftonline.com <br>\*.files.1drv.com <br>\*.onedrive.live.com <br>\*.\*. onedrive.live.com <br>storage.live.com <br>\*.storage.live.com <br>\*.\*. storage.live.com <br>\*.groups.office.live.com <br>\*.groups.photos.live.com <br>\*.groups.skydrive.live.com <br>favorites.live.com <br>oauth.live.com <br>photos.live.com <br>skydrive.live.com <br>api.live.net <br>apis.live.net <br>docs.live.net <br>\*.docs.live.net <br>policies.live.net <br>\*.policies.live.net <br>settings.live.net <br>\*.settings.live.net <br>skyapi.live.net <br>snapi.live.net <br>\*.livefilestore.com <br>\*.\*. livefilestore.com <br>storage.msn.com <br>\*.storage.msn.com <br>\*.*.storage.msn.com | [필수 URL 및 포트를 OneDrive](/onedrive/required-urls-and-ports)
Microsoft Defender Advanced Threat Protection (ATP) | \ *.oms.opinsights.azure.com <br>\*.blob.core.windows.net <br>\*.azure-automation.net <br>\*.ods.opinsights.azure.com <br>winatp-gw-cus.microsoft.com <br>winatp-gw-eus.microsoft.com <br>winatp-gw-neu.microsoft.com <br>winatp-gw-weu.microsoft.com <br>winatp-gw-uks.microsoft.com <br>winatp-gw-ukw.microsoft.com <br>winatp-gw-aus.microsoft.com <br>winatp-gw-aue.microsoft.com | [Windows Defender ATP 끝점](/windows/security/threat-protection/windows-defender-atp/configure-server-endpoints-windows-defender-advanced-threat-protection)
도움말 | \*.support.services.microsoft.com  <br>inprod.support.services.microsoft.com  <br>supportchannels.services.microsoft.com  <br>graph.windows.net  <br>login.windows.net  <br>prod-mwaas-services-customerapi.azurewebsites.net  <br>concierge.live.com <br>rave.office.net | 
빠른 지원 | remoteassistance.support.services.microsoft.com <br>relay.support.services.microsoft.com <br>channelwebsdks.azureedge.net  <br>web.vortex.data.microsoft.com  <br>gateway.channelservices.microsoft.com <br>\*.lync.com | 
SharePoint Online  | \*.sharepoint.com <br>\ *.svc.ms  <br>\<tenant\>.sharepoint.com  <br>\<tenant\>-my.sharepoint.com  <br>\<tenant\>-files.sharepoint.com  <br>\<tenant\>-myfiles.sharepoint.com <br>\*.sharepointonline.com  <br>cdn.sharepointonline.com  <br>static.sharepointonline.com  <br>spoprod-a.akamaihd.net  <br>publiccdn.sharepointonline.com  <br>privatecdn.sharepointonline.com | [Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)
비즈니스용 OneDrive | admin.onedrive.com  <br>officeclient.microsoft.com <br>odc.officeapps.live.com  <br>skydrive.wns.windows.com <br>g.live.com <br>oneclient.sfx.ms <br>\*.log.optimizely.com  <br>click.email.microsoftonline.com  <br>ssw.live.com  <br>storage.live.com |  [Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)
Microsoft Teams | \*.teams.skype.com  <br>\*.teams.microsoft.com  <br>teams.microsoft.com <br>\*.asm.skype.com <br>\ *.cc.skype.com  <br>\*.conv.skype.com  <br>\*.dc.trouter.io  <br>\*.msg.skype.com  <br>prod.registrar.skype.com  <br>prod.tpc.skype.com <br>\*.broker.skype.com <br>\*.config.skype.com  <br>\*.pipe.skype.com  <br>\*.pipe.aria.microsoft.com  <br>config.edge.skype.com  <br>pipe.skype.com  <br>s-0001.s-msedge.net  <br>s-0004.s-msedge.net  <br>scsinstrument-ss-us.trafficmanager.net  <br>scsquery-ss- <br>us.trafficmanager.net  <br>scsquery-ss-eu.trafficmanager.net  <br>scsquery-ss-asia.trafficmanager.net <br>\*.msedge.net <br>compass-ssl.microsoft.com  <br>feedback.skype.com <br>\*.secure.skypeassets.com  <br>mlccdnprod.azureedge.net  <br>videoplayercdn.osi.office.net <br>\*.mstea.ms | [Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)
Power BI | maxcdn.bootstrapcdn.com <br>ajax.aspnetcdn.com <br>netdna.bootstrapcdn.com <br>cdn.optimizely.com <br>google-analytics.com <br>\*.mktoresp.com <br>\*.aadcdn.microsoftonline-p.com <br>\*.msecnd.com <br>\*.localytics.com <br>ajax.aspnetcdn.com <br>\*.localytics.com <br>\*.virtualearth.net <br>platform.bing.com <br>powerbi.microsoft.com <br>c.microsoft.com <br>app.powerbi.com <br>\*.powerbi.com <br>dc.services.visualstudio.com <br>support.powerbi.com <br>powerbi.uservoice.com <br>go.microsoft.com <br>c1.microsoft.com <br>\*.azureedge.net |[Power BI & 익스프레스 경로](/power-bi/service-admin-power-bi-expressroute) 
OneNote | apis.live.net <br>www.onedrive.com <br>login.microsoft.com  <br>www.onenote.com <br>\*.onenote.com <br>\*.msecnd.net <br>\*.microsoft.com <br>\*.office.net <br>cdn.onenote.net <br>site-cdn.onenote.net <br>cdn.optimizely.com <br>Ajax.aspnetcdn.com <br>officeapps.live.com <br>\\*.onenote.com <br>\*cdn.onenote.net <br>contentstorage.osi.office.net <br>\*onenote.officeapps.live.com <br>\*.microsoft.com | [Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>준비 단계 Microsoft Managed Desktop

1. [Microsoft Managed Desktop의 필수 구성 요소](prerequisites.md)를 감토하세요.
2. [준비 상태 평가 도구](readiness-assessment-tool.md)를 실행하세요.
1. [회사 포털](../get-started/company-portal.md)을 구입하세요.
1. [게스트 계정에 대한 필수 구성 요소](guest-accounts.md)를 검토합니다.
1. 네트워크 구성을 확인합니다(이 문서).
1. [인증서 및 네트워크 프로필을 준비](certs-wifi-lan.md)합니다.
1. [데이터에 대한 사용자 액세스를 준비](authentication.md)합니다.
1. [앱을 준비](apps.md)합니다.
1. [매핑된 드라이브를 준비](mapped-drives.md)합니다.
1. [인쇄 리소스를 준비](printing.md)합니다.
1. [장치 이름](address-device-names.md)을 기입합니다.
