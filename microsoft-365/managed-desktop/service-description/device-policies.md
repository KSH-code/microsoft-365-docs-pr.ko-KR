---
title: 장치 구성
description: Microsoft 관리 되는 데스크톱 장치에 적용 된 기본 정책에 알아봅니다.
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: e36c65bab3fa78fc27ee6228e78461b2e6b318dd
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870166"
---
# <a name="device-configuration"></a>장치 구성


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

새 Microsoft 관리 되는 데스크톱 장치 구축 되 고, 될 때 전체에서 Microsoft 관리 되는 데스크톱에 최적화 하는 오른쪽 구성 인지을 확인 합니다. 온 보 딩 프로세스의 일환으로 설정 된 기본 정책 집합이 포함 됩니다. 충돌을 피하려면 이러한 정책은 변경할 수 없습니다. 

장치는 서명 이미지를 파악 한 후 첫번째 사용자가 로그인 할 때 Azure Active Directory 도메인에 가입 됩니다. 장치에서 자동으로 필요한 IT 개입 없이 필요한 정책 및 응용 프로그램 설치 됩니다.

## <a name="why-mdm-over-group-policy"></a>이유 그룹 정책을 통해 MDM

그룹 정책 대신 모바일 장치 관리 (MDM)를 사용 하는 몇가지 이유 가지가 있습니다.

- 보안-MDM 정책은 현대의에서 보안을 강화 합니다. 그룹 정책은 MDM 클라우드 id 관리 (Azure Active Directory)와 가장 잘 작동 하도록 설계 하는 동안 온-프레미스 id를 가진 가장 잘 작동 하도록 설계 되었습니다.
- 안정성-MDM 정책 보다 신뢰할 수 있는 정책 배포를 제공 합니다. 또한 MDM 설정에는 그룹 정책 개체 (GPO) 정책을 덮어씁니다. 1803, 버전, Windows 10로 시작 하 여 MDM 설정 순위를 지정할 그룹 정책 값을 통해 최신 관리로 이동 하는 고객을 지원 하는 합니다. 
- Microsoft 관리 되는 데스크톱 비전에 맞는-정책 배포에서 더 포괄적인 모니터링 기능을 제공 하 고 필요한 경우 배포를 다시 시작 / 일시 중지 하는 기능으로 점진적으로 롤아웃 정책 변경 내용에 대 한 그룹 기반 접근법 방법을 지원 합니다.

자세한 내용은 [모바일 장치 관리](https://docs.microsoft.com/windows/client-management/mdm/)를 참조 하십시오. 

## <a name="default-policies"></a>기본 정책

이 테이블에는 장치 프로 비전 하는 동안 모든 Microsoft 관리 되는 데스크톱 장치에 적용 되는 기본 정책 강조 표시 됩니다. 모든 검색 Microsoft 관리 하는 바탕 화면에서 관리 하는 개체에 Microsoft 관리 되는 데스크톱 작업 팀에서 승인 되지 변경 내용을 취소 됩니다.

정책 | 설명
--- | ---
Security baseline 시작 | [Microsoft 보안 기본](https://docs.microsoft.com/windows/device-security/windows-security-baselines) MDM에 대 한 모든 Microsoft 관리 되는 데스크톱 장치에 대해 구성 됩니다. 이 초기 계획은 업계 표준 구성 합니다. 이 공식 출시, 잘 테스트 하 고 Microsoft 관리 되는 데스크톱 장치 변경 하지 않으려면 Microsoft 보안 전문가가 검토 되었고 및 앱 현대 직장에서 보안을 유지 합니다.<br><br>위협을 완화 하기 위한 보안 위협 지속적으로 진화 상황에서 Microsoft 보안 기본 업데이트 되며 각 Windows 10 기능 업데이트를 사용 하 여 Microsoft 관리 되는 데스크톱 장치에 배포 합니다.<br><br>자세한 내용은 [Windows 10에 대 한 보안 초기 계획](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)을 참조 하십시오.
데스크톱을 관리 하는 Microsoft 권장 보안 서식 파일 | 사용자 환경을 최적화 하는 보안 초기 계획 권장 변경 내용 집합입니다.  이러한 변경 내용은 [보안 부록](#security-addendum)에 설명 되어있습니다. 정책 부록에 대 한 업데이트 필요한 기준에 발생 합니다.  
장치 규정 준수 | 이러한 정책은 기본적으로 모든 Microsoft 관리 되는 데스크톱 장치에 대해 구성 됩니다. 장치를 충족 되지 않으면 다음과 같은 보안 조건 중 하나가 만족 하는 경우 규격이 아닌 것으로 보고 됩니다.<br>-BitLocker 장치 암호화 장치에서 데이터를 보호 하기 위해 사용할 수 있습니다. 자세한 내용은 참조 [개요 (영문)의 BitLocker 장치에서에서 암호화 Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-보안 부팅 사용 하도록 설정 하 고 실행할 수 있으므로 전에 장치에 펌웨어 이미지의 유효성을 검사를 적용 합니다. 자세한 내용은 참조 [보안 부팅 및 장치 암호화 개요.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>Microsoft 관리 되는 데스크톱 장치 로그인에 대 한 암호를 필요합니다.
업데이트 배포 | 비즈니스 (WUfB)에 대 한 Windows Update를 사용 하 여 소프트웨어 업데이트를 점진적으로 배포를 수행 합니다. IT 관리자의 경우에는 배포 그룹 정책에 대 한 설정을 수정할 수 없습니다. 그룹 기반 배포에 대 한 자세한 내용은 [업데이트 처리 되는 방식을](../working-with-managed-desktop/updates.md)참조 하십시오.
원격 분석 | 장치를 Microsoft 알려진된 상업용 식별자에서 향상 된 진단 데이터를 제공 하도록 설정 됩니다. 데스크톱을 관리 하는 Microsoft의 일부로, IT 관리자가 이러한 설정의 변경할 수 없습니다. 고객에 대 한 일반적 데이터 보호 규정 (GDPR) 지역, 최종 사용자를 줄일 수 제공 되는 진단 데이터의 수준을 있지만 서비스 감소 됩니다. 예, Microsoft 관리 되는 데스크톱 설정 및 정책을 성능 및 보안 요구 사항에 가장 부합 하에서 반복 하는 데 필요한 데이터를 수집할 수 없습니다. 자세한 내용은 참조 [조직에서 Windows 구성 진단 데이터.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>보안 addendum

 이 섹션에서는 표준 Microsoft 관리 되는 데스크톱 정책 변수에 대 한 추가으로 배포할 수 있는 정책에 설명 합니다. 표준 정책이 [기본 정책에](#default-policies)나열 됩니다. 이 구성은 금융 서비스 산업을 염두에 매우 규제 된와 디자인: 사용자의 생산성을 유지 하는 동안 가장 안전한 입장을 최적화 합니다.

 ### <a name="additional-security-policies"></a>추가 보안 정책

 이러한 정책은 매우 규제 된 산업 분야에 대 한 보안을 강화 하기 추가 됩니다. 
 - **응용 프로그램 허용 목록**: Microsoft 관리 되는 데스크톱 장치에서 실행 하려면 조직에서 앱을 신뢰 해야 합니다. 잠겨있는 환경을 제공 합니다. Onboarded 되어야 하는 모든 앱 Microsoft 관리 되는 데스크톱 작업 팀에 게 전달 해야 합니다. 자세한 내용은 [Windows Defender 장치 Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)를 참조 하십시오.
 - **보안 모니터링**: Microsoft [Windows Defender 고급 위협 보호](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)를 사용 하 여 장치를 모니터링 합니다. Microsoft는 고객 알림을 생성 하는 위협 감지 될 경우 해당 장치를 분리 하 고 원격으로 문제를 해결 합니다. 

