---
title: 콘텐츠 배달 네트워크
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: 이 정보를 사용하여 Office 365에서 CDNS(콘텐츠 배달 네트워크)를 사용하여 성능을 개선하는 방법에 대해 자세히 알아보겠습니다.
ms.openlocfilehash: 1c2230b76f354bf6f3de524b2b8c75b7d8c380e7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692472"
---
# <a name="content-delivery-networks-cdns"></a>콘텐츠 배달 네트워크(CDN)

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

CDNS는 최종 사용자에게 Office 365를 빠르고 안정적으로 유지하는 데 도움이 됩니다. Office 365와 같은 클라우드 서비스는 CDNS를 사용하여 정적 자산을 요청하는 브라우저에 더 가깝게 캐시하여 다운로드 속도를 향상하고 최종 사용자 인식 대기 시간을 줄입니다. 이 항목의 정보는 CDNS(콘텐츠 배달 네트워크) 및 Office 365에서 CDNS를 사용하는 방법에 대해 자세히 알아보는 데 도움이 됩니다.

## <a name="what-exactly-is-a-cdn"></a>CDN이란 정확히 무엇입니까?

CDN은 고속 백본 네트워크로 연결된 데이터 센터의 프록시 및 파일 서버로 구성된 지리적으로 분산된 네트워크입니다. CDNS는 웹 사이트 또는 서비스의 지정된 파일 및 개체 집합에 대한 대기 시간 및 로드 시간을 줄이는 데 사용됩니다. CDN에는 모든 위치에서 들어오는 요청을 최적으로 처리하기 위한 끝점이 수천 개 있을 수 있습니다.

CDNS는 일반적으로 Javascript 파일, 아이콘 및 이미지와 같은 웹 사이트 또는 서비스에 대한 일반 콘텐츠를 더 빠르게 다운로드하는 데 사용하며, SharePoint Online 문서 라이브러리의 파일, 스트리밍 미디어 파일 및 사용자 지정 코드와 같은 사용자 콘텐츠에 대한 개인 액세스를 제공할 수도 있습니다.

CDNS는 대부분의 엔터프라이즈 클라우드 서비스에서 사용됩니다. Office 365와 같은 클라우드 서비스에는 전자 메일과 같은 독점 콘텐츠와 일반 콘텐츠(예: 아이콘)의 혼합을 한 번 다운로드하는 고객이 있습니다. 모든 사용자가 사용하는 이미지(아이콘)를 사용자 컴퓨터에 최대한 가깝게 두는 것이 더 효율적입니다. 모든 클라우드 서비스에서 이러한 일반 콘텐츠를 대도시 지역이나 전 세계 모든 주요 인터넷 허브에 저장하는 CDN 데이터 센터를 구축하는 것은 실용적이지 않습니다. 따라서 이러한 CDN 중 일부가 공유됩니다.

## <a name="how-do-cdns-make-services-work-faster"></a>CDNS를 통해 서비스를 더 빠르게 작동할 수 있는 방법

사이트 이미지 및 아이콘과 같은 일반적인 개체를 여러 번 다운로드하면 전자 메일 또는 문서와 같은 중요한 개인 콘텐츠를 다운로드하는 데 더 잘 사용할 수 있는 네트워크 대역폭을 사용할 수 있습니다. Office 365에서는 CDNS가 포함된 아키텍처를 사용하게 됐기 때문에 클라이언트 컴퓨터와 더 가까운 서버에서 아이콘, 스크립트 및 기타 일반 콘텐츠를 다운로드할 수 있어 다운로드 속도가 빨라집니다. 즉, Office 365 데이터 센터에 안전하게 저장되는 개인 콘텐츠에 빠르게 액세스할 수 있습니다.

CDNS는 여러 가지 방법으로 클라우드 서비스 성능을 개선하는 데 도움이 됩니다.

- CDNS는 네트워크의 일부와 파일 다운로드 부담을 클라우드 서비스에서 멀어지면서 정적 자산에 대한 요청을 처리해야 하는 필요성을 줄여 사용자 콘텐츠 및 기타 서비스를 제공하는 클라우드 서비스 리소스를 확보합니다.
- CDNS는 고성능 네트워크 및 파일 서버를 구현하고 [HTTP/2와](https://en.wikipedia.org/wiki/HTTP/2) 같은 업데이트된 네트워크 프로토콜(예: 매우 효율적인 압축 및 요청 멀티플렉스)을 활용하여 대기 시간이 짧은 파일 액세스를 제공하기 위한 것입니다.
- CDN 네트워크는 전역으로 분산된 여러 끝점을 사용하여 사용자가 콘텐츠를 최대한 가깝게 사용할 수 있도록 합니다.

## <a name="the-office-365-cdn"></a>The Office 365 CDN

Office 365 관리자는 기본 제공 Office 365 CDN(콘텐츠 배달 네트워크)을 통해 요청하는 브라우저에 더 가깝게 정적 자산을 캐싱하여 조직의 SharePoint Online 페이지에 대해 더 나은 성능을 제공할 수 있으며, 이는 다운로드 속도를 향상하고 대기 시간을 줄이는 데 도움이 됩니다. Office 365 CDN은 향상된 압축 및 다운로드 속도를 위해 [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) 프로토콜을 사용합니다.

> [!NOTE]
> Office 365 CDN은 프로덕션(전 세계) 클라우드의 테넌트만 사용할 수 있습니다.  미국 정부, 중국 및 독일 클라우드의 테넌트는 현재 Office 365 CDN을 지원하지 않습니다.

Office 365 CDN은 여러 위치, 즉 _출발지_ 에 정적 자산을 호스트하고 글로벌 고속 네트워크에서 제공할 수 있는 여러 CDN으로 구성됩니다. Office 365 CDN에서 호스팅하려는 콘텐츠의 종류에 따라 **공개** 출처, **비공개** 출처 또는 둘 다를 추가할 수 있습니다.

![Office 365 CDN 개념 다이어그램](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN 개념 다이어그램")

Office 365 CDN 내의 **공개** 출처의 콘텐츠는 익명으로 액세스할 수 있으며 호스팅 된 자산에 대한 URL을 지닌 사람이면 누구나 액세스할 수 있습니다. 공개 출처의 콘텐츠에 대한 액세스는 익명이기 때문에 캐시 javascript 파일, 스크립트, 아이콘 및 이미지와 같은 중요하지 않은 일반 콘텐츠에만 사용할 수 있습니다. Office 365 CDN은 기본적으로 공개 출처의 Office 365 클라이언트 응용 프로그램 같은 일반 리소스를 다운로드하는 데 사용됩니다.

 Office 365 CDN 내의 비공개 출처는 SharePoint Online 문서 라이브러리, 사이트 및 소유 이미지와 같은 사용자 콘텐츠에 대한 개인 액세스를 제공합니다. 비공개 출처의 콘텐츠에 대한 액세스는 동적으로 생성 된 토큰으로 보호되므로 원본 문서 라이브러리 또는 저장 위치에 대한 사용 권한을 가진 사용자만 액세스할 수 있습니다. Office 365 CDN의 비공개 출처는 SharePoint Online 콘텐츠에만 사용할 수 있으며 SharePoint Online 테넌트의 리디렉션을 통해 자산에만 액세스할 수 있습니다.

Office 365 CDN 서비스는 SharePoint Online 구독의 일부로 포함되어 있습니다.

Office 365 CDN을 사용하는 방법에 대한 자세한 내용은 [SharePoint Online에서 Office 365](use-microsoft-365-cdn-with-spo.md)콘텐츠 배달 네트워크 사용을 참조하세요.

Office 365 CDN 사용에 대한 개념 및 HOWTO 정보를 제공하는 일련의 짧은 비디오를 시청하기 위해 SharePoint 개발자 패턴 및 사례 YouTube 채널을 [방문하세요.](https://aka.ms/sppnp-videos)

## <a name="other-microsoft-cdns"></a>기타 Microsoft CDNS

Office 365 CDN의 일부가 아니어도 Office 365 테넌트에서 이러한 CDN을 사용하여 Office 365 CDN의 범위를 벗어날 수 있는 SharePoint 개발 라이브러리, 사용자 지정 코드 및 기타 목적에 액세스할 수 있습니다.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>2020년 3분기부터 SharePoint Online은 향상된 비디오 재생 및 안정성을 지원하기 위해 Azure CDN에서 비디오 캐싱을 시작할 것입니다. 인기 있는 비디오는 사용자에게 가장 가까운 CDN 끝점에서 스트리밍됩니다. 이 데이터는 Microsoft 365 규정 준수 경계 내에 유지됩니다. 이 서비스는 모든 테넌트에 대한 무료 서비스이며 구성하기 위해 고객 작업이 필요하지 않습니다.

**Azure CDN을** 사용하여 사용자 지정 웹 파트, 라이브러리 및 기타 리소스 자산을 호스팅하기 위한 자체 CDN 인스턴스를 배포할 수 있으며, 이를 통해 CDN 저장소에 선택키를 적용하고 CDN 구성을 보다 세분화할 수 있습니다. Azure CDN은 무료가 아니며 Azure 구독이 필요합니다.

Azure CDN 인스턴스를 구성하는 방법에 대한 자세한 내용은 빠른 시작: Azure 저장소 계정과 [Azure CDN 통합을 참조하세요.](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn)

Azure CDN을 사용하여 SharePoint 웹 파트를 호스팅하는 방법의 예는 [Azure CDN에 SharePoint 클라이언트 쪽 웹 파트 배포를 참조하세요.](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn)

Azure CDN PowerShell 모듈에 대한 자세한 내용은 [PowerShell을 사용하여 Azure CDN 관리를 참조하세요.](https://docs.microsoft.com/azure/cdn/cdn-manage-powershell)

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsoft의 **Ajax CDN은** jQuery(및 기타 모든 라이브러리), ASP.NET Ajax, 부트스트럭, Knockout.js 등의 인기 있는 개발 라이브러리를 제공하는 읽기 전용 CDN입니다.
  
프로젝트에 이러한 스크립트를 포함하기 위해 공개적으로 사용 가능한 이러한 라이브러리에 대한 참조를 프로젝트 자체에 포함하지 않고 CDN 주소에 대한 참조로 바꾸면 됩니다. 예를 들어 다음 코드를 사용하여 jQuery에 연결합니다.

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Microsoft Ajax CDN을 사용하는 방법에 대한 자세한 내용은 [Microsoft Ajax CDN을 참조하십시오.](https://docs.microsoft.com/aspnet/ajax/cdn/overview)

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Office 365는 CDN의 콘텐츠를 어떻게 사용하나요?

Office 365 테넌트에 대해 구성한 CDN에 관계없이 기본 데이터 검색 프로세스는 동일합니다.

1. 클라이언트(브라우저 또는 Office 클라이언트 응용 프로그램)가 Office 365에서 데이터를 요청합니다.

2. Office 365는 데이터를 클라이언트에 직접 반환하거나, 데이터가 CDN에서 호스트하는 콘텐츠 집합의 일부인 경우 클라이언트를 CDN URL로 리디렉션합니다.

    a. 데이터가 이미 공개 출처에  캐시되어 있는 경우 클라이언트는 가장 가까운 CDN 위치에서 클라이언트로 데이터를 직접 다운로드합니다.

    b. 데이터가 이미 개인 원본에  캐시되어 있는 경우 CDN 서비스는 원본에 대한 Office 365 사용자 계정의 사용 권한을 검사합니다. 사용 권한이 있는 경우 SharePoint Online은 CDN 및 두 액세스 토큰의 자산 경로로 구성된 사용자 지정 URL을 동적으로 생성하고 사용자 지정 URL을 클라이언트에 반환합니다. 그런 다음 클라이언트는 사용자 지정 URL을 사용하여 가장 가까운 CDN 위치에서 클라이언트로 데이터를 직접 다운로드합니다.

3. 데이터가 CDN에 캐시되지 않은 경우 CDN 노드는 Office 365에서 데이터를 요청한 다음 클라이언트가 데이터를 다운로드한 후 해당 데이터를 잠시 캐시합니다.

CDN은 사용자의 브라우저에 가장 가까운 데이터 센터를 알아내고 리디렉션을 사용하여 요청된 데이터를 다운로드합니다. CDN 리디렉션은 빠르며 사용자에게 많은 다운로드 시간을 절약할 수 있습니다.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>CDNS가 Office 365에서 가장 잘 작동할 수 있도록 네트워크를 어떻게 설정해야 하나요?

네트워크의 클라이언트와 CDN 끝점 간의 대기 시간을 최소화하는 것이 최적의 성능을 보장하기 위한 주요 고려 사항입니다. [Office 365](managing-office-365-endpoints.md) 끝점 관리에 설명된 모범 사례를 사용하여 네트워크 구성에서 불필요한 대기 시간이 발생하지 않도록 중앙 proxy를 통해 CDN 트래픽을 라우팅하는 대신 클라이언트 브라우저가 CDN에 직접 액세스할 수 있도록 할 수 있습니다.

[Office 365](https://aka.ms/o365networkingprinciples) 네트워크 연결 원칙을 읽어 Office 365 네트워크 성능을 최적화하는 개념을 이해할 수도 있습니다.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Office 365에서 사용하는 모든 CDNS 목록이 있나요?

Office 365에서 사용하는 CDN은 항상 변경될 수 있으며, 대부분의 경우 이벤트 1을 사용할 수 없는 경우 여러 CDN 파트너가 구성됩니다. Office 365에서 사용하는 기본 CDNS는 다음입니다.

|CDN  |Company  |Usage  |링크  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |공개 출처의 일반 자산, 비공개 출처의 SharePoint 사용자 콘텐츠         |[SharePoint Online에서 Office 365 콘텐츠 배달 네트워크 사용](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |사용자 지정 코드, SharePoint Framework 솔루션         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN(읽기 전용)     |Microsoft         |Ajax, jQuery, ASP.NET, Bootstrap, Knockout.js 라이브러리.         |[Microsoft Ajax CDN](https://docs.microsoft.com/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>CDN은 어떤 성능 향상을 제공하나요?

Office 365에서 직접 다운로드한 데이터와 테넌트와 가장 가까운 CDN 끝점에 대한 위치, CDN에서 처리되는 페이지의 자산 수, 네트워크 대기 시간 및 대역폭의 일시적인 변경 등 특정 CDN에서 다운로드한 데이터 간의 특정 성능 차이를 측정하는 데에는 여러 가지 요인이 있습니다. 그러나 간단한 A/B 테스트는 특정 파일의 다운로드 시간 차이를 표시하는 데 도움이 될 수 있습니다.

다음 스크린샷은 Office 365의 기본 파일 위치와 Microsoft Ajax 콘텐츠 배달 네트워크에서 호스트되는 동일한 파일 간의 다운로드 속도 차이를 [보여 주는 스크린샷입니다.](https://docs.microsoft.com/aspnet/ajax/cdn/overview) 이러한 스크린샷은 11개 개발자 도구의 Internet Explorer 탭에서 나타났습니다.  이러한 스크린샷은 인기 라이브러리 jQuery의 대기 시간을 보여 주며, 이 화면을 표시하려면 Internet Explorer **F12를** 누르고 Wi-Fi  아이콘으로 기호화된 네트워크 탭을 선택합니다.
  
![F12 네트워크의 스크린샷](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
이 스크린샷은 SharePoint Online 사이트 자체의 마스터 페이지 갤러리에 업로드된 라이브러리를 보여줍니다. 라이브러리를 업로드하는 데 걸려간 시간은 1.51초입니다.
  
![1.51초의 로드 시간을 보여 주는 스크린샷](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
두 번째 스크린샷은 Microsoft CDN에서 제공한 동일한 파일을 보여줍니다. 이 시간의 대기 시간은 약 496밀리초입니다. 이는 크게 개선된 기능으로, 개체를 다운로드하는 데 1초가 1초가 떨어졌다는 것입니다.
  
![469밀리초의 로드 시간을 보여 주는 스크린샷](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>내 데이터가 안전한가요?

당사는 비즈니스를 운영하는 데이터를 보호하기 위해 많은 주의를 다하고 있습니다. Office 365 CDN에 저장된 데이터는 전송 중과 보관 시 모두 암호화되며 Office 365 SharePoint CDN의 데이터에 대한 액세스는 Office 365 사용자 권한 및 토큰 권한 부여에 의해 보호됩니다. Office 365 SharePoint CDN의 데이터에 대한 요청은 Office 365 테넌트에서 참조(리디렉션)되거나 권한 부여 토큰이 생성되지 않습니다.

데이터를 안전하게 유지 관리하기 위해 공용 CDN에 사용자 콘텐츠 또는 기타 중요한 데이터를 저장하지 않는 것이 좋습니다. 공용 CDN의 데이터에 대한 액세스는 익명이기 때문에 공용 CDN은 웹 스크립트 파일, 아이콘, 이미지 및 기타 중요하지 않은 자산과 같은 일반 콘텐츠를 호스팅하는 데만 사용해야 합니다.

> [!NOTE]
> 제3자 CDN 공급자는 Office 365 보안 센터에 설명된 약정과는 다른 개인 정보 보호 및 규정 준수 표준이 있을 수 있습니다. CDN 서비스를 통해 캐시된 데이터는 Microsoft DPT(데이터 처리 약관)를 준수하지 않을 수 있으며 Office 365 보안 센터 규정 준수 경계를 밖에 있을 수 있습니다.

Office 365 CDN 공급자의 개인 정보 보호 및 데이터 보호에 대한 자세한 내용은 다음을 방문하세요.  

- Microsoft 보안 센터에서 Office 365 개인 정보 보호 및 데이터 보호에 [대한 자세한 정보](https://www.microsoft.com/trustcenter)
- Akamai 개인 정보 보호 보안 센터에서 Akamai의 개인 정보 보호 및 데이터 [보호에 대해 자세히 알아보시고](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Azure 보안 센터에서 Azure 개인 정보 보호 및 데이터 보호에 [대한 자세한 정보](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>이러한 모든 제3자 서비스를 사용하여 네트워크를 보호하는 방법

광범위한 파트너 서비스 집합을 활용하면 Office 365에서 Office 365를 사용할 때 가용성 요구 사항을 확장하고 충족하고 사용자 환경을 향상시킬 수 있습니다. Office 365에서 활용하는 제3자 서비스에는 인증서 해지 목록이 모두 포함됩니다. 예: crl.microsoft.com 또는 sa.symcb.com, CDNs 예로 r3.res.outlook.com. Office 365에서 생성된 모든 CDN FQDN은 Office 365의 사용자 지정 FQDN입니다. Office 365의 요청에 따라 FQDN으로 전송되는 경우 CDN 공급자가 해당 위치의 FQDN 및 기반 콘텐츠를 제어합니다.
  
Microsoft 또는 Office 365 데이터 센터로 전송되는 요청을 제3자에 대한 요청과 분산하려는 고객을 위해 [Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)끝점 관리에 대한 지침을 작성했습니다.

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>CDNS를 활용하는 모든 FQDNS 목록이 있나요?

FQDNS 목록 및 시간이 지날수록 CDNS를 활용하는 방법 게시된 Office [365](https://go.microsoft.com/fwlink/p/?LinkID=293744) URL 및 IP 주소 범위 페이지를 참조하여 CDNS를 활용하는 최신 FQDNS를 최신으로 활용하세요.

[Office 365 IP](microsoft-365-ip-web-service.md) 주소 및 URL 웹 서비스를 사용하여 CSV 또는 JSON 형식의 현재 Office 365 URL 및 IP 주소 범위를 요청할 수도 있습니다.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>자체 CDN을 사용하여 로컬 네트워크에 콘텐츠를 캐시할 수 있나요?

당사는 고객의 요구를 지원하는 새로운 방법을 지속적으로 찾고 있으며 현재 캐싱 프록시 솔루션 및 기타 프레미스 CDN 솔루션 사용을 탐색하고 있습니다.

Office 365 CDN의 일부가 아니지만 사용자 지정 웹 파트, 라이브러리 및 기타 리소스 자산을 호스팅하는 데 **Azure CDN을** 사용할 수도 있습니다. 이를 통해 CDN 저장소에 선택키를 적용하고 CDN 구성을 보다 잘 제어할 수 있습니다. Azure CDN은 무료가 아니며 Azure 구독이 필요합니다. Azure CDN 인스턴스를 구성하는 방법에 대한 자세한 내용은 빠른 시작: Azure 저장소 계정과 [Azure CDN 통합을 참조하세요.](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn)

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Office 365용 Azure ExpressRoute를 사용하고 있습니다. 이 변경이 있나요?

[Office 365용 Azure ExpressRoute는](azure-expressroute.md) 공용 인터넷에서 연결이 끊어진 Office 365 인프라에 대한 전용 연결을 제공합니다. 즉, 클라이언트는 ExpressRoute에서 지원하는 서비스 목록에 명시적으로 포함되지 않은 CDNs 및 기타 Microsoft 인프라에 연결하기 위해 비 ExpressRoute 연결을 통해 연결해야 합니다. CDNS로 예정된 요청과 같은 특정 트래픽을 라우팅하는 방법에 대한 자세한 내용은 [Office 365](routing-with-expressroute.md)네트워크 트래픽 관리를 참조하세요.

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>SharePoint Server에서 CDNS를 사용할 수 있나요?

CDNs를 사용하는 것은 SharePoint Online 컨텍스트에서만 의미가 있으며 SharePoint Server에서는 사용하지 않도록 해야 합니다. 이는 서버가 어떤 경우든 지리적 위치에 있는 경우 지리적 위치에 대한 모든 이점이 참이지 않습니다. 또한 호스트되는 서버에 대한 네트워크 연결이 있는 경우 인터넷 연결 없이 사이트를 사용할 수 있으므로 CDN 파일을 검색할 수 없습니다. 그렇지 않은 경우 사이트에 필요한 라이브러리 및 파일에 대해 안정적이고 사용 가능한 CDN이 있는 경우 CDN을 사용해야 합니다.
  
다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/o365cdns](https://aka.ms/o365cdns)
  
## <a name="see-also"></a>참고 항목

[Office 365 네트워크 연결 원칙](https://aka.ms/o365networkingprinciples)

[Office 365 네트워크 연결 평가](assessing-network-connectivity.md) 

[Office 365 엔드포인트 관리](managing-office-365-endpoints.md)

[Office 365 URL 및 IP 주소 범위](https://go.microsoft.com/fwlink/p/?LinkID=293744)

[SharePoint Online에서 Office 365 콘텐츠 배달 네트워크 사용](use-microsoft-365-cdn-with-spo.md)

[Microsoft 보안 센터](https://www.microsoft.com/trustcenter)

[Office 365 성능 조정](tune-microsoft-365-performance.md)
