---
title: 콘텐츠 배달 네트워크
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: 이 정보를 사용하여 OFFICE 365 CDNS(콘텐츠 배달 네트워크)를 사용하여 성능을 개선하는 방법에 대해 자세히 알아보겠습니다.
ms.openlocfilehash: 1aecd8b23502ed8626979d258f7d26a90b4d3d51
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60186696"
---
# <a name="content-delivery-networks-cdns"></a>콘텐츠 배달 네트워크(CDN)

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

CDNS를 사용하면 최종 Office 365 빠르고 안정적으로 사용할 수 있습니다. Office 365 같은 클라우드 서비스는 CDNS를 사용하여 요청하는 브라우저에 더 가까운 정적 자산을 캐시하여 다운로드 속도를 향상하고 인식된 최종 사용자 대기 시간을 줄입니다. 이 항목의 정보는 CDNS(콘텐츠 배달 네트워크)와 CDNs에서 사용하는 방법에 대해 자세히 Office 365.

## <a name="what-exactly-is-a-cdn"></a>정확히 어떤 것이 CDN?

CDN 네트워크는 고속 백본 네트워크로 연결된 데이터 센터의 프록시 및 파일 서버로 구성된 지리적으로 분산된 네트워크입니다. CDNS는 웹 사이트 또는 서비스의 지정된 파일 및 개체 집합에 대한 대기 시간 및 로드 시간을 줄이는 데 사용됩니다. 한 CDN 위치에서 들어오는 요청을 최적으로 처리하기 위해 수천 개의 끝점이 있을 수 있습니다.

CDNS는 일반적으로 Javascript 파일, 아이콘 및 이미지와 같은 웹 사이트 또는 서비스에 대한 일반 콘텐츠를 더 빠르게 다운로드하는 데 사용하며, SharePoint Online 문서 라이브러리의 파일, 스트리밍 미디어 파일 및 사용자 지정 코드와 같은 사용자 콘텐츠에 대한 개인 액세스를 제공할 수도 있습니다.

CDNS는 대부분의 엔터프라이즈 클라우드 서비스에서 사용됩니다. Office 365 같은 클라우드 서비스에는 전자 메일과 같은 독점 콘텐츠와 일반 콘텐츠(예: 아이콘)의 혼합을 다운로드하는 고객이 수백만 명 있습니다. 모든 사용자가 사용하는 이미지(아이콘)를 사용자 컴퓨터에 최대한 가깝게 두는 것이 더 효율적입니다. 모든 클라우드 서비스가 모든 대도시 지역이나 전 세계 모든 주요 인터넷 허브에 이러한 일반 콘텐츠를 저장하는 CDN 데이터 센터를 구축하여 이러한 CDNS 중 일부를 공유하는 것은 실용적이지 않습니다.

## <a name="how-do-cdns-make-services-work-faster"></a>CDNS를 통해 서비스가 어떻게 더 빠르게 작동할 수 있나요?

사이트 이미지 및 아이콘과 같은 일반적인 개체를 여러 번 다운로드하면 전자 메일 또는 문서와 같은 중요한 개인 콘텐츠를 다운로드하는 데 더 잘 사용할 수 있는 네트워크 대역폭을 사용할 수 있습니다. 이 Office 365 CDNS가 포함된 아키텍처를 사용하기 때문에 클라이언트 컴퓨터와 더 가까운 서버에서 아이콘, 스크립트 및 기타 일반 콘텐츠를 다운로드할 수 있어 다운로드 속도가 빨라집니다. 즉, 데이터 센터에 안전하게 저장되는 개인 콘텐츠에 Office 365 수 있습니다.

CDNS는 여러 가지 방법으로 클라우드 서비스 성능을 개선하는 데 도움이 됩니다.

- CDNS는 네트워크 및 파일 다운로드 부담을 클라우드 서비스에서 멀어지면서 고정 자산에 대한 요청을 처리해야 하는 필요성을 줄여 사용자 콘텐츠 및 기타 서비스를 제공하는 클라우드 서비스 리소스를 확보합니다.
- CDNS는 고성능 네트워크 및 파일 서버를 구현하고 [HTTP/2와](https://en.wikipedia.org/wiki/HTTP/2) 같은 업데이트된 네트워크 프로토콜을 활용하여 대기 시간이 짧은 파일 액세스를 제공하기 위해 고안되었습니다.
- CDN 네트워크에서는 전역으로 분산된 여러 끝점을 사용하여 사용자가 콘텐츠를 최대한 가깝게 사용할 수 있도록 합니다.

## <a name="the-office-365-cdn"></a>Office 365 CDN

기본 제공 Office 365 Content Delivery Network(CDN)를 사용하면 Office 365 관리자가 정적 자산을 요청하는 브라우저에 더 가깝게 캐싱하여 조직의 SharePoint Online 페이지에 대한 성능을 향상할 수 있으며, 이를 통해 다운로드 속도를 향상하고 대기 시간을 단축할 수 있습니다. 이 Office 365 CDN [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) 프로토콜을 사용하여 압축 및 다운로드 속도를 향상합니다.

> [!NOTE]
> 이 Office 365 CDN 프로덕션(전 세계) 클라우드의  테넌트만 사용할 수 있습니다. 미국 정부, 중국 및 독일 클라우드의 테넌트는 현재 이 서비스를 지원하지 Office 365 CDN.

Office 365 CDN은 여러 위치, 즉 _출발지_ 에 정적 자산을 호스트하고 글로벌 고속 네트워크에서 제공할 수 있는 여러 CDN으로 구성됩니다. Office 365 CDN에서 호스팅하려는 콘텐츠의 종류에 따라 **공개** 출처, **비공개** 출처 또는 둘 다를 추가할 수 있습니다.

![Office 365 CDN 다이어그램을 참조합니다.](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN 다이어그램")

Office 365 CDN 내의 **공개** 출처의 콘텐츠는 익명으로 액세스할 수 있으며 호스팅 된 자산에 대한 URL을 지닌 사람이면 누구나 액세스할 수 있습니다. 공개 출처의 콘텐츠에 대한 액세스는 익명이기 때문에 Javascript 파일, 스크립트, 아이콘 및 이미지와 같은 중요하지 않은 일반 콘텐츠를 캐시하는 데만 해당 콘텐츠를 사용해야 합니다. Office 365 CDN은 기본적으로 공개 출처의 Office 365 클라이언트 응용 프로그램 같은 일반 리소스를 다운로드하는 데 사용됩니다.

**사이트** 내의 비공개 출처는 Office 365 CDN 온라인 문서 라이브러리, 사이트 및 소유 이미지와 SharePoint 콘텐츠에 대한 개인 액세스를 제공합니다. 비공개 출처의 콘텐츠에 대한 액세스는 동적으로 생성 된 토큰으로 보호되므로 원본 문서 라이브러리 또는 저장 위치에 대한 사용 권한을 가진 사용자만 액세스할 수 있습니다. Office 365 CDN의 비공개 출처는 SharePoint Online 콘텐츠에만 사용할 수 있으며 SharePoint Online 테넌트의 리디렉션을 통해 자산에만 액세스할 수 있습니다.

Office 365 CDN 서비스는 SharePoint Online 구독의 일부로 포함되어 있습니다.

Office 365 CDN 방법에 대한 자세한 내용은 Use the [Office 365 content delivery network with SharePoint Online을 참조하십시오.](use-microsoft-365-cdn-with-spo.md)

앱 사용에 대한 개념 및 HOWTO 정보를 제공하는 일련의 짧은 비디오를 Office 365 CDN 개발자 패턴 및 SharePoint YouTube 채널을 [방문하세요.](https://aka.ms/sppnp-videos)

## <a name="other-microsoft-cdns"></a>기타 Microsoft CDNS

Office 365 CDN 일부가 아니어도 Office 365 테넌트에서 이러한 CDNS를 사용하여 SharePoint 개발 라이브러리, 사용자 지정 코드 및 기타 용도에 액세스할 수 Office 365 CDN.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>2020년 3분기부터 SharePoint Online은 향상된 비디오 재생 및 안정성을 지원하기 위해 Azure CDN 비디오 캐싱을 시작할 것입니다. 인기 있는 비디오는 사용자에게 가장 가까운 CDN 비디오에서 스트리밍됩니다. 이 데이터는 준수 경계 내에 Microsoft 365 유지됩니다. 이 서비스는 모든 테넌트에 대한 무료 서비스이며 구성하기 위해 고객 작업이 필요하지 않습니다.

Azure CDN 사용하여  사용자 지정 웹 파트CDN 라이브러리 및 기타 리소스 자산을 호스팅하기 위한 자체 CDN 인스턴스를 배포할 수 있습니다. 이렇게 하면 CDN 저장소에 선택키를 적용하고 CDN 구성을 보다 세분화할 수 있습니다. 이 Azure CDN 무료가 아니며 Azure 구독이 필요합니다.

Azure CDN 인스턴스를 구성하는 방법에 대한 자세한 내용은 [빠른 시작: Azure](/azure/cdn/cdn-create-a-storage-account-with-cdn)저장소 계정과 통합을 Azure CDN.

웹 파트를 호스팅하는 Azure CDN 방법의 예는 SharePoint 클라이언트 쪽 웹 파트를 SharePoint 배포를 [Azure CDN.](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn)

PowerShell 모듈의 Azure CDN 자세한 내용은 [PowerShell을 사용하여 Azure CDN 관리를 참조하세요.](/azure/cdn/cdn-manage-powershell)

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsoft의 **Ajax CDN ajax** CDN jQuery(및 기타 모든 라이브러리), ASP.NET Ajax, 부트스트럭, Knockout.js 등 많은 인기 개발 라이브러리를 제공하는 읽기 전용 라이브러리입니다.
  
프로젝트에 이러한 스크립트를 포함하기 위해 공개적으로 사용할 수 있는 라이브러리에 대한 참조를 프로젝트 자체에 포함하지 않고 CDN 주소에 대한 참조로 바꾸면 됩니다. 예를 들어 다음 코드를 사용하여 jQuery에 연결합니다.

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Microsoft Ajax 응용 CDN 방법에 대한 자세한 내용은 [Microsoft Ajax](/aspnet/ajax/cdn/overview)CDN.

## <a name="how-does-office-365-use-content-from-a-cdn"></a>웹 Office 365 콘텐츠는 어떻게 CDN?

CDN 테넌트에 대해 구성하는 Office 365 관계없이 기본 데이터 검색 프로세스는 동일합니다.

1. 클라이언트(브라우저 또는 Office 응용 프로그램)가 클라이언트에서 데이터를 Office 365.

2. Office 365 데이터를 클라이언트에 직접 반환하거나 데이터가 클라이언트에서 호스팅하는 콘텐츠 집합의 일부인 CDN 클라이언트를 CDN URL로 리디렉션합니다.

    a. 데이터가 공개 원본에 이미  캐시되어 있는 경우 클라이언트는 가장 가까운 위치에서 클라이언트로 CDN 직접 다운로드합니다.

    b. 데이터가 이미 개인 원본에  캐시되어 있는 경우 CDN 서비스에서 원본에 대한 Office 365 사용자 계정의 권한을 검사합니다. 권한이 있는 경우 SharePoint Online은 CDN 및 두 개의 액세스 토큰에 대한 경로로 구성된 사용자 지정 URL을 동적으로 생성하고 클라이언트에 사용자 지정 URL을 반환합니다. 그런 다음 클라이언트는 사용자 지정 URL을 사용하여 가장 가까운 CDN 위치에서 클라이언트로 데이터를 직접 다운로드합니다.

3. 데이터가 CDN 캐시되지 않은 경우 CDN 노드는 Office 365 데이터를 요청한 다음 클라이언트가 데이터를 다운로드한 후 Office 365 동안 데이터를 캐시합니다.

이 CDN 브라우저에 가장 가까운 데이터 센터를 알아내고 리디렉션을 사용하여 요청된 데이터를 다운로드합니다. CDN 리디렉션이 빠르고 사용자에게 많은 다운로드 시간을 절약할 수 있습니다.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>CDNS가 네트워크에서 가장 잘 작동할 수 있도록 네트워크를 설정해야 Office 365?

네트워크의 클라이언트와 CDN 끝점 간의 대기 시간을 최소화하는 것이 최적의 성능을 보장하기 위한 주요 고려 사항입니다. [Managing Office 365 endpoints에](managing-office-365-endpoints.md) 설명된 모범 사례를 사용하여 네트워크 구성에서 불필요한 대기 시간을 유발하지 않도록 중앙 CDN 트래픽을 라우팅하는 대신 클라이언트 브라우저에서 CDN 직접 액세스할 수 있도록 할 수 있습니다.

또한 네트워크 연결 [Office 365](./microsoft-365-network-connectivity-principles.md) 최적화의 개념을 이해하기 위해 네트워크 연결 원칙을 Office 365 수 있습니다.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>사용하는 모든 CDNS 목록이 Office 365 있습니까?

OFFICE 365 사용 중이던 CDNS는 항상 변경될 수 있으며, 대부분의 경우 사용할 수 없는 이벤트에 여러 CDN 파트너가 구성됩니다. 기본 CDNS는 Office 365.

|CDN  |Company  |사용 현황  |링크  |
|---------|---------|---------|---------|
|Office 365 CDN     |Microsoft Azure         |공개 출처의 일반 자산, SharePoint 원본의 사용자 콘텐츠         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Azure CDN     |Microsoft         |사용자 지정 코드, SharePoint 프레임워크 솔루션         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN(읽기 전용)     |Microsoft         |Ajax, jQuery, ASP.NET, 부트스트ap, Knockout.js 라이브러리         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>이 경우 성능상 어떤 CDN 있나요?

테넌트와 가장 가까운 CDN 끝점에 대한 위치, CDN 및 대역폭의 일시적인 변경 등 Office 365에서 직접 다운로드한 데이터와 특정 CDN에서 다운로드한 데이터 간의 성능 차이를 측정하는 데에는 여러 가지 요인이 있습니다. 그러나 간단한 A/B 테스트는 특정 파일의 다운로드 시간 차이를 표시하는 데 도움이 될 수 있습니다.

다음 스크린샷은 의 기본 파일 위치와 [Microsoft Ajax](/aspnet/ajax/cdn/overview)Office 365 호스트되는 파일 간의 다운로드 속도 차이를 Content Delivery Network. 이러한 스크린샷은 11개 개발자 **도구의** 네트워크 Internet Explorer 있습니다. 이러한 스크린샷은 인기 라이브러리 jQuery의 대기 시간을 보여 합니다. 이 화면을 표시하려면 Internet Explorer **F12를** 누르고 네트워크  탭을 선택하면 Wi-Fi 표시됩니다.
  
![F12 네트워크 스크린샷.](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
이 스크린샷은 온라인 사이트 자체의 마스터 페이지 갤러리에 SharePoint 보여줍니다. 라이브러리를 업로드하는 데 걸려간 시간은 1.51초입니다.
  
![로드 시간 1.51의 스크린샷.](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
두 번째 스크린샷은 Microsoft에서 제공한 동일한 파일을 CDN. 이 시간의 대기 시간은 약 496밀리초입니다. 이는 크게 개선된 기능으로, 개체를 다운로드하는 데 1초가 1초가 떨어졌다는 것입니다.
  
![469 ms의 로드 시간 스크린샷.](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>내 데이터가 안전한가요?

당사는 비즈니스를 운영하는 데이터를 보호하기 위해 많은 주의를 다합니다. 전송 중이나 Office 365 CDN 모두 암호화되며, 사용자 권한 및 토큰 권한 Office 365 SharePoint CDN 액세스는 Office 365 보호됩니다. Office 365 SharePoint CDN 데이터 요청은 Office 365 또는 권한 부여 토큰에서 참조(리디렉션)해야 합니다.

데이터를 안전하게 유지 관리하기 위해 공용 저장소에 사용자 콘텐츠 또는 기타 중요한 데이터를 저장하지 않는 것이 CDN. 공용 데이터 액세스는 익명이기 CDN 공용 CDNS는 웹 스크립트 파일, 아이콘, 이미지 및 기타 중요하지 않은 자산과 같은 일반 콘텐츠를 호스팅하는 데만 사용되어야 합니다.

> [!NOTE]
> 제3자 CDN 공급자는 보안 센터에 명시된 약정과는 다른 개인 정보 보호 및 규정 준수 Office 365 있습니다. CDN 서비스를 통해 캐시된 데이터는 Microsoft DPT(데이터 처리 약관)를 준수하지 않을 수 있으며 보안 센터 준수 경계를 Office 365 수 있습니다.

Office 365 CDN 공급자의 개인 정보 보호 및 데이터 보호에 대한 자세한 내용은 다음을 방문하세요.  

- Microsoft 보안 Office 365 개인 정보 보호 및 데이터 보호에 대한 자세한 [정보](https://www.microsoft.com/trustcenter)
- Akamai 개인 정보 보호 보안 센터에서 Akamai의 개인 정보 보호 및 데이터 보호에 [대해 자세히 알아보시고](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Azure 보안 센터에서 Azure 개인 정보 보호 및 데이터 보호에 [대한 자세한 정보](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>이러한 모든 제3자 서비스를 사용하여 네트워크를 보호하는 방법

광범위한 파트너 서비스 집합을 활용하면 Office 365 사용할 때 가용성 요구 사항을 확장하고 충족하고 사용자 환경을 향상시킬 수 Office 365. 활용을 위한 제3자 Office 365 인증서 해지 목록이 모두 포함됩니다. 예: crl.microsoft.com 또는 sa.symcb.com, CDNs; 예로 r3.res.outlook.com. 모든 CDN FQDN은 Office 365 사용자 지정 FQDN Office 365. 요청 시 FQDN으로 전송되는 경우 Office 365 공급자가 해당 위치의 FQDN 및 CDN 콘텐츠를 제어합니다.
  
Microsoft 또는 Office 365 데이터 센터로 전송되는 요청을 제3자로 전송되는 요청과 분산하려는 고객의 경우 Office 365 끝점 관리에 대한 지침을 [작성했습니다.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>CDNS를 활용하는 모든 FQDNS 목록이 있나요?

FQDNS 목록 및 시간이 지날수록 CDNS를 활용하는 방법 게시된 Office 365 URL 및 [IP](./urls-and-ip-address-ranges.md) 주소 범위 페이지를 참조하여 CDNS를 활용하는 최신 FQDNS를 최신으로 업데이트합니다.

또한 IP 주소 [및 URL Office 365](microsoft-365-ip-web-service.md) 웹 서비스를 사용하여 CSV 또는 JSON 형식의 현재 Office 365 URL 및 IP 주소 범위를 요청할 수도 있습니다.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>로컬 네트워크에서 자체 CDN 캐시할 수 있나요?

계속해서 고객의 요구를 지원할 수 있는 새로운 방법을 찾고 있으며 현재 캐싱 프록시 솔루션 및 기타 CDN 탐색하고 있습니다.

사용자 지정 웹 파트Office 365 CDN 라이브러리 및 기타 리소스 자산을 호스팅하는 데 Azure CDN 사용할 수도 있습니다. 이렇게 하면 CDN 저장소에 선택키를 적용하고 CDN 구성을 보다 잘 제어할 수 있습니다.  이 Azure CDN 무료가 아니며 Azure 구독이 필요합니다. Azure CDN 인스턴스를 구성하는 방법에 대한 자세한 내용은 [빠른 시작: Azure](/azure/cdn/cdn-create-a-storage-account-with-cdn)저장소 계정과 통합을 Azure CDN.

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>I'm using Azure ExpressRoute for Office 365, does that change things?

[Azure ExpressRoute for Office 365](azure-expressroute.md) 공용 인터넷에서 Office 365 인프라에 대한 전용 연결을 제공합니다. 즉, 클라이언트는 ExpressRoute에서 지원하는 서비스 목록에 명시적으로 포함되지 않은 CDNs 및 기타 Microsoft 인프라에 연결하기 위해 비 ExpressRoute 연결을 통해 계속 연결해야 합니다. CDNS로 이동되는 요청과 같은 특정 트래픽을 라우팅하는 방법에 대한 자세한 내용은 네트워크 트래픽 Office 365 [참조하세요.](routing-with-expressroute.md)

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>SHAREPOINT 서버와 함께 CDNS를 사용할 수 있나요?

CDNS를 사용하는 것은 SharePoint 온라인 컨텍스트에서만 의미가 있으며 SharePoint 좋습니다. 이는 서버가 사내에 위치하거나 지리적으로 가까이 있는 경우 지리적 위치에 대한 모든 이점이 참이 아니기 때문에 그에 해당하지 않습니다. 또한 호스트되는 서버에 대한 네트워크 연결이 있는 경우 인터넷에 연결하지 않고 사이트를 사용할 수 있으므로 해당 사이트를 검색할 CDN 없습니다. 그렇지 않은 경우 사이트에 필요한 CDN 사용할 수 있는 안정적 라이브러리 및 파일이 있는 경우 웹 사이트를 사용해야 합니다.
  
다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>참고 항목

[Office 365 네트워크 연결 원칙](./microsoft-365-network-connectivity-principles.md)

[Office 365 네트워크 연결 평가](assessing-network-connectivity.md) 

[Office 365 엔드포인트 관리](managing-office-365-endpoints.md)

[Office 365 URL 및 IP 주소 범위](./urls-and-ip-address-ranges.md)

[온라인에서 Office 365 콘텐츠 배달 SharePoint 사용](use-microsoft-365-cdn-with-spo.md)

[Microsoft 보안 센터](https://www.microsoft.com/trustcenter)

[Office 365 성능 조정](tune-microsoft-365-performance.md)
