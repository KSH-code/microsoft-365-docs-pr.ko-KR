---
title: 1단계. Syntex를 SharePoint 사용하여 계약 파일을 식별하고 데이터 추출
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Syntex를 사용하여 SharePoint 솔루션을 사용하여 계약 파일을 식별하고 데이터를 추출하는 Microsoft 365 대해 알아보십시오.
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281342"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>1단계. Syntex를 SharePoint 사용하여 계약 파일을 식별하고 데이터 추출

조직에서는 받은 많은 파일에서 모든 계약 문서를 식별하고 분류하는 방법이 필요합니다. 또한 식별된 각 계약 파일의 여러 주요 요소(예: *클라이언트,* 계약자 및 수수료 금액)를 빠르게 볼 *수 있습니다.* 이 작업을 위해 [Syntex를](index.md) SharePoint 문서 이해 모델을 만들어 문서 라이브러리에 적용할 수 있습니다.

[문서 이해는](document-understanding-overview.md) 인공 지능(AI) 모델을 사용하여 파일 분류 및 정보 추출을 자동화합니다. 문서 이해 모델은 필요한 정보가 테이블이나 양식(예: 계약)에 포함되어 있지 않은 구조화되지 않은 문서 및 반구조적 문서에서 정보를 추출할 때도 최적의 모델입니다.

1. 먼저 식별하려는 콘텐츠 형식(계약)에 특정한 특성을 검색하기 위해 모델을 "학습"하는 데 사용할 수 있는 5개 이상의 예제 파일을 찾아야 합니다. 

2. Syntex를 SharePoint 새 문서 이해 모델을 만들어야 합니다. 예제 파일을 사용하여 분류자 [를 만들어야 합니다.](create-a-classifier.md) 분류자에 예제 파일을 교육하여 회사 계약에서 볼 수 있는 특징을 검색하도록 교육합니다. 예를 들어 서비스 계약, 계약 조건 및 보상과 같이 계약에 있는 특정 문자열을 검색하는 ["설명"을](create-a-classifier.md#create-an-explanation) *만들 수 있습니다.* 문서의 특정 섹션에서 또는 다른 문자열 옆에 있는 이러한 문자열을 검색하도록 설명을 교육할 수도 있습니다. 필요한 정보를 사용하여 분류자 교육을 했다고 생각되는 경우 예제 파일 예제 집합에서 모델을 테스트하여 효율성을 볼 수 있습니다. 테스트 후 필요한 경우 설명을 보다 효율적으로 변경하기 위해 변경할 수 있습니다. 

3. 모델에서 각 계약에서 특정 데이터 조각을 끌어오는 추출기 만들기를 만들 수 있습니다. [](create-an-extractor.md) 예를 들어 각 계약에 대해 가장 우려되는 정보는 클라이언트의 사용자, 계약자 이름 및 총 비용입니다.

4. 모델을 성공적으로 만든 후 SharePoint [라이브러리에 적용합니다.](apply-a-model.md) 문서 라이브러리에 문서를 업로드하면 문서 이해 모델이 실행되고 모델에서 정의한 계약 콘텐츠 형식과 일치하는 모든 파일을 식별하고 분류합니다. 계약으로 분류된 모든 파일은 사용자 지정 라이브러리 보기에 표시됩니다. 파일에는 추출기에서 정의한 각 계약의 값도 표시됩니다.

   ![문서 라이브러리의 계약](../media/content-understanding/doc-lib-solution.png)

5. 또한 계약에 대한 보존 요구 사항이 있는 경우 모델을 사용하여 [](apply-a-retention-label-to-a-model.md) 지정된 기간 동안 계약이 삭제되지 않도록 하는 보존 레이블을 적용할 수도 있습니다.

## <a name="next-step"></a>다음 단계

[2단계. 이 Microsoft Teams 사용하여 계약 관리 채널 만들기](solution-manage-contracts-step2.md)