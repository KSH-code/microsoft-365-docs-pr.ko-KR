---
title: 데이터 이동 도중 및 이후
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 09/22/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: 데이터 이동은 Microsoft가 테넌트의 서비스 및 관련 데이터를 새 데이터 센터 지역으로 이동할 때 발생하는 백 엔드 작업입니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f90957447e9d301594f50e67ff51ae495464b63e
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491090"
---
# <a name="during-and-after-your-data-move"></a>데이터 이동 도중 및 이후

데이터 이동은 최종 사용자에게 최소의 영향만 미치는 백 엔드 작업입니다. Microsoft에서 사용자의 테넌트의 각 서비스 및 연결된 데이터를 새 데이터 센터 지역으로 이동하는 동안 필요한 작업은 없습니다. 사용자에게 최소한의 영향만 미치면서, 백그라운드에서 사전에 데이터 전송 및 유효성 검사가 진행됩니다.
  
> [!NOTE]
> 서비스마다 다른 시간에 이동이 발생합니다. 결과적으로 다른 시간에 각 서비스의 기능이 제한된다는 설명이 표시될 수 있습니다.
 
  
각 Microsoft 365, SharePoint Exchange Online Online 및 Teams 서비스에 대한 이동이 완료되면 Teams 메시지 센터에서 확인을 시청하세요. 아래 표에 표시된 것 처럼 등록 기간이 끝나고 최대 24개월이 걸릴 수 있습니다. 휴지의 핵심 고객 데이터를 새 데이터 센터 지역으로 이동하는 데는 최대 24개월이 걸릴 수 있습니다.   

|**등록 국가가 있는 고객**|**모든 이동 완료 시기**|
|:-----|:-----|
|오스트레일리아, 뉴질랜드, 피지  <br/> |2022년 7월 1일  <br/> |
|일본  <br/> |2022년 7월 1일  <br/> |
|인도  <br/> |2022년 7월 1일  <br/> |
|캐나다  <br/> |2022년 7월 1일  <br/> |
|대한민국  <br/> |2022년 7월 1일  <br/> |
|영국  <br/> |2022년 7월 1일  <br/> |
|프랑스  <br/> |2022년 7월 1일  <br/> |
|아랍에미리트  <br/> |2022년 7월 1일  <br/> |
|남아프리카 공화국  <br/> |2022년 7월 1일  <br/> |
|스위스, 리히텐스테인  <br/> |2022년 7월 1일  <br/> |
|노르웨이  <br/> |2022년 11월 1일  <br/> |
|독일  <br/> |2023년 5월 1일  <br/> |
|브라질  <br/> |2023년 6월 1일  <br/> |

## <a name="exchange-online"></a>Exchange Online

각 사용자를 새 데이터 센터 지역으로 이동하는 데 시간이 걸리므로 일부 사용자는 다른 사용자가 새 데이터 센터 지역으로 이동되는 동안 이전 데이터 센터 지역에 계속 남아 있게 됩니다. 즉, 여러 사서함에 액세스하는 데 관련된 일부 기능은 이동 프로세스의 기간 동안 완전히 작동하지 않을 수 있습니다(주 동안 지속될 수 있습니다). 이러한 기능은 다음 섹션에 설명되어 있습니다.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Outlook Web Access에서 "공유 폴더" 열기 

일부 사용자는 "공유 폴더" 기능을 사용하여 Outlook 웹 액세스에서 다른 사서함(사용자가 읽기 또는 쓰기 권한이 있는)에서 공유 메일 폴더를 여는 경우도 있습니다. 다음 표에서는 사서함을 이동하는 동안 공유 폴더에 대한 액세스가 작동하는 방식에 대해 설명하고 있습니다. 공유 사서함에 대한 모든 권한이 있는 사용자는 이동하는 동안 Outlook Web Access를 사용하여 사서함을 열 수 있습니다. 
  
|**구성**|**설명**|
|:-----|:-----|
|사용자에게 다른 사서함에 대한 사서함 폴더 권한이 있음  <br/> |제한될 수 있습니다.  <br/> 테넌트 이동 중에 사용자 A와 사서함 B가 같은 지역이 아닌 경우 사용자 A가 사서함 B의 특정 폴더에 대한 권한만 있는 경우 Outlook Web Access에서 사서함 B의 폴더를 열 수 없습니다.  <br/> 공유 폴더를 추가하려면 왼쪽 탐색 패널에서 사용자 이름을 마우스 오른쪽 단추로 클릭하고 **공유 폴더 추가** 를 선택합니다.  <br/> |
|사용자에게 다른 사서함에 대한 모든 사서함 권한이 있음  <br/> |완전히 지원됩니다.  <br/> 사용자 A에게 사서함 B에 대한 "모든 권한" 권한이 있는 경우 사용자 A는 웹 액세스의 왼쪽 탐색 패널에서 Outlook 폴더를 클릭하여 사서함 B가 Outlook 창을 열 수 있습니다.  사용자는 이동 중에 부정적인 영향을 Outlook Web Access를 사용하여 공유 사서함을 열 수 있습니다. 이러한 제한 사항은 사서함의 폴더 수준 공유에만 적용됩니다.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

온라인 SharePoint 이동하면 다음 서비스에 대한 데이터도 이동됩니다.
  
- 비즈니스용 OneDrive
    
- Microsoft 365 비디오 서비스
    
- Office 브라우저에서 실행
    
- 엔터프라이즈용 Microsoft 365 앱
    
- Visio Pro 대한 Microsoft 365
    
온라인 SharePoint 이동을 완료하면 다음과 같은 몇 가지 효과가 표시될 수 있습니다.
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 비디오 서비스

- 비디오에서는 SharePoint Online에서 콘텐츠의 나머지 부분에 대 한 이동을 보다 긴 데이터 이동합니다.
    
- 온라인 SharePoint 이동한 후 비디오를 재생할 수 없는 시간 프레임이 있게 됩니다.
    
- 이전 데이터 센터에서 코드 변환된 복사본을 제거한 후 새로운 데이터 센터에서 다시 코드 변환을 수행하기 때문입니다.
    
### <a name="search"></a>검색

온라인 SharePoint 이동하는 과정에서 검색 인덱스 및 검색 설정을 새 위치로 마이그레이션합니다. SharePoint Online  데이터의 이동을 완료할 때까지 원본 위치의 인덱스에서 사용자에게 계속 서비스를 제공합니다. 새 위치에서 검색은 온라인 데이터 이동을 완료한 후 자동으로 콘텐츠 크롤링을 SharePoint 시작합니다. 이 시점부터는 마이그레이션된 인덱스에서 고객의 사용자에게 서비스를 제공합니다. 마이그레이션 후 발생하는 콘텐츠 변경 내용은 크롤링하기 전까지 마이그레이션된 인덱스에 포함되지 않습니다. 대부분의 고객은 SharePoint Online 데이터 이동을 완료한 직후에 결과가 덜 신선하다는 사실은 인식하지 못하지만 일부 고객은 처음 24~48시간 동안 신선도 감소를 경험할 수 있습니다. 
  
영향을 받는 기능은 다음과 같습니다.
  
- 검색 결과 및 검색 웹 파트: 마이그레이션 후 발생한 변경 내용은 크롤링하기 전까지 결과에 포함되지 않습니다. 
    
- Delve: 마이그레이션 후 발생한 변경 내용은 크롤링하기 전까지 Delve에 포함되지 않습니다.
    
- 사이트의 인기도 및 검색 보고서: 새 위치에 있는 Excel 보고서의 수에는 SharePoint Online 데이터 이동을 완료한 후 실행된 사용 현황 보고서의 마이그레이션된 수와 SharePoint 포함됩니다. 중간 기간의 모든 수는 손실되며 복구할 수 없습니다. 이 기간은 일반적으로 이틀 정도입니다. 일부 고객은 손실되는 기간이 더 짧거나 길 수도 있습니다.
    
- 비디오 포털: 비디오 포털의 조회수 및 통계는 Excel 보고서 통계에 따라 달라지므로 Excel 보고서의 손실 기간만큼 비디오 포털에 대한 조회수 및 통계가 손실됩니다.
    
- eDiscovery: 마이그레이션하는 동안 변경된 항목은 크롤링하기 전까지 표시되지 않습니다.
    
- DLP(데이터 손실 방지): 항목의 변경 내용을 크롤링하기 전까지는 항목에 정책이 적용되지 않습니다.

마이그레이션의 일부로 기본 지역이 변경되고 모든 새 콘텐츠가 새 기본 지역에 저장됩니다. 기존 콘텐츠는 관리 센터의 SharePoint 온라인 데이터 위치로 처음 변경된 후 최대 90일 동안 영향을 끼치지 SharePoint 백그라운드에서 이동됩니다.

## <a name="microsoft-teams"></a>Microsoft Teams

### <a name="files-tab"></a>파일 탭

마이그레이션이 완료된 후 사용자가 파일 탭을 처음 사용하려고 할 때 파일 탭을 완전히 로드하는 데 추가 시간(최대 7초)이 걸릴 수 있습니다. 

### <a name="read-only-period"></a>읽기 전용 기간

Teams 서비스는 각 스레드를 개별적으로 이동합니다.  스레드는 이동하는 동안 읽기 전용 상태로 잠겨 스레드당 몇 초 동안 지속됩니다.  마이그레이션 중에 스레드에 계속 액세스할 수 있습니다.

## <a name="skype-for-business"></a>비즈니스용 Skype

비즈니스용 Skype 이동을 더 이상 사용할 수 없습니다.  [비즈니스용 Skype 온라인은](/lifecycle/announcements/skype-for-business-online-retirement) 2021년 7월 31일에 사용 중지됩니다. 그 이후로는 이 서비스에 더 이상 액세스할 수 없게 됩니다. 
  
## <a name="related-topics"></a>관련 항목 
 
[데이터 이동을 요청하는 방법](request-your-data-move.md)
    
[데이터 이동 일반 FAQ](data-move-faq.yml)
  
[새 데이터 센터 Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[지역별로 Azure 서비스](https://azure.microsoft.com/regions/)
