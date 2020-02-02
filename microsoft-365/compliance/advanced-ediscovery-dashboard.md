---
title: 검토 집합에 대 한 고급 eDiscovery 대시보드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 127e2c9a04977bf6e902a1ce669fa9e4248e3ef2
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662256"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets-preview"></a>검토 집합에 대 한 고급 eDiscovery 대시보드 (미리 보기)

고급 eDiscovery의 경우 검토 해야 하는 문서 및 전자 메일 메시지의 양이 많을 수 있습니다. 검토 프로세스를 시작 하기 전에 모음를 빠르게 분석 하 여 검토 전략을 개발 하는 데 도움이 되는 추세 또는 주요 통계를 파악할 수 있습니다. 이렇게 하려면 검토 집합에 대해 고급 eDiscovery 대시보드를 사용 하 여 모음를 빠르게 분석할 수 있습니다.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>1 단계: 검토 집합 대시보드에 위젯 만들기

1. 보안 & 준수 센터에서 **eDiscovery > Advanced eDiscovery** 로 이동 하 여 조직의 사례 목록을 표시 합니다.
  
2. 기존 사례를 선택 합니다.
  
3. **검토 설정** 탭을 클릭 한 후 검토 집합을 선택 합니다.
  
4. **개별 결과** 드롭다운 목록에서 **검색 프로필 보기**를 클릭 합니다. 

   ![DashbordPivot](media/dashboardpivot.png)

   **검색 프로필 보기** 페이지가 표시 됩니다. 이 페이지를 처음 표시할 때 세 개의 기본 위젯을 표시 합니다.

   ![대시보드](media/dashboardonly.png)
  
5. **새 위젯을** 클릭 하 고 다음 항목 중 하나를 선택 합니다.

   ![새 위젯 드롭다운 목록](media/NewWidgetDropdownBox.png)

   - **라이브러리에서 선택:** 위젯의 기본 라이브러리를 표시 합니다. 위젯을 클릭 한 다음 **추가** 를 클릭 하 여 **검색 프로필 보기** 페이지의 위젯에 추가 합니다.
  
   - **사용자 지정 위젯 만들기:** 사용자 지정 위젯을 설정 하는 데 사용할 수 있는 플라이 아웃 페이지를 표시 합니다. 

6. 사용자 지정 위젯을 만들려면 위젯 플라이 아웃 **추가** 페이지에서 다음을 수행 합니다.

   ![위젯 만들기](media/addwidget.png)

    a. 위젯 제목 표시줄에 표시 되는 위젯 이름을 입력 합니다. Widget 이름은 필수 이지만 widget 데이터를 식별 하는 것이 좋습니다.

    b. 위젯 데이터에 사용 될 속성을 **피벗 선택** 드롭다운 목록에서 선택 합니다. 이 목록의 항목은 검토 집합의 항목에 대 한 검색 가능 속성입니다. 이러한 속성에 대 한 자세한 내용은 [Advanced eDiscovery의 문서 메타 데이터 필드](document-metadata-fields-in-Advanced-eDiscovery.md)를 참조 하십시오. 위젯의 피벗 옵션은이 항목의 **검색 가능한 필드 이름** 열에 표시 됩니다.

    c. 차트 종류를 선택 하 여 선택한 피벗 속성의 데이터를 표시 합니다.

  6. **추가** 를 클릭 하 여 사용자 지정 위젯을 만들고 **검색 프로필 보기** 페이지에 표시 합니다.

## <a name="step-2-create-a-review-set-search-query"></a>2 단계: 검토 집합 검색 쿼리 만들기

1. 위젯 제목 표시줄에서 ... 조건을 클릭 한 다음 **조건 적용**을 **클릭 합니다.**

   ![대시보드](media/searchprofilehome.png)

2. 플라이 아웃 페이지에서 위젯 키 또는 위젯 차트의 요소를 클릭 하 여 필터를 만듭니다.

   ![CreateFilter](media/applyconditionfilter.png)

3. 다른 widget 여러 widget에 대해 1-2 단계를 반복 합니다. 

4. 작업이 완료 되 면 **쿼리로 저장** 을 클릭 하 여 조건을 검토 집합에 대 한 새 검색 쿼리로 저장 합니다.

   ![Query](media/savequery.png)

5. **검색 프로필 보기** 를 닫아 검색 결과 보기로 돌아갑니다.

   시각적 필터를 만든 경우 결과 쿼리가 표시 되는 검색 결과에 적용 되 고 4 단계에서 저장 한 검색 쿼리가 **저장 된 쿼리**아래에 표시 됩니다. 집합 쿼리 검토에 대 한 자세한 내용은 [Query the data in a review set](review-set-search.md)을 참조 하십시오.
