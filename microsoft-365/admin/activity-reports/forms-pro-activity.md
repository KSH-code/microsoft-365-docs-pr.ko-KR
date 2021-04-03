---
title: 관리 센터의 Microsoft 365 보고서 - Dynamics 365 고객 음성 활동
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Microsoft 365 관리 센터의 Microsoft 365 보고서 대시보드를 사용하여 Microsoft Dynamics 365 고객 음성 활동 보고서를 다운로드하는 방법을 학습합니다.
ms.openlocfilehash: 26d376602caebcb5276b77a3d2c962a14e5fead5
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579653"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>관리 센터의 Microsoft 365 보고서 - Dynamics 365 고객 음성 활동

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.
  
예를 들어 Dynamics 365 Customer Voice와의 상호 작용을 보고 Microsoft Dynamics 365 Customer Voice를 사용하기 위해 라이선스가 부여된 모든 사용자의 활동을 이해할 수 있습니다. 또한 만든 Pro 설문 조사 및 사용자가 응답한 Pro 설문 조사 수를 보고 진행되는 공동 작업 수준을 이해하는 데도 도움이 됩니다. 
  
> [!NOTE]
> Microsoft 365의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 또는 Exchange, SharePoint, Teams 서비스, Teams Communications 또는 비즈니스용 Skype 관리자인 경우 보고서를 볼 수 있어야 합니다. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Forms Pro 활동 보고서에 도착하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.

    
2. 보고서 **선택 드롭다운에서** **Dynamics 365 Customer Voice 활동 을** \> **선택합니다.**

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 고객 음성 활동 보고서 해석

활동 및 사용자 차트를 확인하여 사용자의 Dynamics 365 고객 음성 활동을 **볼** **수** 있습니다. 

![양식 활동 보고서](../../media/formsproactivity.png)

|항목|설명|
|:-----|:-----|
|1.  <br/> |**Dynamics 365 고객** 음성 활동 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 표(7)에 현재 날짜로부터 최대 28일간의 데이터가 표시됩니다(보고서가 생성된 날짜가 아 아지 않습니다).   <br/> |
|2.  <br/> |각 보고서의 데이터는 일반적으로 지난 48시간 동안의 최신 데이터입니다.  <br/> |
|3.  <br/> |사용자 **보기를** 통해 활성 Dynamics 365 고객 음성 사용자 수의 추세를 이해할 수 있습니다. 사용자가 특정 기간 내에 Pro 설문 조사(만들기, 편집, 보기 등)를 실행한 경우 활성으로 간주됩니다.  <br/> |
|4.  <br/> |활동 **보기는** 활성 사용자 수의 추세를 이해하는 데 도움이 됩니다. 사용자가 지정된 기간 동안 파일 활동(저장, 동기화, 수정 또는 공유)을 실행하거나 페이지를 방문한 경우 활성으로 간주됩니다.<br/> 참고: 단일 설문 조사에 대해 활동이 여러 번 발생할 수 있지만 하나의 활성 설문 조사로 계산됩니다. 예를 들어, Pro 설문 조사를 만들고 지정된 기간 동안 동일한 설문 조사를 여러 번 편집할 수 있으며 단일 설문 조사로 계산됩니다. <br>|
|5.<br/>|사용자 **차트에서** Y축은 고유 사용자 수입니다. X축은 고유 사용자가 활성화된 날짜입니다. 범례는 다음입니다.<br/><br/>**디자이너는** 사용자가 Dynamics 365 고객 음성 설문 조사를 만들거나 편집했다는 의미입니다.<br><br>활동 **차트에서** Y축은 설문 조사당 Dynamics 365 고객 음성 응답 수입니다. X축은 설문 조사 또는 응답 활동이 발생한 날짜입니다. 범례는 다음입니다.<br/><br/>**설문 조사는** 사용자가 만든 고유한 Dynamics 365 고객 음성 설문 조사 수입니다.<br>**응답은** 설문 조사를 받은 사용자가 제출한 익명 또는 익명이 아닌 응답의 수입니다. |
|6.<br/>|범례에서 항목을 선택하여 차트에 있는 계열을 필터링할 수 있습니다. 예를 들어 사용자 차트에서 디자이너, 응답자 또는 총 사용자를 선택하여 각각에 관련된 정보만 볼 수 있습니다. 이 선택을 변경해도 아래의 눈금 표에 있는 정보가 변경되지는 않습니다.|
|7.<br/>|이 표에는 사용자 수준별 활동 분석이 표시됩니다. 범례는 다음입니다.<br/><br/>**사용자** 이름은 Microsoft Forms에서 활동을 수행한 사용자의 전자 메일 주소입니다.<br/>**마지막 활동 날짜(UTC)는** 선택한 날짜 범위에 대해 사용자가 양식 활동을 마지막으로 수행한 날짜입니다. 특정 날짜에 발생한 활동을 보려면 차트에서 직접 날짜를 선택합니다.<br/>이렇게 하면 해당 특정 일자에 활동을 수행한 사용자에 대한 파일 활동 데이터만 표시하도록 테이블이 필터링됩니다.<br/><br/>**만들어진 설문 조사 수는** 사용자가 만든 설문 조사 수입니다.<br/> **설문 응답 수는** 설문 조사를 배포한 응답자로부터의 응답 수입니다.|
|8.<br/>|열 **관리 아이콘을** 선택하여 보고서에서 열을 추가하거나 제거합니다.|
|9.<br/>|내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 파일로 내보낼 **수** 있습니다. 이렇게 하면 모든 사용자에 대한 데이터를 내보내고 추가 분석을 위해 간단한 집계, 정렬 및 필터링을 할 수 있습니다. 사용자가 100명 미만인 경우 보고서 자체의 표 내에서 정렬 및 필터링할 수 있습니다. 사용자가 100명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.|