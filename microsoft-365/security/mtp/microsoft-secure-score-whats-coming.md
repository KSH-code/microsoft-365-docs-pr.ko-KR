---
title: Microsoft 보안 점수가 어떻게 제공 됩니까?
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 세부 정보를 계산 하는 방법 및 보안 관리자가 예상할 수 있는 사항에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 점수, 보안 센터, 개선 작업
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895444"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft 보안 점수가 어떻게 제공 됩니까?

Microsoft의 보안 점수를 보안 환경을 보다 효율적으로 대표 하 고 유용성을 향상 시키기 위해 곧 몇 가지 사항을 변경 하 고 있습니다. 점수와 가능한 최대 점수가 변경 됩니다. 그러나 보안 환경을 변경 하는 것은 아닙니다.

최근 변경 내용에 대 한 자세한 내용은 [Microsoft 보안 점수의 새로운 기능](microsoft-secure-score.md#whats-new) 을 참조 하세요.

## <a name="april-21st-2020"></a>4 월 21 일 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업을 제거 하거나 보안 환경을 효과적으로 표현 하지 않습니다.

Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.

- 지난 30 일 동안 사용 되지 않은 계정 삭제/차단
- 전역 관리자를 5 명 미만으로 지정
- 문서에 IRM 보호 적용
- 데이터 손실 방지 정책 적용

### <a name="adding-additional-control-support-in-the-preview-version"></a>미리 보기 버전에서 컨트롤 지원 추가
- 사용자가 관리 되지 않는 응용 프로그램에 동의 하도록 허용 하지 않습니다 (현재 릴리스된 버전에서 사용 가능).

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a>추가 Microsoft Cloud App Security 개선 작업 지원
- 도메인 컨트롤러에서 인쇄 스풀러 서비스 사용 안 함
- 가장을 방지 하도록 보안 되지 않은 Kerberos 위임 수정
- Microsoft 랩를 사용 하 여 로컬 관리자 암호 보호 및 관리
- 중요 한 엔터티에 대 한 측면 이동 경로 위험 감소
- 중요 한 그룹에서 유휴 계정 제거
- 엔터티에서 보안 되지 않은 SID 기록 특성 제거
- 보안 되지 않은 계정 특성 확인
- 일반 텍스트 자격 증명 노출 중지
- 레거시 프로토콜 통신 중지
- 약한 암호화 사용 중지

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>TVM (Microsoft Defender ATP Threat &) 보안 권장 사항에 대 한 지원
- 이제 TVM에서 제공 하는 모든 릴리스된 보안 권장 사항을 Microsoft 보안 점수 에서도 사용할 수 있습니다.
