---
title: Advanced eDiscovery 대시보드에서 검토 집합
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 검토 집합에 Advanced eDiscovery 대시보드를 사용하여 신속하게 코퍼스를 분석하여 검토 전략을 개발하는 데 도움이 되는 추세 또는 주요 통계를 식별합니다.
ms.openlocfilehash: b7bc487e95c2dbae1a65aaad94face6bee19d39b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175482"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>Advanced eDiscovery 대시보드에서 검토 집합

경우에 따라 Advanced eDiscovery 검토해야 하는 대량의 문서 및 전자 메일 메시지가 있을 수 있습니다. 검토 프로세스를 시작하기 전에 신속하게 코퍼스를 분석하여 검토 전략을 개발하는 데 도움이 되는 추세 또는 주요 통계를 식별할 수 있습니다. 이렇게 하면 검토 집합에 대한 Advanced eDiscovery 대시보드를 사용하여 신속하게 코퍼스를 분석할 수 있습니다.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>1단계: 검토 집합 대시보드에 위젯 만들기

1. 조직 Microsoft 365 규정 준수 센터 **eDiscovery** > Advanced eDiscovery 조직의 사례 목록을 표시합니다.
  
2. 기존 사례를 선택합니다.
  
3. 검토 집합 **탭을** 클릭한 다음 검토 집합을 선택합니다.
  
4. **개별 결과** 드롭다운 목록에서 **검색 프로필 보기** 를 클릭합니다. 

   ![DashbordPivot.](../media/dashboardpivot.png)

   검색 **프로필 보기** 페이지가 표시됩니다. 이 페이지를 처음 표시하면 세 개의 기본 위젯이 표시됩니다.

   ![대시보드.](../media/dashboardonly.png)
  
5. 새 **위젯을 클릭하고** 다음 항목 중 하나를 선택합니다.

   ![새 위젯 드롭다운 목록입니다.](../media/NewWidgetDropdownBox.png)

   - **라이브러리에서 선택:** 위젯의 기본 라이브러리를 표시됩니다. 위젯을 클릭한 다음  추가를 클릭하여 검색 프로필 보기 페이지의 위젯에 **추가합니다.**
  
   - **사용자 지정 위젯 만들기:** 사용자 지정 위젯을 설정하는 데 사용할 수 있는 플라이아웃 페이지를 표시됩니다. 

6. 사용자 지정 위젯을 만들하려면 위젯 플라이아웃 추가 페이지에서 **다음을** 합니다.

   ![위젯을 생성합니다.](../media/addwidget.png)

    a. 위젯 제목 표시줄에 표시되는 위젯의 이름을 입력합니다. 위젯 이름을 정해야 하지만 위젯 데이터를 식별하는 것이 유용합니다.

    b. 위젯 데이터에 사용할  피벗 선택 드롭다운 목록에서 속성을 선택합니다. 이 목록의 항목은 검토 집합의 항목에 대한 검색 가능한 속성입니다. 이러한 속성에 대한 설명은 의 문서 메타데이터 [필드를 Advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md) 위젯에 대한 피벗 옵션은 이 항목의 검색 가능한 **필드** 이름 열에 나열되어 있습니다.

    c. 선택한 피벗 속성의 데이터를 표시하려면 차트 종류를 선택합니다.

  6. 추가를 클릭하여 사용자 지정 위젯을 만들고 검색 프로필 보기 페이지에 **표시합니다.** 

## <a name="step-2-create-a-review-set-search-query"></a>2단계: 검토 집합 검색 쿼리 만들기

1. 위젯 **제목** 표시줄에서 ...를 클릭한 다음 조건 **적용을 클릭합니다.**

   ![대시보드.](../media/searchprofilehome.png)

2. 플라이아웃 페이지에서 위젯 키 또는 위젯 차트의 요소를 클릭하여 필터를 만드십시오.

   ![CreateFilter.](../media/applyconditionfilter.png)

3. 다른 위젯 여러 위젯에 대해 1-2단계를 반복합니다. 

4. 완료되면 쿼리로 저장을 **클릭하여** 조건을 검토 집합에 대한 새 검색 쿼리로 저장합니다.

   ![쿼리.](../media/savequery.png)

5. 검색 프로필 **보기를 닫고** 검색 결과 보기로 돌아 습니다.

   시각적 필터를 만든 경우 결과 쿼리는 표시되는 검색 결과에 적용되고 4단계에서 저장한 검색 쿼리는 저장된 쿼리 **아래에 표시됩니다.** 검토 집합 쿼리에 대한 자세한 내용은 검토 집합의 데이터 [쿼리를 참조하세요.](review-set-search.md)
