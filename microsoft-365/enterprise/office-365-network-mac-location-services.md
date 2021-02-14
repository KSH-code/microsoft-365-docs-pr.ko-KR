---
title: Microsoft 365 Network Connectivity Location Services(미리 보기)
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
description: Microsoft 365 Network Connectivity Location Services(미리 보기)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200784"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Microsoft 365 Network Connectivity Location Services(미리 보기)

이제 Microsoft 365 관리 센터에는 Microsoft 365 테넌트에서 수집되고 테넌트의 관리자만 볼 수 있는 라이브 성능 메트릭인 **네트워크** 인사이트 및 성능 권장 사항이 표시됩니다. 조직 네트워크 연결은 인터넷으로의 네트워크 이동 위치를 통해 사무실 위치당 디자인됩니다. Microsoft 365 클라이언트 연결은 해당 경로를 사용하여 인터넷을 통해 Microsoft 서비스 프런트 도어 서버를 연결합니다. 사무실 위치를 식별하는 것은 이러한 네트워크 정보를 표시하는 데 핵심입니다.

## <a name="location-in-network-measurements"></a>네트워크 측정 위치

조직의 관리자는 이 기능에 사용되는 네트워크 측정에 포함될 위치를 옵트인(opt in)할 수 있습니다. 이렇게 하면 각 사무실이 있는 도시를 자동으로 검색할 수 있습니다. 위치 정보는 정확하지 않습니다. 300m로 난청되어 도시별로 분류됩니다. Windows 장치에서 위치가 캡처될 때 도구 트레이에  사용 중 위치 아이콘이 표시될 수 있으며 관리자는 이를 사용자에게 알릴 수 있습니다. 이 처리를 통해 위치는 개인 또는 장치의 위치가 아니라 조직 사무실 위치로 처리됩니다. 네트워크 인사이트는 검색된 사무실 위치 도시에서 볼 수 있습니다. 권장 사항이 더 정확하게 필요한 경우 관리자는 특정 사무실 위치 주소를 입력할 수 있으며 네트워크 인사이트는 대신 이러한 주소로 집계됩니다. Office 위치는 300미터보다 긴밀하게 집계할 수 없습니다.

## <a name="location-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터의 위치

Microsoft 365 관리 센터에서 Bing 지도 컨트롤은 조직 사무실 위치 위치를 표시하고 선택한 사무실 위치에 대한 네트워크 경계 토폴로지 표시에 사용됩니다. 관리자가 사무실 위치에 대한 특정 주소 정보를 추가하면 Bing 지도를 사용하여 데이터를 보다 쉽게 입력할 수 있도록 주소를 제안합니다.

## <a name="terms-of-use"></a>사용 약관

Bing 지도를 통해 제공되는 모든 콘텐츠(지오코드 포함)는 콘텐츠가 제공되는 제품 내에서만 사용할 수 있습니다. 고객의 Microsoft 365 관리 센터 위치 서비스 기능 사용은 Bing 지도를 통해 지원됩니다. _Bing 지도_ 최종 사용자 사용 약관 및 사용 가능한 Microsoft 개인 정보 취급 방침의 <https://go.microsoft.com/?linkid=9710837> 관리 <https://go.microsoft.com/fwlink/?LinkID=248686.>

Bing 지도를 통해 제공되는 이 기능은 **Here 기술에서도 지원됩니다.** Bing 지도가 여기 기술에서 제공하는 위치 서비스를 활용하는 방식은 사용 가능한 여기 기술 _서비스_ 약관에 따라 <https://legal.here.com/en-gb/terms> 관리됩니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 관리 센터의 네트워크 연결(미리 보기)](office-365-network-mac-perf-overview.md)

[Microsoft 365 네트워크 성능 인사이트(미리 보기)](office-365-network-mac-perf-insights.md)

[Microsoft 365 네트워크 평가(미리 보기)](office-365-network-mac-perf-score.md)

[M365 관리 센터의 Microsoft 365 연결 테스트(미리 보기)](office-365-network-mac-perf-onboarding-tool.md)
