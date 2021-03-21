---
title: 독일의 Office 365 끝점
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: 이 문서에서는 독일의 Office 365를 사용하는 고객이 도달할 수 있는 끝점을 찾을 수 있습니다.
hideEdit: true
ms.openlocfilehash: 8d3e8bfe2a52027b412aff87e063f2458ca47f74
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923993"
---
# <a name="office-365-germany-endpoints"></a>Office 365 Germany 끝점

 *적용 사항: Office 365 관리자*

Office 365를 사용하려면 인터넷에 연결해야 합니다. 아래 끝점은 **Office 365 Germany** 요금제만 사용하는 고객에게 도달할 수 있습니다.
  
 **Office 365 끝점:** [전 세계(GCC 포함)](urls-and-ip-address-ranges.md)  | [21vianet에서 운영하는 Microsoft Office 365](urls-and-ip-address-ranges-21vianet.md)  | *Microsoft Office 365 Germany*  |  [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**Last updated:** 12/01/2020 - ![ RSS ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) |**다운로드:** 모든 필수 및 선택 대상을 [JSON 형식](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) 목록에 다운로드합니다.  <br/> |

이 데이터를 사용하여 네트워크 연결을 관리하기 위한 권장 사항을 이해하려면 [Office 365 끝점 관리](managing-office-365-endpoints.md)에서 시작하세요. 끝점 데이터는 활성화되기 30일 전에 게시된 새 IP 주소와 URL을 사용하여 매월 초에 필요한 경우 업데이트됩니다. 따라서 아직 자동화된 업데이트가 없는 고객은 새 연결이 필요하기 전에 프로세스를 완료할 수 있습니다. 지원 에스컬레이션, 보안 인시던트 또는 기타 즉각적인 운영 요구 사항을 해결해야 하는 경우 끝점은 해당 월 중에 업데이트될 수도 있습니다. 변경 로그 구독 을 [항상 참조할 수 있습니다.](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

이 페이지에 아래에 표시된 데이터는 모두 REST 기반 웹 서비스에서 생성됩니다. 스크립트나 네트워크 장치를 사용하여 이 데이터에 액세스하는 경우 직접 [웹 서비스로](microsoft-365-ip-web-service.md) 이동해야 합니다.

아래의 끝점 데이터는 사용자의 컴퓨터와 Office 365의 연결에 대한 요구 사항을 나열합니다. 하이브리드 또는 인바운드 네트워크 연결이라고도 하는 Microsoft에서 고객 네트워크로의 네트워크 연결을 포함하지 않습니다.

끝점은 네 가지 서비스 영역으로 그룹화됩니다. 첫 번째 세 개의 서비스 영역은 연결용으로 개별 선택할 수 있습니다. 네 번째 서비스 영역(Microsoft 365 Common 및 Office 라고 함)은 일반적인 종속성이 있으며 항상 네트워크에 연결된 상태여야 합니다.

표시된 데이터 열:

- **ID**: 행의 ID 번호는 끝점 집합이라고도 합니다. 이 ID는 해당 끝점 집합에 대한 웹 서비스에서 반환되는 것과 동일합니다.

- **범주**: 끝점 집합이 "최적화", "허용" 또는 "기본"으로 분류되는지 여부를 보여줍니다. [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md)에서 이러한 범주 및 관리에 대한 지침을 읽을 수 있습니다. 이 열에서도 네트워크에 연결하는 데 필요한 끝점 집합을 나열합니다. 네트워크에 연결하는 데 필요하지 않은 끝점 집합의 경우, 이 필드에서 메모를 제공해 끝점 집합이 차단되면 어떤 기능을 사용할 수 없는지 표시해줍니다. 전체 서비스 영역을 제외하는 경우, 필요한 것으로 나열된 끝점 집합은 연결이 필요하지 않습니다.

- **ER**: Microsoft Azure ExpressRoute 및 Microsoft Office 365 경로 접두사에서 끝점 집합을 지원하는 경우 **예** 로 설정되어 있습니다. 표시된 경로 접두사를 포함하는 BGP 커뮤니티를 나열된 서비스 영역과 맞춥니다. ER이 **아니요** 인 경우는 ExpressRoute가 끝점 집합을 지원하지 않는다는 것을 의미합니다. 그러나 ER이 **아니요** 라고 하여 끝점 집합에 보급되는 경로가 없다고 간주할 수는 없습니다.

- **주소**: 끝점 집합의 FQDN 또는 와일드카드 도메인 이름 및 IP 주소 범위를 보여줍니다. IP 주소 범위가 CIDR 형식이며 특정 네트워크에서 여러 개의 개별 IP 주소를 포함할 수 있다는 점에 유의하시기 바랍니다.
 
- **포트**: 주소와 결합하여 네트워크 끝점을 이루는 TCP 또는 UDP 포트를 나열합니다. 다른 포트도 나열되어 있으면, IP 주소 범위에서 몇 가지 중복되는 경우도 있습니다.

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

