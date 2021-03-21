---
title: 'Office 365 URL 및 IP 주소 범위 '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/01/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
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
ms.openlocfilehash: 1c0a2a486bf6964edc9b94fd670c96ade161cacd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925271"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="0394d-104">Office 365 URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="0394d-104">Office 365 URLs and IP address ranges</span></span>

<span data-ttu-id="0394d-p102">Office 365를 사용하려면 인터넷에 연결되어 있어야 합니다. 아래의 끝점은 정부 커뮤니티 클라우드(GCC)를 포함하여 Office 365 요금제를 사용하는 고객에 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-p102">Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
<span data-ttu-id="0394d-107">*Office 365 Worldwide(+GCC)* | [21vianet에서 운영하는 Microsoft Office 365](urls-and-ip-address-ranges-21vianet.md) | [Microsoft Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="0394d-107">*Office 365 Worldwide (+GCC)* | [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="0394d-108">**마지막 업데이트:** 2021/01/03 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [로그 구독 변경](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="0394d-108">**Last updated:** 03/01/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span> <br/> |<span data-ttu-id="0394d-109">**다운로드:** 모든 필수 및 선택 대상을 [JSON 형식](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) 목록에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-109">**Download:** all required and optional destinations in one [JSON formatted](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) list.</span></span>  <br/> | <span data-ttu-id="0394d-110">**사용:** 프록시 [PAC 파일](managing-office-365-endpoints.md#pacfiles)</span><span class="sxs-lookup"><span data-stu-id="0394d-110">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span> <br/> |

 <span data-ttu-id="0394d-111">이 데이터를 사용하여 네트워크 연결을 관리하기 위한 권장 사항을 이해하려면 [Office 365 끝점 관리](managing-office-365-endpoints.md)에서 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="0394d-111">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data.</span></span> <span data-ttu-id="0394d-112">끝점 데이터는 활성화되기 30일 전에 게시된 새 IP 주소와 URL을 사용하여 매월 초에 필요한 경우 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-112">Endpoints data is updated as needed at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active.</span></span> <span data-ttu-id="0394d-113">이를 통해 새 연결이 필요하기 전에 아직 자동 업데이트를 사용하지 않는 고객이 프로세스를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-113">This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required.</span></span> <span data-ttu-id="0394d-114">지원 에스컬레이션, 보안 인시던트 또는 기타 즉각적인 운영 요구 사항을 해결해야 하는 경우 끝점은 해당 월 중에 업데이트될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-114">Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements.</span></span> <span data-ttu-id="0394d-115">이 페이지에 아래에 표시된 데이터는 모두 REST 기반 웹 서비스에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-115">The data shown on this page below is all generated from the REST-based web services.</span></span> <span data-ttu-id="0394d-116">스크립트나 네트워크 장치를 사용하여 이 데이터에 액세스하는 경우 직접 [웹 서비스로](microsoft-365-ip-web-service.md) 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-116">If you are using a script or a network device to access this data, you should go to the [Web service](microsoft-365-ip-web-service.md) directly.</span></span>

<span data-ttu-id="0394d-p104">아래의 엔드포인트 데이터는 사용자의 컴퓨터에서 Microsoft Office 365에 연결할 때의 요구 사항을 나열합니다. 이는 하이브리드 또는 인바운드 네트워크 연결이라 불리며 Microsoft에서 고객 네트워크로의 네트워크 연결을 포함하지 않습니다. 자세한 내용은 [추가 끝점](additional-office365-ip-addresses-and-urls.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0394d-p104">Endpoint data below lists requirements for connectivity from a user's machine to Office 365. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections. See [Additional endpoints](additional-office365-ip-addresses-and-urls.md) for more information.</span></span>

<span data-ttu-id="0394d-p105">끝점은 네 가지 서비스 영역으로 그룹화됩니다. 첫 번째 세 개의 서비스 영역은 연결용으로 개별 선택할 수 있습니다. 네 번째 서비스 영역(Microsoft 365 Common 및 Office 라고 함)은 일반적인 종속성이 있으며 항상 네트워크에 연결된 상태여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-p105">The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office) and must always have network connectivity.</span></span>

<span data-ttu-id="0394d-123">표시된 데이터 열:</span><span class="sxs-lookup"><span data-stu-id="0394d-123">Data columns shown are:</span></span>

- <span data-ttu-id="0394d-p106">**ID**: 행의 ID 번호는 끝점 집합이라고도 합니다. 이 ID는 해당 끝점 집합에 대한 웹 서비스에서 반환되는 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-p106">**ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="0394d-p107">**범주**: 끝점 집합이 "최적화", "허용" 또는 "기본"으로 분류되는지 여부를 보여줍니다. [새로운 Office 365 끝점 범주](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)에서 범주 및 관리에 대한 지침을 읽을 수 있습니다. 이 열에서도 네트워크에 연결하는 데 필요한 끝점 집합을 나열합니다. 네트워크에 연결하는 데 필요하지 않은 끝점 집합의 경우, 이 필드에서 메모를 제공해 끝점 집합이 차단되면 어떤 기능을 사용할 수 없는지 표시해줍니다. 전체 서비스 영역을 제외하는 경우, 필요한 것으로 나열된 끝점 집합은 연결이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-p107">**Category**: Shows whether the endpoint set is categorized as "Optimize", "Allow", or "Default". You can read about these categories and guidance for management of them at [New Office 365 endpoint categories](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). This column also lists which endpoint sets are required to have network connectivity. For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="0394d-p108">**ER**: Microsoft Azure ExpressRoute 및 Microsoft Office 365 경로 접두사에서 끝점 집합을 지원하는 경우 **예** 로 설정되어 있습니다. 표시된 경로 접두사를 포함하는 BGP 커뮤니티를 나열된 서비스 영역과 맞춥니다. ER이 **아니요** 인 경우는 ExpressRoute가 끝점 집합을 지원하지 않는다는 것을 의미합니다. 그러나 ER이 **아니요** 라고 하여 끝점 집합에 보급되는 경로가 없다고 간주할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-p108">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="0394d-p109">**주소**: 끝점 집합의 FQDN 또는 와일드카드 도메인 이름 및 IP 주소 범위를 보여줍니다. IP 주소 범위가 CIDR 형식이며 특정 네트워크에서 여러 개의 개별 IP 주소를 포함할 수 있다는 점에 유의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-p109">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="0394d-p110">**포트**: 네트워크 끝점을 형성하기 위해 주소와 결합된 TCP 또는 UDP 포트를 나열합니다. 다른 포트가 나열된 IP 주소 범위에서 일부 중복을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-p110">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
><span data-ttu-id="0394d-139">Yammer IP 주소 및 URL에 대한 권장 사항은 [Yammer 블로그에서 하드 코드된 IP 주소 사용은 권장되지 않음](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0394d-139">For recommendations on Yammer IP addresses and URLs, see [Using hard-coded IP addresses for Yammer is not recommended](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) on the Yammer blog.</span></span>
>

## <a name="related-topics"></a><span data-ttu-id="0394d-140">관련 주제</span><span class="sxs-lookup"><span data-stu-id="0394d-140">Related Topics</span></span>

[<span data-ttu-id="0394d-141">Office 365 끝점 관리</span><span class="sxs-lookup"><span data-stu-id="0394d-141">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="0394d-142">일반적인 Microsoft Stream 끝점</span><span class="sxs-lookup"><span data-stu-id="0394d-142">General Microsoft Stream endpoints</span></span>](/stream/network-overview#general-microsoft-stream-endpoints)
  
[<span data-ttu-id="0394d-143">Microsoft 365 연결 모니터링</span><span class="sxs-lookup"><span data-stu-id="0394d-143">Monitor Microsoft 365 connectivity</span></span>](./monitor-connectivity.md)

[<span data-ttu-id="0394d-144">타사 응용 프로그램 시스템의 루트 CA 및 중간 CA 번들</span><span class="sxs-lookup"><span data-stu-id="0394d-144">Root CA and the Intermediate CA bundle on the third-party application system</span></span>](../compliance/encryption-office-365-certificate-chains.md)
  
[<span data-ttu-id="0394d-145">클라이언트 연결</span><span class="sxs-lookup"><span data-stu-id="0394d-145">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="0394d-146">콘텐츠 배달 네트워크</span><span class="sxs-lookup"><span data-stu-id="0394d-146">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="0394d-147">Microsoft Azure IP 범위 및 서비스 태그 – 공용 클라우드</span><span class="sxs-lookup"><span data-stu-id="0394d-147">Microsoft Azure IP Ranges and Service Tags – Public Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=56519)

[<span data-ttu-id="0394d-148">Microsoft Azure IP 범위 및 서비스 태그 – 미국 정부 클라우드</span><span class="sxs-lookup"><span data-stu-id="0394d-148">Microsoft Azure IP Ranges and Service Tags – US Government Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57063)

[<span data-ttu-id="0394d-149">Microsoft Azure IP 범위 및 서비스 태그 – 독일 클라우드</span><span class="sxs-lookup"><span data-stu-id="0394d-149">Microsoft Azure IP Ranges and Service Tags – Germany Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57064)

[<span data-ttu-id="0394d-150">Microsoft Azure IP 범위 및 서비스 태그 – 중국 클라우드</span><span class="sxs-lookup"><span data-stu-id="0394d-150">Microsoft Azure IP Ranges and Service Tags – China Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57062)
  
[<span data-ttu-id="0394d-151">Microsoft 공용 IP 공간</span><span class="sxs-lookup"><span data-stu-id="0394d-151">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)

[<span data-ttu-id="0394d-152">서비스 이름 및 전송 프로토콜 포트 번호 레지스트리</span><span class="sxs-lookup"><span data-stu-id="0394d-152">Service Name and Transport Protocol Port Number Registry</span></span>](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)