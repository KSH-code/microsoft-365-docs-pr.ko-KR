---
title: Microsoft 365 네트워크 연결 위치 서비스
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 네트워크 연결 위치 서비스
ms.openlocfilehash: 0aff9ca565d4e79ddbf7df723e7c102c0db92422015b722327029be12bdb2934
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53858474"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365 네트워크 연결 위치 서비스

이제 Microsoft 365 관리 센터에는 네트워크 Insights 및 성능 권장 사항이 표시되고, 이는 Microsoft 365 테넌트에서 수집된 라이브 성능 메트릭입니다. 이러한 메트릭은 테넌트의 관리 사용자만 볼 수 있습니다. 조직 네트워크 연결은 인터넷으로의 네트워크 이동 위치를 통해 사무실 위치당 설계됩니다. Microsoft 365 클라이언트 연결에서는 해당 경로를 사용하여 인터넷을 통해 Microsoft 서비스 프런트 도어 서버로 연결합니다. 사무실 위치를 식별하는 것은 이러한 네트워크 정보를 표시하는 데 핵심입니다.

## <a name="location-in-network-measurements"></a>네트워크 측정의 위치

조직의 관리자는 이 기능에 사용되는 네트워크 측정에 포함될 위치를 옵트인(opt in)할 수 있습니다. 이렇게 하면 각 사무실이 있는 구를 자동으로 검색할 수 있습니다. 위치 정보는 정확하지 않습니다. 300m로 난청되어 도시별로 분류됩니다. 위치가 Windows 디바이스에 캡처될 때 장치에 도구 트레이에 사용  중 위치 아이콘이 표시됩니다. 관리자는 사용자에게 이 아이콘의 모양을 알리고 싶을 수 있습니다. 이 처리를 통해 위치는 개인 또는 장치의 위치가 아니라 조직 사무실 위치로 처리됩니다. 네트워크 인사이트는 검색된 사무실 위치 도시에서 볼 수 있습니다. 권장 사항에서 더 높은 정확도를 원할 경우 특정 사무실 위치 주소를 입력할 수 있습니다. 네트워크 인사이트는 해당 위치로 집계됩니다. Office 위치는 300미터보다 긴밀하게 집계할 수 없습니다.

## <a name="location-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터의 위치

Microsoft 365 관리 센터에서는 조직 Bing 위치를 표시하는 데 지도 컨트롤이 사용됩니다. 컨트롤에는 선택한 사무실 위치에 대한 네트워크 경계 토폴로지도 표시됩니다. 관리자가 사무실 위치에 대한 특정 주소 정보를 추가하면 Bing 지도 쉽게 입력할 수 있도록 주소를 제안하는 데도 사용됩니다.

## <a name="terms-of-use"></a>사용 약관

지오코드를 Bing 지도 통해 제공되는 모든 콘텐츠는 콘텐츠가 제공되는 제품 내에서만 사용할 수 있습니다. 고객의 Microsoft 365 관리 센터 위치 서비스 기능 사용은 Bing 지도 사용 약관 및 Microsoft 개인 정보  취급 방침의 Bing 지도 End-User 사용 약관에 <https://go.microsoft.com/?linkid=9710837> 따라 [관리됩니다.](https://go.microsoft.com/fwlink/?LinkID=248686)

이 기능은 **TomTom** Bing 지도 통해 제공됩니다. TomTom의 제품 및 서비스에 대한 자세한 내용은 에서 찾을 수 [https://www.tomtom.com/legal](https://www.tomtom.com/legal) 있습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 관리 센터의 네트워크 연결(미리 보기)](office-365-network-mac-perf-overview.md)

[Microsoft 365 네트워크 성능 인사이트(미리 보기)](office-365-network-mac-perf-insights.md)

[Microsoft 365 네트워크 평가(미리 보기)](office-365-network-mac-perf-score.md)

[Microsoft 365(미리 보기)의 Microsoft 365 관리 센터 연결 테스트](office-365-network-mac-perf-onboarding-tool.md)
