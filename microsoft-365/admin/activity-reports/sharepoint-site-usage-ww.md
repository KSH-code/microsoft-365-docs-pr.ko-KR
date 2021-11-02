---
title: Microsoft 365 관리 센터의 보고서 - SharePoint 사용 현황
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
description: SharePoint 사이트 사용 현황 보고서를 통해 사용자가 SharePoint 사이트에 저장하는 파일 수, 적극적으로 사용되는 파일 수 및 사용된 총 저장소를 알 수 있습니다.
ms.openlocfilehash: 2c29234df1076fa31ea836b7ead51234e121004e
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648822"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365 관리 센터의 보고서 - SharePoint 사용 현황

관리자로 Microsoft 365 보고서 대시보드에는 조직의 다양한 제품에 대한 활동 개요가 표시됩니다. 각 제품의 고유한 활동에 대한 자세한 정보를 확인할 수 있습니다. 예를 들어 사용자가 SharePoint 사이트에 저장하는 총 파일 수, SharePoint 현재 사용되고 있는 파일 수 및 이러한 모든 사이트에서 사용되는 저장소의 관점에서 SharePoint 값을 개성적으로 볼 수 있습니다. 그런 다음, SharePoint 사이트 사용 보고서를 확인하여 추세와 모든 사이트에 대한 수준별 세부 정보를 파악할 수 있습니다. 

## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>SharePoint 사이트 사용 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈페이지의 대시보드 카드에서  더 보기 단추를 SharePoint 클릭합니다.

## <a name="show-user-details-in-the-reports"></a>보고서에서 사용자 세부 정보 표시

보고서는 조직의 사용량 데이터에 대한 정보를 제공합니다. 기본적으로 보고서에는 사용자, 그룹 및 사이트의 식별 가능한 이름이 포함된 정보가 표시됩니다. Microsoft는 2021년 9월 1일부터 회사가 현지 개인 정보 보호법을 지원할 수 있도록 돕는 지속적인 노력의 일환으로 기본적으로 모든 보고서에 대해 사용자 정보를 숨기고 있습니다.
  
사용자 목록은 다음과 같습니다.
  
![보고서 - 익명 사용자 목록.](../../media/2ed99bce-4978-4ee3-9ea2-4a8db26eef02.png)
  
전역 관리자는 해당 테넌트에 대해 이 변경 내용을 되돌리고 조직의 개인정보처리방침에서 허용하는 경우 식별 가능한 사용자 정보를 표시할 수 있습니다. 이러한 결과는 Microsoft 365 관리 센터에서 다음 단계를 수행하여 달성할 수 있습니다.
  
1. 관리 센터에서 **설정** \> **조직 설정**\>**서비스** 로 이동합니다.

2. **보고서** 를 선택합니다. 
  
3. **모든 보고서에서 사용자, 그룹 및 사이트의 비식별화된 이름 표시** 를 선택 취소한 다음 변경 내용을 저장합니다. 
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>사이트 SharePoint 보고서 해석

사이트 사용 현황 탭을 선택하여 SharePoint 보고서에서 사이트 사용 **현황을 볼 수** 있습니다.

:::image type="content" alt-text="Microsoft 365 보고서 - Microsoft SharePoint 사이트 사용 현황 보고서입니다." source="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png" lightbox="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png":::

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.

:::image type="content" alt-text="SharePoint 사용 현황 보고서 - 열을 선택하십시오." source="../../media/71ac3195-c494-40c1-9346-a858125ef6df.png":::

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 

사이트 **SharePoint** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 보고서가 생성된 날짜가 아니라 현재 날짜로부터 최대 28일간의 데이터가 표에 표시됩니다.
  
|메트릭|설명|
|:-----|:-----|
|사이트 URL  |사이트의 전체 URL입니다. |
|삭제됨  |사이트의 지우기 상태입니다. 사이트가 삭제됨으로 표시되려면 7일 이상이 소요됩니다.  |
|사이트 소유자  |사이트의 기본 소유자의 사용자 이름입니다.   |
|사이트 소유자 사용자 이름  |사이트 소유자의 전자 메일 주소입니다. |
|마지막 활동 날짜(UTC)  | 파일 활동이 마지막으로 검색되거나 사이트에서 페이지를 본 날짜입니다.  |
|사이트 민감도 레이블 ID  | 사이트의 민감도 레이블입니다.  |
|외부 공유  | 사이트의 외부 공유 가능 설정입니다.  |
|관리되지 않는 장치 정책  | 관리되지 않는 장치에 대한 사이트 액세스 정책입니다.  |
|지리적 위치  | 사이트의 지리적 위치입니다.  |
|파일  |사이트의 파일 수입니다. |
|활성 파일  | 사이트의 활성 파일 수입니다.<br/> 참고: 보고서에 대해 지정된 기간 동안 파일이 제거된 경우 보고서에 표시된 활성 파일 수가 사이트의 현재 파일 수보다 클 수 있습니다.  |
|Storage(MB)  |현재 사이트에서 사용 중인 저장소의 양입니다.  |
|Storage(MB)  |사이트에 할당된 최대 저장소 양입니다.  |
|페이지 보기  |사이트에서 페이지를 본 횟수입니다.  |
|방문한 페이지  |사이트에서 방문한 고유 페이지 수입니다.  |
|익명 링크 수  |사이트에서 "링크가 있는 모든 사용자"를 사용하여 문서 또는 폴더를 공유하는 횟수입니다.  |
|회사 링크 수  |사이트에서 "링크가 있는 사용자"를 사용하여 문서 또는 폴더를 공유하는 횟수입니다.  |
|게스트 수에 대한 보안 링크  |사이트에서 "특정 사용자"를 사용하여 문서 또는 폴더를 공유하는 횟수입니다.  |
|구성원 수에 대한 보안 링크  |사이트에서 "특정 사용자"를 사용하여 문서 또는 폴더를 공유하는 횟수입니다.  |
|루트 웹 서식 파일  |사이트를 만드는 데 사용되는 서식 파일입니다.  <br/> 참고: 다른 사이트 유형으로 데이터를 필터링하려는 경우 데이터를 내보내고 루트 웹 서식 파일 열을 사용하세요. |

