---
title: Office 365 미국 정부 GCC High 엔드포인트
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/29/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid: MET150
ms.assetid: cbd2369c-fd96-464c-bf48-c99826b459ee
description: 이 문서에서는 미국 정부 및 고가 요금제로 Office 365 끝점에 GCC 있습니다.
hideEdit: true
ms.openlocfilehash: a179a6637da33c7273d177594cab7f3dea4a1421
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60668310"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Office 365 미국 정부 GCC High 엔드포인트

*적용 사항: Office 365 관리자*

Office 365은 인터넷을 연결해야 합니다. The endpoints below should be reachable for customers using Office 365 U.S. Government GCC High plans only.
  
 **Office 365 끝점:** 미국 GCC Office 365 [](urls-and-ip-address-ranges.md) \| [21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 Germany](microsoft-365-germany-endpoints.md) Office 365 미국 정부 \| [DoD](microsoft-365-u-s-government-dod-endpoints.md) Office 365 미국 정부 GCC \| *High에서* 운영하는 전 세계(GCC 포함)

<br>

****

|메모|다운로드|
|---|---|
|**Last updated:** 10/29/2021 - ![ RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [로그 구독 변경](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**다운로드:** [JSON 형식의 전체 목록](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|
|

 이 데이터를 사용하여 네트워크 연결을 관리하기 위한 권장 사항을 이해하려면 [Office 365 끝점 관리](managing-office-365-endpoints.md)에서 시작하세요. 끝점 데이터는 활성화되기 30일 전에 게시된 새 IP 주소와 URL을 사용하여 매월 초에 필요한 경우 업데이트됩니다. 따라서 아직 자동화된 업데이트가 없는 고객은 새 연결이 필요하기 전에 프로세스를 완료할 수 있습니다. 지원 에스컬레이션, 보안 인시던트 또는 기타 즉각적인 운영 요구 사항을 해결해야 하는 경우 끝점은 해당 월 중에 업데이트될 수도 있습니다. 이 페이지에 아래에 표시된 데이터는 모두 REST 기반 웹 서비스에서 생성됩니다. 스크립트나 네트워크 장치를 사용하여 이 데이터에 액세스하는 경우 직접 [웹 서비스로](microsoft-365-ip-web-service.md) 이동해야 합니다.

아래의 끝점 데이터는 사용자의 컴퓨터에서 Microsoft Office 365에 연결할 때의 요구 사항을 나열합니다. 이는 하이브리드 또는 인바운드 네트워크 연결이라 불리며 Microsoft에서 고객 네트워크로의 네트워크 연결을 포함하지 않습니다.

끝점은 네 가지 서비스 영역으로 그룹화됩니다. 첫 번째 세 개의 서비스 영역은 연결용으로 개별 선택할 수 있습니다. 네 번째 서비스 영역(Microsoft 365 Common 및 Office 라고 함)은 일반적인 종속성이 있으며 항상 네트워크에 연결된 상태여야 합니다.

표시된 데이터 열:

- **ID**: 행의 ID 번호는 끝점 집합이라고도 합니다. 이 ID는 해당 끝점 집합에 대한 웹 서비스에서 반환되는 것과 동일합니다.

- **범주**: 끝점 집합이 "최적화", "허용" 또는 "기본"으로 분류되는지 여부를 보여줍니다. [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md)에서 이러한 범주 및 관리에 대한 지침을 읽을 수 있습니다. 이 열에서도 네트워크에 연결하는 데 필요한 끝점 집합을 나열합니다. 네트워크에 연결하는 데 필요하지 않은 끝점 집합의 경우, 이 필드에서 메모를 제공해 끝점 집합이 차단되면 어떤 기능을 사용할 수 없는지 표시해줍니다. 전체 서비스 영역을 제외하는 경우, 필요한 것으로 나열된 끝점 집합은 연결이 필요하지 않습니다.

- **ER**:  끝점 집합이 Azure ExpressRoute에서 지원되는 경우 예입니다Office 365. 표시된 경로 prefix가 포함된 BGP 커뮤니티는 나열된 서비스 영역에 맞춰 정렬됩니다. ER이 **아니요인** 경우 이는 ExpressRoute가 이 끝점 집합에 지원되지 않는다는 의미입니다. 그러나 ER이 아니요인 끝점 집합에 대해 보급되는 경로가 없다고 가정하면 **안 됩니다.** Azure AD 커넥트 사용하려면 특수 고려 사항 [](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) 섹션을 읽고 적절한 Azure AD 구성을 커넥트 합니다.

- **주소**: 끝점 집합의 FQDN 또는 와일드카드 도메인 이름 및 IP 주소 범위를 보여줍니다. IP 주소 범위가 CIDR 형식이며 특정 네트워크에서 여러 개의 개별 IP 주소를 포함할 수 있다는 점에 유의하시기 바랍니다.

- **포트**: 네트워크 끝점을 형성하기 위해 주소와 결합된 TCP 또는 UDP 포트를 나열합니다. 다른 포트가 나열된 IP 주소 범위에서 일부 중복을 볼 수 있습니다.

[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

이 표에 대한 참고 사항

- SCC(보안 및 준수 센터)는 Azure ExpressRoute를 Office 365. 보고, 감사, Advanced eDiscovery, 통합 DLP 및 데이터 거버넌스와 같이 SCC를 통해 노출되는 많은 기능에도 동일하게 적용됩니다. PST Import 및 eDiscovery Export의 두 가지 특정 기능은 현재 Azure Blob 및 eDiscovery에 대한 종속성으로 인해 Office 365 경로 필터만 사용하여 Azure ExpressRoute를 지원하지 Storage. 이러한 기능을 사용하려면 인터넷 연결 또는 Azure 공용 경로 필터를 Storage Azure ExpressRoute를 사용하는 지원되는 Azure 연결 옵션을 사용하여 Azure Blob 2013에 별도의 연결이 필요합니다. 이러한 두 기능에 대해 이러한 연결을 설정하는지 평가해야 합니다. Office 365 Information Protection 팀은 이러한 제한에 대해 알고 있으며 이러한 두 기능에 대한 Office 365 경로 필터로 제한되는 Office 365 Office 365 Azure ExpressRoute에 대한 지원을 제공하기 위해 적극적으로 작업하고 있습니다.

- 목록에 없는 추가 선택적 엔터프라이즈용 Microsoft 365 앱 응용 프로그램을 시작하고 문서를 편집하는 데 필요하지 않은 추가 엔터프라이즈용 Microsoft 365 앱 끝점이 있습니다. 선택적 끝점은 Microsoft 데이터 센터에서 호스팅하며 고객 데이터를 처리, 전송 또는 저장하지 않습니다. 이러한 끝점에 대한 사용자 연결은 기본 인터넷 시작 경계로 연결하는 것이 좋습니다.
