---
title: Office 365 IP 주소 및 URL 웹 서비스에 포함되지 않은 추가 엔드포인트
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/19/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: '요약: 새로운 엔드포인트 웹 서비스에는 특정 시나리오에 맞는 적은 수의 엔드포인트가 포함되어 있지 않습니다.'
hideEdit: true
ms.openlocfilehash: 1313bc4dd10afe07f82fdc2c1b5df9d9d9bd0f2a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150825"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Office 365 IP 주소 및 URL 웹 서비스에 포함되지 않은 추가 엔드포인트

일부 네트워크 끝점은 이전에 게시되었으며 [Office 365 IP 주소 및 URL 웹 서비스](microsoft-365-ip-web-service.md)에 포함되어 있지 않습니다. 웹 서비스 범위는 엔터프라이즈 경계 네트워크에서 Office 365 사용자의 연결에 필요한 네트워크 끝점입니다. 현재는 다음 내용이 포함되어 있지 않습니다.

1. Microsoft 데이터 센터에서 고객 네트워크(인바운드 하이브리드 서버 네트워크 트래픽)로 연결 시 필요할 수 있는 네트워크 연결.
2. 고객 네트워크의 서버에서 엔터프라이즈 경계(아웃 바운드 서버 네트워크 트래픽) 전체에 네트워크 연결.
3. 한 사용자의 네트워크 연결 요구 사항에 대한 일반적이지 않은 시나리오.
4. DNS 확인 연결 요구 사항(아래 나열되지 않음).
5. Internet Explorer 또는 Microsoft Edge의 신뢰할 수 있는 사이트.

DNS 외에도 설명된 특정 시나리오가 필요하지 않는 경우 대부분의 고객에게 이러한 사항은 모두 선택 사항입니다.

<br>

****

|행|용도|대상|유형|
|---|---|---|---|
|1|PST 및 파일 수집를 위한 [서비스 가져오기](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6)|추가 요구 사항은 [서비스 가져오기](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6)를 참조하세요.|일반적이지 않은 아웃바운드 시나리오|
|2|[Office 365용 Microsoft 고객 지원 및 복구 도우미](https://diagnostics.office.com/#/)|<https://autodiscover.outlook.com> <br> <https://officecdn.microsoft.com> <br> <https://api.diagnostics.office.com> <br> <https://apibasic.diagnostics.office.com> <br> <https://autodiscover-s.outlook.com> <br> <https://cloudcheckenabler.azurewebsites.net> <br> <https://login.live.com> <br> <https://login.microsoftonline.com> <br> <https://login.windows.net> <br> <https://o365diagtelemetry.trafficmanager.net> <br> <https://odc.officeapps.live.com> <br> <https://offcatedge.azureedge.net> <br> <https://officeapps.live.com> <br> <https://outlook.office365.com> <br> <https://outlookdiagnostics.azureedge.net>|아웃바운드 서버 트래픽|
|3 |Azure AD Connect(w/SSO 옵션)-WinRM 및 원격 PowerShell|고객 STS 환경(AD FS 서버 및 AD FS 프록시) \| TCP 포트 80 및 443|인바운드 서버 트래픽|
|4 |AD FS 프록시 서버와 같은 STS(페더레이션 고객만 해당)|고객 STS(예: AD FS 프록시) \| 포트 TCP 443 또는 TCP 49443 w/ClientTLS|인바운드 서버 트래픽|
|5|[Exchange Online의 통합 메시징/SBC 통합](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers)|-프레미스 세션 경계 컨트롤러와 \* .um.outlook.com|아웃바운드 서버 전용 트래픽|
|6 |사서함 마이그레이션. 사서함 마이그레이션이 Exchange 하이브리드에서 하이브리드로 Office 365 Office 365 EWS(Exchange 웹 서비스)/MRS(사서함 복제 서비스) 서버에 연결됩니다. [](/exchange/exchange-deployment-assistant) 특정 원본 IP 범위의 인바운드 연결을 제한하기 위해 Exchange Online 서버에서 사용하는 NAT IP 주소가 필요한 경우 "Exchange Online" 서비스 영역의 Office 365 [URL & IP](urls-and-ip-address-ranges.md) 범위에 나열됩니다. <p> 특정 원본 IP 범위에서 TCP 443 연결을 제한하기 전에 MRS 프록시가 별도의 FQDN 및 공용 IP 주소로 확인되도록 하여 OWA와 같은 게시된 EWS 끝점에 대한 액세스가 영향을 갖지 않도록 해야 합니다.|고객 온-프레미스 EWS/MRS 프록시 <br> TCP 포트 443|인바운드 서버 트래픽|
|7 |약속 있음/없음 공유와 같은 [Exchange 하이브리드](/exchange/exchange-deployment-assistant) 공존 기능|고객 온-프레미스 Exchange 서버|인바운드 서버 트래픽|
|8 |[Exchange 하이브리드](/exchange/exchange-deployment-assistant) 프록시 인증|고객 온-프레미스 STS|인바운드 서버 트래픽|
|9 |[Exchange 하이브리드 구성 마법사](/exchange/hybrid-configuration-wizard)를 사용하여 [Exchange 하이브리드](/exchange/exchange-deployment-assistant)를 구성하는 데 사용됩니다. <p> 참고 :이 끝점은 Exchange 하이브리드 구성에만 필요합니다|TCP 포트 80 및 443의 domains.live.com. Exchange 2010 SP3 하이브리드 구성 마법사에서만 필요합니다. <p> GCC High, DoD IP 주소: 40.118.209.192/32; 168.62.190.41/32 <p> Worldwide Commercial & GCC: \* .store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net ; <br> aka.ms/hybridwizard; <br> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;|아웃바운드 서버 전용 트래픽|
|10 |AutoDetect 서비스는 [Exchange 하이브리드](/exchange/exchange-deployment-assistant) 시나리오에서 [iOS 및 Android용 Outlook을 통한 하이브리드 최신 인증](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)과 함께 사용됩니다. <p> `*.acompli.net` <br> `*.outlookmobile.com` <br> `*.outlookmobile.us` <br> `52.125.128.0/20` <br> `52.127.96.0/23`|TCP 443의 고객 온-프레미스 Exchange 서버|인바운드 서버 트래픽|
|11 |Exchange 하이브리드 Azure AD 인증|*.msappproxy.net|TCP 아웃바운드 서버 전용 트래픽|
|12 |Office 2016의 비즈니스용 Skype에는 UDP 포트를 사용하는 비디오 기반 화면 공유 기능이 포함되어 있습니다. Office 2013 이하의 이전 비즈니스용 Skype 클라이언트에서는 TCP 포트 443을 사용하는 RDP를 이용했었습니다.|52.112.0.0/14에 열린 TCP 포트 443|Office 2013 이전의 비즈니스용 Skype 이전 클라이언트 버전|
|13|비즈니스용 Skype Online에 대한 비즈니스용 Skype 하이브리드 온-프레미스 서버 연결|13.107.64.0/18, 52.112.0.0/14 <br> UDP 포트 50,000~59,999 <br> TCP 포트 50,000~59,999; 5061|비즈니스용 Skype 온-프레미스 서버 아웃바운드 연결|
|14 |온-프레미스 하이브리드 연결을 사용하는 클라우드 PSTN에는 온-프레미스 호스트에 열린 네트워크 연결이 필요합니다. 비즈니스용 Skype Online 하이브리드 구성에 대한 자세한 내용은|[비즈니스용 Skype 서버 및 Office 365 간 하이브리드 연결 플랜](/skypeforbusiness/hybrid/plan-hybrid-connectivity)을 참조하세요.|비즈니스용 Skype 온-프레미스 하이브리드 인바운드|
|15 |**인증 및 ID FQDN** <p> 작동하려면 FQDN `secure.aadcdn.microsoftonline-p.com`가 클라이언트의 Internet Explorer(IE) 또는 Edge의 신뢰할 수 있는 사이트 영역에 있어야 합니다.||신뢰할 수 있는 사이트|
|16 |**Microsoft Teams FQDN** <p> Internet Explorer 또는 Microsoft Edge를 사용하는 경우 먼저 제3자 쿠키를 사용하고 팀의 FQDN을 신뢰할 수 있는 사이트에 추가해야 합니다. 이는 14번째 줄에 나열된 제품군 전체의 FQDN, CDN 및 원격 분석 외에 추가되는 사항입니다. 자세한 내용은 [Microsoft Teams에 대한 알려진 문제점](/microsoftteams/known-issues)을 참조하세요.||신뢰할 수 있는 사이트|
|17 |**SharePoint Online 및 비즈니스용 OneDrive FQDN** <p> FQDN에서 \<tenant\>에 대한 모든 ‘.sharepoint.com’ FQDN가 클라이언트의 IE 혹은 EDGE 신뢰하는 사이트 구역에 있어야 기능이 작동합니다. 14번 줄에 나열된 제품군 전체 FQDN, CDN 및 원격 측정 외에도 이러한 끝점을 추가해야 합니다.||신뢰할 수 있는 사이트|
|18 |**Yammer**  <br> Yammer는 브라우저에서만 사용할 수 있으며 인증된 사용자는 프록시를 통해 전달되어야 합니다. 모든 Yammer FQDN은 클라이언트의 IE 또는 Edge의 신뢰할 수 있는 사이트 영역에 있어야 작동할 수 있습니다.||신뢰할 수 있는 사이트|
|19|[Azure AD Connect](/azure/active-directory/hybrid/)를 사용하여 온프레미스 사용자 계정을 Azure AD에 동기화합니다.|[포트 및 프로토콜이 필요한 하이브리드 ID](/azure/active-directory/hybrid/reference-connect-ports), [Azure AD 연결 문제 해결](/azure/active-directory/hybrid/tshoot-connect-connectivity) 그리고 [Azure AD Connect Health 에이전트 설치](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints)를 참조합니다.|아웃바운드 서버 전용 트래픽|
|20|온-프레미스 사용자 계정을 Azure AD에 동기화하기 위한 중국의 21 ViaNet과 [Azure AD Connect](/azure/active-directory/hybrid/)|\*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <br> secure.aadcdn.partner.microsoftonline-p.cn:443 <br> \*.partner.microsoftonline.cn:443 <p> [Azure AD 연결 수신 문제 해결](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity)을 참조하세요.|아웃바운드 서버 전용 트래픽|
| 21|Microsoft Stream(Azure AD 사용자 토큰 필요) <br> Office 365 월드와이드(GCC 포함)|\*.cloudapp.net <br> \*.api.microsoftstream.com <br> \*.notification.api.microsoftstream.com <br> amp.azure.net <br> api.microsoftstream.com <br> az416426.vo.msecnd.net <br> s0.assets-yammer.com <br> vortex.data.microsoft.com <br> web.microsoftstream.com <br> TCP 포트 443|인바운드 서버 트래픽|
|22|다중 요소 인증 요청(서버 새로 설치 및 AD DS(Active Directory Domain Services)로 설정)에 MFA 서버를 사용하세요.|Azure AD 다단계 인증 서버 [시작을 참조하세요.](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)|아웃바운드 서버 전용 트래픽|
|23|Microsoft Graph 변경 알림 <p> 개발자는[변경 알림](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0)을 활용하여 Microsoft Graph의 이벤트를 구독할 수 있습니다.|Public Cloud: 52.159.23.209, 52.159.17.84, 52.147.213.251, 52.147.213.181, 13.85.192.59, 13.85.192.123, 13.89.108.233, 13.89.104.147, 20.96.21.67, 20.69.245.215, 137.135.11.161, 137.135.11.116, 52.162.219.103, 52.162.218.180, 52.229.38.131, 52.183.67.212, 52.142.114.29, 52.142.115.31, 51.124.75.43, 51.124.73.177, 20.44.210.83, 20.44.210.146, 40.80.232.177, 40.80.232.118, 20.48.12.75, 20.48.11.201, 104.215.13.23, 104.215.6.169, 52.148.24.136, 52.148.27.39, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 13.86.37.15, 52.154.246.238, 20.96.21.98, 20.96.21.115, 137.135.11.222, 137.135.11.250, 52.162.219.149, 52.162.219.167, 52.151.30.78, 52.191.173.85, 51.104.159.213, 51.104.159.181, 51.138.90.7, 51.138.90.52, 52.148.115.48, 52.148.114.238, 40.80.233.14, 40.80.239.196, 20.48.14.35, 20.48.15.147, 104.215.18.55, 104.215.12.254 <p> Microsoft Cloud for US Government: 52.244.33.45, 52.244.35.174, 52.243.157.104, 52.243.157.105, 52.182.25.254, 52.182.25.110, 52.181.25.67, 52.181.25.66, 52.244.111.156, 52.244.111.170, 52.243.147.249, 52.243.148.1 9, 52.182.32.51, 52.182.32.143, 52.181.24.199, 52.181.24.220 <p> 21Vianet에서 운영하는 Microsoft 클라우드 중국: 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56, 40.125.138.23, 40.125.136.69, 40.72.155.199, 40.72.155.216 <br> TCP 포트 443 <p> 참고: 개발자는 구독을 만들 때 여러 포트를 지정할 수 있습니다.|인바운드 서버 트래픽|
|

## <a name="related-topics"></a>관련 주제

[Office 365 끝점 관리](managing-office-365-endpoints.md)
  
[Microsoft 365 연결 모니터링](./monitor-connectivity.md)
  
[클라이언트 연결](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[콘텐츠 배달 네트워크](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Azure IP 범위 및 서비스 태그 – 공용 클라우드](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP 범위 및 서비스 태그 – 미국 정부 클라우드](https://www.microsoft.com/download/details.aspx?id=57063)

[Azure IP 범위 및 서비스 태그 – 독일 클라우드](https://www.microsoft.com/download/details.aspx?id=57064)

[Azure IP 범위 및 서비스 태그 – 중국 클라우드](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft 공용 IP 공간](https://www.microsoft.com/download/details.aspx?id=53602)
