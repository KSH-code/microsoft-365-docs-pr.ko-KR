---
title: 앱 정책 시작
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 앱 정책에 대해 알아보겠습니다.
ms.openlocfilehash: 2f22e56195b94f07a6b8499bd69c60d65f37cce8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190119"
---
# <a name="get-started-with-app-policies"></a>앱 정책 시작

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Microsoft 앱 거버넌스의 앱 정책은 조직에서 앱 규정 준수 관련 특정 요구 사항에 대한 경고 또는 자동 수정을 만들기 위해 사전적 또는 반응적인 환경을 구축합니다.

현재 앱 정책 목록을 보려면 **Microsoft 365 규정 준수 센터 > 앱 거버넌스 > 정책** 으로 이동합니다.

![Microsoft 365 규정 준수 센터의 MAPG 정책 요약 페이지.](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a>앱 정책 대시보드에서 사용할 수 있는 기능

활성, 비활성 및 감사 정책의 수와 각 정책에 대한 다음 정보를 볼 수 있습니다.

- **정책 이름**
- **상태**

  - **활성**: 모든 정책 평가 및 작업이 활성 상태입니다.
  - **비활성**: 모든 정책 평가 및 작업이 비활성 상태입니다.
  - **감사 모드**: 정책 평가가 활성화되어 있지만(경고가 트리거됨) 정책 작업을 사용할 수 없습니다.

- **심각도**: 정책 구성의 일부로 TRUE로 평가되는 정책에 인해 트리거된 모든 경고에 대한 심각도 수준이 설정됩니다.
- **활성 경고 수**: 정책에 의해 생성된 **진행 중** 또는 **새** 상태라는 경고입니다.
- **총 경고 수**: 이 정책의 활성 경고 및 해결된 경고입니다.
- **마지막 경고 날짜**: 마지막으로 이 정책으로 인해 생성된 경고의 날짜입니다.
- **마지막 수정 날짜**: 이 정책이 마지막으로 변경된 날짜입니다.

정책 목록은 기본적으로 **마지막 수정 날짜** 를 기준으로 정렬됩니다. 목록을 다른 앱 특성별로 정렬하려면 특성 이름을 선택합니다.

정책을 선택하면 다음과 같은 추가 세부 정보가 포함된 자세한 정책 창이 표시됩니다.

- **설명**: 정책의 목적에 대한 자세한 설명입니다.
- **만든 사람**: 정책을 만든 계정의 UPN(사용자 계정 이름)입니다.
- 이 정책에 의해 생성된 총 경고와 활성 경고의 목록입니다.

자세한 정책 창에서 **편집** 또는 **삭제** 를 선택하거나 정책 목록에서 정책의 세로 줄임표를 선택하여 앱 정책을 편집하거나 삭제할 수 있습니다.

다음을 수행할 수도 있습니다.

- 새 정책을 만듭니다. 앱 사용 정책 또는 사용 권한 정책으로 시작할 수 있습니다.
- 정책 목록을 쉼표로 구분된 값(CSV) 파일로 내보냅니다. 예를 들어 Microsoft Excel에서 CVS 파일을 열고 **심각도** 별에 이어 **총 경고 수** 별로 정렬할 수 있습니다.
- 정책 목록을 검색합니다.

## <a name="next-step"></a>다음 단계

[앱 정책을 만듭니다.](app-governance-app-policies-create.md)
