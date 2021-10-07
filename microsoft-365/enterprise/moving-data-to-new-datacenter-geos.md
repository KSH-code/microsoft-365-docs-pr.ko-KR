---
title: 핵심 데이터를 새 데이터 Microsoft 365 지역으로 이동
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 0a35176a-e585-4dec-a90b-36be8314667f
f1.keywords:
- NOCSH
description: 새로운 Office 365 데이터 센터 지역 및 데이터 상주 옵션을 사용하여 핵심 데이터를 새 지역으로 이동하는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 724021bc3fb5fd8a0946bcf5f460e4848c44bf9f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209648"
---
# <a name="moving-core-data-to-new-microsoft-365-datacenter-geos"></a>핵심 데이터를 새 데이터 Microsoft 365 지역으로 이동

서비스용 새 데이터 센터 지역을 Microsoft 365 있습니다. 이러한 새로운 데이터 센터 지역은 지속적인 고객 요구 및 사용 증가를 지원하기 위해 용량 및 계산 리소스를 추가합니다. 또한 새 데이터 센터 지역은 핵심 고객 데이터에 대한 지역 내 데이터 레지스터를 제공합니다. 

핵심 고객 데이터는 고객 데이터의 하위 집합을 참조하는 용어로, 
- Exchange Online 콘텐츠(전자 메일 본문, 일정 항목 및 전자 메일 첨부 파일 콘텐츠)
- SharePoint 온라인 사이트 콘텐츠 및 해당 사이트에 저장된 파일
- 파일에 업로드된 비즈니스용 OneDrive
- Teams 메시지, 채널 메시지 및 채팅에 사용되는 이미지를 비롯한 채팅 메시지
  
핵심 고객 데이터가 기존 데이터 센터 지역에 이미 저장되어 있는 기존 고객은 새 데이터 센터 지역의 시작에 영향을 받지 않습니다. Microsoft는 새 데이터 센터 지역에 고유한 기능 또는 규정 준수 인증을 도입하지 않습니다. 두 지역 중 어떤 지역의 고객이든 이전과 동일한 서비스 품질, 성능 및 보안 제어를 경험할 수 있습니다. 아래 표에 나열된 기존 고객에게 휴지 상태의 조직의 핵심 고객 데이터를 새 데이터 센터 지역으로 조기 마이그레이션할 수 있는 옵션을 제공합니다.
  
|**테넌트 등록 국가가 있는 고객**|**이전 데이터 센터 지역**|**새 데이터 센터 지역**|**지역 서비스 재개 시점**|
|:-----|:-----|:-----|:-----|
|**일본**| 아시아/태평양 | 일본 | 2014년 12월 |
|**오스트레일리아, 뉴질랜드, 피지**| 아시아/태평양 | 오스트레일리아 | 2015년 3월 |
|**인도**| 아시아/태평양 | 인도 | 2015년 10월 |
|**캐나다**| 미국 | 캐나다 | 2016년 5월 |
|**영국**| 유럽 연합 | 영국 | 2016년 9월 |
|**대한민국**| 아시아/태평양 | 대한민국 | 2017년 4월 |
|**프랑스**| 유럽 연합 | 프랑스 | 2018년 3월 |
|**아랍에미리트**| 유럽 연합 | 아랍에미리트 | 2019년 6월 |
|**남아프리카 공화국**| 유럽 연합 | 남아프리카 공화국 | 2019년 7월 |
|**스위스, 리히텐스테인**| 유럽 연합 | 스위스 | 2019년 12월 |
|**독일**| 유럽 연합 | 독일 | 2019년 12월 |
|**노르웨이**| 유럽 연합 | 노르웨이 | 2020년 4월 |
|**브라질**| 아메리카 | 브라질 | 2020년 11월 |

2020년 10월 1일 현재 테넌트에 Office 365 Education 구독이 있는 고객은 마이그레이션할 수 없습니다.

모든 데이터 센터 지역, 데이터 센터 및 미사용 고객 데이터 위치의 전체 목록은 대화형 데이터 센터 맵의 [일부로 사용할 수 있습니다.](https://office.com/datamaps) 
  
## <a name="data-residency-option"></a>데이터 상주 옵션

위 표에 나열된 데이터 센터 지역을 Microsoft 365 자격이 있는 고객에게 데이터 상주 옵션을 제공합니다. 이 옵션을 사용하면 데이터 상주 요구 사항이 있는 적격 고객은 조직의 핵심 고객 데이터 미사용 마이그레이션을 새 데이터 센터 지역으로 요청할 수 있습니다.  Microsoft는 등록 기간 동안 마이그레이션을 요청하는 모든 적격 고객에게 커밋된 기한을 제공합니다.  데이터 [센터](request-your-data-move.md) 지리적으로 열려 있는 등록 창에 대한 자세한 내용과 프로그램에 등록하는 단계에 대한 자세한 내용은 데이터 이동을 요청하는 방법 페이지를 검토하세요.  데이터 이동은 요청 기간이 완료된 후 최대 24개월이 걸릴 수 있습니다.

Microsoft는 새 데이터 센터 지역에 고유한 기능 또는 규정 준수 인증을 도입하지 않습니다.
    
전체적으로 운영되는 자동화 환경에서 데이터 이동을 수행할 때 수반되는 복잡성, 정밀도 및 규모 때문에 귀하의 테넌트 또는 다른 단일 테넌트에서 데이터 이동이 완료될 것으로 예상되는 시기를 알려드리기가 어렵습니다. 고객은 데이터 이동이 완료되었을 때 메시지 센터에서 관련 서비스별로 1번의 확인을 받게 됩니다. 
    
데이터 이동은 최종 사용자에게 최소의 영향만 미치는 백 엔드 서비스 작업입니다. 영향을 받을 수 있는 기능은 [During and after your data move](during-and-after-your-data-move.md) 페이지에 나와 있습니다. 당사는 가용성을 [Microsoft Online Services](https://go.microsoft.com/fwlink/p/?LinkId=523897) SLA(서비스 수준 계약)를 준수하기 때문에 이동 중에 고객이 준비하거나 모니터링할 필요가 없습니다. 서비스 유지 관리에 대한 알림은 필요한 경우에 수행됩니다. 

새 데이터 센터 지역으로의 데이터 이동은 추가 비용으로 고객에게 완료됩니다.
    
## <a name="related-topics"></a>관련 항목 
 
[데이터 이동을 요청하는 방법](request-your-data-move.md)
    
[데이터 이동 일반 FAQ](data-move-faq.yml)
  
[새 데이터 센터 Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[지역별로 Azure 서비스](https://azure.microsoft.com/regions/)

[Teams 지역 지원 테넌시의 Microsoft 365 환경 제공](/microsoftteams/teams-experience-o365odb-spo-multi-geo)
