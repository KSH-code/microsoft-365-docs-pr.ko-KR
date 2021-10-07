---
title: Blackboard Microsoft Teams 클래스 사용
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: Blackboard Microsoft Teams 클래스 사용
ms.openlocfilehash: b74aaca3df01b2e6f222605f3700066c980cd9bd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170118"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a>Blackboard Microsoft Teams 클래스 사용

팀워크는 모든 최신 조직의 핵심입니다. 공동 작업을 육성하여 성공적인 모든 기관의 특징을 정의합니다. 각 클래스와 페어링하여 Blackboard Learn Ultra의 모든 기능과 Microsoft Teams 있습니다.

클래스에는 실시간 대화, 비디오 모임 또는 비동기 조작이 포함되어 있을 수 있습니다. 학생을 위한 파일 공유 및 공동 준비 환경을 한 장소에 모두 추가할 수 있습니다. Microsoft Teams 학습을 통해 교육의 역동성 및 효과적인 학습의 의미를 다시 정합니다.

> [!IMPORTANT]
> [SIS(학생](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning) 정보 시스템)에서 기관 전자 메일 필드를 성공적으로 설정해야 합니다.
>
>Microsoft Teams 클래스 통합은 SIS의 기관 전자 메일 필드를 통해 AAD(Microsoft Azure Active Directory) [UPN(사용자](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes)원칙 이름)에 매핑됩니다. 기관 전자 메일이 프로비전되지 않은 경우 이 전자 메일은 기본적으로 기존 전자 메일로 설정됩니다. 데이터가 올바르게 동기화되도록 모든 사용자에 대해 이 필드를 설정하고 AAD와 Blackboard Learn Ultra 간에 전자 메일 데이터가 충돌하지 않도록 하는 것이 좋습니다.
>
> SIS 매핑에서 이 필드를 적절하게 설정하지 않은 경우 통합이 계속 작동하지만 사용자가 만든 Teams 나타나지 않을 수 있으며 오류가 발생할 수 있습니다.

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a>기관 데이터 매핑 지원 - 기관 전자 메일 SIS 필드

클라우드 공급자 통합의 일부로 Blackboard Learn Ultra는 학생  정보 시스템 프레임워크 통합과 공용 REST API 모두에 새로운 기관 전자 메일 필드를 만들어 기관이 Blackboard Learn Ultra와 AAD 간에 데이터 동기화 프로세스를 효과적으로 관리할 수 있도록 합니다.

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a>기관 전자 메일의 의미와 지원 여부

기관 **전자 메일 필드를** 사용하면 클라이언트의 외부에서 지원되는 데이터 원본과 Blackboard Learn Ultra 간에 사용자 지정된 필드 매핑을 사용할 수 있습니다. 데이터 원본이 Microsoft와 같은 클라우드 공급자인 경우 UPN(사용자 원칙 이름)은 @ 기호와 함께 가입된 UPN 접두사(사용자의 계정 이름)와 UPN 접미사(DNS 도메인 이름)로 구성된 각 사용자의 기본 고유 식별자입니다. 이렇게 하면 사용자 계정 내의 각 특정 사용자에 대해 고유한 전자 메일 Microsoft Azure Active Directory.

데이터가 정확하고 Blackboard Learn Ultra 및 Microsoft Teams 클래스 간의 등록 또는 멤버 자격이 올바르게 달성되도록 보장하려면 사용자의 전자 메일 주소가 두 시스템 간에 일치해야 합니다. Blackboard Learn Ultra에서 사용자는 사용자 인터페이스에서 기존 전자 메일 주소를 변경하거나 이로 인해 동기화 오류가 발생하고 사용자가 수업 팀에 올바르게 추가되지 않을 수 있습니다. 기관 **전자 메일** 필드 매핑을 사용하면 사용자가 Blackboard Learn Ultra 내에서 전자 메일을 변경한 경우와 관계없이 이 수준의 보안 및 유효성 검사 검사를 올바르게 관리할 수 있습니다.

 두 전자 메일 주소가 서로 다른 경우 다음 중 하나를 사용합니다.

- 우선 순위를 가지는 원본에 대한 결정을 내리고 개인 및 기관 전자 메일로 취해야 합니다.
  또는
- 기관은 기관 전자 메일에서 사용자 정의 필드 매핑을 설정하여 잠재적인 충돌을 해결할 수 있습니다.

이제 **고급** 구성에서 모든 기존 SIS 통합 유형에 대해 기관 **전자 메일** 필드 매핑을 사용할 설정 개체 유형 필드 매핑을 사용할 수  >    >  **있습니다.**

> [!NOTE]
> 기본적으로 기관 전자 메일은 모든 SIS 형식에 대해  개인 전자 메일로 설정되어 있으며 각 사용자에 대해 고유해야 합니다.  전자 메일이 중복될 경우 SIS에서 사용자를 가져오지 못하기 때문에 설정 및 실행 중인 모든 기존 통합에는 이 데이터 매핑이 설정됩니다. 기관에서 기관 전자 메일을 사용자 지정으로 변경할 수 있는 기능을 요구하는  경우 SIS의 고급 구성 설정 관리해야 합니다.

## <a name="requirements"></a>요구 사항

이 Microsoft Teams 통합은 울트라 코스 보기 과정에만 **사용할 수 있습니다.** 해당 기관에서 다음 요구 사항을 충족해야 합니다.

- 초고속 탐색을 사용하도록 설정한 Blackboard가 매우 자세히 학습 SaaS를 사용하도록 설정

  ![이 기능의 예는 과정에서 사용하도록 설정됩니다.](media/feature-availability.png)

- 과정에 사용할 LTI를 사용하도록 설정

  a. 관리자 패널   >  **LTI 도구 공급자 전역** 속성 관리 로  >  **이동하세요.**

  b. 과정에서 **LTI 사용 을 선택하고** 원하는 경우 **조직에서 사용 을 선택합니다.**

  c. **전송** 을 선택합니다.

- LTI가 구성되어 있어야 합니다.

- Add Blackboard Learn Ultra Teams Classes LTI Integration

- 추가 Microsoft Teams 클래스 LTI 1.3 도구

- REST API 도구 및 원본 간 리소스 공유 추가

- 통합 클래스 Microsoft Teams 구성 및 승인

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a>Blackboard Learn Ultra Teams 클래스 LTI 1.3 도구 추가

1. 관리자 **패널에서** **LTI 도구 공급자 를 선택합니다.**

2. **LTI 1.3 도구 등록을 선택합니다.**

3. 클라이언트 **ID 필드에** 이 ID를 입력하거나 복사하여 붙여넣습니다.

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. 미리 채워진 모든 설정을 검토하고 도구 상태 에서 **를** 검토한 다음 사용 을 **선택합니다.**

5. 기관 **정책에서** 과정의 **역할,** 이름 및 전자 메일 주소를 선택한 다음 둘 **다에 대해 예를** 선택합니다.

6. 등급 **서비스 액세스 허용 및** 멤버 자격 서비스 액세스 **허용을 선택합니다.**

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a>Microsoft Teams 클래스 LTI 1.3 도구 추가

1. 관리자 **패널에서** **LTI 도구 공급자 를 선택합니다.**

2. **LTI 1.3 도구 등록을 선택합니다.**

3. 클라이언트 **ID 필드에** 이 ID를 입력하거나 복사하여 붙여넣습니다.

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. 미리 채워진 모든 설정을 검토하고 도구 상태를 *검토하고* 사용 을 *선택합니다.*

5. 기관 **정책에서** **과정의 역할, 이름 및** 전자 메일 주소를 **선택합니다.** 둘 **다에 대해 예를** 선택합니다.

6. 등급 **서비스 액세스 허용 및** 멤버 자격 서비스 액세스 **허용을 선택합니다.**

## <a name="add-the-rest-api-tool"></a>REST API 도구 추가

1. 관리자 **패널에서** 통합으로 **이동하고** **Rest API Integrations 를 선택합니다.**

2. 통합 **만들기를 선택합니다.**

3. 응용 **프로그램 ID 필드에** 이 ID를 입력하거나 복사하여 붙여넣습니다.

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. 이 통합에 대한 사용자를 입력합니다.

   이 사용자는 응용 프로그램이 연결된 홈 API 액세스 권한이 있는 사용자가 됩니다.

5. **전송** 을 선택합니다.

## <a name="add-the-cross-origin-resource-sharing"></a>원본 간 리소스 공유 추가

1. 관리자 **패널에서** 통합으로 **이동하고** * 원본 간 리소스 공유 *를 선택합니다.*

2. 구성 **만들기를 선택합니다.**

3. 원본 **필드에** 이 URL을 복사하여 붙여넣습니다.

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. 허용되는 **헤더 필드에** 권한 부여 를 **입력합니다.**

5. 사용 **가능을 예로** **설정**

6. **전송** 을 선택합니다.

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a>통합 클래스 Microsoft Teams 구성 및 승인

Blackboard Learn Ultra 인스턴스를 Microsoft Teams 클래스와 성공적으로 통합하려면 Blackboard Learn Ultra 응용 프로그램이 Microsoft Azure 테넌트 내에서 액세스가 승인되어 있는지 확인해야 합니다. 이 프로세스는 기관의 전역 관리자가 Microsoft 365 합니다.

이 프로세스는 Blackboard Learn Ultra Instance에서 LTI 응용 프로그램을 구성하기 전이나 후에 완료할 수 있습니다.

### <a name="before-configuring-the-lti-applications"></a>LTI 응용 프로그램을 구성하기 전에

LTI 통합을 구성하기 전에 Blackboard Learn Ultra Teams Classes Azure 앱을 승인하려면 Microsoft Identity Platform 관리자 동의 끝점으로 **리디렉션해야 합니다.** URL이 표시됩니다.

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> **{Tenant}를** 특정 기관용 테넌트 Microsoft Azure 대체합니다.

사용자에게 액세스 권한을 Blackboard Learn Ultra에 부여할 수 있는 권한을 설명하는 사용 권한 창이 Microsoft Teams.

![Microsoft 및 Blackboard에 대한 사용 권한 창입니다.](media/permissions1.png)

### <a name="after-configuring-the-lti-applications"></a>LTI 응용 프로그램 구성 후

1. 관리자 **패널에서** 도구  및 유틸리티로 이동하고 통합 **Microsoft Teams 선택합니다.**

2. 에서 **사용 을 Microsoft Teams.**

3. 사용 가능한 **텍스트 필드에 Microsoft 테넌트 ID를** 추가합니다.

4. 다음 옵션 중 하나를 선택합니다.

   - 앱에 사전 동의가 있는 경우 작은 확인 표시가 표시 됩니다. 확인 표시가 나타나면 제출을 **선택합니다.**

   - 동의가 승인되지 않은 경우 설명된 단계에 따라 동의를 위해 URL을 생성하고 승인을 위해 Microsoft 365 전역 관리자에게 전송합니다.

5. 승인을 확인한 후 다시 **시도를** 선택하여 확인한 다음 제출을 **선택합니다.**
