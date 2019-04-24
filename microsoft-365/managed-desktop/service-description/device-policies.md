---
title: 장치 구성
description: Microsoft Managed Desktop 장치에 적용 되는 기본 정책에 대해 알아봅니다.
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a080c044939dfde223c231dfebdd248861d5f9f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278627"
---
# <a name="device-configuration"></a>장치 구성


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

새로운 microsoft managed desktop 장치를 프로 비전 하는 경우에는 microsoft managed desktop에 맞게 최적화 된 구성이 적절 한지 확인 해야 합니다. 여기에는 온 보 딩 프로세스의 일부로 설정 된 기본 정책 집합이 포함 됩니다. 충돌을 방지 하기 위해 이러한 정책을 변경 해서는 안 됩니다. 

장치는 서명 이미지와 함께 도착 하 고 첫 번째 사용자가 로그인 할 때 Azure Active Directory 도메인에 참가 합니다. 장치는 IT 개입 없이 필요한 정책 및 응용 프로그램을 자동으로 설치 합니다.

## <a name="why-mdm-over-group-policy"></a>MDM이 그룹 정책을 초과 하는 이유

그룹 정책 대신 MDM (모바일 장치 관리)을 사용 하는 몇 가지 이유는 다음과 같습니다.

- 보안-MDM 정책은 현대 세상에서 더 안전 합니다. 그룹 정책은 MDM이 클라우드 id 관리 (Azure Active Directory)와 가장 잘 작동 하도록 설계 된 동안 온-프레미스 id와 가장 잘 작동 하도록 설계 되었습니다.
- 안정성-MDM 정책을 통해 보다 안정적인 정책 배포를 제공 합니다. 또한 MDM 설정은 GPO (그룹 정책 개체) 정책을 덮어씁니다. Windows 10부터 버전 1803까지, MDM 설정은 최신 관리로 전환 하는 고객을 지 원하는 그룹 정책 값 보다 우선 순위가 지정 됩니다. 
- Microsoft Managed Desktop 비전과 맞춤-정책 배포를 보다 포괄적으로 모니터링 하 고, 필요한 경우 배포를 일시 중지/다시 시작 하는 기능으로 점진적으로 정책 변경을 단계적으로 롤아웃 하는 그룹 기반 접근 방식을 지원 합니다.

자세한 내용은 [모바일 장치 관리](https://docs.microsoft.com/windows/client-management/mdm/)를 참조 하세요. 

## <a name="default-policies"></a>기본 정책

이 표에는 장치 프로 비전 중에 모든 Microsoft Managed Desktop 장치에 적용 되는 기본 정책이 강조 되어 있습니다. microsoft managed desktop 운영 팀이 승인 하지 않은 모든 검색 변경 내용이 microsoft managed desktop에서 관리 하는 개체를 되돌렸습니다.

정책 | 설명
--- | ---
보안 초기 계획 | MDM 용 [microsoft 보안 기준은](https://docs.microsoft.com/windows/device-security/windows-security-baselines) 모든 Microsoft 관리 데스크톱 장치에 대해 구성 됩니다. 이 기준은 업계 표준 구성입니다. 이 기능은 공개적으로 출시 되 고 테스트 되었으며 microsoft의 관리 되는 데스크톱 장치 및 앱을 최신 회사에서 안전 하 게 유지 하기 위해 마이크로소프트 보안 전문가가 검토 하 고 있습니다. <br><br>지속적으로 진화 하는 보안 위협 가로의 위협을 완화 하기 위해 microsoft 보안 기준은 각 Windows 10 기능 업데이트를 사용 하 여 microsoft 관리 되는 데스크톱 장치에 배포 됩니다.<br><br>자세한 내용은 [Windows 10에 대 한 보안 기준을](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)참조 하십시오.
Microsoft Managed Desktop 권장 보안 서식 파일 | 보안 기준이 사용자 환경을 최적화 하는 권장 변경 사항 집합입니다.  이러한 변경 내용은 [보안 추 록](#security-addendum)에 설명 되어 있습니다. 추 록 정책에 대 한 업데이트는 필요한 기준에 따라 발생 합니다.  
장치 준수 | 이러한 정책은 모든 Microsoft 관리 데스크톱 장치에 대해 기본적으로 구성 됩니다. 다음 보안 조건 중 하나가 충족 되지 않으면 장치가 비규격으로 보고 됩니다.<br>-장치에서 데이터를 보호 하기 위해 BitLocker 장치 암호화를 사용 하도록 설정 합니다. 자세한 내용은 [Windows 10의 BitLocker 장치 암호화 개요](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10) 를 참조 하세요.<br>-보안 부팅을 사용 하도록 설정 하 고 적용 하 여 장치에서 실행 되기 전에 펌웨어 이미지의 유효성을 검사 합니다. 자세한 내용은 [보안 부팅 및 장치 암호화 개요](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview) 를 참조 하세요.<br>-Microsoft Managed Desktop 장치에 로그인 하는 데 암호가 필요 합니다.
업데이트 배포 | WUfB (Windows Update for Business)를 사용 하 여 소프트웨어 업데이트의 점진적 배포를 수행 합니다. IT 관리자는 배포 그룹 정책에 대 한 설정을 수정할 수 없습니다. 그룹 기반 배포에 대 한 자세한 내용은 업데이트를 [처리 하는 방법을](../working-with-managed-desktop/updates.md)참조 하세요.
진단 데이터 | 알려진 상업용 식별자에 따라 Microsoft에 향상 된 진단 데이터를 제공 하도록 장치가 설정 됩니다. Microsoft Managed Desktop의 일부로 IT 관리자는 이러한 설정을 변경할 수 없습니다. gdpr (일반 데이터 보호 규정) 영역에 있는 고객의 경우 최종 사용자는 제공 되는 진단 데이터의 수준을 줄일 수 있지만 서비스 감소가 감소 합니다. 예를 들어 Microsoft Managed Desktop은 성능 및 보안 요구 사항에 맞게 설정 및 정책을 반복 하는 데 필요한 데이터를 수집할 수 없습니다. 자세한 내용은 [조직에서 Windows 진단 데이터 구성](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level) 를 참조 하세요.

 ## <a name="security-addendum"></a>보안 추 록

 이 섹션에서는 표준 Microsoft 관리 데스크톱 정책에 추가 되는 정책에 대해 간략하게 설명 합니다. 표준 정책은 [기본 정책](#default-policies)에 나열 됩니다. 이 구성은 금융 서비스 및 고도로 규제 된 업계에 맞게 설계 되었으며, 사용자 생산성을 유지 하면서 가장 안전한 태세를 최적화 합니다.

 ### <a name="additional-security-policies"></a>추가 보안 정책

 이러한 정책은 고도로 규제 된 업계에 대 한 보안을 강화 하기 위해 추가 됩니다. 
 - **앱 허용 목록**: Microsoft Managed Desktop 장치에서 실행 하려면 조직에서 앱을 신뢰 해야 합니다. 이를 통해 잠긴 환경이 제공 됩니다. 등록 해야 하는 모든 앱은 Microsoft Managed Desktop Operations 팀으로 전달 해야 합니다. 자세한 내용은 [Windows Defender Device Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)를 참조 하세요.
 - **보안 모니터링**: Microsoft는 [Windows Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)을 사용 하 여 장치를 모니터링 합니다. 위협이 검색 되 면 Microsoft는 고객에 게 알리고, 장치를 격리 하 고, 원격으로 문제를 해결 합니다. 

