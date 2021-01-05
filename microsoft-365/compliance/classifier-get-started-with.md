---
title: 학습 가능한 분류자 시작
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 분류자에서는 볼 샘플을 제공하여 다양한 유형의 콘텐츠를 인식할 수 있는 도구입니다. 이 문서에서는 사용자 지정 분류기를 만들고 교육하는 방법과 정확도를 높이기 위해 분류기를 다시 학습하는 방법을 보여집니다.
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752662"
---
# <a name="get-started-with-trainable-classifiers"></a>학습 가능한 분류자 시작

Microsoft 365 학습 가능한 분류자는 다양한 유형의 콘텐츠를 인식할 수 있는 도구로, 살펴보기 위한 샘플을 제공합니다. 교육이 이행된 후 이를 사용하여 Office 민감도 레이블, 커뮤니케이션 준수 정책 및 보존 레이블 정책의 적용을 위한 항목을 식별할 수 있습니다.

학습 가능한 사용자 지정 분류자 만들기는 먼저 해당 범주와 일치하는 사람이 선택된 샘플을 제공해야 합니다. 그런 다음 분류자에 양수 샘플과 음의 샘플을 혼합하여 예측할 수 있는 기능을 테스트합니다. 이 문서에서는 사용자 지정 분류기를 만들고 교육하는 방법과 재 교육을 통해 학습 가능한 사용자 지정 분류자 및 사전 학습된 분류자의 성능을 개선하는 방법을 보여줍니다.

다양한 분류자 유형에 대한 자세한 내용은 학습 가능한 분류자에 [대한 자세한 내용을 참조합니다.](classifier-learn-about.md)

## <a name="prerequisites"></a>필수 구성 요소

### <a name="licensing-requirements"></a>라이선스 요구 사항

분류기는 Microsoft 365 E5 또는 E5 규정 준수 기능입니다. 이러한 구독을 사용하려면 이러한 구독 중 하나만 있어야 합니다.

### <a name="permissions"></a>권한

UI의 분류자에 액세스하는 경우: 

- 전역 관리자는 테넌트에 대해 옵트인(opt in)하여 사용자 지정 분류를 만들어야 합니다.
- 분류자 교육을 위해서는 준수 관리자 역할이 필요합니다.

이러한 시나리오에서 분류기를 사용하려면 다음 권한이 있는 계정이 필요합니다.

- 보존 레이블 정책 시나리오: 레코드 관리 및 보존 관리 역할 
- 민감도 레이블 정책 시나리오: 보안 관리자, 준수 관리자, 준수 데이터 관리자
- 커뮤니케이션 준수 정책 시나리오: 내부자 위험 관리 관리자, 관리 검토 관리자 

> [!IMPORTANT]
> 기본적으로 사용자 지정 분류자를 만든 사용자만 해당 분류자에 의해 만들어진 예측을 학습하고 검토할 수 있습니다.

## <a name="prepare-for-a-custom-trainable-classifier"></a>학습 가능한 사용자 지정 분류자 준비 

학습 가능한 사용자 지정 분류자 만들기와 관련된 것을 이해하면 도움이 됩니다. 

### <a name="timeline"></a>시간 표시 막대

이 타임라인은 학습 가능한 분류자에 대한 샘플 배포를 반영합니다.

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> 학습 가능한 분류자에 대해 옵트인(opt-in)이 처음 필요합니다. Microsoft 365에서 조직 콘텐츠에 대한 기준 평가를 완료하는 데 12일이 걸립니다. 전역 관리자에게 문의하여 옵트인 프로세스를 시작하십시오.

### <a name="overall-workflow"></a>전체 워크플로

학습 가능한 사용자 지정 분류자 만들기의 전체 워크플로에 대한 자세한 내용은 학습 가능한 고객 분류자 만들기를 위한 프로세스 흐름을 [참조하세요.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)

### <a name="seed-content"></a>시드 콘텐츠

학습 가능한 분류자를 통해 특정 콘텐츠 범주에 속하는 것으로 항목을 독립적으로 정확하게 식별하려는 경우 먼저 범주에 속하는 콘텐츠 형식의 많은 샘플을 제공해야 합니다. 학습 가능한 분류자에 샘플을 공급하는 이를 시드라고 *합니다.* 시드 콘텐츠는 사람이 선택하며 콘텐츠의 범주를 나타내는 것으로 판단됩니다.

> [!TIP]
> 최소 50개의 양의 샘플과 500개가 필요합니다. 학습 가능한 분류자는 가장 최근에 만든 500개 샘플(파일 생성 날짜/타임스탬프를 통해)까지 처리합니다. 샘플을 더 많이 제공할수록 분류자는 예측의 정확도를 더 정확하게 예측할 수 있습니다.

### <a name="testing-content"></a>콘텐츠 테스트

학습 가능한 분류자에서 예측 모델을 빌드하기 위해 충분한 양의 샘플을 처리한 후 예측을 테스트하여 분류가 범주와 일치하는 항목과 일치하지 않는 항목을 올바르게 구분할 수 없는지 확인해야 합니다. 이 작업을 위해 범주에 속해야 하는 샘플과 원하지 않는 샘플로 구성된 사람이 선택한 다른 콘텐츠 집합을 선택합니다. 처음에 제공한 시드 데이터와는 다른 데이터로 테스트해야 합니다. 이러한 결과를 처리하고 나면 수동으로 결과를 거치고 각 예측이 올바르지 않거나, 잘못된지 또는 확실하지 않은지 확인합니다. 학습 가능한 분류기는 이 피드백을 사용하여 예측 모델을 개선합니다.

> [!TIP]
> 최상의 결과를 얻기 위해 테스트 샘플 집합에 200개 이상의 항목이 있으며 양수와 음의 일치 항목이 고율로 분포되어 있습니다.

## <a name="how-to-create-a-trainable-classifier"></a>학습 가능한 분류자 만들기 방법

1. 50-500개 사이의 시드 콘텐츠 항목을 수집합니다. 이러한 샘플은 학습 가능한 분류자에서 분류 범주에 속하는 것으로 확인하려는 콘텐츠의 유형을 강력하게 나타내는 샘플만 있어야 합니다. 지원되는 파일 형식에 대한 [SharePoint Server의](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 크롤링된 기본 파일 이름 확장명 및 구문 분석된 파일 형식을 참조합니다.

   > [!IMPORTANT]
   > 시드 및 테스트 샘플 항목은 암호화되지 말고 영어로 표시되어야 합니다.

   > [!IMPORTANT]
   > 시드 집합의 항목이 범주의  강력한 예가 되어 있는지 확인합니다. 학습 가능한 분류기는 처음에 시드한 것을 기반으로 모델을 빌드합니다. 분류자에서는 모든 시드 샘플이 강력한 양수로 가정하며, 샘플이 범주와 약한 또는 음수 일치인지를 알 수 없습니다.

2. 시드 콘텐츠만 보유하는 전용 SharePoint Online 폴더에 *시드 콘텐츠를 배치합니다.* 사이트, 라이브러리 및 폴더 URL을 메모합니다.

   > [!TIP]
   > 시드 데이터에 대한 새 사이트 및 폴더를 만드는 경우 해당 시드 데이터를 사용할 학습 가능한 분류기를 만들기 전에 적어도 1시간 동안 해당 위치를 인덱싱하도록 허용합니다.

3. 준수 관리자 또는 보안 관리자 역할 액세스로 Microsoft 365 규정 준수 센터에 로그인하고 **Microsoft 365** 규정 준수 센터 또는 Microsoft **365** 보안 센터 데이터 분류를  >  **하세요.**

4. 학습 가능한 **분류자 탭을** 선택합니다.

5. 학습 **가능한 분류자 만들기를 선택 합니다.**

6. 학습 가능한 분류자를 식별할 항목 범주의 필드 및 해당 값을 `Name` `Description` 입력합니다.

7. 2단계에서 시드 콘텐츠 사이트의 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 선택합니다. Choose `Add` .

8. 설정을 검토하고 `Create trainable classifier` 선택합니다.

9. 학습 가능한 분류자는 24시간 이내에 시드 데이터를 처리하고 예측 모델을 빌드합니다. 분류자 상태는 시드 `In progress` 데이터를 처리하는 동안입니다. 분류자에서 시드 데이터 처리를 마치면 상태가 으로 `Need test items` 변경됩니다.

10. 이제 분류기를 선택하여 세부 정보 페이지를 볼 수 있습니다.

    > [!div class="mx-imgBorder"]
    > ![학습 가능한 분류자 테스트 준비](../media/classifier-trainable-ready-to-test-detail.png)

11. 최상의 결과를 얻으 위해 최소 200개 이상의 테스트 콘텐츠 항목(최대 10,000개)을 수집합니다. 이러한 항목은 강력한 양성, 강력한 부정 및 특성상 약간 명확하지 않다고 생각할 수 있는 항목의 혼합이 틀려야 합니다. 지원되는 파일 형식에 대한 [SharePoint Server의](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 크롤링된 기본 파일 이름 확장명 및 구문 분석된 파일 형식을 참조합니다.

    > [!IMPORTANT]
    > 샘플 항목은 암호화되지 말고 영어로 번역해야 합니다.

12. 테스트 콘텐츠만 보유하는 전용 SharePoint Online *폴더에 테스트 콘텐츠를 배치합니다.* SharePoint Online 사이트, 라이브러리 및 폴더 URL을 확인합니다.

    > [!TIP]
    > 테스트 데이터에 대한 새 사이트 및 폴더를 만드는 경우 해당 시드 데이터를 사용할 학습 가능한 분류기를 만들기 전에 적어도 한 시간 동안 해당 위치를 인덱싱하도록 허용합니다.

13. Choose `Add items to test` .

14. 12단계에서 테스트 콘텐츠 사이트의 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 선택합니다. Choose `Add` .

15. 를 선택하여 마법사를 `Done` 완료합니다. 학습 가능한 분류자는 테스트 파일을 처리하는 데 최대 1시간이 소요됩니다.

16. 학습 가능한 분류자는 테스트 파일 처리를 완료하면 세부 정보 페이지의 상태가 `Ready to review` 으로 변경됩니다. 테스트 샘플 크기를 증가해야 하는 경우 학습 가능한 분류기를 선택하고 추가 항목을 처리하도록 `Add items to test` 허용합니다.

    > [!div class="mx-imgBorder"]
    > ![스크린샷을 검토할 준비가 완료되었습니다.](../media/classifier-trainable-ready-to-review-detail.png)

17. 항목을 `Tested items to review` 검토할 탭을 선택합니다.

18. Microsoft 365는 한에 30개 항목을 제시합니다. 검토하고 상자에 다음 중 하나 또는 를 `We predict this item is "Relevant". Do you agree?` `Yes` `No` `Not sure, skip to next item` 선택합니다. 모델 정확도는 30개 항목마다 자동으로 업데이트됩니다.

    > [!div class="mx-imgBorder"]
    > ![검토 항목 상자](../media/classifier-trainable-review-detail.png)

19. 200개 이상의 항목을 검토합니다.  정확도 점수가 안정화되면  게시 옵션을 사용할 수 있으며 분류자 상태가 `Ready to use` 표시됩니다.

    > [!div class="mx-imgBorder"]
    > ![정확도 점수 및 게시 준비](../media/classifier-trainable-review-ready-to-publish.png)

20. 분류자 게시

21. 분류자가 게시된 후 민감도 레이블이 있는 [Office](apply-sensitivity-label-automatically.md)자동 레이블 [지정에서](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) 조건으로 사용할 수 있습니다. 조건 및 커뮤니케이션 규정 준수에 따라 보존 레이블 정책을 자동으로 [적용합니다.](communication-compliance.md)
