---
title: Microsoft SharePoint Syntex의 양식 처리 개요
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft SharePoint Syntex의 양식 처리 모델에 대해 알아봅니다.
ms.openlocfilehash: 8079f12c3b05d62de95bcb08808d1acc931a37d7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189252"
---
# <a name="form-processing-overview-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex의 양식 처리 개요

 ![AI 작성기.](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex는 Microsoft Power Apps [AI 작성기](/ai-builder/overview) 양식 처리를 사용하여 SharePoint 문서 라이브러리내에 모델을 만듭니다.

AI 작성기 양식 처리를 사용하여 기계 학습 기술로 양식 및 송장과 같은 구조적 또는 반구조적 문서에서 키-값 쌍과 테이블 데이터를 식별하고 추출하는 AI 모델을 만들 수 있습니다.

조직은 종종 메일, 팩스, 전자 메일 등과 같은 다양한 출처로부터 다량의 송장을 받습니다. 이러한 문서를 수동으로 데이터베이스에 입력해 처리하기 위해서는 많은 시간이 소요됩니다. AI를 사용하여 문서에서 텍스트, 키/값 쌍 및 표를 추출하는 양식 처리 프로세스를 자동화합니다. 

> [!NOTE]
> 양식 처리 시나리오 예제에 대한 자세한 내용은 [SharePoint Syntex 채택: 시작 가이드](./adoption-getstarted.md)를 참조하세요.

예를 들어 문서 라이브러리에 업로드 되는 모든 구매 주문 문서를 식별하는 양식 처리 모델을 만들 수 있습니다. 각 구매 주문서에서 *PO 번호*, *날짜* 또는 *전체 비용* 과 같이 사용자에게 중요 한 특정 데이터를 추출하여 표시할 수 있습니다.

![문서 라이브러리 보기.](../media/content-understanding/doc-lib-done.png)</br>  

예제 파일을 사용하여 모델을 훈련시키고 양식에서 추출할 정보를 정의할 수 있습니다. 문서의 레이아웃은 모델 교육을 통해 배울 수 있습니다. 5개의 양식 문서가 있으면 시작 할 수 있습니다. AI 작성기는 예제 파일에서 키-값 쌍을 분석하고 사용자는 감지되지 않은 정보를 수동으로 식별할 수 있습니다.  AI 작성기는 예제 파일에서 모델의 정확도를 테스트 하도록 합니다.

모델을 훈련하고 게시하면 모델은 [파워 자동화 흐름](/power-automate/getting-started)을 만듭니다. 파일이 SharePoint 문서 라이브러리에 업로드 되면 흐름이 실행되고 모델에서 식별된 데이터를 추출합니다. 추출 된 데이터가 모델의 문서 라이브러리 보기에서 열에 표시 됩니다.

Office 365 관리자는 SharePoint 문서 라이브러리 [양식 처리 사용을 설정](./set-up-content-understanding.md)을 하여 사용자가 [양식 처리 모델 만들기](create-a-form-processing-model.md)를 할 수 있도록 해야 합니다. 설치 중 또는 관리 설정에서 설정 후에 사이트를 선택할 수 있습니다.

### <a name="file-limitations"></a>파일 제한 사항

폼 처리 모델을 사용할 때 [파일 사용에 대한 요구 사항과 제한 사항](/ai-builder/form-processing-model-requirements)을 기록해야 합니다.

### <a name="multi-geo-environments"></a>Multi-Geo 환경

[Microsoft 365 Multi-Geo 환경](../enterprise/microsoft-365-multi-geo.md)에서 SharePoint Syntex를 설정할 때는 중앙 위치에서 양식 처리를 사용하도록만 구성할 수 있습니다. 위성 위치에서 양식 처리를 사용하려는 경우 Microsoft 지원에 문의하세요.






## <a name="see-also"></a>참고 항목
  
[파워 자동화 문서](/power-automate/)

[양식 처리 모델 만들기](create-a-form-processing-model.md)

[문서 이해 개요](document-understanding-overview.md)

[교육: AI 작성기를 사용하여 비즈니스 성과 개선](/learn/paths/improve-business-performance-ai-builder/?source=learn)