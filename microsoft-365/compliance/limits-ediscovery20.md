---
title: Advanced eDiscovery 제한
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Advanced eDiscovery 솔루션에 적용된 사례 제한, 인덱싱 제한 및 검색 제한에 대해 Microsoft 365.
ms.openlocfilehash: 7771f653550c050250126b7ff93b83ee2e175937
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59188083"
---
# <a name="limits-in-advanced-ediscovery"></a>Advanced eDiscovery 제한 사항

이 문서에서는 Advanced eDiscovery 솔루션의 제한에 대해 Microsoft 365.

## <a name="case-and-review-set-limits"></a>사례 및 검토 집합 제한

다음 표에는 각 사례 및 검토 집합에 대한 제한이 Advanced eDiscovery.

| 제한 설명 | 제한 유형 |
|:-----|:-----|
|사례에 추가할 수 있는 총 문서 수입니다(모든 검토 집합의 경우).  <br/> |3백만 개 <br/> |
|부하 집합당 총 파일 크기입니다. 여기에는 검토 집합에 비 Office 365 로드하는 것이 포함됩니다.  <br/> |300GB <br/> |
|조직의 모든 검토 집합에 매일 로드되는 총 데이터 양입니다.<br/> |2 TB <br/> |
|사례당 최대 부하 집합 수입니다.  <br/> |200 <br/> |
|사례당 최대 검토 집합 수입니다.  <br/> |20 <br/> |
|사례당 최대 태그 그룹 수입니다.  <br/> |1000 <br/> |
|대소문자당 최대 태그 수입니다.  <br/> |1000 <br/> |
|검토 집합에 콘텐츠를 추가할 수 있는 조직의 최대 동시 작업 수입니다. 이러한 작업의 이름은 **검토** 집합에 데이터 추가로  지정되고, 경우에 따라 작업 탭에 표시됩니다.| 10 <sup>4</sup> |
|사용자당 검토 집합에 콘텐츠를 추가할 수 있는 최대 동시 작업 수입니다. 이러한 작업의 이름은 **검토** 집합에 데이터 추가로  지정되고, 경우에 따라 작업 탭에 표시됩니다. | 3  |
|||

## <a name="hold-limits"></a>보류 제한

다음 표에는 사례와 연결된 보류에 대한 제한이 Advanced eDiscovery 나열되어 있습니다.

| 제한 설명 | 제한 유형 |
|:-----|:-----|
|단일 케이스 보류의 최대 사서함 수입니다. 이 제한에는 사용자 사서함의 총 합계와 Microsoft 365, Microsoft Teams 및 그룹과 연결된 Yammer 포함됩니다. <br/> |1,000  <br/> |
|단일 케이스 보류의 최대 사이트 수입니다. 이 제한에는 비즈니스용 OneDrive, SharePoint 사이트, Microsoft 365 그룹, Microsoft Teams 및 Yammer 그룹과 연결된 사이트가 Yammer 포함됩니다.  <br/> |100  <br/> |

## <a name="indexing-limits"></a>인덱싱 제한

다음 표에는 각 항목의 인덱싱 제한이 Advanced eDiscovery.

| 제한 설명 | 제한 유형 |
|:-----|:-----|
|단일 파일에서 추출된 최대 문자 수입니다.  <br/> |<sup>1,000만 개</sup> <br/> |
|단일 파일의 최대 크기입니다.   <br/> |150MB<sup>1</sup> <br/> |
|문서에 포함된 항목의 최대 깊이입니다.  <br/> |25<sup>1</sup> <br/> |
|OCR(광학 문자 인식)에서 처리되는 파일의 최대 크기입니다.  <br/> |24MB<sup>1</sup> <br/>  
|||

## <a name="search-limits"></a>검색 제한

이 섹션에 설명된 제한은 검색 탭의  검색 도구를 사용하여 사례에 대한 데이터를 수집하는 작업과 관련이 있습니다. 자세한 내용은 에서 사례에 대한 데이터 수집을 [Advanced eDiscovery.](collecting-data-for-ediscovery.md)

| 제한 설명 | 제한 유형 |
|:-----|:-----|
|단일 검색에서 검색할 수 있는 최대 사서함 또는 사이트 수입니다. |제한 없음|
|동시에 실행할 수 있는 최대 검색 수입니다. |제한 없음 |
|단일 사용자가 동시에 시작할 수 있는 최대 검색 수입니다. |10  | 
|연산자 및 조건을 포함하여 검색 쿼리의 최대 문자 수입니다. |10,000 &nbsp; <sup>2</sup>|
|연산자 및 조건을 포함하여 SharePoint 및 비즈니스용 OneDrive 쿼리에 대한 최대 문자 수입니다. |10,000<br>와일드카드 &nbsp; <sup>2가 있는 4,000개</sup>|
|와일드카드와일드카드의 최소 알파 문자 수 예를 들어 **1 \* *_ 또는 _ set* 입니다. \***|3  |  
|정확한 구를 검색하기 위해 또는 피두어 와일드카드와 **NEAR** 부울 연산자를 사용할 때 반환되는 최대 변형입니다. |10,000 &nbsp; <sup>3</sup>|
|검색을 위해 미리 보기 페이지에 표시되는 사용자 사서함당 최대 항목 수입니다. 가장 새로운 항목이 표시됩니다. |100|
|검색을 위해 미리 보기 페이지에 표시되는 모든 사서함의 최대 항목 수입니다.|1,000|
|검색 결과에 대해 미리 볼 수 있는 최대 사서함 수입니다.  검색 쿼리와 일치하는 항목이 포함된 사서함이 1,000개가 넘는 경우 미리 보기에 결과가 가장 많은 상위 1,000개 사서함만 미리 보기에 사용할 수 있습니다.|1,000|
|검색을 위해 미리 보기 페이지에 SharePoint 비즈니스용 OneDrive 사이트의 최대 항목 수입니다. 가장 새로운 항목이 표시됩니다. |200|
|검색 SharePoint 비즈니스용 OneDrive 미리 볼 수 있는 최대 사이트 및 사이트 수입니다. 검색 쿼리와 일치하는 항목이 포함된 사이트가 200개가 넘는 경우 결과가 가장 많은 상위 200개 사이트만 미리 보기에 사용할 수 있습니다.|200|
|검색을 위해 미리 보기 페이지에 표시되는 공용 폴더 사서함당 최대 항목 수입니다. |100|
|검색을 위해 미리 보기 페이지에 표시된 모든 공용 폴더 사서함 항목에 있는 최대 항목 수입니다. |200|
|검색 결과에 대해 미리 볼 수 있는 공용 폴더 사서함의 최대 수입니다. 검색 쿼리와 일치하는 항목이 포함된 공용 폴더 사서함이 500개가 넘는 경우 미리 보기에 결과가 가장 많은 상위 500개 사서함만 미리 보기에 사용할 수 있습니다.|500|
|||

## <a name="search-times"></a>검색 시간

Microsoft는 모든 조직에서 실행한 검색에 대한 성능 정보를 수집합니다. 검색 쿼리의 복잡성이 검색 시간에 영향을 줄 수 있지만, 검색 시간에 영향을 미치는 가장 큰 요인은 검색하는 사서함 수입니다. Microsoft는 검색 시간을 위한 서비스 수준 계약을 제공하지는 않습니다. 다음 표에는 검색에 포함된 사서함 수에 따라 컬렉션 검색의 평균 검색 횟수가 나열됩니다.
  
  | 사서함 수 | 평균 검색 시간 |
  |:-----|:-----|
  |100  <br/> |30초  <br/> |
  |1,000  <br/> |45초  <br/> |
  |10,000  <br/> |4분  <br/> |
  |25,000  <br/> |10분  <br/> |
  |50,000  <br/> |20분  <br/> |
  |100,000  <br/> |25분  <br/> |
  |||

## <a name="viewer-limits"></a>뷰어 제한

| 제한 설명 | 제한 유형 |
|:-----|:-----|
|기본 Excel 볼 수 있는 최대 파일 크기입니다.  <br/> |4MB  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a>내보내기 제한 - 검토 집합에서 최종 내보내기

이 섹션에 설명된 제한은 검토 집합에서 문서를 내보내는 경우와 관련이 있습니다.

| 제한 설명 | 제한 유형 |
|:-----|:-----|
|단일 내보내기 최대 크기입니다.|문서 500만 개 또는 500GB(더 작은 문서)|
|검토 집합당 최대 동시 내보내기 수입니다. | 1 |
|||

## <a name="review-set-download-limits"></a>집합 다운로드 제한 검토

| 제한 설명 | 제한 유형 |
|:-----|:-----|
|검토 집합에서 다운로드한 총 파일 크기 또는 최대 문서 수입니다.  <br/> |3MB 또는 문서 <sup>50개</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> 단일 파일 제한을 초과하는 항목은 처리 오류로 표시됩니다.
>
> <sup>2</sup> SharePoint 비즈니스용 OneDrive 검색할 때 검색되는 사이트의 URL에 있는 문자가 이 제한에 해당합니다. 총 문자 수는 다음으로 구성됩니다.<br>
> - 사용자 필드와 필터 필드의 모든 문자
> - 사용자에게 적용되는 모든 검색 권한 필터입니다.
> - 검색에 있는 모든 위치 속성의 문자 여기에는 ExchangeLocation,PublicFolderLocation,SharPointLocation,ExchangeLocationExclusion,PublicFolderLocationExclusion,SharePointLocationExclusion, OneDriveLocationExclusion이 포함됩니다.
>   예를 들어 모든 SharePoint 사이트 및 OneDrive 계정을 포함하면 SharePointLocation 필드와 OneDriveLocation 필드에 모두 "ALL"이라는 단어가 표시될 때 6자까지 계산됩니다.
>
> <sup>3</sup> 구가 아닌 쿼리(두 번의 인용 부호를 사용하지 않는 키워드 값)의 경우 특수한 prefix 인덱스를 사용 합니다. 이렇게 하면 문서에서 단어가 발생하지만 문서에서 단어가 발생하는 위치는 알 수 없습니다. 구 쿼리(두 번의 인용 부호가 있는 키워드 값)를 수행하려면 문서 내의 위치를 구의 단어와 비교해야 합니다. 즉, 구 쿼리에 대해 prefix 인덱스를 사용할 수 없습니다. 이 경우 내부적으로는 가능한 모든 단어가 있는 쿼리를 확장합니다. 예를 들어 **time _ can expand to \* *_*"time OR timer OR times OR timex OR timeboxed OR ..."**. 10,000개 제한은 쿼리와 일치하는 문서 수가 아니라 확장할 수 있는 최대 변형 수입니다. 구문이 아닌 용어의 상한은 없습니다.
>
> <sup>4</sup> 이 제한은 다른 eDiscovery 도구에서 콘텐츠 내보내기와 공유됩니다. 즉, 콘텐츠 검색 및 Core eDiscovery의 동시 내보내기 및 콘텐츠 검토 집합에 콘텐츠를 Advanced eDiscovery 모두 이 제한에 대해 적용됩니다.
>
> <sup>5</sup> 이 제한은 검토 집합에서 선택한 문서를 다운로드하는 데 적용됩니다. 검토 집합에서 문서를 내보내는 데는 적용되지 않습니다. 문서 다운로드 및 내보내기에 대한 자세한 내용은 에서 사례 데이터 [내보내기 를 Advanced eDiscovery.](exporting-data-ediscover20.md)
>
