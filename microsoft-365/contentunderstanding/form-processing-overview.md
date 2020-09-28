---
title: 양식 처리 개요
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint Syntex의 양식 처리에 대해 자세히 알아보기
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295179"
---
# <a name="form-processing-overview-preview"></a>양식 처리 개요 (미리 보기)

이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기에 대 한 것입니다. [자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.

Project Cortex에서는 Microsoft PowerApps [AI 작성기](https://docs.microsoft.com/ai-builder/overview) 양식 처리를 사용 하 여 SharePoint 문서 라이브러리 내에서 모델을 만듭니다.

AI Builder 양식 처리 기능을 사용 하 여 기계 학습 기술을 사용 하는 AI 모델을 만들어 양식 및 송장과 같은 구조화 되거나 반구조적 문서에서 키-값 쌍 및 테이블 데이터를 식별 하 고 추출할 수 있습니다.

AI Builder 양식 처리 기능을 사용 하 여 ML (기계 학습) 기술을 활용 하는 AI 모델을 만들어 양식 및 송장 같은 구조화 된 문서 또는 반구조적 문서의 키-값 쌍 및 테이블 데이터를 식별 하 고 추출할 수 있습니다.

조직은 종종 메일, 팩스, 전자 메일 등의 다양 한 원본에서 송장을 많이 받습니다. 이러한 문서를 처리 하 고이를 데이터베이스에 수동으로 입력 하면 상당한 시간이 소요 될 수 있습니다. AI를 사용 하 여 문서에서 텍스트, 키/값 쌍 및 표를 추출 하면 양식 처리가이 프로세스를 자동화 합니다. 

예를 들어 문서 라이브러리에 업로드 되는 모든 구매 주문 문서를 식별 하는 양식 처리 모델을 만들 수 있습니다. 각 구매 주문에서 *PO 번호*, *날짜*또는 *총 비용*같은 중요 한 특정 데이터를 추출 하 여 표시할 수 있습니다.

샘플 파일을 사용 하 여 모델을 학습 하 고 양식에서 추출할 정보를 정의할 수도 있습니다. 모델을 학습 하면 문서의 레이아웃을 알 수 있습니다. 시작 하려면 양식 문서가 5 개 이상 필요 합니다. AI 건물에서는 주요 키-값 쌍에 대 한 샘플 파일을 분석 한 다음 검색 되지 않았을 수 있는 항목을 수동으로 식별 합니다.  AI 작성기에서는 샘플 파일의 모델 정확성을 테스트할 수 있습니다.

모델을 훈련 하 고 게시 한 후에는 SharePoint 문서 라이브러리에 파일을 업로드 한 후에 실행 되는 [전원 자동화 흐름](https://docs.microsoft.com/power-automate/getting-started) 을 만드는 데 사용 됩니다. 그런 다음 모델에서 식별 된 데이터를 추출 합니다. 추출 된 데이터는 모델의 문서 라이브러리 보기에 열에 표시 됩니다.

샘플 파일을 사용 하 여 모델을 학습 하 고 양식에서 추출할 정보를 정의 합니다. 모델을 학습 하면 문서의 레이아웃을 알 수 있습니다. 시작 하려면 양식 문서가 5 개 필요 합니다. AI Builder는 키-값 쌍에 대 한 예제 파일을 분석 하 고 검색 되지 않았을 수 있는 항목을 수동으로 식별할 수도 있습니다.  AI 작성기에서는 샘플 파일의 모델 정확성을 테스트할 수 있습니다.

모델을 학습 하 고 게시 한 후에는 [전원 자동화 흐름](https://docs.microsoft.com/power-automate/getting-started)을 만드는 것입니다. 파일을 SharePoint 문서 라이브러리에 업로드 하 고 모델에서 식별 된 데이터를 추출할 때 흐름이 실행 됩니다. 추출 된 데이터는 모델의 문서 라이브러리 보기에 열에 표시 됩니다.

사용자가 SharePoint 문서 라이브러리에서 양식 처리 [모델을 만들](create-a-form-processing-model.md) 수 있도록 하려면 Office 365 관리자가 해당 [양식을 처리](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) 해야 합니다.

## <a name="see-also"></a>참고 항목
  
[파워 자동화 설명서](https://docs.microsoft.com/power-automate/)</br>
[양식 처리 모델 만들기](create-a-form-processing-model.md)</br>
[문서 이해 개요](document-understanding-overview.md)</br>
[교육: AI Builder를 사용 하 여 비즈니스 성과 개선](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
