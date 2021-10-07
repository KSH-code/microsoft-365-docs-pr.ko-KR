---
title: Exchange Online 성능 조정
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: 이 문서에는 일반적인 팁과 다른 리소스에 대한 링크가 포함되어 있으며, 이 링크를 통해 사용자 관리의 성능을 Exchange Online.
ms.openlocfilehash: 5feb704a1da83ef93ebc3bbe72fb12c7f0c54574
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201580"
---
# <a name="tune-exchange-online-performance"></a>Exchange Online 성능 조정

이 문서에는 일반적인 팁과 기타 리소스에 대한 링크가 포함되어 있으며, 특히 마이그레이션 앞에서 Exchange Online 성능 향상 방법을 알 수 있습니다. 이 문서는 프로젝트의 네트워크 계획 및 성능 [Office 365](./network-planning-and-performance.md) 중입니다.
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>성능 향상을 위해 고려할 Exchange Online 있습니다.

마이그레이션 속도를 개선하고 조직의 대역폭 제한을 Exchange Online 다음을 고려합니다.
  
- **사서함 크기를 줄입니다.** 사서함 크기가 작을 경우 마이그레이션 속도가 향상됩니다. 
    
- **하이브리드 배포에서 사서함 이동 Exchange 사용** 하이브리드 Exchange 오프라인 메일(형식)을 사용할 수 있습니다. OST 파일)을 사용하여 마이그레이션할 때 다시 다운로드할 필요가 Exchange Online. 이렇게 하면 다운로드 대역폭 요구 사항이 크게 줄어듭니다. 
    
- **인터넷 트래픽이 적고, 낮은 인터넷 트래픽이 발생하는 동안 사서함 이동이 발생할 수 Exchange 예약합니다.** 이동을 위한 경우 마이그레이션 요청이 사서함 복제 프록시로 전송되어 즉시 수행되지 않을 수 있습니다. 
    
- **을 위해 린트 웹용 Outlook.** 작은 팝업은 서버에서 일부 구성 요소를 렌더링하여 Microsoft Edge 또는 Internet Explorer 전자 메일 메시지의 메모리를 많이 사용하는 더 작고 적은 버전을 제공합니다. 자세한 내용은 린트 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 메모리 [줄이기를 참조하세요.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)


## <a name="general-advice"></a>일반 조언

- 사용자 위치에 대한 DNS outlook.office.com 논리적 입력 위치에 MS-datacenter를 입력해야 합니다.

- 사서함 캐싱을 조사하고 적절한 옵션(다시)을 선택합니다. 캐싱 기간, 공유 사서함 캐싱, et cetera).

- 인터넷을 Outlook VPN 연결이 중앙 사무실로 전달되지 못하게 합니다.

- 사서함 데이터가 폴더 및 항목, 금액에 대한 제한을 준수하는지 확인합니다.
    
마이그레이션 성능 Exchange 대한 자세한 내용은 Office 365 성능 및 [모범 사례를 참조하세요.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)
