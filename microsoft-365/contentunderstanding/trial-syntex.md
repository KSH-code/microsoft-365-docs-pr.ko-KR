---
title: Microsoft 365 평가판 SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom:
- Adopt
- admindeeplinkMAC
search.appverid: ''
ms.localizationpriority: medium
description: 조직에서 사용할 수 있는 파일럿 프로그램을 계획하고 SharePoint Syntex 방법을 학습합니다.
ms.openlocfilehash: 74b44c14140f26e0744aac73fd948e58d9d33e24
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156381"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>Microsoft 365 평가판 SharePoint Syntex

이 문서에서는 시험 파일럿 프로그램을 설정하고 실행하여 조직에 파일럿 프로그램을 SharePoint Syntex 방법을 설명합니다. 평가판에 대한 모범 사례도 권장됩니다.

## <a name="sign-up-for-a-trial"></a>평가판 등록

평가판을 SharePoint Syntex 30일 동안 300명에게 액세스할 수 있습니다.

> [!NOTE]
> 평가판에는 최대 300명이 포함되어 1,000만 AI 작성기 크레딧을 자동으로 추가합니다. 평가판을 성공하기 위해 300명을 포함할 수 없습니다.

다음 소스 중 하나에서 평가판을 다운로드할 수 있습니다.

- 제품 [SharePoint Syntex 페이지](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- Microsoft 365 관리 센터 [](https://admin.microsoft.com)
    1. [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.
    2. 청구 **구매**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**서비스로 이동**</a>
    3. 아래로 스크롤하여 **추가 기능** 섹션으로 이동합니다.
    4. 타일 SharePoint Syntex 세부 **정보를 선택합니다.**
    5. **사용 가능한 평가판** 을 선택하세요.
    6. 평가판을 확인하기 위해 나머지 마법사 단계를 따릅니다.

평가판을 활성화하려면 Microsoft 365 관리자 또는 대금 청구 관리자 되어야 합니다.

### <a name="who-should-be-involved-in-a-trial"></a>Who 평가판에 참여해야 하는지

|역할|활동|
|---|---|
|Microsoft 365 관리자 또는 대금 청구 관리자|평가판 활성화 및 라이선스 할당|
|Microsoft 365 관리자 또는 SharePoint 관리자|콘텐츠 SharePoint Syntex 구성 및 만들기|
|비즈니스 사용자|모델 구축 및 테스트|

### <a name="before-you-activate-a-trial"></a>평가판을 활성화하기 전에

평가판을 SharePoint Syntex 다음 요인을 고려합니다.

- 가장 의미 있는 테스트는 "실제" 시나리오 및 데이터에 대해 완료됩니다.
- 테넌트당 한 번만 SharePoint Syntex 평가판을 활성화할 수 있습니다.

테스트 또는 데모 테넌트는 "건조 실행"으로 사용하여 정품 인증 단계 및 관리 컨트롤을 단계적으로 진행할 수 있습니다. 그러나 프로덕션 테넌트에서 모델 구축을 평가하는 것이 가장 좋은 것일 수 있습니다.

프로덕션 테넌트에 대한 평가판의 가치를 최대화하기 위해 계획 및 비즈니스 참여가 필수적입니다. 하나 SharePoint Syntex 이상의 비즈니스 영역을 개입하여 3~6개 사용 사례를 식별해야 합니다. 이러한 사용 사례는 다음을 해야 합니다.

- 양식 처리 또는 문서 이해 모델로 해결할 수 있는 시나리오를 포함합니다.
- 추출된 메타데이터의 용도를 명확하게 이해해야 합니다. 예를 들어 보기 서식 또는 자동화를 사용하여 Power Automate. SharePoint Syntex 분류하고 메타데이터를 추출하는 데 초점을 맞추는 동안 수량화할 값은 이 메타데이터에서 사용할 수 있는 값입니다.
- 정의된 데이터 집합을 기반으로 합니다. 예를 들어 특정 SharePoint 라이브러리를 지정합니다. 일반적인 SharePoint Syntex 일반적인 용도의 모델을 모든 조직 콘텐츠에 적용할 수 있습니다. 보다 정확한 보기는 대상 위치의 특정 비즈니스 문제를 해결하는 데 도움이 하도록 모델을 구축했다는 것입니다.

이러한 모든 사용 사례는 이러한 사용 사례에 적합하지 않을 수 SharePoint Syntex. 품질 평가판의 목표는 모든 시나리오에 SharePoint Syntex 증명하는 것이 아닙니다. 대신 평가판을 통해 제품의 가치를 더 잘 이해할 수 있습니다.

계획된 각 사용 사례에 대해 관련 콘텐츠 또는 프로세스의 주제 전문가인 사용자를 식별합니다. 사용자 SharePoint Syntex 만들기는 IT 전문가나 개발자 리소스가 아니라 콘텐츠의 도메인 전문가를 중심으로 합니다.

## <a name="activate-a-trial"></a>평가판 활성화

평가판을 시작할 때 다음을 해야 합니다.

- 관련 사용자에게 라이선스를 할당합니다.
- 의 [추가 설치를 SharePoint Syntex.](set-up-content-understanding.md)
  - 추가 콘텐츠 [센터를 만들 수 있습니다.](create-a-content-center.md)

평가판이 활성화된 후 모델을 만들고 파일을 처리합니다. 모델 [만들기에 대한 지침을 참조하세요.](create-a-content-center.md)

## <a name="during-a-trial"></a>평가판 중

평가 기간은 제한되어 있으므로 처음에는 SharePoint Syntex 모델이 문서를 분류하고 정의된 사용 사례에 대한 메타데이터를 추출할 수 있는지 여부를 중점적으로 설명하는 것이 가장 좋은 것입니다. 평가 기간이 지난 후 메타데이터를 악용할 수 있는 방법을 평가할 수 있습니다.

## <a name="after-a-trial"></a>평가판 이후

평가판의 결과에 따라 평가판의 프로덕션 사용을 진행할지 여부를 결정할 SharePoint Syntex.

### <a name="proceed-to-production-use"></a>프로덕션 사용 진행

서비스의 연속성을 보장하려면 필요한 수의 라이선스를 구매하고 해당 라이선스를 사용자에게 할당해야 합니다. 평가 기간이 끝나면 정식 라이선스가 없는 평가판 사용자는 평가판을 완전히 활용할 수 SharePoint Syntex.

양식 처리의 예상 사용을 예측하고 예상되는 AI 작성기 크레딧의 양을 계획해야 할 수 있습니다. 도움이 필요한 경우 에 적합한 AI 작성기 용량 예측을 [참조합니다.](https://powerapps.microsoft.com/ai-builder-calculator/)

### <a name="dont-proceed-to-production-use"></a>프로덕션 사용을 계속 진행하지 않습니다.

평가판 다음에 라이선스를 구매하지 않는 경우:

- 새 모델을 만들 수 없습니다.
- 모델을 실행 중인 라이브러리는 더 이상 파일을 자동으로 분류하거나 모델을 추출하지 않습니다.
- 이전에 분류된 파일 또는 추출된 메타데이터는 영향을 받지 않습니다.
- 콘텐츠 센터 및 문서 이해 모델은 자동으로 삭제되지 않습니다. 이러한 라이선스는 향후 라이선스를 구매하기로 결정한 경우 계속 사용할 수 있습니다.
- 양식 처리 모델은 기본 Power Platform 환경의 Dataverse(이전 명명된 일반 데이터 서비스 [CDS]) 인스턴스에 저장됩니다. 이러한 라이선스는 Power Platform의 SHAREPOINT SYNTEX 또는 AI 작성기 기능과 함께 향후 라이선싱에 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Microsoft SharePoint Syntex 도입: 시작](adoption-getstarted.md)
