---
title: Microsoft Managed Desktop을 사용하여 Windows 11 미리 보기 및 테스트
description: 환경에서 Windows 11을 설정하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: de608fa58d0267050b510ef8308d716b608f8e37
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215115"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 사용하여 Windows 11 미리 보기 및 테스트

 사용자 환경 내에서 Windows 11 호환성 테스트 프로그램을 등록하고 참여하는 Microsoft Managed Desktop 방법 일반적으로 11 Windows 및 Microsoft Managed Desktop 자세한 내용은 Windows [11](../intro/win11-overview.md)및 Microsoft Managed Desktop. 

## <a name="add-devices-to-the-windows-11-test-group"></a>Windows 11 테스트 그룹에 장치 추가

요청이 있는 경우 **11을** 테스트하고 평가하기 위한 장치 그룹(최신 작업 공간 - Windows 11 시험판 테스트 장치)을 Windows 있습니다. 이 그룹의 장치는 새로운 Windows 11 빌드 및 Microsoft Managed Desktop 기준 구성을 사용할 수 있으며 안정성 문제를 모니터링합니다.

Windows 11 테스트를 위해 기존 또는 새 장치를 선택할 수 있지만 시험판 빌드에서 결함 또는 호환성 문제가 발생하여 이 그룹에 프로덕션 장치를 등록하면 안 됩니다. 이 그룹에 할당하면 이전 장치 그룹 할당이 제거됩니다.

시험판 테스트 그룹에 장치를 등록하는 경우:

1. 서비스 엔지니어링 팀과 함께 새 서비스 Microsoft Managed Desktop 를 열 수 있습니다.
2. 필드에 다음 값을 사용합니다.
    - 제목: Windows 11 호환성 등록
    - 요청 유형: 변경 요청
    - 범주: 장치
    - 하위 구성: 배포 그룹 할당
3. 설명 필드에 11 테스트에 사용할 장치의 일련 번호를 Windows 나열합니다. 지정된 디바이스가 있는 경우 해당 테넌트에 아직 배포되지 Microsoft Managed Desktop 않습니다.

## <a name="prioritize-applications-to-submit-to-test-base"></a>테스트 기반으로 제출할 응용 프로그램 우선 순위 지정

업무상 중요한 응용 프로그램은 11 환경의 닫힌 환경에서 더 많은 유효성 검사를 Windows 가장 적합한 후보입니다. 사용 현황 및 안정성 데이터를 기반으로 Windows 앱의 우선 순위를 지정할 수 있습니다. 권장 사항을 요청하기 위해 다음 단계를 따르세요.

1. 서비스 엔지니어링 팀과 함께 새 서비스 Microsoft Managed Desktop 를 열 수 있습니다. 요청을 제출하는 방법에 대한 자세한 내용은 관리자 지원을 [참조하세요.](admin-support.md)
2. 필드에 다음 값을 사용합니다.
    - 제목: Windows 11개 테스트 기준 후보
    - 요청 유형: 정보 요청
    - 범주: 앱
    - 하위계정: 기타

## <a name="report-issues"></a>문제 보고

업무 Windows 또는 Microsoft 365 11개 호환성 문제가 발생하는 경우 조사 및 수정을 위해 이를 저희에게 보고하세요. 문제를 보고하기 위해 다음 단계를 수행합니다.

1. 서비스 엔지니어링 팀과 함께 새 서비스 Microsoft Managed Desktop 를 열 수 있습니다.
2. 필드에 다음 값을 사용합니다.
    - 제목: Windows 11 호환성 테스트
    - 요청 유형: 인시던트
    - 범주: 장치
    - 하위ategory: Windows/업데이트
3. 프로덕션 환경에서 비즈니스를 방해하는 동작과 심각하게 설명

Microsoft Managed Desktop 영향에 따라 사전 릴리스 빌드의 문제를 세분화하고 처리합니다. 서비스 설명은 사전 릴리스 빌드의 문제를 다루지 않는 반면, 고객 관리자와 회의하여 사용자 생산성을 차단하는 문제가 특정 테넌트 내에서 마이그레이션을 시작하기 전에 해결되도록 할 것입니다.
