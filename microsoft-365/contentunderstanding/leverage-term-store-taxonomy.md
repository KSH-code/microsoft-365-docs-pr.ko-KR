---
title: Microsoft SharePoint Syntex에서 추출기를 만들 때 용어 저장소 분류/분류법 활용
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
description: Microsoft SharePoint Syntex의 문서 이해 모델에서 추출기를 만들 때 용어 저장소 분류를 사용하세요.
ms.openlocfilehash: dd064a1e93692f79b5cfc5417b0b5b09df09c9fd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197488"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex에서 추출기를 만들 때 용어 저장소 분류/분류법 활용

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

SharePoint Syntex를 사용하여 문서 이해 모델에서 추출자를 생성할 때 [ 용어 저장소](/sharepoint/managed-metadata)의 글로벌 용어 세트를 활용하여 추출하는 데이터에 대한 선호 용어를 표시할 수 있습니다.  

예를 들어, 모델은 문서 라이브러리에 업로드 되는 모든 **계약서** 를 식별하고 분류합니다.  또한 모델은 각 계약서에서 **계약 서비스** 값을 추출하고 라이브러리 보기의 열에 표시합니다. 계약서의 다양한 계약 서비스에는 회사가 더 이상 사용하지 않고 이름이 변경 된 여러가지 이전 값이 있습니다. 예를 들어 *디자인*, *그래픽* 또는 *지형* 계약 서비스에 대한 모든 참조는 이제 *창의성* 이라고 불립니다. 모델이 계약 문서에서 오래 된 용어를 추출할 때 사용자는 라이브러리 보기에서 현재 용어인 창의성을 보기 원합니다. 아래 예제에서 모델 교육을 하는 동안 예시 문서에 *디자인* 의 오래된 용어가 포함되어 있는 것이 보입니다.

   ![용어 저장소.](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a>추출기에서 관리되는 메타데이터 열 사용

용어 집합은 SharePoint 관리 센터에서 MMS(관리되는 메타데이터 서비스) 용어 저장소에 구성 됩니다. 아래 예제에서 *계약 서비스* [용어 집합](/sharepoint/managed-metadata#term-set)은 *창의성* 을 포함하여 여러 용어를 포함하도록 구성되어 있습니다.  세부 내역에는 용어에 세 가지의 동의어(*디자인*, *그래픽* 및 *지형*)가 있다고 보여주며 이 동의어는 *창의성* 이라고 해석되어야 합니다. 

   ![용어 집합.](../media/content-understanding/term-store.png)</br>

용어 집합에서 동의어를 사용하는데는 여러 이유가 있습니다. 예를 들어, 이름을 지을 때 예전에 사용된 용어, 이름이 바뀐 용어 혹은 조직 부서간에 다르게 사용되는 용어가 있을 수 있습니다.

모델에서 추출기를 만들 때 관리되는 메타데이터 필드를 선택하도록 하려면 [관리되는 메타데이터 사이트 열로 추가](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f)해야 합니다. 사이트 열을 추가한 후 모델에 대한 추출기를 만들 때 선택할 수 있습니다.

   ![계약 서비스.](../media/content-understanding/contract-services.png)</br>

문서 라이브러리에 모델을 적용 한 후 문서가 라이브러리에 업로드 되면 추출자가 동의어 값(*디자인*, *그래픽*, 및 *지형*)을 찾으면 *창의성 서비스* 칼럼이 기본 용어(*창의성*)로 보여집니다.

   ![계약 서비스 열.](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>참고 항목
[관리되는 메타데이터 소개](/sharepoint/managed-metadata#terms)

[추출자 만들기](create-an-extractor.md)

[관리되는 메타데이터 열 만들기](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)