---
title: Microsoft 365 관리 센터의 보고서 - 비즈니스용 OneDrive 사용 현황
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: '조직에서 비즈니스용 OneDrive 총 파일 및 저장소 수를 확인하려면 사용 현황 보고서를 다운로드합니다. '
ms.openlocfilehash: 2deff1e5438dcc6edbe5f12ecd9f428e0242b93f
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648846"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365 관리 센터의 보고서 - 비즈니스용 OneDrive 사용 현황

Microsoft 365 보고서 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.
  
예를 들어 대시보드의 OneDrive 카드에서는 비즈니스용 OneDrive에서 가져오는 값(예: 총 파일 수 및 조직 전체를 통해 사용되는 저장소)을 대략적으로 볼 수 있습니다. 그런 다음 하위 수준을 표시하여 활성 OneDrive 계정의 추세, 사용자가 상호 작용 중인 파일 수 외에도 사용되는 저장소를 파악할 수 있습니다. 사용자의 OneDrive에 대한 세부 정보도 제공합니다.

## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>사용 현황 보고서에 OneDrive 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈페이지의 대시보드 카드에서  더 보기 단추를 OneDrive 클릭합니다.
  
## <a name="interpret-the-onedrive-usage-report"></a>OneDrive 사용 현황 보고서 해석

사용 현황 탭을 선택하여 OneDrive 보고서에서 사용 현황을 볼 **수** 있습니다.<br/>![Microsoft 365 - Microsoft OneDrive 보고서입니다.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![OneDrive 보고서 - 열을 선택 합니다.](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 

사용 **비즈니스용 OneDrive** 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 보고서가 생성된 날짜가 아니라 현재 날짜로부터 최대 28일간의 데이터가 표에 표시됩니다.
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|URL  <br/> |사용자 계정의 웹 OneDrive. <br/> |
|삭제됨  <br/> |업데이트의 OneDrive. 계정이 삭제됨으로 표시되려면 7일 이상이 소요됩니다.  <br/> |
|소유자  <br/> |조직의 기본 관리자 사용자 OneDrive.   <br/> |
|소유자 사용자 이름  <br/> |소유자의 전자 메일 주소입니다OneDrive. <br/> |
|마지막 활동 날짜(UTC)  <br/> | 파일 활동이 파일 작업에서 수행된 가장 최근 OneDrive. OneDrive에 파일 활동이 없으면, 값은 비어 있게 됩니다.  <br/> |
|파일  <br/> |파일 수를 OneDrive. <br/>|
|활성 파일  <br/> | 기간 내의 활성 파일 수입니다.<br/> 참고: 보고서에 대해 지정된 기간 동안 파일이 제거된 경우 보고서에 표시된 활성 파일 수가 보고서의 현재 파일 수보다 클 OneDrive. >  삭제된 사용자는 180일 동안 계속해서 보고서에 표시됩니다.  <br/> |
|Storage(MB)  <br/> |저장소 저장소의 OneDrive MB입니다. |
|||