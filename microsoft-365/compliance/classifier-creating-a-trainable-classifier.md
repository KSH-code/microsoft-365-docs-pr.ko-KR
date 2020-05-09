---
title: Trainable 분류자 만들기 (미리 보기)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 기본 제공 분류자 중 하나가 사용자의 요구 사항을 충족 하지 않는 경우 trainable 분류자를 사용 합니다. Microsoft 365 분류자는 다양 한 유형의 콘텐츠를 확인할 수 있도록 교육을 제공 하는 도구입니다. 이 항목에서는 사용자 지정 분류자를 만드는 방법을 보여 줍니다.
ms.openlocfilehash: 6358f333b274c4a1ce618d87598e7ea5340b77c9
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173510"
---
# <a name="creating-a-trainable-classifier-preview"></a>Trainable 분류자 만들기 (미리 보기)

상자 분류자 중 하나가 사용자의 요구 사항을 충족 하지 않는 경우 trainable 분류자를 사용 합니다. Microsoft 365 분류자는 다양 한 유형의 콘텐츠를 확인할 수 있도록 교육을 제공 하는 도구입니다. 교육 분류자는 먼저 사용자가 선택한 것 이며 범주와 정확히 일치 하는 샘플을 제공 합니다. 그런 다음 처리 된 것으로, 긍정적이 고 부정적 샘플을 함께 제공 하 여 예측을 테스트 합니다.

서로 다른 종류의 분류자에 대 한 자세한 내용은 [trainable 분류자 시작 (미리 보기)](classifier-getting-started-with.md) 을 참조 하십시오.

이 타임 라인은 예제 배포를 반영 합니다.

![trainable-분류자-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Trainable 분류자에 대해 처음으로 옵트인이 필요 합니다. Microsoft 365에서 조직의 콘텐츠를 기준으로 평가 하는 데 12 일이 걸립니다. 전역 관리자에 게 연락 하 여 옵트인 프로세스를 시작 합니다.

## <a name="seed-content"></a>콘텐츠 시드

Trainable 분류자가 특정 콘텐츠 범주에 있는 항목을 독립적으로 식별 하도록 하려면 먼저 범주에 포함 된 콘텐츠 형식의 여러 샘플을 사용 하 여이를 제공 해야 합니다. 이러한 trainable 분류자에 대 한 샘플 공급을 *시드*라고 합니다. 시드 콘텐츠는 사용자가 선택 하 고 콘텐츠 범주를 나타내도록 판단 됩니다.

> [!TIP]
> 최소 50의 양수 500 샘플을 포함 해야 합니다. Trainable 분류자는 가장 최근에 생성 500 된 샘플 (파일을 만든 날짜/시간 스탬프)까지 처리 합니다. 제공 하는 샘플이 많을 수록 분류자가 더 정확 하 게 예측할 수 있습니다.

## <a name="testing-content"></a>콘텐츠 테스트

Trainable 분류자가 예측 모델을 작성 하기에 충분 한 긍정적인 샘플을 처리 한 후에는 해당 분류자가 해당 범주 및 항목과 일치 하는 항목을 올바르게 구분할 수 있는지 여부를 확인 하는 예측을 테스트 해야 합니다. 이 작업을 수행 하면 범주 및 샘플에 포함 되는 샘플로 구성 된 사용자가 선택한 콘텐츠 집합을 다른 사람에 게 공급할 수 있습니다. 이러한 프로세스를 처리 하면 수동으로 결과를 확인 하 여 각 예측이 올바른지, 부정확 한지 또는 확실 하지 않을 지를 확인할 수 있습니다. Trainable 분류자는이 피드백을 사용 하 여 예측 모델을 개선 합니다.

> [!TIP]
> 최상의 결과를 위해서는 테스트 샘플 집합에 1만 항목에 긍정 및 음의 일치를 고르게 분산 하 여 사용 해야 합니다.

## <a name="how-to-create-a-trainable-classifier"></a>Trainable 분류자를 만드는 방법

1. 50-500 seed 콘텐츠 항목을 수집 합니다. 이러한 샘플은 trainable 분류자가 분류 범주에서 진행 되는 것 처럼 식별 하려는 콘텐츠 유형을 강력 하 게 나타내는 예제 일 뿐입니다. 지원 되는 파일 형식에 대해서는 [기본 크롤링 파일 이름 확장명 및 구문 분석 된 파일 형식 SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 를 참조 하세요.

> [!IMPORTANT]
> Seed 및 test 샘플 항목은 암호화 하지 않아야 하며 영어로 되어 있어야 합니다.

> [!IMPORTANT]
> 시드 집합의 항목이 범주의 **강력한** 예 지 확인 합니다. Trainable 분류자는 초기 시드를 기반으로 모델을 만듭니다. 이 분류자는 모든 시드 샘플을 강력 하 게 가정 하며, 샘플이 해당 범주와 가장 약한 지 또는 음의 일치 인지를 알 수 있는 방법이 없습니다.

2. Seed 콘텐츠만 보관 전용으로 설정 된 시드 콘텐츠를 SharePoint Online 폴더에 배치 *합니다.* 사이트, 라이브러리 및 폴더 URL을 기록해 둡니다.

> [!TIP]
> 시드 데이터에 대 한 새 사이트 및 폴더를 만드는 경우 해당 위치에 대해 최소 1 시간 이상 해당 시드 데이터를 사용 하는 trainable 분류자를 만들기 전에이를 인덱싱할 수 있습니다.

3. 준수 관리자 또는 보안 관리자 역할 액세스를 사용 하 여 microsoft 365 준수 센터에 로그인 하 고 **microsoft 365 준수 센터** 또는 **microsoft 365 보안 센터** > **데이터 분류** 열기

4. **Trainable 분류자** 탭을 선택 합니다.

5. **Trainable 분류자 만들기**를 선택 합니다.

6. 이 trainable 분류자가 식별 하 `Name`는 데 `Description` 사용할 항목의 범주에 적절 한 값과 필드를 입력 합니다.

7. 2 단계의 정확한 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 시드 콘텐츠 사이트에 입력 합니다. 을 `Add`선택 합니다.

8. 설정을 검토 하 고를 `Create trainable classifier`선택 합니다.

9. 24 시간 이내에 trainable 분류자는 시드 데이터를 처리 하 고 예측 모델을 작성 합니다. 분류자 상태는 시드 `In progress` 데이터를 처리 하는 중입니다. 분류자가 시드 데이터 처리를 마치면 상태가로 `Need test items`변경 됩니다.

10. 이제 분류자를 선택 하 여 세부 정보 페이지를 볼 수 있습니다.


![trainable 분류자에서 테스트할 준비가 되었습니다.](../media/classifier-trainable-ready-to-test-detail.png)

11. 테스트 콘텐츠 항목을 200 개 이상 수집 합니다. 최상의 결과를 위해 1만을 권장 합니다. 이러한 항목은 강력한 포지티브, 강력한 네거티브 및 해당 특성을 약간 명확 하 게 나타내는 항목과 함께 사용할 수 있습니다. 지원 되는 파일 형식에 대해서는 [기본 크롤링 파일 이름 확장명 및 구문 분석 된 파일 형식 SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 를 참조 하세요.

> [!IMPORTANT]
> 샘플 항목은 암호화 하지 않아야 하며 영어로 되어 있어야 합니다.

12. 테스트 *콘텐츠만*보류 전용으로 설정 된 테스트 콘텐츠를 SharePoint Online 폴더에 배치 합니다. SharePoint Online 사이트, 라이브러리 및 폴더 URL을 기록해 둡니다.

> [!TIP]
> 테스트 데이터에 대 한 새 사이트와 폴더를 만드는 경우 해당 위치에 대해 최소 1 시간 이상 해당 시드 데이터를 사용 하는 trainable 분류자를 만들기 전에이를 인덱싱할 수 있습니다.

13. 을 `Add items to test`선택 합니다.

14. 12 단계에서 테스트 콘텐츠 사이트에 대 한 정확한 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 입력 합니다. 을 `Add`선택 합니다.

15. 을 선택 `Done`하 여 마법사를 완료 합니다. Trainable 분류자는 테스트 파일을 처리 하는 데 최대 1 시간까지 소요 됩니다.

16. Trainable 분류자가 테스트 파일의 처리를 마치면 세부 정보 페이지의 상태가로 `Ready to review`변경 됩니다. 테스트 샘플 크기 `Add items to test` 를 증가 시켜야 하는 경우에는 trainable 분류자가 추가 항목을 처리 하도록 허용 합니다.

![스크린샷 검토 준비 완료](../media/classifier-trainable-ready-to-review-detail.png)

17. 항목 `Tested items to review` 을 검토 하려면 탭을 선택 합니다.

18. Microsoft 365는 한 번에 30 개의 항목을 제공 합니다. 이러한 항목을 검토 하 `We predict this item is "Relevant". Do you agree?` 고 상자에서 `Yes` 또는 `No` 또는 `Not sure, skip to next item`를 선택 합니다. 모델 정확도는 30 개 항목 마다 자동으로 업데이트 됩니다.

![검토 항목 상자](../media/classifier-trainable-review-detail.png)

19. *최소* 200 항목을 검토 합니다.

<!-- insert Analyze steps here-->

20. 정확도가 최소 70%이 고 `Publish the classifier` 상태가 인지 `Ready to use`때까지 계속 검토 합니다.

![정확성과 게시할 준비가 완료 되었습니다.](../media/classifier-trainable-review-ready-to-publish.png)

21. 분류자를 게시 합니다.

22. 게시 한 분류자는 [민감도 레이블이 있는 Office autolabeling](apply-sensitivity-label-automatically.md)의 조건으로 제공 되며, 조건 및 [통신 준수](communication-compliance.md)에 [따라 보존 레이블 정책을 자동으로 적용](labels.md#applying-a-retention-label-automatically-based-on-conditions) 합니다.

> [!CAUTION]
> 일단 분류자가 게시 되 면 추가 교육을 받을 수 없으므로 가능한 한 많은 항목을 테스트 하 고 검토 하 여 정확성을 최대한 높게 유지 해야 합니다.

## <a name="see-also"></a>참고 항목

- [학습 가능한 분류자 시작 (미리 보기)](classifier-getting-started-with.md)
- [SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
