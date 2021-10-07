---
title: EDiscovery 검색 결과에서 중복 제거
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
ms.custom:
- seo-marvel-apr2020
description: 전자 메일 메시지의 복사본을 하나만 내보낼 수 있도록 중복 eDiscovery 검색 결과를 제거하는 방법을 배워야 합니다.
ms.openlocfilehash: 792726062576f6e17adb5a10cc544e7efdb02e03
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153081"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>EDiscovery 검색 결과에서 중복 제거

이 문서에서는 eDiscovery 검색 결과의 중복 제거 작동 방식에 대해 설명하고 중복 제거 알고리즘의 제한 사항을 설명합니다.
  
eDiscovery 도구를 사용하여 eDiscovery 검색 결과를 내보낼 때 내보낼 결과 중복을 제거하는 옵션이 제공됩니다. 시나리오 중복 제거를 사용하도록 설정하면(기본적으로 중복 제거가 사용되지 않는 경우) 동일한 메시지의 여러 인스턴스가 검색된 사서함에서 발견된 경우에도 전자 메일 메시지의 복사본 하나만 내보낼 수 있습니다. 중복 제거를 사용하면 검색 결과를 내보낼 때 검토 및 분석해야 하는 항목 수를 줄여 시간을 절약할 수 있습니다. 그러나 중복 제거가 작동하는 방식에 대해 이해하고 내보내기 프로세스 중에 고유한 항목이 중복 항목으로 표시될 수 있는 알고리즘에 제한이 있습니다.
  
## <a name="how-duplicate-messages-are-identified"></a>중복된 메시지를 식별하는 방법

eDiscovery 도구는 다음 전자 메일 속성의 조합을 사용하여 메시지가 중복 메시지인지 여부를 판단합니다.
  
- **InternetMessageId** - 이 속성은 특정 메시지의 특정 버전을 참조하는 전역 고유 식별자인 전자 메일 메시지의 인터넷 메시지 식별자를 지정합니다. 이 ID는 메시지를 보내는 보낸 사람 전자 메일 클라이언트 프로그램 또는 호스트 전자 메일 시스템에 의해 생성됩니다. 사용자가 두 개 이상의 받는 사람에게 메시지를 보내는 경우 인터넷 메시지 ID는 메시지의 각 인스턴스에 대해 동일합니다. 원본 메시지에 대한 후속 변경은 다른 메시지 식별자를 받게 됩니다. 

- **ConversationTopic** - 이 속성은 메시지의 대화 스레드 제목을 지정합니다. **ConversationTopic** 속성 값은 대화의 전체 항목을 설명하는 문자열입니다. 보존은 초기 메시지와 초기 메시지에 대한 회신으로 전송된 모든 메시지로 구성됩니다. 같은 대화 내의 메시지는 **ConversationTopic** 속성 값과 동일합니다. 이 속성의 값은 일반적으로 대화를 시작한 초기 메시지의 Subject 줄입니다. 

- **BodyTagInfo** - 내부 Exchange 속성입니다. 이 속성의 값은 메시지 본문에서 다양한 특성을 확인하여 계산됩니다. 이 속성은 메시지 본문의 차이점을 식별하는 데 사용됩니다. 

eDiscovery 내보내기 프로세스 중에 검색 조건과 일치하는 모든 메시지에 대해 이러한 세 가지 속성을 비교합니다. 이러한 속성이 둘 이상의 메시지에 대해 동일한 경우 해당 메시지는 중복된 것으로 확인되어 중복 제거를 사용하도록 설정한 경우 메시지 복사본이 하나만 내보내집니다. 내보내는 메시지를 "원본 항목"이라고 합니다. 중복 메시지에 대한 정보는 내보낼Results.csv **Manifest.xml** 보고서 및 보고서에 포함되어 있습니다. 항목 **Results.csv** 중복 항목 열에 값이 있는 경우 중복 메시지가 **식별됩니다.** 이 열의 값은 내보낼 메시지의 항목 **ID** 열 값과 일치합니다. 
  
다음 그래픽은 검색 결과와 함께 내보낼Results.csvManifest.xml보고서에 중복 메시지가 표시되는 방법을 보여 합니다.  이러한 보고서에는 이전에 설명한 중복 제거 알고리즘에 사용되는 전자 메일 속성이 포함되어 있습니다. 대신 보고서에는 보고서  저장소에서 항목에 할당된 항목 ID Exchange 포함됩니다. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results.csv 보고서(Excel)
  
![보고서에서 중복 항목에 대한 Results.csv.](../media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml 보고서(Excel)
  
![보고서에서 중복 항목에 대한 Manifest.xml.](../media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
또한 중복 메시지의 다른 속성이 내보내기 보고서에 포함됩니다. 여기에는 중복 메시지가 있는 사서함, 메시지가 메일 그룹으로 전송된지 여부, 메시지가 다른 사용자에게 Cc'd인지 또는 Bcc'd인지 여부가 포함됩니다.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>중복 제거 알고리즘의 제한 사항

중복 제거 알고리즘에는 고유한 항목이 중복 항목으로 표시될 수 있는 몇 가지 알려진 제한 사항이 있습니다. 선택적 중복 제거 기능을 사용할지 여부를 결정할 수 있도록 이러한 제한 사항을 이해하는 것이 중요합니다.
  
중복 제거 기능이 실수로 메시지를 중복으로 식별하고 내보내지 않을 수 있는 상황이 있습니다(내보내기 보고서에서 여전히 중복으로 인용). 사용자가 편집하지만 보내지 않는 메시지입니다. 예를 들어 사용자가 Outlook 선택하고 메시지 내용을 복사한 다음 새 메시지에 붙여 넣는 경우를 예로 들어 보겠습니다. 그런 다음 첨부 파일을 제거하거나 추가하거나 제목 줄이나 본문 자체를 변경하여 복사본 중 하나를 변경합니다. 이러한 두 메시지가 eDiscovery 검색의 쿼리와 일치하면 검색 결과를 내보낼 때 중복 제거를 사용하도록 설정한 메시지 중 하나만 내보내집니다. 따라서 원본 메시지나 복사된 메시지가 변경되어도 수정된 메시지는 전송되지 않았습니다. 따라서 **InternetMessageId,** **ConversationTopic** 및 **BodyTagInfo** 속성의 값은 업데이트되지 않았습니다. 그러나 앞서 설명한 것 처럼 두 메시지가 내보내기 보고서에 나열됩니다. 
  
사서함에 소송 보류 또는 소송 보류가 있는 경우처럼 기록 중 복사 페이지 보호 기능을 사용하도록 설정한 경우에도 고유한 메시지를 중복으로 In-Place 있습니다. 기록 중 복사 기능은 원본 항목에 대한 변경을 저장하기 전에 원본 메시지를 복사하고 사용자의 복구 가능한 항목 폴더의 버전 폴더에 저장합니다. 이 경우 수정된 복사본과 원본 메시지(복구 가능한 항목 폴더)는 중복 메시지로 간주될 수 있으므로 이 중 하나만 내보낼 수 있습니다.
  
> [!IMPORTANT]
> 중복 제거 알고리즘의 제한 사항이 검색 결과의 품질에 영향을 줄 수 있는 경우 항목을 내보낼 때 중복 제거를 사용하도록 설정하지 말아야 합니다. 이 섹션에 설명된 상황이 검색 결과의 한 요소가 될 가능성이 낮고 중복될 가능성이 높은 항목 수를 줄이면 중복 제거를 사용하도록 설정하는 것이 좋은지 고려해야 합니다. 
  
## <a name="more-information"></a>추가 정보

- 이 문서의 정보는 다음 eDiscovery 도구 중 하나를 사용하여 검색 결과를 내보낼 때 적용할 수 있습니다.

  - 준수 센터의 콘텐츠 Office 365

  - Exchange Online의 원본 위치 eDiscovery

  - SharePoint Onlin의 eDiscovery 센터

- 검색 결과 내보내기에 대한 자세한 내용은 다음을 참조하세요.

  - [콘텐츠 검색 내보내기](export-search-results.md)

  - [콘텐츠 검색 보고서 내보내기](export-a-content-search-report.md)

  - [PST In-Place eDiscovery 검색 결과 내보내기](/exchange/security-and-compliance/in-place-ediscovery/export-search-results)

  - [eDiscovery 센터에서 콘텐츠 내보내기 및 보고서 만들기](/SharePoint/governance/export-content-and-create-reports-in-the-ediscovery-center)