---
title: Exchange Online 성능 조정
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: 이 문서에는 Exchange Online의 성능을 개선하는 방법을 알려 주는 다른 리소스에 대한 일반적인 팁과 링크가 포함되어 있습니다.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692729"
---
# <a name="tune-exchange-online-performance"></a>Exchange Online 성능 조정

이 문서에는 특히 마이그레이션 전 Exchange Online의 성능을 개선하는 방법을 알려 주며 일반적인 팁과 다른 리소스에 대한 링크가 포함되어 있습니다. 이 문서는 [Office 365](https://aka.ms/tune) 프로젝트에 대한 네트워크 계획 및 성능 조정의 일부입니다.
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Exchange Online 성능을 개선하기 위해 고려해야 할 것

마이그레이션 속도를 개선하고 Exchange Online에 대한 조직의 대역폭 제약 조건을 줄이면 다음 사항을 고려하세요.
  
- **사서함 크기를 줄입니다.** 사서함 크기가 작을 경우 마이그레이션 속도가 향상됩니다. 
    
- **Exchange 하이브리드 배포에서 사서함 이동 기능을 사용 합니다.** Exchange 하이브리드 배포를 사용할 경우 오프라인 메일(형식) OST 파일)은 Exchange Online으로 마이그레이션할 때 다시 다운로드할 필요가 없습니다. 이렇게 하면 다운로드 대역폭 요구 사항이 크게 줄어듭니다. 
    
- **인터넷 트래픽이 적고 프레미스 Exchange를 적게 사용하는 기간 동안 사서함 이동이 발생하게 예약합니다.** 이동을 예정하면 마이그레이션 요청이 사서함 복제 프록시로 전송되어 즉시 수행되지 않을 수 있습니다. 
    
- **웹용 Outlook에 대해 린트 팝업을 사용 합니다.** 작은 팝업은 서버에서 일부 구성 요소를 렌더링하여 Microsoft Edge 또는 Internet Explorer 특정 전자 메일 메시지의 더 작고 메모리를 많이 사용하는 버전을 제공합니다. 자세한 내용은 린트 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 [메모리를 줄입니다.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)


## <a name="general-advice"></a>일반 조언

- 사용자 위치에 대한 논리적 outlook.office.com MS-datacenter를 입력하는지 DNS를 검색해야 합니다.

- 사서함 캐싱을 조사하고 적절한 옵션(다시)을 선택합니다. 캐싱 기간, 공유 사서함 캐싱, et cetera).

- Outlook 데이터가 인터넷을 통과하기 전에 VPN 연결을 중앙 사무실로 전달하지 못하게 합니다.

- 사서함 데이터가 폴더 및 항목 금액에 대한 제한을 준수하는지 확인합니다.
    
Exchange 마이그레이션 성능에 대한 자세한 내용은 Office 365 마이그레이션 성능 및 [모범 사례를 참조하세요.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)
  

