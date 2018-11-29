---
title: Microsoft Managed Desktop의 보안
description: ''
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870344"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 보안

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

대부분의 Microsoft 기술을 사용 하 여 Microsoft 관리 되는 데스크톱 장치 안전 하다는 하 고는 Microsoft 관리 되는 데스크톱 보안 작업 팀 수 방지을 감지 하 고 고급 위협에 응답을 확인할 수 했습니다. 제 3 자 보안 제품, 앱 및 서비스 허용 되지 않습니다. Microsoft 장치, identity, 네트워크를 확인 하는 표준 정책 기준을 적용 하 고 회사 데이터는 보안 및 보호 합니다.

다음 섹션에서 설명 하는 이러한 종류의 보안을 적용 합니다.

- [데이터 보안](#data-security) -저장 되 고 Azure 보안 위치를 지정 하는 것에 대 한 요구 사항을 충족 데이터는 확인 하는 방법
- [장치 보안](#device-security) -보안 된 데스크톱을 관리 하는 Microsoft 장치는 확인 하는 방법
- [Id 보안](#identity-security) -현대 직장에서 사용자를 확인 우리는 어떻게 서는 안됩니다
- [네트워크 보안](#network-security) -회사 리소스에 대 한 보안 액세스 하기 위한 방법
- [정보 보안](#information-security) -보안은 회사 데이터는 확인 하는 방법
- [권한 있는 계정 액세스](#privileged-account-access) -액세스는 제한 하는 방법

## <a name="data-security"></a>데이터 보안

테 넌 트에서 전송 되는 데이터는 미국의 경우 호스팅된 Microsoft 테 넌 트의 Azure SQL 데이터베이스에 저장 됩니다. 사용자 데이터 저장 되 고 Azure 보안 위치를 지정 하는 것에 대 한 요구 사항을 만족 해야 합니다. 

자세한 내용은 [Microsoft Azure 보안](https://www.microsoft.com/TrustCenter/Security/azure-security)을 참조 하십시오.

이 목록에는 Microsoft 및 테 넌 트 간에 전송 되는 데이터의 형식을 요약 되어있습니다. 

- 테 넌 트에 Microsoft에서
    - 그룹 이름
    - 보안 정책 구성
    - 장치 주문
    - 사용자 계정 (msadmin, mstest, Microsoft 관리 되는 Desktop_soc_ro, Microsoft 관리 되는 Desktop_wdgsoc)
    - 위의 4 사용자에 게 e 5 라이선스 할당
    - Windows는 업데이트 링에 대 한 정책 업데이트
    - 나중에 추가 기능 개발 될 것 구성 콘텐츠 앱, 정책 및 설정을 포함 하 여 다른 종류의 게시를 허용 하도록 합니다.
- Microsoft에 테 넌 트에서
    - 장치 업데이트, 사용 현황 및 안정성 데이터
    - 응용 프로그램 배포 및 안정성 데이터
    - 업데이트 및 보안 정책 배포 데이터
    - 장치에 할당 된 사용자



## <a name="device-security"></a>장치 보안

이 보안 침해를 방지 하려면 모든 Microsoft 관리 되는 데스크톱 장치는 정상 상태이 고 보안을 확인 하는 것이 중요 합니다. 비정상 장치를 검색 하 고 가능한 한 빨리 위험을 완화할 수는 확인을 동일 하 게 고려해 야 합니다.

다음 표에서 Microsoft 관리 되는 데스크톱 장치는 신뢰할 수 있는, 정상 및 보안을 제공 하는 서비스를 보여줍니다.

서비스 | 설명
--- | ---
바이러스 검사 | 확인 됩니다.<br>Windows Defender AV 설치 및 구성<br>Windows Defender AV 정의 최신 상태입니다.
전체 볼륨 암호화 |    Windows BitLocker는 Microsoft 관리 되는 데스크톱 장치에 대 한 데이터 암호화 솔루션입니다.<br><br>조직에는 서비스로 onboarded 되 면 장치가 절전 모드에서 하거나 해제 하는 경우 로컬 데이터에 무단으로 액세스를 방지 하기 위해 함께 기본 제공 신뢰 플랫폼 모듈 (TPM) Windows BitLocker을 사용 하 여 장치 암호화 됩니다. 
모니터링 |    Windows Defender 고급 위협 보호 (Windows Defender ATP)는 모니터링 솔루션 모든 Microsoft 관리 되는 데스크톱 장치에 대 한 보안 위협. Windows Defender ATP 기업 고객을 감지, 조사 및가 회사 네트워크의 고급 위협에 응답할 수 있습니다. 자세한 내용은 참조 [Windows Defender 고급 위협 보호.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
소프트웨어 업데이트 |  Microsoft은 Windows 및 Windows Update를 사용 하 여 비즈니스를 위한 Office에 대 한 최신 보안 업데이트와 Microsoft 관리 되는 데스크톱 장치는 항상 보안을 보장 합니다.
 복구  |  회사 데이터 비즈니스용 OneDrive에 저장 하 고 Microsoft 관리 되는 데스크톱 장치에 대 한 쉽게 복원할 수 있습니다. 자세한 내용은 참조 [비즈니스용 OneDrive.](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US) 



## <a name="identity-security"></a>Id 보안

회사 자산 및 업무에 중요 한 데이터를 보호 하는 id 및 액세스 관리 합니다. Azure Active Directory (Azure AD) 클라우드에서 id 서비스를 제공 하 고 사용 클라우드 기반 인증만 신뢰할 수 있는 사람을 보장 하는 Microsoft 관리 되는 데스크톱 장치에서 회사 리소스에 액세스할 수 있습니다.

서비스 | 설명
--- | ---
엔터프라이즈 등급 인증 공급자 |  Microsoft에서 사용 하는 azure AD 프리미엄 버전 전체적으로 배포 된 데이터 센터에서 호스트 되는 고가용성 서비스를 제공 합니다. 서비스는 200 백만 개 이상의 활성 사용자에서 매일 인증 십억을 처리 하 고 99.9 %SLA 제공 합니다.
생체 인식 인증 |  Windows Hello 사용자가 자신의 얼굴 또는 암호를 잊어버리거나 훔쳐 하기 어렵습니다 되도록 설정 하는 PIN을 사용 하 여 로그인 합니다. 추가 구성 작업을 수행을 해야할 수 있습니다. 자세한 내용은 참조 [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
다중 요소 인증 | Azure 다단계 인증 온-프레미스에 무단으로 액세스를 차단 및 클라우드를 더 높은 수준의 휴대폰도 같이 셀프서비스 암호 재설정을 사용 하 여 인증을 제공 하 여 응용 프로그램입니다. 
표준 사용자 권한 |  시스템을 보호 하 고 더욱 안전 하 게 하려면 사용자 표준 사용자 권한 할당 됩니다. 이 Windows 작업을 자동화할 즉시의 환경에서의 일부분으로 할당 됩니다.



## <a name="network-security"></a>네트워크 보안

고객에 게는 네트워크 보안에 대 한 책임을 집니다. 

서비스 | 설명
--- | ---
VPN | 고객 소유가 VPN 인프라 확인 인트라넷 외부의 제한 된 회사 리소스를 노출 될 수 있습니다.<br><br>최소 요구 사항: Microsoft 관리 되는 데스크톱 Windows 10 호환 되는 및 지원 되는 VPN 솔루션 필요 합니다. 조직에서 VPN 솔루션을 필요로 하는 경우 Windows 10 지원과 패키지화 되 고 Intune를 통해 배포 될 수 있어야 합니다. 자세한 내용은 소프트웨어 게시자에 게 문의 합니다.<br><br>권장 사항:<br>Microsoft 푸시 VPN 프로필에 Intune를 통해 쉽게 배포할 수 있는 최신 VPN 솔루션을 권장 합니다. 이 회사 네트워크에 액세스 하는 항상-에, 원활 하 게, 안정적이 고 안전한 방법을 제공 합니다. 자세한 내용은 Intune의 VPN 설정을 참조 하십시오.<br>-굵은 VPN 클라이언트 또는 레거시 VPN 클라이언트는 최종 사용자 환경에 영향을 줄 수 있는 것 처럼 Microsoft 관리 되는 데스크톱을 사용 하는 동안 Microsoft에서 권장 되지 않습니다.<br>Microsoft는 성능 문제를 방지 하기 위해 VPN을 거치지 않고 보내는 웹 트래픽을 인터넷에 직접 이동 하는 것이 좋습니다.<br>-원칙적으로, Microsoft Azure Active Directory 응용 프로그램 프록시를 VPN 하는 대신 사용할 것을 권장 합니다.


## <a name="information-security"></a>정보 보안 적용

고객 회사 중요 한 자산을 보호 하려면 이러한 선택적 서비스를 구성할 수도 있습니다. 

서비스 | 설명
--- | ---
조건부 액세스 |    장치를 준수 하는 경우에 회사 리소스 및 서비스에 대 한 액세스를 허용 합니다.
데이터 복구  | 장치에서 주요 폴더에 저장 된 정보는 Bbusiness에 대 한 OneDrive에 백업 됩니다. Microsoft 관리 되는 데스크톱 비즈니스용 OneDrive와 동기화 되지 않은 데이터에 대 한 책임을 집니다있지 않습니다. 
Windows Information Protection |    높은 수준의 정보 보안을 필요로 하는 기업에 대 한 것이 좋습니다 [Windows 정보 보호](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) 및 [Azure 정보 보호.](https://www.microsoft.com/cloud-platform/azure-information-protection)합니다. 


## <a name="privileged-account-access"></a>권한이 부여 된 계정에 액세스

오늘날 우리 대 한 액세스 제한 고객 MSAdmin 자격 증명 및 응용 프로그램에 이러한 메커니즘을 통해:

- **연산자** – Microsoft 전체-일회용-직원은 미국에 있는 배경 및 보안 검사를 정기적으로 성공적으로 완료 했습니다.
- Microsoft에서 설정한 표준에 따라 **연산자 identity** – 보호를 받습니다. 자세한 내용은 [관리 사용자 id 및 Microsoft에서 보안 액세스를](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)참조 하십시오. 
- **로깅** 및 고객의 테 넌 트 내 교환원 환경에서 수행 됩니다. 로그 데이터와 개인정보 해당 환경 내에서 유지 되 고, 환경을 통과 하지 않습니다. 

