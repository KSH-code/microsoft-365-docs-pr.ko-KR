---
title: 장치 구성
description: Microsoft 관리 되는 데스크톱 장치에 적용 된 기본 정책에 알아봅니다.
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 5a97f44641ac38a8785bde66819dbfffffee946d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870166"
---
# <a name="device-configuration"></a>장치 구성


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

새 Microsoft 관리 되는 데스크톱 장치 구축 되 고, 될 때 전체에서 Microsoft 관리 되는 데스크톱에 최적화 하는 오른쪽 구성 인지을 확인 합니다. 온 보 딩 프로세스의 일환으로 구성 된 기본 정책 집합이 포함 됩니다. 충돌을 피하려면 이러한 정책은 변경할 수 없습니다. 

장치는 서명 이미지를 파악 한 후 첫번째 사용자가 로그인 할 때 Azure Active Directory 도메인에 가입 됩니다. 장치에서 자동으로 필요한 IT 개입 없이 필요한 정책 및 응용 프로그램 설치 됩니다.

## <a name="why-mdm-over-group-policy"></a>이유 그룹 정책을 통해 MDM

그룹 정책 대신 모바일 장치 관리 (MDM)를 사용 하는 몇가지 이유 가지가 있습니다.

- 보안-MDM 정책은 현대의에서 보안을 강화 합니다. 그룹 정책 온-프레미스 id를 가진 가장 잘 작동 하도록 설계 되었습니다. MDM은 클라우드 id 관리 (Azure Active Directory (Azure AD)) 가장 잘 작동 하도록 설계 되었습니다.
- 안정성-MDM 정책 보다 신뢰할 수 있는 정책 배포를 제공 합니다. MDM 설정은 그룹 정책 개체 (GPO) 정책 덮어씁니다. 1803, 버전, Windows 10로 시작 하 여 그룹 정책 값을 통해 MDM 설정 순위 됩니다. 현대 관리로 이동 하는 고객을 지원 합니다. 
- Microsoft 관리 되는 데스크톱 비전-정책 배포에서 모니터링 더 효율적으로 맞춥니다. 필요한 경우 배포를 다시 시작 / 일시 중지 하는 기능은 점진적으로 롤아웃 정책 변경 내용에 대 한 연결 기반 접근법을 지원 합니다.

## <a name="default-policies"></a>기본 정책

이 테이블 중요 한 정보는 기본 정책을 장치 프로 비전 하는 동안 모든 Microsoft 관리 되는 데스크톱 장치에 적용 되는 합니다. 충돌을 방지 하려면 이러한 정책은 변경할 수 없습니다. 모든 검색 Microsoft 관리 하는 바탕 화면에서 관리 하는 개체에 Microsoft 관리 되는 데스크톱 작업 팀에서 승인 되지 변경 내용을 취소 됩니다.

정책 | 설명
--- | ---
Security baseline 시작 | [Microsoft 보안 기본](https://docs.microsoft.com/windows/device-security/windows-security-baselines) MDM에 대 한 모든 Microsoft 관리 되는 데스크톱 장치에 대해 구성 됩니다. 이 초기 계획은 업계 표준 구성 합니다. 이 공식 출시, 잘 테스트 하 고 Microsoft 관리 되는 데스크톱 장치 변경 하지 않으려면 Microsoft 보안 전문가가 검토 되었고 및 앱 현대 직장에서 보안을 유지 합니다.<br><br>위협을 완화 하기 위한 보안 위협 지속적으로 진화 상황에서 Microsoft 보안 기본 업데이트 되며 각 Windows 10 기능 업데이트를 사용 하 여 Microsoft 관리 되는 데스크톱 장치에 배포 합니다.<br><br>자세한 내용은 [Windows 10에 대 한 보안 초기 계획](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)을 참조 하십시오.
데스크톱을 관리 하는 Microsoft 권장 보안 서식 파일 | 사용자 환경을 최적화 하는 보안 초기 계획 권장 변경 내용 집합입니다.  이러한 변경 내용은 [보안 부록](#security-addendum)에 설명 되어있습니다. 정책 부록에 대 한 업데이트 필요한 기준에 발생 합니다.  
장치 규정 준수 | 이러한 정책은 기본적으로 모든 Microsoft 관리 되는 데스크톱 장치에 대해 구성 됩니다. 장치를 충족 되지 않으면 다음과 같은 보안 조건 중 하나가 만족 하는 경우 규격이 아닌 것으로 보고 됩니다.<br>-BitLocker 장치 암호화 장치에서 데이터를 보호 하기 위해 사용할 수 있습니다. 자세한 내용은 참조 [개요 (영문)의 BitLocker 장치에서에서 암호화 Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-보안 부팅 사용 하도록 설정 하 고 실행할 수 있으므로 전에 장치에 펌웨어 이미지의 유효성을 검사를 적용 합니다. 자세한 내용은 참조 [보안 부팅 및 장치 암호화 개요.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Microsoft 관리 되는 데스크톱 장치에 액세스 하는 데 필요한 암호입니다.
업데이트 배포 | 비즈니스 (WUfB)에 대 한 Windows Update를 사용 하 여 소프트웨어 업데이트를 점진적으로 배포를 수행 합니다. IT 관리자의 경우에는 배포 링 정책에 대 한 설정을 수정할 수 없습니다. 링 기반 배포에 대 한 자세한 내용은 [업데이트 처리 되는 방식을](../working-with-managed-desktop/updates.md)참조 하십시오.
원격 분석 | 장치는 알려진된 상업용 식별자에서 Microsoft에 향상 된 진단 데이터를 제공 하도록 설정 됩니다. 고객에 대 한 일반적 데이터 보호 규정 (GDPR) 영역 최종 사용자에 게 줄일 수 제공 되는 진단 데이터의 수준을 합니다. 이 사용자 지정할 수 있지만 서비스 감소 됩니다. 자세한 내용은 참조 [조직에서 Windows 구성 진단 데이터.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="advanced-policies"></a>고급 정책

 다음은 매우 규제 된 산업 분야에 대 한 더 secure/잠겨진 환경에 대해 구성할 수 있는 추가 정책입니다.

 정책 | 설명
 --- | ---
 고급 기능 | 진행 (Windows 정보 보호 중) (영문) Azure 정보 보호 (AIP)만 특정 개인 또는 응용 프로그램/서비스의 하위 집합에 대 한 액세스를 허용 하 여 엔터프라이즈 데이터를 보호 하기 위해 사용 됩니다. 자세한 내용은 참조 하십시오.<br>- [Windows 정보 보호를 사용 하 여 엔터프라이즈 데이터를 보호 합니다.](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)<br>- [Azure 정보 보호 클라이언트 관리자 가이드](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)<br>- [Microsoft 데스크톱 보안 Addendum 관리](#security-addendum)

 ## <a name="security-addendum"></a>보안 addendum

 이 섹션에서는 표준 Microsoft 관리 되는 데스크톱 정책 변수에 대 한 추가으로 배포할 수 있는 정책에 설명 합니다. 표준 정책이 [기본 정책에](#default-policies)나열 됩니다. 이 구성은 금융 서비스 산업을 염두에 매우 규제 된와 디자인: 사용자의 생산성을 유지 하는 동안 가장 안전한 입장을 최적화 합니다.

게시 된 **보안 초기 계획**에 대 한 변경, [**네트워크 선택 UI를 표시 하지 않습니다**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowslogon#windowslogon-dontdisplaynetworkselectionui) 설정을 비활성화 됩니다.

 ### <a name="additional-security-policies"></a>추가 보안 정책

 이러한 정책은 매우 규제 된 산업 분야에 대 한 보안을 강화 하기 추가 됩니다. 
 - **응용 프로그램 허용 목록**: Microsoft 관리 되는 데스크톱 장치에서 실행 하려면 조직에서 앱을 신뢰 해야 합니다. 잠겨있는 환경을 제공 합니다. Onboarded 되어야 하는 모든 앱 Microsoft 관리 되는 데스크톱 작업 팀에 게 전달 해야 합니다. 자세한 내용은 [Windows Defender 장치 Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)를 참조 하십시오.
 - **보안 모니터링**: Microsoft [Windows Defender 고급 위협 보호](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)를 사용 하 여 장치를 모니터링 합니다. Microsoft는 고객 알림을 생성 하는 위협 감지 될 경우 해당 장치를 분리 하 고 원격으로 문제를 해결 합니다. 
 - **Guard 악용**: 우리는 Microsoft 관리 되는 데스크톱 장치 보안이 되는지 확인 항상 운영 체제 및 응용 프로그램을 모두에 대 한 최신 보안 업데이트와 [비즈니스를 위한 Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)를 사용 하 여 합니다. 이 악용 Guard 이러한 설정을 사용 하 여 구성 됩니다.

 설정 | 정책
 --- | ---
 Windows 로컬 보안 기관 하위 시스템에서 가로채기 자격 증명에 플래그를 지정합니다 | 감사 전용
 다른 프로세스에 삽입 하는 office 응용 프로그램 | 감사 전용
 Office 앱/매크로 실행 가능한 콘텐츠가 만들기 (영문) | Block
 하위 프로세스를 시작 하는 office 응용 프로그램 | 감사 전용
 Office 매크로 코드에서 Win32를 가져옵니다. | Block
 난독 처리 된 js/vbs/ps/매크로 코드 | Block
 인터넷 (예외 없음)에서 다운로드 한 Js/vbs 페이로드를 실행 합니다. | Block
 PSExec 및 WMI 명령에서 프로세스 만들기 | 감사 전용
 USB에서 실행 되는 신뢰할 수 없는 및 서명 되지 않은 프로세스 | Block
 프로그램 보급, 기간, 또는 신뢰할 수 있는 목록 조건을 충족 하지 않는 실행 파일 | 감사 전용
 실행 가능한 콘텐츠가 실행 하는 전자 메일에서 삭제 | Block
 고급 ransomware 보호 | 감사 전용









