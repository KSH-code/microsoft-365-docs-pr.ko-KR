---
title: Microsoft Managed Desktop의 보안
description: ''
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870344"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 보안

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft 관리 되는 데스크톱 표준 정책 집합을 적용 하는 및 보안 Microsoft 관리 되는 데스크톱 장치, 회사의 저장 된 데이터 등을 위해 많은 Microsoft 기술을 활용 하 여 합니다. 아래에 나열 된 영역 더 자세히 설명 합니다.  

- [데이터 보안](#data-security) -Microsoft 관리 되는 데스크톱 및 안전 하 게 저장 되는 위치에서 수집 된 데이터 형식
- [장치 보안](#device-security) -보안 및 보호 Microsoft 관리 되는 데스크톱 장치에서
- Azure Active Directory id 서비스를 통해 장치 사용 하 여 [id 및 액세스 관리](#identity-and-access-management) -보안 관리
- [네트워크 보안](#network-security) – VPN 정보 및 데스크톱을 관리 하는 Microsoft 권장 되는 솔루션 및 설정
- [정보 보안](#information-security) – 더 중요 한 정보를 보호 하기 위해 사용할 수 있는 선택적 서비스 

## <a name="data-security"></a>데이터 보안

(활성화 하는 Microsoft 관리 되는 데스크톱 IT 서비스 및 운영) 고객 테 넌 트에서 수집한 데이터는 미국에서 호스팅되는 Microsoft 테 넌 트의 Azure SQL 데이터베이스에 저장 됩니다.

자세한 내용은 [Microsoft Azure 보안](https://docs.microsoft.com/azure/security/azure-database-security-overview)을 참조 하십시오.

테 넌 트에서 전송 되는 데이터의 형식을 다음과 같습니다.

- 장치 업데이트, 사용 현황 및 안정성 데이터
- 응용 프로그램 배포 및 안정성 데이터
- 업데이트 및 보안 정책 배포 데이터
- 장치에 할당 된 사용자



## <a name="device-security"></a>장치 보안

Microsoft 관리 되는 데스크톱을 통해 모든 관리 되는 장치 보호 된 하 고, 보호 및 다음 서비스를 사용 하 여 최대한 일찍 위협 요소를 검색:

서비스 | 설명
--- | ---
바이러스 검사 | Windows Defender AV 설치 및 구성<br>Windows Defender AV 정의 최신 상태입니다.
전체 볼륨 암호화 |    Windows BitLocker는 Microsoft 관리 되는 데스크톱 장치에 대 한 볼륨 암호화 솔루션입니다.<br><br>조직에는 서비스로 onboarded 되 면 장치가 절전 모드에서 하거나 해제 하는 경우 로컬 데이터에 무단으로 액세스를 방지 하기 위해 함께 기본 제공 신뢰 플랫폼 모듈 (TPM) Windows BitLocker을 사용 하 여 장치 암호화 됩니다. 
모니터링 |    Windows Defender 고급 위협 보호 (Windows Defender ATP)는 모든 Microsoft 관리 되는 데스크톱 장치에 대해 보안 위협 모니터링에 사용 됩니다. Windows Defender ATP 기업 고객을 감지, 조사, 및가 회사 네트워크의 고급 위협에 응답할 수 있습니다. 자세한 내용은 참조 [Windows Defender 고급 위협 보호.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
소프트웨어 업데이트 |  Microsoft 관리 되는 데스크톱 장치는 항상 최신 보안 업데이트를 사용 하 여 보호 됩니다.
보안 장치 구성 |   Microsoft 관리 되는 데스크톱 Microsoft 보안 초기 계획을 구현합니다. 자세한 내용은 참조 [Windows 보안 기준선.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>ID 및 액세스 관리

회사 자산 및 업무에 중요 한 데이터를 보호 하는 id 및 액세스 관리 합니다. 데스크톱을 관리 하는 Microsoft Azure Active Directory (Azure AD)와 보안 사용 관리 id가 되도록 장치를 구성 합니다. 것은 자신의 Azure AD 테 넌 트에 정확한 정보를 유지 하는 고객의 책임입니다. 

서비스 | 설명
--- | ---
생체 인식 인증 |  Windows Hello 사용자가 자신의 얼굴 또는 암호를 잊어버리거나 훔쳐 하기 어렵습니다 되도록 설정 하는 PIN을 사용 하 여 로그인 합니다. 자세한 내용은 참조 [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Multi-Factor Authentication | Azure 다단계 인증 더 밀접 하 게는 더 높은 수준의 웰 같이 셀프서비스 암호 재설정으로는 휴대폰을 사용 하 여 인증을 제공 하 여 데스크톱을 관리 하는 Microsoft 서비스의 중요 한 기능에 대 한 액세스를 제어 합니다. 
표준 사용자 권한 |  시스템을 보호 하 고 더욱 안전 하 게 하려면 사용자 표준 사용자 권한 할당 됩니다. 이 Windows 작업을 자동화할 즉시의 환경에서의 일부분으로 할당 됩니다.



## <a name="network-security"></a>네트워크 보안

고객에 게는 네트워크 보안에 대 한 책임을 집니다. 

서비스 | 설명
--- | ---
VPN | 고객 소유가 VPN 인프라 확인 인트라넷 외부의 제한 된 회사 리소스를 노출 될 수 있습니다.<br><br>최소 요구 사항: Microsoft 관리 되는 데스크톱 Windows 10 호환 되는 및 지원 되는 VPN 솔루션 필요 합니다. 조직에서 VPN 솔루션을 필요로 하는 경우 Windows 10 지원과 패키지화 되 고 Intune를 통해 배포 될 수 있어야 합니다. 자세한 내용은 소프트웨어 게시자에 게 문의 합니다.<br><br>권장 사항:<br>Microsoft 푸시 VPN 프로필에 Intune를 통해 쉽게 배포할 수 있는 최신 VPN 솔루션을 권장 합니다. 이 회사 네트워크에 액세스 하는 항상-에, 원활 하 게, 안정적이 고 안전한 방법을 제공 합니다. 자세한 내용은 [[Intune의 VPN 설정]을](https://docs.microsoft.com/intune/vpn-settings-configure)참조 하십시오.<br>-굵은 VPN 클라이언트 또는 레거시 VPN 클라이언트는 최종 사용자 환경에 영향을 줄 수 있는 것 처럼 Microsoft 관리 되는 데스크톱을 사용 하는 동안 Microsoft에서 권장 되지 않습니다.<br>Microsoft는 성능 문제를 방지 하기 위해 VPN을 거치지 않고 보내는 웹 트래픽을 인터넷에 직접 이동 하는 것이 좋습니다.<br>-원칙적으로, Microsoft Azure Active Directory 응용 프로그램 프록시를 VPN 하는 대신 사용할 것을 권장 합니다.


## <a name="information-security"></a>정보 보안 적용

고객 회사 중요 한 자산을 보호 하려면 이러한 선택적 서비스를 구성할 수도 있습니다. 

서비스 | 설명
--- | ---
데이터 복구  | 장치에서 주요 폴더에 저장 된 정보는 다음과 같은 비즈니스용 OneDrive에 백업 됩니다. Microsoft 관리 되는 데스크톱 비즈니스용 OneDrive와 동기화 되지 않은 데이터에 대 한 책임을 집니다있지 않습니다. 
Windows Information Protection |    높은 수준의 정보 보안을 필요로 하는 기업에 대 한 것이 좋습니다 [Windows 정보 보호](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) 및 [Azure 정보 보호.](https://www.microsoft.com/cloud-platform/azure-information-protection)합니다. 

