---
title: 장치 구성
description: Microsoft Managed Desktop 장치에 적용 되는 기본 정책에 대해 알아봅니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d16f63490de8060eea7ef06a4ad6960d846f16eb
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529388"
---
# <a name="device-configuration"></a>장치 구성


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

새 Microsoft Managed Desktop 장치를 설정 하는 경우 Microsoft Managed Desktop에 대 한 적절 한 구성이 최적화 되어 있는지 확인 합니다. 여기에는 온 보 딩 프로세스의 일부로 설정 된 기본 정책 집합이 포함 됩니다. 이러한 정책은 가능한 경우 MDM (모바일 장치 관리)을 사용 하 여 배달 됩니다. 자세한 내용은 [모바일 장치 관리](https://docs.microsoft.com/windows/client-management/mdm/)를 참조 하세요. 

>[!NOTE]
>충돌을 방지 하기 위해 이러한 정책을 변경해 서는 안 됩니다.

장치가 서명 이미지와 함께 도착 하 고 첫 번째 사용자가 로그인 할 때 Azure Active Directory 도메인에 참가 합니다. 장치는 IT 직원의 개입 없이 필요한 정책 및 응용 프로그램을 자동으로 설치 합니다.

## <a name="default-policies"></a>기본 정책

이 표에는 장치 프로 비전 중에 모든 Microsoft Managed Desktop 장치에 적용 되는 기본 정책이 강조 되어 있습니다. Microsoft Managed Desktop 운영 팀이 승인 하지 않은 모든 검색 변경 내용이 Microsoft Managed Desktop에서 관리 하는 개체를 되돌렸습니다.

정책 | 설명
--- | ---
보안 초기 계획 | MDM 용 [microsoft 보안 기준은](https://docs.microsoft.com/windows/device-security/windows-security-baselines) 모든 Microsoft 관리 데스크톱 장치에 대해 구성 됩니다. 이 기준은 업계 표준 구성입니다. 이 기능은 공개적으로 출시 되 고 테스트 되었으며 microsoft의 관리 되는 데스크톱 장치 및 앱을 최신 회사에서 안전 하 게 유지 하기 위해 마이크로소프트 보안 전문가가 검토 하 고 있습니다. <br><br>지속적으로 진화 하는 보안 위협 요소에서 위협을 완화 하기 위해 Microsoft 보안 기준은 각 Windows 10 기능 업데이트를 사용 하 여 Microsoft Managed Desktop 장치에 배포 됩니다.<br><br>자세한 내용은 [Windows 보안 기준을](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)참조 하십시오.
Microsoft Managed Desktop 권장 보안 서식 파일 | 보안 기준이 사용자 환경을 최적화 하는 권장 변경 사항 집합입니다.  이러한 변경 내용은 [보안 추 록](#security-addendum)에 설명 되어 있습니다. 추 록 정책에 대 한 업데이트는 필요한 기준에 따라 발생 합니다.  
업데이트 배포 | 비즈니스용 Windows 업데이트를 사용 하 여 소프트웨어 업데이트의 점진적 배포를 수행 합니다. IT 관리자는 배포 그룹 정책에 대 한 설정을 수정할 수 없습니다. 그룹 기반 배포에 대 한 자세한 내용은 [Microsoft Managed Desktop에서 업데이트를 처리 하는 방법을](updates.md)참조 하세요.
데이터 통신 연결 | 기본적으로 LTE 네트워크와 같은 유료 연결을 통한 업데이트는 사용 되지 않지만 각 사용자는 **고급 옵션 > 업데이트 > 설정**에 독립적으로이 기능을 켤 수 있습니다. 모든 사용자가 데이터 통신 연결을 통해 업데이트를 사용 하도록 허용 하려면 모든 장치에 대해이 설정을 사용 하는 [변경 요청을 제출](../working-with-managed-desktop/admin-support.md)합니다.
| 장치 준수 | 이러한 정책은 모든 Microsoft 관리 데스크톱 장치에 대해 구성 됩니다. 장치가 필요한 보안 구성에서 drifts 때 비 준수로 보고 됩니다.

## <a name="diagnostic-data"></a>진단 데이터

 알려진 상업용 식별자에 따라 Microsoft에 향상 된 진단 데이터를 제공 하도록 장치가 설정 됩니다. Microsoft Managed Desktop의 일부로 IT 관리자는 이러한 설정을 변경할 수 없습니다. GDPR (일반 데이터 보호 규정) 영역에 있는 고객의 경우 최종 사용자는 제공 되는 진단 데이터의 수준을 줄일 수 있지만 서비스 감소가 감소 합니다. 예를 들어 Microsoft Managed Desktop은 성능 및 보안 요구 사항에 맞게 설정 및 정책을 반복 하는 데 필요한 데이터를 수집할 수 없습니다. 자세한 내용은 [조직에서 Windows 진단 데이터 구성](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level) 를 참조 하세요.

## <a name="security-addendum"></a>보안 추 록

 이 섹션에서는 [기본 정책](#default-policies)에 나열 된 표준 Microsoft 관리 되는 데스크톱 정책 외에도 배포 되는 정책에 대해 설명 합니다. 이 구성은 재무 서비스 및 높은 규제 업계를 염두에 두고 설계 되어 있으며, 사용자 생산성을 유지 하면서도 가장 높은 수준의 보안을 최적화 합니다.

 ### <a name="additional-security-policies"></a>추가 보안 정책

 높은 규제 대상 업계에 대 한 보안을 강화 하기 위해 이러한 정책이 추가 됩니다. 
 - **보안 모니터링**: Microsoft는 [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)을 사용 하 여 장치를 모니터링 합니다. 위협이 검색 되 면 Microsoft는 고객에 게 알리고, 장치를 격리 하 고, 원격으로 문제를 해결 합니다. 
 - **Powershell V2 사용 안 함**: Microsoft에서 Powershell V2 8 월 2017을 제거 했습니다. 이 기능은 모든 Microsoft 관리 되는 데스크톱 장치에서 사용 하지 않도록 설정 되었습니다. 이 변경 사항에 대 한 자세한 내용은 [Windows PowerShell 2.0](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)을 참조 하십시오.
