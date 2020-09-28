---
title: 추출기를 만들 때 용어 저장소 분류 활용
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint Syntex의 모델을 이해 하는 문서에서 추출기를 만들 때 용어 저장소 분류법을 활용 합니다.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296012"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>추출기를 만들 때 용어 저장소 분류 활용


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

문서에 SharePoint Syntex의 모델을 이해 하는 추출기를 만들 때 [관리 되는 메타 데이터 서비스](https://docs.microsoft.com/sharepoint/managed-metadata#terms) 용어 저장소 분류를 활용 하 여 추출한 데이터에 대 한 기본 용어를 표시할 수 있습니다.  

예를 들어 모델은 문서 라이브러리에 업로드 되는 모든 **계약** 문서를 식별 하 고 분류 합니다.  또한 모델은 각 계약에서 **계약 서비스** 값을 추출 하 고이를 라이브러리 보기의 열에 표시 합니다. 계약의 다양 한 계약 서비스 값 중에는 회사에서 더 이상 사용 하지 않고 이름이 바뀐 이전 값이 여러 개 있습니다. 예를 들어 *디자인*, *그래픽*또는 *Topography* 계약 서비스 라는 용어에 대 한 모든 참조를 이제 *Creative*이라고 합니다. 모델이 계약 문서에서 오래 된 용어 중 하나를 추출한 경우 라이브러리 보기에 현재 용어 소재를 표시 하도록 할 수 있습니다. 아래 예제에서는 모델을 교육 하는 동안 해당 샘플 문서에는 오래 된 *디자인*용어가 포함 된 것으로 표시 됩니다.

   ![용어 저장소](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>용어 집합 동의어 

용어 집합은 SharePoint 관리 센터의 Managed Metadata service 용어 저장소에 구성 됩니다. 아래 예에서 *계약 서비스* [용어 집합](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) 은 *소재*를 비롯 한 여러 용어를 포함 하도록 구성 됩니다.  이에 대 한 세부 정보는 용어에 세 개의 동의어 (*디자인*, *그래픽*및 *Topography*)가 있음을 보여 *줍니다.*

   ![용어 집합](../media/content-understanding/term-store.png)</br>

여기서는이를 설명 하는 방법에 대해 잘 모르는 <합니다.  어떤 작업을 수행 하 여 계약 서비스 열을 추출 하 고 표시 하는 추출기를 만들 때 "표시" 열이 Creative Services에 대해 관리 되는 메타 데이터 용어 집합을 사용 하는 방법은 무엇 인가요? >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>관리 되는 메타 데이터 필드에 대 한 문서 라이브러리 사이트 열 구성


   ![관리 되는 메타 데이터 만들기](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>참고 항목
[관리 되는 메타 데이터 소개](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[추출기 만들기](create-an-extractor.md)</br>
[관리되는 메타데이터 열 만들기](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





