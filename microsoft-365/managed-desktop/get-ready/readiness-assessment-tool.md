---
title: 준비 상태 평가 도구
description: 도구 실행에 대 한 검사 및 결과의 의미에 대해 설명 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e2d1c68c3fe963c957e4c3e18fce441b92c96bf1
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519824"
---
# <a name="readiness-assessment-tool"></a>준비 상태 평가 도구

Microsoft Managed Desktop에 등록할 때 발생할 수 있는 환경에 대 한 원활한 다양 한 설정과 기타 매개 변수를 미리 설정 해야 합니다. 이 도구를 사용 하 여 해당 설정을 확인 하 고, 적절 하지 않은 문제를 해결 하기 위한 자세한 단계를 받을 수 있습니다.

이 도구는 microsoft Endpoint Manager (특히, Microsoft Intune), Azure Active Directory (Azure AD) 및 microsoft 365의 설정을 검사 하 여 Microsoft Managed Desktop에서 작동 하도록 합니다. Microsoft Managed Desktop은 Azure AD 조 직 (테 넌 트)에서 검사를 마지막으로 실행 한 후 12 개월 동안 이러한 검사와 관련 된 데이터를 보존 합니다. 12 개월 후에는 식별 되지 않은 형식으로 보존 됩니다.  수집한 데이터를 삭제 하도록 선택할 수 있습니다.

적어도 Intune 관리자 역할을 가진 모든 사용자는이 도구를 실행할 수 있지만 두 가지 검사 ([조건부 액세스 정책](readiness-assessment-fix.md#conditional-access-policies) 및 [다단계 인증](readiness-assessment-fix.md#multi-factor-authentication) 에 추가 권한이 필요 함)가 있습니다.
 
평가 도구는 다음 항목을 확인 합니다.

## <a name="microsoft-intune-settings"></a>Microsoft Intune 설정

|수표  |설명  |
|---------|---------|
|Autopilot 배포 프로필     | Autopilot 배포 프로필의 할당이 모든 장치에 적용 되지 않는지 확인 합니다 (프로필을 Microsoft Managed Desktop 장치에 *할당 하면 안 됩니다.* ).       |
|인증서 커넥터     | 인증서 커넥터의 상태를 검사 하 여 활성 상태임을 확인 합니다.   |
|조건부 액세스     | 조건부 액세스 정책이 모든 사용자에 게 할당 되지 않았는지 확인 합니다 (조건부 액세스 정책을 Microsoft Managed Desktop service 계정에 할당할 수 *없음* ).    |
|장치 준수 정책     | Intune 준수 정책이 모든 사용자에 게 할당 되어 있지 않은지 확인 합니다 (이 정책은 어떠한 Microsoft 관리 되는 데스크톱 장치에도 지정 *되지* 않아야 함).    |
|장치 구성 프로필     | 구성 프로필이 모든 사용자 또는 모든 장치에 할당 되지 않았는지 확인 합니다 (구성 프로필을 Microsoft Managed Desktop 장치에 할당 *하지* 않아야 함).     |
|장치 유형 제한     | 조직의 Windows 10 장치가 Intune에서 등록을 허용 하는지 확인 합니다.        |
|등록 상태 페이지     | 등록 상태 페이지가 사용 하도록 설정 되지 않았음을 확인 합니다.      |
|Intune 등록     | Azure AD 조직의 Windows 10 장치가 Intune에 자동으로 등록 되는지 확인 합니다.         |
|비즈니스용 Microsoft Store     | Microsoft Store for Business가 사용 하도록 설정 되었으며 Intune과 동기화 되는지 확인 합니다.        |
|다단계 인증 | Multi-factor authentication이 Microsoft Managed Desktop service 계정에 적용 되지 않는지 확인 합니다.
|PowerShell 스크립트     | Microsoft Managed Desktop 장치를 대상으로 하는 방식으로 Windows PowerShell 스크립트가 할당 *되지 않음* 을 확인 합니다.    |
|지역     | Microsoft Managed Desktop에서 해당 지역이 지원 되는지 확인 합니다.        |
|보안 기준     | 보안 기본 프로필이 모든 사용자 또는 모든 장치를 대상으로 하지 않는지 확인 합니다 (보안 기본 정책은 Microsoft Managed Desktop 장치를 대상으로 *하지* 않아야 함).       |
|Windows 앱     | Microsoft Managed Desktop 장치에 할당할 앱 검토      |
|비즈니스용 Windows Hello     | 비즈니스용 Windows Hello가 사용 되도록 설정 되었는지 확인 합니다.        |
|Windows 10 업데이트 링     | Intune의 "Windows 10 업데이트 링" 정책이 모든 사용자 또는 모든 장치를 대상으로 하지 않는지 확인 합니다 (정책이 Microsoft Managed Desktop 장치를 대상으로 *하지* 않아야 함).     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory 설정

|수표  |설명  |
|---------|---------|
|엔터프라이즈 상태 로밍에 대 한 "Ad hoc" 구독     | "False"로 설정 된 경우 엔터프라이즈 상태 로밍이 제대로 작동 하지 않는 설정을 확인 하는 방법을 제안 합니다.  |
|Enterprise State Roaming     | 엔터프라이즈 상태 로밍이 사용 하도록 설정 되었는지 확인 하는 방법을 제안 합니다.       |
|라이선스     | 필요한 [라이선스](prerequisites.md#more-about-licenses) 를 가져왔는지 확인 합니다.         |
|다단계 인증     | Multi-factor authentication이 모든 사용자에 게 적용 되지 않는 것을 확인 합니다 (다단계 인증은 실수로 Microsoft Managed Desktop service 계정에 적용 되지 않아야 함).|
|보안 계정 이름   | Microsoft Managed Desktop이 자체 사용을 위해 예약한 사용자 이름과 충돌 하는 것을 확인 합니다.        |
|보안 관리자 역할     | 끝점에 대 한 Microsoft Defender에서 보안 판독기, 보안 운영자 또는 전역 독자 역할을 할당 받은 사용자에 게 해당 역할을 지정 했는지 확인 합니다.         |
|보안 기본값 | Azure AD 조직이 Azure Active Directory에서 보안 기본값을 사용 하는지 여부를 확인 합니다. |
|셀프 서비스 암호 재설정     | 셀프 서비스 암호 재설정이 사용 하도록 설정 되어 있는지 확인        |
|표준 사용자 역할     | 사용자가 표준 사용자이 고 로컬 관리자 권한이 없는지 확인 합니다.         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 Apps for enterprise 설정

|수표  |설명  |
|---------|---------|
|비즈니스용 OneDrive     | 비즈니스용 OneDrive에서 지원 되지 않는 설정을 사용 하는지 여부를 확인 합니다.        |


각 검사에 대해이 도구는 다음과 같은 네 가지 가능한 결과 중 하나를 보고 합니다.


|결과  |의미  |
|---------|---------|
|맞춤형     | 등록을 완료 하기 전에 작업을 수행할 필요가 없습니다.        |
|조언    | 등록 및 사용자를 위한 최상의 환경을 위한 도구에 나와 있는 단계를 수행 합니다. 등록을 완료할 *수* 있지만 첫 번째 장치를 배포 하기 전에 이러한 문제를 해결 해야 합니다.        |
|준비되지 않음 | 이러한 문제를 해결 하지 않으면 *등록에 실패* 합니다. 도구의 단계에 따라 문제를 해결 합니다.        |
|오류 | 사용 중인 Azure 활성 디렉터 (AD) 역할에이 검사를 실행할 수 있는 충분 한 권한이 없습니다. |
