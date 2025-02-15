---
title: 'Office 365 URL 및 IP 주소 범위 '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/29/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: '요약: Office 365를 사용하려면 인터넷에 연결되어 있어야 합니다. 아래의 끝점은 Government 커뮤니티 클라우드(GCC)를 포함하여 Office 365 요금제를 사용하는 고객에 연결할 수 있어야 합니다.'
hideEdit: true
ms.openlocfilehash: d223ec20be108cdcfa53a2357e95cccdf6474e69
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60700888"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL 및 IP 주소 범위

Office 365를 사용하려면 인터넷에 연결되어 있어야 합니다. 아래의 끝점은 정부 커뮤니티 클라우드(GCC)를 포함하여 Office 365 요금제를 사용하는 고객에 연결할 수 있어야 합니다.
  
*Office 365 Worldwide(+GCC)* \| [Office 365(21 Vianet 제공)](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 독일](microsoft-365-germany-endpoints.md) \| [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) \| [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) \|

|메모|다운로드|사용|
|---|---|---|
|**최종 업데이트:** 2021년 10월 29일 - ![RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [로그 구독 변경](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**다운로드:** 모든 필수 및 선택 대상을 [JSON 형식](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) 목록에 다운로드합니다.|**사용:** 프록시 [PAC 파일](managing-office-365-endpoints.md#pacfiles)|
|

[Office 365 끝점 관리](managing-office-365-endpoints.md)에서 시작해 이 데이터를 사용해 네트워크 연결을 관리하는 데 추천하는 사항을 파악합니다. 끝점 데이터는 새 IP 주소 및 URL이 활성화되기 30일 전인 월초에 필요에 따라 업데이트됩니다. 이렇게 하면 자동 업데이트를 설정하지 않은 고객에게 새로운 연결이 필요하기 해당 프로세스를 완료할 수 있습니다. 끝점 주소는 지원 에스컬레이션, 보안 문제 또는 그 외의 즉각적인 운영 요구 사항을 처리하는 데 필요한 경우 월중에 업데이트될 수 있습니다. 이 페이지 아래에 표시되는 데이터는 모두 REST 기반 웹 서비스에서 생성됩니다. 스크립트 또는 네트워크 장치를 사용하여 이 데이터에 액세스 하는 경우, 직접 [웹 서비스](microsoft-365-ip-web-service.md)로 이동해야 합니다.

아래 끝점 데이터에는 사용자 컴퓨터에서 Office 365로 연결하기 위한 요구 사항이 나열되어 있습니다. Microsoft에서 고객 네트워크로의 네트워크 연결에 사용되는 IP 주소(하이브리드 또는 인바운드 네트워크 연결이라고도 함)에 대한 자세한 내용은 [추가 엔드포인트](additional-office365-ip-addresses-and-urls.md)를 참조하세요.

끝점은 세 가지 기본 워크로드와 공통 리소스 집합을 나타내는 네 가지 서비스 영역으로 그룹화됩니다. 그룹은 트래픽 흐름을 특정 애플리케이션과 연결하는 데 사용할 수 있지만 기능이 여러 워크로드에서 엔드포인트를 사용하는 경우가 많다는 점을 감안할 때 이러한 그룹은 액세스를 제한하는 데 효과적으로 사용할 수 없습니다.

표시된 데이터 열:

- **ID**: 행의 ID 번호는 끝점 집합이라고도 합니다. 이 ID는 해당 끝점 집합에 대한 웹 서비스에서 반환되는 것과 동일합니다.

- **범주**: 끝점 집합이 "최적화", "허용" 또는 "기본"으로 분류되는지 여부를 보여줍니다. [새로운 Office 365 끝점 범주](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)에서 범주 및 관리에 대한 지침을 읽을 수 있습니다. 이 열에서도 네트워크에 연결하는 데 필요한 끝점 집합을 나열합니다. 네트워크에 연결하는 데 필요하지 않은 끝점 집합의 경우, 이 필드에서 메모를 제공해 끝점 집합이 차단되면 어떤 기능을 사용할 수 없는지 표시해줍니다. 전체 서비스 영역을 제외하는 경우, 필요한 것으로 나열된 끝점 집합은 연결이 필요하지 않습니다.

- **ER**: Microsoft Azure ExpressRoute 및 Microsoft Office 365 경로 접두사에서 끝점 집합을 지원하는 경우 **예** 로 설정되어 있습니다. 표시된 경로 접두사를 포함하는 BGP 커뮤니티를 나열된 서비스 영역과 맞춥니다. ER이 **아니요** 인 경우는 ExpressRoute가 끝점 집합을 지원하지 않는다는 것을 의미합니다. 그러나 ER이 **아니요** 라고 하여 끝점 집합에 보급되는 경로가 없다고 간주할 수는 없습니다.

- **주소**: 끝점 집합의 FQDN 또는 와일드카드 도메인 이름 및 IP 주소 범위를 보여줍니다. IP 주소 범위가 CIDR 형식이며 특정 네트워크에서 여러 개의 개별 IP 주소를 포함할 수 있다는 점에 유의하시기 바랍니다.

- **포트**: 네트워크 끝점을 형성하기 위해 주소와 결합된 TCP 또는 UDP 포트를 나열합니다. 다른 포트가 나열된 IP 주소 범위에서 일부 중복을 볼 수 있습니다.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

> [!NOTE]
> Yammer IP 주소 및 URL에 대한 권장 사항은 [Yammer 블로그에서 하드 코드된 IP 주소 사용은 권장되지 않음](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592)을 참조하세요.

## <a name="related-topics"></a>관련 주제

[Office 365 IP 주소 및 URL 웹 서비스에 포함되지 않은 추가 엔드포인트](additional-office365-ip-addresses-and-urls.md)

[Office 365 끝점 관리](managing-office-365-endpoints.md)

[일반적인 Microsoft Stream 끝점](/stream/network-overview#general-microsoft-stream-endpoints)
  
[Microsoft 365 연결 모니터링](./monitor-connectivity.md)

[타사 응용 프로그램 시스템의 루트 CA 및 중간 CA 번들](../compliance/encryption-office-365-certificate-chains.md)
  
[클라이언트 연결](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[콘텐츠 배달 네트워크](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Microsoft Azure IP 범위 및 서비스 태그 – 공용 클라우드](https://www.microsoft.com/download/details.aspx?id=56519)

[Microsoft Azure IP 범위 및 서비스 태그 – 미국 정부 클라우드](https://www.microsoft.com/download/details.aspx?id=57063)

[Microsoft Azure IP 범위 및 서비스 태그 – 독일 클라우드](https://www.microsoft.com/download/details.aspx?id=57064)

[Microsoft Azure IP 범위 및 서비스 태그 – 중국 클라우드](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft 공용 IP 공간](https://www.microsoft.com/download/details.aspx?id=53602)

[서비스 이름 및 전송 프로토콜 포트 번호 레지스트리](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
