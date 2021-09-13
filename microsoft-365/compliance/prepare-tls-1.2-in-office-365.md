---
title: Office 365 및 Office 365 GCC에서 TLS 1.2 준비
description: TLS 1.0 및 1.1에 대한 지원이 비활성화 된 후에 Office 365 및 Office 365 GCC에서 모든 클라이언트-서버 및 브라우저-서버 조합에 대해 TLS 1.2 사용을 준비하는 방법
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 053ee63d80f37753b3737d834c9e79e4001f8a79
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186060"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>Office 365 및 Office 365 GCC에서 TLS 1.2 준비

## <a name="summary"></a>요약

Microsoft는 고객에게 최고 수준의 암호화를 제공하기 위해 Office 365 및 Office 365 GCC에서 TLS(Transport Layer Security) 버전 1.0 및 1.1을 더 이상 사용하지 않을 계획입니다. 데이터 보안이 중요하다는 점을 이해하고 있으며 TLS 서비스 사용에 영향을 줄 수 있는 변경 사항에 대해 투명성을 유지할 것을 약속드립니다.

[Microsoft TLS 1.0 구현](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n)에 알려진 보안상 취약한 부분은 없습니다. 그러나 향후 프로토콜 다운그레이드 공격 및 기타 TLS 취약점이 발생할 수 있으므로 Microsoft Office 365 및 Office 365 GCC에서 TLS 1.0 및 1.1에 대한 지원을 중단합니다.

TLS 1.0 및 1.1 종속성을 제거하는 방법에 대한 자세한 내용은 다음 백서를 참조하세요. [TLS 1.0 문제 해결](https://www.microsoft.com/download/details.aspx?id=55266).

TLS 1.2로 업그레이드한 후 사용 하는 암호 제품군이 Azure Front Door에서 지원 하는지 확인 합니다. Microsoft 365 Azure Front Door는 암호 제품군 지원에 약간의 차이가 있습니다. 자세한 내용은 Azure Front Door에서 지원하는 현재 암호 [제품군은 무엇입니까?를 참조하세요.](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)

## <a name="more-information"></a>추가 정보

2020년 1월부터 이미 TLS 1.0과 1.1의 사용 중단이 시작되었습니다. DoD 또는 GCC High 인스턴스에서 TLS 1.0 또는 1.1을 통해 Office 365에 연결되는 모든 클라이언트, 디바이스 또는 서비스는 지원되지 않습니다. Office 365 고객의 경우 TLS 1.0 및 1.1 사용이 2020년 10월 15일부터 시작되고 출시는 다음 주와 몇 개월에 진행됩니다.

모든 클라이언트-서버 및 브라우저-서버 조합에서는 Office 365 서비스 연결을 유지하기 위해 TLS 1.2(이상의 버전)를 사용하는 것이 좋습니다. 특정 클라이언트-서버 및 브라우저-서버 조합을 업데이트해야 할 수 있습니다.

TLS 1.2를 사용하려면 TLS Microsoft 365 또는 TLS 1.1을 통해 Microsoft 365 응용 프로그램을 업데이트해야 합니다. .NET 4.5는 기본적으로 TLS 1.1로 설정됩니다. .NET 구성을 업데이트하려면 [클라이언트에서 TLS(전송 계층 보안) 1.2를](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)사용하도록 설정하는 방법을 참조합니다.

다음 클라이언트는 TLS 1.2를 사용할 수 없습니다. 서비스에 중단 없이 액세스할 수 있도록 클라이언트를 업데이트하세요.

- Android 4.3 이하 버전
- Firefox 5.0 이하 버전
- Windows 7 이하 버전의 Internet Explorer 8-10
- Windows Phone 8의 Internet Explorer 10
- Safari 6.0.4/OS X10.8.4 이하 버전

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>Microsoft Teams Rooms 및 Surface Hub용 TLS 1.2

Microsoft Teams Rooms(이전 Skype Room System V2 SRS V2)는 2018년 12월부터 TLS 1.2를 지원하고 있습니다. Rooms 디바이스에는 Microsoft Teams Rooms 앱 버전 4.0.64.0 이상이 설치되어 있는 것이 좋습니다. 자세한 내용은 [릴리스 노트](/microsoftteams/room-systems/srs2-release-note)를 참조하세요. 변경 사항은 이전 및 이후 버전과 호환됩니다.

Surface Hub는 2019년 5월에 TLS 1.2 지원을 릴리스했습니다.

Microsoft Teams Rooms 및 Surface Hub 제품에서 TLS 1.2를 지원하려면 서버 쪽 코드도 다음과 같이 변경해야 합니다.

- 비즈니스용 Skype Online 서버 변경 내용은 2019년 4월에 적용되었습니다. 이제 비즈니스용 Skype Online에서는 TLS 1.2를 사용하여 Microsoft Teams Rooms 및 Surface Hub 장치를 연결할 수 있습니다.
- Teams Rooms Systems 및 Surface Hub에 TLS 1.2를 사용하려는 비즈니스용 Skype 서버 고객은 CU(누적 업데이트)를 설치해야 합니다.

  - 비즈니스용 Skype 서버 2015의 경우 2019년 5월에 CU9가 이미 릴리스되었습니다.
  - 비즈니스용 Skype 서버 2019의 경우 CU1은 이전에 2019년 4월에 계획되었지만 2019년 6월로 연기되었습니다.

  > [!NOTE]
  > 비즈니스용 Skype 온-프레미스 고객은 비즈니스용 Skype 서버의 특정 CU를 설치하기 전에 TLS 1.0/1.1을 사용하지 않도록 설정해서는 안 됩니다.

하이브리드 시나리오 또는 Active Directory Federation Services에 대해 온-프레미스 인프라를 사용하는 경우 인프라에서 TLS 1.2를 사용하는 인바운드 및 아웃바운드 연결을 모두 지원할 수 있는지 확인하십시오.

## <a name="references"></a>참조

다음 리소스에서는 클라이언트가 TLS 1.2 이상 버전을 사용하고 TLS 1.0 및 1.1을 비활성화하는 데 도움이 되는 지침을 제공합니다.

- Office 365에 연결하는 Windows 7 클라이언트의 경우 Windows의 WinHTTP에서 TLS 1.2가 기본 보안 프로토콜인지 확인하세요. 자세한 내용은 [KB 3140245 - Windows의 WinHTTP에서 기본 보안 프로토콜로 TLS 1.1 및 TLS 1.2를 사용하도록 업데이트](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)를 참조하십시오.
- [지원되는 TLS 암호 Office 365](/microsoft-365/compliance/technical-reference-details-about-encryption#tls-cipher-suites-supported-by-office-365)
- TLS 1.0 및 1.1 종속성을 제거하여 취약한 TLS 사용을 해결하려면 [Microsoft의 TLS 1.2 지원](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)을 참조하십시오.
- [새로운 IIS 기능](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)을 사용하면 취약한 보안 프로토콜로 서비스에 연결하는 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 및 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334)에서 클라이언트를 쉽게 찾을 수 있습니다.
- [TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)문제를 해결하는 방법에 대한 자세한 정보를 얻습니다.
- 보안에 접근하는 방식에 대한 일반적인 정보는 [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365)로 이동하십시오.
- SMTP 클라이언트에서 사용되는 TLS 버전을 식별하기 위해 보안 및 준수 [센터에서 SMTP & 보고를 참조합니다.](../security/office-365-security/mfi-smtp-auth-clients-report.md)
- [TLS 1.0/1.1 사용 중단 준비 - Office 365 비즈니스용 Skype](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS 지침, 1부: TLS 1.2 준비](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange Server TLS 지침 2부: TLS 1.2 사용 및 이를 사용하지 않는 클라이언트 식별](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange Server TLS 지침 3부: TLS 1.0/1.1 끄기](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Office Online Server에서 TLS 1.1 및 TLS 1.2 지원 사용](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
