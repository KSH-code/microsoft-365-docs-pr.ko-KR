---
title: 통신 규정 준수에서 분류자 재조정 방법
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 커뮤니케이션 규정 준수에서 학습 가능한 분류자에 피드백을 제공하는 방법을 학습합니다.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752652"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>통신 규정 준수에서 분류자 재조정 방법

Microsoft 365 학습 가능한 분류자는 다양한 유형의 콘텐츠를 인식할 수 있는 도구로, 살펴보기 위한 샘플을 제공합니다. 교육이 이행된 후 이를 사용하여 Office 민감도 레이블, 커뮤니케이션 준수 정책 및 보존 레이블 정책의 적용을 위한 항목을 식별할 수 있습니다.

이 문서에서는 사용자 지정 학습 가능한 분류자 및 사전 학습된 일부 분류자에 대한 성능을 개선하는 방법을 보여 주며 추가 피드백을 제공합니다.

다양한 분류자 유형에 대한 자세한 내용은 학습 가능한 분류자에 [대한 자세한 내용을 참조합니다.](classifier-learn-about.md)

## <a name="permissions"></a>권한

Microsoft 365 규정 준수 센터에서 분류자에 액세스하는 경우:

- 분류자 교육을 위해 준수 관리자 역할 또는 준수 데이터 관리자 필요

이러한 시나리오에서 분류기를 사용하려면 다음 권한이 있는 계정이 필요합니다.

- 커뮤니케이션 준수 정책 시나리오: 내부자 위험 관리 관리자, 관리 검토 관리자 

## <a name="overall-workflow"></a>전체 워크플로

> [!IMPORTANT]
> 분류기를 조건으로 사용하는 준수 솔루션에 피드백을 제공합니다. **분류기를 조건으로 사용하는 통신 준수 정책이 없는 경우 여기에서 중지하세요.**

분류기를 사용할 때 분류하는 분류의 정밀도를 높이는 것이 더 나을 수 있습니다. 이 작업을 위해 일치하는 것으로 식별되거나 일치하지 않은 것으로 식별된 항목에 대한 분류 품질을 평가합니다. 분류자에 대해 30회 평가를 수행한 후 해당 피드백을 반영하고 자동으로 자체적으로 다시 제한합니다.

분류자 재조정의 전체 워크플로에 대한 자세한 내용은 분류자 재조정에 대한 프로세스 흐름을 [참조하세요.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> 분류자는 이미 게시되어 있으며 사용 중이면 다시 사용할 수 있습니다.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>통신 준수 정책에서 분류자 재조정 방법

1. 분류기를 조건으로 사용하는 통신 준수 정책을 열고 보류 중인 목록에서 식별된 항목 중 **하나를** 선택합니다.
2. 타원을 선택하고 **분류를 개선합니다.**
3. 세부 **피드백 창에서** 항목이 실제 양수이면 일치 항목을 **선택하십시오.**  항목이 범주에 잘못 포함되어 있는 경우 일치하지 **않음을 선택합니다.**
4. 항목에 더 적합한 다른 분류자인 경우 교육 가능한 다른 분류자 제안 목록에서 선택할 **수** 있습니다. 이렇게 하면 다른 분류자에서 항목을 평가합니다.

> [!TIP]
> 여러 항목을 모두 선택한 다음 명령 표시줄에서  자세한 피드백 제공을 선택하여 여러 항목에 대한 피드백을 동시에 제공할 수 있습니다.

5. 피드백 **보내기를** 선택하면 평가를 보내고 교육 가능한 다른 분류자도 `match` `not a match` 제안할 수 있습니다. 분류자에 30개 피드백 인스턴스를 제공하면 자동으로 재조정됩니다. 재조정에는 1~4시간이 걸릴 수 있습니다. 분류자에는 하루 두 번만 재조정할 수 있습니다.

> [!IMPORTANT]
> 이 정보는 테넌트의 분류자로 이동하고 **Microsoft로 돌아가지 않습니다.**

6.  **Microsoft 365** 규정 **준수** 센터에서 데이터 분류 페이지를 여십시오.
7. 학습 **가능한 분류자 열기.**
8. 커뮤니케이션 준수 정책에 사용된 분류자는 재 교육 **제목에** 표시됩니다.

![재조정 상태의 분류자](../media/classifier-retraining.png)

9. 재 교육이 완료되면 분류기를 선택해 재조정 개요를 열 수 있습니다.

![분류자 재조정 결과 개요](../media/classifier-retraining-overview.png)

10. 권장 작업과 재조정된 분류자 및 현재 게시된 버전의 예측 비교를 검토합니다.
11. 재작성 결과가 만족스러우면 다시 게시를 **선택 합니다.**
12. 재실행 결과에 만족하지 않는 경우 통신 준수 인터페이스에서 분류자에 추가 피드백을 제공하고 다른 재조정 주기를 시작하거나, 현재 게시된 분류자 버전이 계속 사용되는 경우 아무 것도 하지 않을 수 있습니다. 

## <a name="details-on-republishing-recommendations"></a>권장 사항 다시 게시에 대한 세부 정보

다음은 재조정된 분류자 다시 게시 또는 추가 재조정을 제안하기 위한 권장을 수식화하는 방법에 대한 약간의 정보입니다. 이를 위해서는 학습 가능한 분류자 작동 방식에 대해 좀 더 깊이 이해해야 합니다.

재조정 후 피드백이 있는 항목과 원래 분류자 교육에 사용된 모든 항목에 대해 분류자 성능을 평가합니다. 

- 기본 제공 모델의 경우 분류자 학습에 사용되는 항목은 모델을 빌드하는 데 Microsoft에서 사용하는 항목입니다.
- 사용자 지정 모델의 경우 원래 교육에 사용된 항목 분류자는 테스트 및 검토를 위해 추가한 사이트의 항목입니다.

재게시 및 게시된 분류자에 대한 두 항목 집합의 성능 수를 비교하여 재게시 개선이 있는지 여부를 권장합니다. 

## <a name="see-also"></a>참고 항목

- [학습 가능한 분류자에 대해 자세히](classifier-learn-about.md)
- [SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
