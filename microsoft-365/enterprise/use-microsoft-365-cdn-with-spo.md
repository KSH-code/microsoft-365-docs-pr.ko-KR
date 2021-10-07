---
title: 온라인 Office 365 Content Delivery Network(CDN)를 SharePoint 사용
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/13/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Office 365 Content Delivery Network(CDN)를 사용하여 온라인 자산의 배달 속도를 SharePoint 방법을 알아보습니다.
ms.openlocfilehash: 21ef8fd29e53e2c832a518613a3ed44d8f7687cf
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154869"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기

기본 제공 Office 365 Content Delivery Network(CDN)을 사용하여 정적 자산을 호스팅하여 SharePoint Online 페이지의 성능을 향상시킬 수 있습니다. Office 365 CDN은 정적 자산을 요청하는 브라우저에 더 가깝게 캐싱하여 성능을 향상시켜 다운로드 속도를 높이고 대기 시간을 줄이는 데 기여합니다. 또한 이 Office 365 CDN 향상된 압축 및 HTTP 파이프라이너를 위해 [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) 프로토콜을 사용합니다. Office 365 CDN 서비스는 SharePoint Online 구독의 일부로 포함되어 있습니다.

> [!NOTE]
> 이 Office 365 CDN 프로덕션(전 세계) 클라우드의  테넌트만 사용할 수 있습니다. 미국 정부, 중국 및 독일 클라우드의 테넌트는 현재 이 서비스를 지원하지 Office 365 CDN.

Office 365 CDN은 여러 위치, 즉 _출발지_ 에 정적 자산을 호스트하고 글로벌 고속 네트워크에서 제공할 수 있는 여러 CDN으로 구성됩니다. Office 365 CDN에서 호스팅하려는 콘텐츠의 종류에 따라 **공개** 출처, **비공개** 출처 또는 둘 다를 추가할 수 있습니다. 공개 [원본과](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) 개인 출처 간의 차이점에 대한 자세한 내용은 각 출처가 공개 또는 비공개인지 선택을 참조하세요.

![Office 365 CDN 다이어그램을 참조합니다.](../media/O365-CDN/o365-cdn-flow-transparent.png "Office 365 CDN 다이어그램")

CDNS 작동 방식에 이미 익숙한 경우 테넌트에 대해 CDNS를 사용하도록 설정하기 위해 몇 Office 365 CDN만 수행하면 됩니다. 이 항목에서는 방법을 설명합니다. 정적 자산 호스팅을 시작하는 방법에 대한 자세한 내용을 읽어 읽습니다.

> [!TIP]
> 특수 사용 시나리오에 대해 Office 365 사용할 수 있는 다른 Microsoft 호스팅 CDNS가 있지만 이 항목에서는 이러한 CDNS가 특정 시나리오의 범위를 벗어날 수 Office 365 CDN. 자세한 내용은 기타 [Microsoft CDNs를 참조하세요.](content-delivery-networks.md#other-microsoft-cdns)

 **에 대한 네트워크 계획 및 성능 [조정으로 Office 365.](./network-planning-and-performance.md)**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Office 365 CDN Online의 SharePoint 개요

조직에 대한 Office 365 CDN 설정하기 위해 다음 기본 단계를 수행합니다.

+ [배포 계획 Office 365 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + 에서 호스트할 정적 [자산을 CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [자산을 저장할 위치를 결정하십시오.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) 이 위치는 SharePoint, 라이브러리 또는 폴더일 수 있으며 원점이라고 _합니다._
  + [각 원본이 공용인지 비공개인지를 선택 합니다.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) 공용 형식과 개인 형식의 원본을 여러 개 추가할 수 있습니다.

+ PowerShell 또는 CDN Online CLI를 사용하여 SharePoint 설정 및 구성

  + [온라인 관리 셸을 CDN 설정 및 SharePoint 구성](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [PnP PowerShell을 CDN 설정 및 구성](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [CLI를 사용하여 CDN 설정 및 Office 365 구성](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  이 단계를 완료하면 다음을 할 수 있습니다.

  + 조직에 CDN 사용하도록 설정했습니다.
  + 출처가 추가되었습니다. 각 원점은 공개 또는 비공개로 식별합니다.

설치가 완료되면 다음을 수행하여 Office 365 CDN [수](use-microsoft-365-cdn-with-spo.md#CDNManage) 있습니다.

+ 자산 추가, 업데이트 및 제거
+ 원본 추가 및 제거
+ 정책 CDN 구성
+ 필요한 경우 이 응용 CDN

마지막으로, [CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) 자산을 사용하여 공개 및 개인 출처에서 CDN 자산에 액세스하는 방법을 참조합니다.

일반적인 [문제를 Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) 지침은 문제 해결을 참조하세요.

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>배포 계획 Office 365 CDN

Office 365 CDN 테넌트에 Office 365 배포하기 전에 계획 프로세스의 일부로 다음 요소를 고려해야 합니다.

  + [설정에서 호스트할 정적 자산을 CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [자산을 저장할 위치 결정](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [각 출처를 공개 또는 비공개로 선택할 수 있습니다.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>설정에서 호스트할 정적 자산을 CDN

일반적으로 CDNS는 정적 자산 또는 자주 변경되지 않는 자산을 호스팅하는 데 가장 효과적입니다. 이러한 조건의 일부 또는 전체를 충족하는 파일을 식별하는 것이 좋습니다.

+ 페이지에 포함된 정적 파일(예: 스크립트 및 이미지)이 페이지 로드 시간의 증분에 큰 영향을 줄 수 있습니다.
+ 실행 파일 및 설치 파일과 같은 큰 파일
+ 클라이언트 쪽 코드를 지원하는 리소스 라이브러리

예를 들어 사이트 이미지 및 스크립트와 같이 반복적으로 요청되는 작은 파일은 사이트 렌더링 성능을 크게 개선하고 SharePoint Online 사이트에 대한 로드를 CDN 수 있습니다. 설치 실행 파일과 같은 더 큰 파일은 CDN 다운로드할 수 있으며, 이러한 파일을 자주 액세스하지 않는 경우에도 SharePoint Online 사이트의 부하가 감소하고 성능에 긍정적인 영향을 미치게 됩니다.

파일 기준의 성능 향상은 클라이언트가 가장 가까운 CDN, 로컬 네트워크의 일시적 조건 등을 비롯한 여러 요인에 따라 달라집니다. 많은 정적 파일은 매우 작고 1초 Office 365 다운로드할 수 있습니다. 그러나 웹 페이지에는 몇 초의 누적 다운로드 시간이 포함된 여러 파일이 포함될 수 있습니다. 파일에서 이러한 파일을 CDN 전체 페이지 로드 시간을 크게 줄일 수 있습니다. 성능 [향상에 대한](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) CDN 예시를 참조하세요.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>자산을 저장할 위치 결정

이 CDN 원본 이라는 위치에서 자산을 _페치합니다._ 원본은 URL에서 액세스할 SharePoint 사이트, 문서 라이브러리 또는 폴더일 수 있습니다. 조직의 출처를 지정할 때 유연성이 뛰어나게 됩니다. 예를 들어 여러 원점 또는 모든 원본 자산을 넣을 단일 원본을 지정할 CDN 있습니다. 조직에 대한 공개 출처 또는 비공개 출처를 둘 다 찾게 선택할 수 있습니다. 대부분의 조직에서는 둘의 조합을 구현하기로 선택합니다.

폴더 또는 문서 라이브러리와 같은 원본에 대한 새 컨테이너를 만들고 원본에서 사용할 수 있도록 할 파일을 CDN. 이 방법은 CDN 사용할 특정 자산 집합이 있으며 컨테이너의 파일로만 CDN 자산 집합을 제한하려는 경우 좋은 접근 방식입니다.

기존 사이트 모음, 사이트, 라이브러리 또는 폴더를 원본으로 구성하여 컨테이너의 모든 적합한 자산을 원본으로 구성할 수도 CDN. 기존 컨테이너를 원본으로 추가하기 전에 익명 액세스나 권한이 없는 사용자에게 자산을 부수적으로 노출하지 못하게 콘텐츠 및 사용 권한을 알고 있는지를 반드시 알고 있어야 합니다.

원본의 _콘텐츠를_ CDN 정책을 정의하여 원본에서 콘텐츠를 제외할 수 CDN. CDN 정책은 파일 형식 및 사이트 분류와 같은  특성에 따라 공개 또는 개인 출처의 자산을 제외하며 정책에서 지정한 CdnType(개인 또는 공용)의 모든 원본에 적용됩니다. 예를 들어 여러 하위 사이트가 포함된 사이트로 구성된 비공개 출처를 추가하는 경우 기밀로 표시된  사이트를 제외하는 정책을 정의하여 분류가 적용된 사이트의 콘텐츠가 해당 사이트에서 제공되지 CDN. 정책은 해당 정책에  추가한 모든 비공개 출처의 콘텐츠에 CDN.

원점 수가 클수록 서비스에서 요청을 처리하기 위해 CDN 영향을 커야 합니다. 가능한 한 원점 수를 제한하는 것이 좋습니다.

<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>각 출처를 공개 또는 비공개로 선택할 수 있습니다.

출처를 식별할 때 출처를 공개 또는 비공개로 _지정할지_ 여부를 _지정합니다._ 공개 CDN 자산에 대한 액세스는 익명이며, CDN 원본의 콘텐츠는 동적으로 생성된 토큰을 통해 보호되어 보안을 강화합니다. 선택한 옵션에 관계없이 Microsoft는 사용자 자체의 관리와 관련하여 모든 CDN 합니다. 또한 나중에 정보를 설정하고 출처를 식별한 CDN 변경할 수 있습니다.

공개 옵션과 개인 옵션 모두 비슷한 성능 이점을 제공하지만 각각 고유한 특성과 장점이 있습니다.

**웹** 사이트 내의 공개 Office 365 CDN 익명으로 액세스할 수 있으며, 자산 URL이 있는 모든 사용자가 호스팅된 자산에 액세스할 수 있습니다. 공개 출처의 콘텐츠에 대한 액세스는 익명이기 때문에 JavaScript 파일, 스크립트, 아이콘, 이미지와 같은 민감하지 않은 일반 콘텐츠를 캐시하기 위해서만 사용해야 합니다.

**사이트** 내의 비공개 출처는 Office 365 CDN 온라인 문서 라이브러리, 사이트 및 소유 이미지와 SharePoint 콘텐츠에 대한 개인 액세스를 제공합니다. 비공개 원본의 콘텐츠에 대한 액세스는 동적으로 생성된 토큰을 통해 보호되어 원본 문서 라이브러리 또는 저장 위치에 대한 사용 권한이 있는 사용자만 액세스할 수 있습니다. Office 365 CDN 원본은 SharePoint Online 콘텐츠에만 사용할 수 있으며, SharePoint Online 테넌트에서 리디렉션을 통해 개인 출처의 자산에만 액세스할 수 있습니다.

개인 출처의 자산에 대한 액세스 권한을 CDN 방법에 대한 자세한 내용은 [Using assets in private origins에서 을(를)](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)읽어 볼 수 있습니다.

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>공개 출처에서 자산을 호스팅하는 특성 및 이점

+ 공개 출처에 노출된 자산은 모든 사람이 익명으로 액세스할 수 있습니다.
    > [!IMPORTANT]
    > 사용자 정보를 포함하거나 조직에 중요한 것으로 간주되는 리소스를 공개 출처에 두면 안 됩니다.

+ 공개 출처에서 자산을 제거하는 경우 자산은 캐시에서 최대 30일 동안 계속 사용할 수 있습니다. 그러나 15분 이내에 자산에 대한 CDN 무효화합니다.

+ 공개 원본에서 스타일시트(CSS 파일)를 호스팅하는 경우 코드 내에서 상대 경로 및 URIS를 사용할 수 있습니다. 즉, 배경 이미지 및 기타 개체의 위치를 호출하는 자산의 위치를 참조할 수 있습니다.

+ 공개 출처의 URL을 구성할 수 있는 동안에는 신중하게 진행하고 페이지 컨텍스트 속성을 활용하고 이에 대한 지침을 따라야 합니다. 이 때문에 CDN 액세스할 수 없게 되는 경우 URL이 SharePoint Online의 조직으로 자동으로 확인되지 않고 링크 및 기타 오류가 발생할 수 있습니다. 또한 URL은 변경될 수 있습니다. 이 때문에 현재 값으로 하드 코딩되지 않습니다.

+ 공개 원본에 포함된 기본 파일 형식은 .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff 및 .woff2입니다. 추가 파일 형식을 지정할 수 있습니다.

+ 지정한 사이트 분류로 식별된 자산을 제외하도록 정책을 구성할 수 있습니다. 예를 들어 허용된 파일 형식이고 공개 출처에 있는 경우에도 "기밀" 또는 "제한"으로 표시된 모든 자산을 제외하도록 선택할 수 있습니다.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>개인 출처에서 자산을 호스팅하는 특성 및 이점

+ 개인 출처는 온라인 자산에 SharePoint 수 있습니다.

+ 사용자는 컨테이너에 액세스할 수 있는 권한이 있는 경우 개인 출처의 자산에만 액세스할 수 있습니다. 이러한 자산에 대한 익명 액세스는 금지됩니다.

+ 비공개 출처의 자산은 온라인 테넌트에서 SharePoint 참조해야 합니다. 개인 CDN 직접 액세스가 작동하지 않습니다.

+ 개인 출처에서 자산을 제거하는 경우 캐시에서 최대 1시간 동안 자산을 계속 사용할 수 있습니다. 그러나 자산이 제거된 후 CDN 자산에 대한 링크가 무효화됩니다.

+ 비공개 .gif 원본에 포함된 기본 파일 형식은 .ico, .jpeg, .jpg, .js 및 .png. 추가 파일 형식을 지정할 수 있습니다.

+ 공개 출처와 마찬가지로, 와일드카드를 사용하여 폴더 또는 문서 라이브러리 내의 모든 자산을 포함하기 위해 지정한 사이트 분류로 식별된 자산을 제외하도록 정책을 구성할 수 있습니다.

Office 365 CDN, 일반 CDN 개념 및 Office 365 사용할 수 있는 기타 Microsoft CDNS를 사용하는 이유에 대한 자세한 내용은 [Content Delivery Networks를 참조하세요.](content-delivery-networks.md)

### <a name="default-cdn-origins"></a>기본 CDN 원본

달리 지정하지 않는 한, Office 365 사용하도록 설정할 때 기본 출처를 Office 365 CDN. 처음에 프로비전하지 않을 경우 설치를 완료한 후 이러한 원본을 추가할 수 있습니다. 기본 원본 설정을 건너뛰는 경우의 결과를 이해하고 특정 이유가 없는 한 기본 원본을 사용하도록 설정할 때 만들 수 있도록 허용해야 CDN.

기본 개인 CDN 원본:

+ \*/userphoto.aspx
+ \*/siteassets

기본 공용 CDN 원본:

+ \*/masterpage
+ \*/style library
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets는_ 2017년 12월에 Office 365 CDN 서비스에 추가된 기본 공개 출처입니다. 이 원본은 원본 원본이 SharePoint 프레임워크 솔루션이 작동하려면 CDN 있어야 합니다. 2017년 12월 이전에 Office 365 CDN 또는 기본 원본 설정을 건너뛴 경우 CDN 원본을 수동으로 추가할 수 있습니다. 자세한 내용은 클라이언트 쪽 웹 파트 또는 SharePoint 프레임워크 [작동하지 않습니다.를 참조하세요.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>온라인 관리 셸을 Office 365 CDN 설정 및 SharePoint 구성

이 섹션의 절차를 수행하려면 SharePoint Online에 연결하기 위해 SharePoint 합니다. 자세한 내용은 커넥트 [PowerShell을 SharePoint 참조하세요.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

다음 단계를 완료하여 CDN Online 관리 셸을 사용하여 SharePoint 자산을 호스트하도록 SharePoint 구성합니다.

<details>
  <summary>클릭하여 확장</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>조직에서 조직에서 다음을 사용하도록 Office 365 CDN

테넌트 CDN 변경하기 전에 CDN 테넌트에서 private CDN 구성의 현재 상태를 Office 365 합니다. 커넥트 온라인 관리 셸을 사용하여 테넌트에 SharePoint 다음을 할 수 있습니다.

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

이제 **Get-SPOTenantCdnEnabled** cmdlet을 사용하여 테넌트에서 CDN 상태 설정을 검색합니다.

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

지정한 CDN CdnType의 상태는 화면에 출력됩니다.

**Set-SPOTenantCdnEnabled** cmdlet을 사용하여 조직에서 이 응용 Office 365 CDN. 조직에서 공개 출처, 비공개 출처 또는 둘 다를 한에 사용하도록 설정할 수 있습니다. 기본 원본 설정을 CDN 건너뛰도록 기본 원본 설정을 구성할 수도 있습니다. 이 항목에 설명된 바와 같이 언제든지 이러한 출처를 추가할 수 있습니다.

온라인 Windows PowerShell 대한 SharePoint:

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

예를 들어 조직에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

조직에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 하지만 기본 원본 설정을 건너뛰기 위해 다음 명령을 입력합니다.

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

기본 [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) 사용하도록 설정할 때 기본적으로 프로비전되는 원본에 대한 자세한 Office 365 CDN 기본 원본 설정을 건너뛰는 경우의 잠재적인 영향에 대한 자세한 내용은 Default CDN origins를 참조하십시오.

조직에서 공개 출처를 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

조직에서 비공개 출처를 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

이 cmdlet에 대한 자세한 내용은 [Set-SPOTenantCdnEnabled 를 참조하세요.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>파일 형식 목록에 포함할 파일 형식 목록 Office 365 CDN(선택 사항)

> [!TIP]
> **Set-SPOTenantCdnPolicy** cmdlet을 사용하여 파일 형식을 정의하는 경우 현재 정의된 목록을 덮어 덮어 엽니다. 목록에 추가 파일 형식을 추가하려는 경우 먼저 cmdlet을 사용하여 이미 허용된 파일 형식을 찾아 새 파일 형식과 함께 목록에 포함합니다.

**Set-SPOTenantCdnPolicy** cmdlet을 사용하여 공용 및 개인 원본에서 호스팅할 수 있는 정적 파일 형식을 정의할 수 CDN. 기본적으로 일반적인 자산 유형(예: .css, .gif, .jpg 및 .js.

온라인 Windows PowerShell 대한 SharePoint:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

예를 들어. CDN .css 및 .png 호스트할 수 있도록 설정하려면 다음 명령을 입력합니다.

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

현재 허용되는 파일 형식을 CDN **Get-SPOTenantCdnPolicies** cmdlet을 사용 합니다.

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

이러한 cmdlet에 대한 자세한 내용은 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) 및 [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/)를 참조하세요.

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>목록에서 제외할 사이트 분류 목록 Office 365 CDN(선택 사항)

> [!TIP]
> **Set-SPOTenantCdnPolicy** cmdlet을 사용하여 사이트 분류를 제외하는 경우 현재 정의된 목록을 덮어 덮어 덮어입습니다. 추가 사이트 분류를 제외하려는 경우 먼저 cmdlet을 사용하여 이미 제외된 분류를 확인한 다음 새 분류와 함께 추가합니다.

**Set-SPOTenantCdnPolicy** cmdlet을 사용하여 사이트 분류에서 사용할 수 있도록 설정하지 않을 사이트 분류를 CDN. 기본적으로 사이트 분류는 제외되지 않습니다.

온라인 Windows PowerShell 대한 SharePoint:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

현재 제한된 사이트 분류를 표시하기 위해 **Get-SPOTenantCdnPolicies** cmdlet을 사용하세요.

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

반환될 속성은 _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ 및 _ExcludeIfNoScriptDisabled입니다._

_IncludeFileExtensions_ 속성에는 해당 속성에서 제공될 파일 확장명 목록이 CDN.

> [!NOTE]
> 기본 파일 확장명은 public과 private 간에 다릅니다.

_ExcludeRestrictedSiteClassifications_ 속성에는 목록에서 제외하려는 사이트 분류가 CDN. 예를 들어 기밀로 표시된  사이트를 제외하여 분류가 적용된 사이트의 콘텐츠가 해당 사이트에서 제공되지 CDN.

_ExcludeIfNoScriptDisabled_ 속성은 사이트 수준 _noScript_ 특성 CDN 콘텐츠는 제외됩니다. 기본적으로 _NoScript_ 특성은 최신 사이트에 대해 **사용으로** 설정되어 _있으며_ 클래식 사이트에는 **사용** _안 하게_ 설정됩니다. 이는 테넌트 설정에 따라 다를 수 있습니다.

이러한 cmdlet에 대한 자세한 내용은 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) 및 [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/)를 참조하세요.

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>자산의 원점 추가

**Add-SPOTenantCdnOrigin** cmdlet을 사용하여 원점 정의 여러 원본을 정의할 수 있습니다. 원본은 웹 응용 SharePoint 호스트할 자산이 포함된 SharePoint 폴더를 지정하는 url입니다CDN.

> [!IMPORTANT]
> 사용자 정보를 포함하거나 조직에 중요한 것으로 간주되는 리소스를 공개 출처에 두면 안 됩니다.

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

_path_ 값은 자산이 포함된 라이브러리 또는 폴더의 상대 경로입니다. 상대 경로와 함께 와일드카드를 사용할 수 있습니다. 원본은 URL에 추가된 와일드카드를 지원합니다. 이렇게 하면 여러 사이트에 걸쳐 있는 원본을 만들 수 있습니다. 예를 들어 모든 사이트의 masterpages 폴더에 모든 자산을 CDN 다음 명령을 입력합니다.

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ 와일드카드 수정자 *는 경로의 시작에만 사용할 수 있으며 지정된 URL 아래에 있는 **/** 모든 URL 세그먼트와 일치합니다.
+ 경로는 문서 라이브러리, 폴더 또는 사이트를 포인터로 사용할 수 있습니다. 예를 들어 _경로 */site1은_ 사이트의 모든 문서 라이브러리와 일치합니다.

특정 상대 경로를 사용하여 원점을 추가할 수 있습니다. 전체 경로를 사용하여 원점은 추가할 수 없습니다.

이 예제에서는 특정 사이트에서 siteassets 라이브러리의 개인 출처를 추가합니다.

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

이 예제에서는 사이트 모음의 사이트 자산 라이브러리에 있는 _folder1_ 폴더의 개인 출처를 추가합니다.

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

경로에 공백이 있는 경우 경로를 작은 따옴표로 둘러싸거나 공백을 URL 인코딩 %20으로 바꿀 수 있습니다. 다음 예제에서는 사이트 모음의 사이트 자산 라이브러리에 있는 _폴더 1_ 폴더의 개인 출처를 추가합니다.

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

이 명령 및 해당 구문에 대한 자세한 내용은 [Add-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)

> [!NOTE]
> 개인 출처에서 공유되는 자산은 원본에서 공유되는 주 버전을 게시해야만 해당 원본에서 액세스할 수 CDN.

명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다. 최대 15분이 걸릴 수 있습니다.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>예제: 마스터 페이지 및 온라인용 스타일 라이브러리에 대한 공개 SharePoint 구성

일반적으로 이러한 원본은 사용자 지정 원본을 사용하도록 설정할 때 기본적으로 Office 365 CDN. 그러나 수동으로 사용하도록 설정하려면 다음 단계를 따르세요.

+ **Add-SPOTenantCdnOrigin** cmdlet을 사용하여 스타일 라이브러리를 공용 원본으로 정의합니다.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ **Add-SPOTenantCdnOrigin** cmdlet을 사용하여 마스터 페이지를 공개 원본으로 정의합니다.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

이 명령 및 해당 구문에 대한 자세한 내용은 [Add-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)

명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다. 최대 15분이 걸릴 수 있습니다.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>예: SharePoint Online에 대한 사이트 자산, 사이트 페이지 및 게시 이미지에 대한 비공개 출처 구성

+ **Add-SPOTenantCdnOrigin** cmdlet을 사용하여 사이트 자산 폴더를 비공개 원본으로 정의합니다.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ **Add-SPOTenantCdnOrigin** cmdlet을 사용하여 사이트 페이지 폴더를 비공개 원본으로 정의합니다.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ **Add-SPOTenantCdnOrigin** cmdlet을 사용하여 게시 이미지 폴더를 비공개 원본으로 정의합니다.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

이 명령 및 해당 구문에 대한 자세한 내용은 [Add-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)

명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다. 최대 15분이 걸릴 수 있습니다.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>예: SharePoint Online의 사이트 모음에 대한 비공개 출처 구성

**Add-SPOTenantCdnOrigin** cmdlet을 사용하여 사이트 모음을 비공개 원본으로 정의합니다. 예:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

이 명령 및 해당 구문에 대한 자세한 내용은 [Add-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)

명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다. SharePoint Online  테넌트가 SharePoint 서비스로 연결될 것으로 예상되는 구성 보류 중인 CDN 있습니다. 최대 15분이 걸릴 수 있습니다.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>관리 Office 365 CDN

구성을 설정한 CDN 이 섹션에 설명된 바와 같이 콘텐츠를 업데이트하거나 요구 사항이 변경될 때 구성을 변경할 수 있습니다.

<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>사용자 계정에서 자산을 추가, 업데이트 또는 Office 365 CDN

설치 단계를 완료한 후 원하는 경우 새 자산을 추가하고 기존 자산을 업데이트하거나 제거할 수 있습니다. 원본으로 식별한 폴더 또는 SharePoint 자산을 변경하기만 합니다. 새 자산을 추가하는 경우 자산을 즉시 CDN 있습니다. 그러나 자산을 업데이트하는 경우 새 복사본이 전파되어 해당 자산에서 사용 가능한 데 최대 15분이 CDN.

원점의 위치를 검색해야 하는 경우 **Get-SPOTenantCdnOrigins** cmdlet을 사용할 수 있습니다. 이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Get-SPOTenantCdnOrigins 를 참조하세요.](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>원본을 원본에서 Office 365 CDN

원본으로 식별한 폴더 또는 SharePoint 라이브러리에 대한 액세스를 제거할 수 있습니다. 이렇게하려면 **Remove-SPOTenantCdnOrigin** cmdlet을 사용 합니다.

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Remove-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>원본의 원본을 Office 365 CDN

만든 원본은 수정할 수 없습니다. 대신 원점은 제거한 다음 새 원본을 추가합니다. 자세한 내용은 원본에서 원본을 제거하려면 Office 365 CDN 자산의 원점 [추가를 참조하세요.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh) [](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>이 Office 365 CDN

**Set-SPOTenantCdnEnabled** cmdlet을 사용하여 조직에 대한 CDN 사용하지 않도록 설정할 수 있습니다. 공용 원본과 개인 원본을 모두 사용하도록 CDN 다음 예제와 같이 cmdlet을 두 번 실행해야 합니다.

원본에서 공용 출처를 사용하지 CDN 다음 명령을 입력합니다.

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

원본에서 개인 출처를 사용하지 CDN 다음 명령을 입력합니다.

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

이 cmdlet에 대한 자세한 내용은 [Set-SPOTenantCdnEnabled 를 참조하세요.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>PnP PowerShell을 Office 365 CDN 설정 및 구성

이 섹션의 절차를 수행하려면 PnP PowerShell을 사용하여 온라인에 SharePoint 합니다. 자세한 내용은 [PnP PowerShell 시작을 참조하세요.](https://github.com/SharePoint/PnP-PowerShell#getting-started)

PnP PowerShell을 사용하여 CDN 자산을 호스트하도록 SharePoint 단계를 완료합니다.

<details>
  <summary>클릭하여 확장</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>조직에서 조직에서 다음을 사용하도록 Office 365 CDN

테넌트 CDN 변경하기 전에 CDN 테넌트에서 private CDN 구성의 현재 상태를 Office 365 합니다. 커넥트 PnP PowerShell을 사용하여 테넌트에 다음을 추가합니다.

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

이제 **Get-PnPTenantCdnEnabled** cmdlet을 사용하여 테넌트에서 CDN 상태 설정을 검색합니다.

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

지정한 CDN CdnType의 상태는 화면에 출력됩니다.

**Set-PnPTenantCdnEnabled cmdlet을 사용하여 조직에서 Set-PnPTenantCdnEnabled** cmdlet을 Office 365 CDN. 조직에서 공개 출처, 비공개 출처 또는 둘 다를 동시에 사용하도록 설정할 수 있습니다. 기본 원본 설정을 CDN 건너뛰도록 기본 원본 설정을 구성할 수도 있습니다. 이 항목에 설명된 바와 같이 언제든지 이러한 출처를 추가할 수 있습니다.

PnP PowerShell에서:

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

예를 들어 조직에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

조직에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 하지만 기본 원본 설정을 건너뛰기 위해 다음 명령을 입력합니다.

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

기본 [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) 사용하도록 설정할 때 기본적으로 프로비전되는 원본에 대한 자세한 Office 365 CDN 기본 원본 설정을 건너뛰는 경우의 잠재적인 영향에 대한 자세한 내용은 Default CDN origins를 참조하십시오.

조직에서 공개 출처를 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

조직에서 비공개 출처를 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

이 cmdlet에 대한 자세한 내용은 [Set-PnPTenantCdnEnabled 를 참조하세요.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>파일 형식 목록에 포함할 파일 형식 목록 Office 365 CDN(선택 사항)

> [!TIP]
> **Set-PnPTenantCdnPolicy** cmdlet을 사용하여 파일 형식을 정의하는 경우 현재 정의된 목록을 덮어 덮어 엽니다. 목록에 추가 파일 형식을 추가하려는 경우 먼저 cmdlet을 사용하여 이미 허용된 파일 형식을 찾아 새 파일 형식과 함께 목록에 포함합니다.

**Set-PnPTenantCdnPolicy** cmdlet을 사용하여 공용 및 개인 원본에서 호스팅할 수 있는 정적 파일 형식을 정의할 수 CDN. 기본적으로 일반적인 자산 유형(예: .css, .gif, .jpg 및 .js.

PnP PowerShell에서:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

예를 들어. CDN .css 및 .png 호스트할 수 있도록 설정하려면 다음 명령을 입력합니다.

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

현재 허용되는 파일 형식을 CDN **Get-PnPTenantCdnPolicies** cmdlet을 사용 합니다.

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

이러한 cmdlet에 대한 자세한 내용은 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) 및 [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)를 참조하세요.

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>목록에서 제외할 사이트 분류 목록 Office 365 CDN(선택 사항)

> [!TIP]
> **Set-PnPTenantCdnPolicy** cmdlet을 사용하여 사이트 분류를 제외하는 경우 현재 정의된 목록을 덮어 덮어 덮어입습니다. 추가 사이트 분류를 제외하려는 경우 먼저 cmdlet을 사용하여 이미 제외된 분류를 확인한 다음 새 분류와 함께 추가합니다.

**Set-PnPTenantCdnPolicy** cmdlet을 사용하여 사이트 분류에서 사용할 수 있도록 설정하지 않을 사이트 분류를 CDN. 기본적으로 사이트 분류는 제외되지 않습니다.

PnP PowerShell에서:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

현재 제한되는 사이트 분류를 표시하기 위해 **Get-PnPTenantCdnPolicies** cmdlet을 사용하세요.

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

반환될 속성은 _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ 및 _ExcludeIfNoScriptDisabled입니다._

_IncludeFileExtensions_ 속성에는 해당 속성에서 제공될 파일 확장명 목록이 CDN.

> [!NOTE]
> 기본 파일 확장명은 public과 private 간에 다릅니다.

_ExcludeRestrictedSiteClassifications_ 속성에는 목록에서 제외하려는 사이트 분류가 CDN. 예를 들어 기밀로 표시된  사이트를 제외하여 분류가 적용된 사이트의 콘텐츠가 해당 사이트에서 제공되지 CDN.

_ExcludeIfNoScriptDisabled_ 속성은 사이트 수준 _noScript_ 특성 CDN 콘텐츠는 제외됩니다. 기본적으로 _NoScript_ 특성은 최신 사이트에 대해 **사용으로** 설정되어 _있으며_ 클래식 사이트에는 **사용** _안 하게_ 설정됩니다. 이는 테넌트 설정에 따라 다를 수 있습니다.

이러한 cmdlet에 대한 자세한 내용은 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) 및 [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)를 참조하세요.

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>자산의 원점 추가

**Add-PnPTenantCdnOrigin** cmdlet을 사용하여 원점 정의 여러 원본을 정의할 수 있습니다. 원본은 웹 응용 SharePoint 호스트할 자산이 포함된 SharePoint 폴더를 지정하는 url입니다CDN.

> [!IMPORTANT]
> 사용자 정보를 포함하거나 조직에 중요한 것으로 간주되는 리소스를 공개 출처에 두면 안 됩니다.

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

_path_ 값은 자산이 포함된 라이브러리 또는 폴더의 상대 경로입니다. 상대 경로와 함께 와일드카드를 사용할 수 있습니다. 원본은 URL에 추가된 와일드카드를 지원합니다. 이렇게 하면 여러 사이트에 걸쳐 있는 원본을 만들 수 있습니다. 예를 들어 모든 사이트의 masterpages 폴더에 모든 자산을 CDN 다음 명령을 입력합니다.

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ 와일드카드 수정자 *는 경로의 시작에만 사용할 수 있으며 지정된 URL 아래에 있는 **/** 모든 URL 세그먼트와 일치합니다.
+ 경로는 문서 라이브러리, 폴더 또는 사이트를 포인터로 사용할 수 있습니다. 예를 들어 _경로 */site1은_ 사이트의 모든 문서 라이브러리와 일치합니다.

특정 상대 경로를 사용하여 원점을 추가할 수 있습니다. 전체 경로를 사용하여 원점은 추가할 수 없습니다.

이 예제에서는 특정 사이트에서 사이트 자산 라이브러리의 개인 출처를 추가합니다.

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

이 예제에서는 사이트 모음의 사이트 자산 라이브러리에 있는 _folder1_ 폴더의 개인 출처를 추가합니다.

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

경로에 공백이 있는 경우 경로를 작은 따옴표로 둘러싸거나 공백을 URL 인코딩 %20으로 바꿀 수 있습니다. 다음 예제에서는 사이트 모음의 사이트 자산 라이브러리에 있는 _폴더 1_ 폴더의 개인 출처를 추가합니다.

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

이 명령 및 해당 구문에 대한 자세한 내용은 [Add-PnPTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

> [!NOTE]
> 개인 출처에서 공유되는 자산은 원본에서 공유되는 주 버전을 게시해야만 해당 원본에서 액세스할 수 CDN.

명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다. 최대 15분이 걸릴 수 있습니다.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>예제: 마스터 페이지 및 온라인용 스타일 라이브러리에 대한 공개 SharePoint 구성

일반적으로 이러한 원본은 사용자 지정 원본을 사용하도록 설정할 때 기본적으로 Office 365 CDN. 그러나 수동으로 사용하도록 설정하려면 다음 단계를 따르세요.

+ **Add-PnPTenantCdnOrigin** cmdlet을 사용하여 스타일 라이브러리를 공용 원본으로 정의합니다.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ **Add-PnPTenantCdnOrigin** cmdlet을 사용하여 마스터 페이지를 공개 원본으로 정의합니다.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

이 명령 및 해당 구문에 대한 자세한 내용은 [Add-PnPTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다. 최대 15분이 걸릴 수 있습니다.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>예: SharePoint Online에 대한 사이트 자산, 사이트 페이지 및 게시 이미지에 대한 비공개 출처 구성

+ **Add-PnPTenantCdnOrigin** cmdlet을 사용하여 사이트 자산 폴더를 비공개 원본으로 정의합니다.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ **Add-PnPTenantCdnOrigin** cmdlet을 사용하여 사이트 페이지 폴더를 비공개 원본으로 정의합니다.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ **Add-PnPTenantCdnOrigin** cmdlet을 사용하여 게시 이미지 폴더를 비공개 원본으로 정의합니다.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

이 명령 및 해당 구문에 대한 자세한 내용은 [Add-PnPTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다. 최대 15분이 걸릴 수 있습니다.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>예: SharePoint Online의 사이트 모음에 대한 비공개 출처 구성

**Add-PnPTenantCdnOrigin** cmdlet을 사용하여 사이트 모음을 비공개 원본으로 정의합니다. 예:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

이 명령 및 해당 구문에 대한 자세한 내용은 [Add-PnPTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다. SharePoint Online  테넌트가 SharePoint 서비스로 연결될 것으로 예상되는 구성 보류 중인 CDN 있습니다. 최대 15분이 걸릴 수 있습니다.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>관리 Office 365 CDN

구성을 설정한 CDN 이 섹션에 설명된 바와 같이 콘텐츠를 업데이트하거나 요구 사항이 변경될 때 구성을 변경할 수 있습니다.

<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>사용자 계정에서 자산을 추가, 업데이트 또는 Office 365 CDN

설치 단계를 완료한 후 원하는 경우 새 자산을 추가하고 기존 자산을 업데이트하거나 제거할 수 있습니다. 원본으로 식별한 폴더 또는 SharePoint 자산을 변경하기만 합니다. 새 자산을 추가하는 경우 자산을 즉시 CDN 있습니다. 그러나 자산을 업데이트하는 경우 새 복사본이 전파되어 해당 자산에서 사용 가능한 데 최대 15분이 CDN.

원점의 위치를 검색해야 하는 경우 **Get-PnPTenantCdnOrigin** cmdlet을 사용할 수 있습니다. 이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Get-PnPTenantCdnOrigin을 참조하십시오.](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>원본을 원본에서 Office 365 CDN

원본으로 식별한 폴더 또는 SharePoint 라이브러리에 대한 액세스를 제거할 수 있습니다. 이렇게하려면 **Remove-PnPTenantCdnOrigin** cmdlet을 사용 합니다.

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Remove-PnPTenantCdnOrigin을 참조하십시오.](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>원본의 원본을 Office 365 CDN

만든 원본은 수정할 수 없습니다. 대신 원점은 제거한 다음 새 원본을 추가합니다. 자세한 내용은 원본에서 원본을 제거하려면 Office 365 CDN 자산의 원점 [추가를 참조하세요.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh) [](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>이 Office 365 CDN

**Set-PnPTenantCdnEnabled** cmdlet을 사용하여 조직의 CDN 사용하지 않도록 설정할 수 있습니다. 공용 원본과 개인 원본을 모두 사용하도록 CDN 다음 예제와 같이 cmdlet을 두 번 실행해야 합니다.

원본에서 공용 출처를 사용하지 CDN 다음 명령을 입력합니다.

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

원본에서 개인 출처를 사용하지 CDN 다음 명령을 입력합니다.

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

이 cmdlet에 대한 자세한 내용은 [Set-PnPTenantCdnEnabled 를 참조하세요.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>CLI를 사용하여 Office 365 CDN 설정 및 Office 365 구성

이 섹션의 절차를 수행하려면 CLI 를 [설치해야 Office 365 합니다.](https://aka.ms/o365cli) 그런 다음 로그인 명령을 Office 365 테넌트에 [연결합니다.](https://pnp.github.io/office365-cli/cmd/login/)

CLI를 사용하여 CDN 온라인에서 자산을 호스트하도록 SharePoint 구성하기 위해 다음 Office 365 완료합니다.

<details>
  <summary>클릭하여 확장</summary>

### <a name="enable-the-office-365-cdn"></a>다음 Office 365 CDN

스포 [cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) 집합 명령을 사용하여 테넌트에서 Office 365 CDN 상태를 관리할 수 있습니다.

테넌트에서 Office 365 Public CDN 실행하려면 다음을 실행합니다.

```cli
spo cdn set --type Public --enabled true
```

다음을 Office 365 SharePoint CDN 실행합니다.

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>현재 상태 보기 Office 365 CDN

특정 유형의 Office 365 CDN 활성화 또는 사용하지 않도록 설정되어 있는지 확인하기 위해 [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) 명령을 사용 합니다.

공용 Office 365 사용하도록 CDN 확인을 위해 다음을 실행합니다.

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>원본 Office 365 CDN 보기

현재 구성된 공용 Office 365 원본을 CDN 실행합니다.

```cli
spo cdn origin list --type Public
```

기본 [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) 사용하도록 설정할 때 기본적으로 프로비전되는 원본에 대한 자세한 내용은 기본 Office 365 CDN.

### <a name="add-an-office-365-cdn-origin"></a>원본 Office 365 CDN 추가

> [!IMPORTANT]
> 조직에 중요한 것으로 간주되는 리소스를 공용 원본으로 구성된 SharePoint 라이브러리에 두면 안 됩니다.

spo [cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) 명령을 사용하여 CDN 정의합니다. 여러 원본을 정의할 수 있습니다. 원본은 웹 응용 SharePoint 호스트할 자산이 포함된 SharePoint 폴더를 지정하는 url입니다CDN.

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

여기서 `path` 은 자산이 포함된 폴더의 상대 경로입니다. 상대 경로와 함께 와일드카드를 사용할 수 있습니다.

모든 사이트의 마스터 페이지 **갤러리에** 모든 자산을 공개 원본으로 포함하기 위해 다음을 실행합니다.

```cli
spo cdn origin add --type Public --origin */masterpage
```

특정 사이트 모음에 대해 비공개 원본을 구성하기 위해 다음을 실행합니다.

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> 원본을 CDN 서비스에서 파일을 검색하는 데 최대 15분이 걸릴 CDN 있습니다. spo [cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 출처 목록 명령을 사용하여 특정 원본이 이미 활성화되어 있는지 확인할 수 있습니다.

### <a name="remove-an-office-365-cdn-origin"></a>원본 Office 365 CDN 제거

[spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) 명령을 사용하여 지정된 CDN 원본을 CDN 있습니다.

공용 원본을 구성에서 제거하려면 CDN 실행합니다.

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> 원본 CDN 제거해도 해당 원본과 일치하는 문서 라이브러리에 저장된 파일에는 영향을 주지 않습니다. 이러한 자산이 해당 SharePoint URL을 사용하여 참조된 SharePoint 자동으로 문서 라이브러리를 SharePoint 원래 URL로 다시 전환됩니다. 그러나 공용 CDN URL을 사용하여 자산을 참조한 경우 원본을 제거하면 링크가 중단되고 수동으로 변경해야 합니다.

### <a name="modify-an-office-365-cdn-origin"></a>원본 Office 365 CDN 수정

기존 원본은 수정할 수 CDN 없습니다. 대신 명령을 사용하여 이전에 정의한 CDN 원본을 제거하고 명령을 사용하여 새 원본을 `spo cdn origin remove` 추가해야 `spo cdn origin add` 합니다.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>파일에 포함할 파일 형식을 Office 365 CDN

기본적으로 _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff 및 .woff2_ 파일 형식이 CDN. 파일 형식에 추가 파일 형식을 포함해야 CDN [spo cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 정책 집합 명령을 사용하여 CDN 구성을 변경할 수 있습니다.

> [!NOTE]
> 파일 형식 목록을 변경할 때 현재 정의된 목록을 덮어 덮어 덮어 니다. 추가 파일 형식을 포함하려는 경우 먼저 [spo cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 정책 목록 명령을 사용하여 현재 구성된 파일 형식을 찾아야 합니다.

공용 파일에 포함된 파일 형식의 기본 목록에 _JSON_ 파일 형식을 CDN 실행합니다.

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>목록에서 제외할 사이트 분류 목록을 Office 365 CDN

[spo cdn 정책 집합](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 명령을 사용하여 사이트 분류에서 사용할 수 있도록 설정하지 않을 사이트 분류를 CDN. 기본적으로 사이트 분류는 제외되지 않습니다.

> [!NOTE]
> 제외된 사이트 분류 목록을 변경할 때 현재 정의된 목록을 덮어 덮어 덮어입습니다. 추가 분류를 제외하려는 경우 먼저 [spo cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) 정책 목록 명령을 사용하여 현재 구성된 분류를 찾아야 합니다.

_HBI로_ 분류된 사이트를 공용 웹 사이트에서 CDN 실행

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>이 Office 365 CDN

명령을 사용하지 Office 365 CDN 명령을 사용 합니다. 예를 `spo cdn set` 들면 다음과 같습니다.

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>사용자 CDN 사용

이제 원본 및 정책을 CDN 및 정책을 사용하도록 설정한 후 CDN 있습니다.

이 섹션에서는 SharePoint 페이지 및 콘텐츠에서 CDN URL을 사용하는 방법을 이해하여 SharePoint 원본과 비공개 원본 모두의 자산에 대한 요청을 해당 url로 리디렉션하는 CDN.

+ [CDN 링크 업데이트](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [공개 출처에서 자산 사용](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [개인 출처에서 자산 사용](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

클라이언트 쪽 웹 파트를 호스팅하는 CDN 방법에 대한 자세한 내용은 [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)항목을 참조하십시오.

> [!NOTE]
> _ClientSideAssets_ 폴더를 개인 CDN  원본 목록에 추가하면 CDN 사용자 지정 웹 파트가 렌더링되지 않습니다. SPFX 웹 파트에서 사용하는 파일은 공용 파일만 사용할 수 CDN ClientSideAssets 폴더는 공용 웹 파트의 기본 원본 CDN.

### <a name="updating-links-to-cdn-assets"></a>CDN 링크 업데이트

원본에 추가한 자산을 사용하기 위해 원본 파일의 경로로 원본 파일에 대한 링크를 업데이트하기만 합니다.

+ 원본에 추가한 자산에 대한 링크가 포함된 페이지 또는 콘텐츠를 편집합니다. 또한 링크가 나타나는 모든 곳에서 특정 자산으로 링크를 업데이트하려는 경우 여러 방법 중 하나를 사용하여 입력 사이트 또는 사이트 모음 전체에서 링크를 전역적으로 검색하고 바꿀 수 있습니다.
+ 원점에 있는 자산에 대한 각 링크에 대해 경로를 원본 파일의 경로로 CDN. 상대 경로를 사용할 수 있습니다.
+ 페이지 또는 콘텐츠를 저장합니다.

예를 들어 이미지 _/site/SiteAssets/images/image.png_ _/site/CDN_origins/public/_ 에 복사했다고 생각할 수 있습니다. CDN 원본 경로를 이미지 파일 위치에 대한 원본 경로로 바꾸어 새 URL _/site/site/CDN_origins/public/image.png._

상대 경로 대신 자산에 대한 전체 URL을 사용하려면 링크를 구성합니다.

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> 일반적으로 URL을 해당 URL의 자산으로 직접 하드코딩하면 CDN. 그러나 필요한 경우 공개 출처의 자산에 대한 URL을 수동으로 구성할 수 있습니다. 자세한 내용은 [공용 자산에 대한 CDN 하드코드를 참조하세요.](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)

자산이 에서 제공되고 있는지 확인하는 방법에 대한 자세한 [](use-microsoft-365-cdn-with-spo.md#CDNConfirm) 내용은 CDN 문제 해결에서 CDN 자산이 제공되고 있는지 확인하는 [방법을 Office 365 CDN.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

### <a name="using-assets-in-public-origins"></a>공개 출처에서 자산 사용

SharePoint  Online의 게시 기능은 공개 원본에 저장된 자산의 URL을 해당 자산의 CDN 해당 url로 자동으로 다시 덮어 CDN 대신 CDN 서비스에서 SharePoint.

원본이 게시 기능을 사용하도록 설정된 사이트에 있는 경우 CDN로 오프로드할 자산이 다음 범주 중 하나에 있는 경우 SharePoint 정책에 의해 자산이 제외되지 않은 경우 원본에 있는 자산의 URL을 자동으로 다시 CDN.

다음은 게시 기능에서 링크를 자동으로 다시 SharePoint 개요입니다.

+ 클래식 게시 페이지 HTML 응답의 IMG/LINK/CSS URL
  + 여기에는 페이지의 HTML 콘텐츠 내에서 작성자가 추가한 이미지가 포함됩니다.
+ 그림 라이브러리 SlideShow 웹파트 이미지 URL
+ SPList REST API(RenderListDataAsStream) 결과의 이미지 필드
  + 새 속성 _ImageFieldsToTryRewriteToCdnUrls를_ 사용하여 콤보로 구분된 필드 목록을 제공합니다.
  + 하이퍼링크 필드 및 PublishingImage 필드 지원
+ SharePoint 이미지 Nditions

다음 다이어그램은 워크플로를 보여 SharePoint 원본에서 자산이 포함된 페이지에 대한 요청을 받는 경우 워크플로를 보여 주며,

![워크플로 다이어그램: Office 365 CDN 원본에서 자산 검색](../media/O365-CDN/o365-cdn-public-steps-transparent.png "워크플로: Office 365 CDN 원본에서 자산 검색")

> [!TIP]
> 페이지의 특정 URL에 대해 자동 다시 작성을 사용하지 않도록 설정하려는 경우 페이지를 체크 아웃하고 쿼리 문자열 매개 변수를 추가할 수 **있습니다. NoAutoReWrites=true이면** 사용하지 않도록 설정할 각 링크의 끝입니다.

#### <a name="constructing-cdn-urls-for-public-assets"></a>공용 CDN URL 생성

게시 _기능이_ 공개 출처에 대해 사용하도록 설정되어 있지 않은 경우 또는 자산이 CDN 서비스의 자동 다시 사용 기능에서 지원되는 링크 유형 중 하나가 아닌 경우 자산의 CDN 위치에 대한 URL을 수동으로 생성하고 콘텐츠에서 이러한 URL을 사용할 수 있습니다.

> [!NOTE]
> URL의 마지막 섹션을 구성하는 필수 액세스 토큰은 리소스가 요청될 때 생성되어 CDN 원본에 있는 자산에 대한 URL을 하드코드하거나 구성할 수 없습니다. Public 2013에 대한 URL을 CDN 수 있으며 URL은 변경될 수 있는 하드 코딩되지 않습니다.

공용 CDN 자산의 경우 URL 형식은 다음과 같습니다.

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

**TenantHostName을 테넌트** 이름으로 바 대체합니다. 예제:

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> 페이지 컨텍스트 속성은 하드 코딩 " "대신에 prefix를 구성하는 데 https://publiccdn.sharepointonline.com 사용됩니다. URL은 변경될 수 있으며 하드 코딩되지 않습니다. 클래식 SharePoint Online에서 표시 서식 파일을 사용하는 경우 표시 서식 파일에서 URL의 window._spPageContextInfo.publicCdnBaseUrl" 속성을 사용할 수 있습니다. 최신 SPFx 클래식 웹 파트에 대한 웹 파트를 SharePoint "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" 속성을 사용할 수 있습니다. 이렇게 하면 변경된 경우 구현이 업데이트될 수 있도록 사전이 제공될 것입니다. 예를 SPFx URL은 "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item"을 사용하여 구성할 수 있습니다. 시리즈 [1](https://youtu.be/IH1RbQlbhIA) CDN 일부인 클라이언트 쪽 코드에서 CDN 코드를 [참조하시기 바랍니다.](https://aka.ms/sppnp-perfvideos)


### <a name="using-assets-in-private-origins"></a>개인 출처에서 자산 사용

개인 출처의 자산을 사용하기 위해 추가 구성이 필요하지 않습니다. SharePoint 온라인에서는 개인 출처의 자산에 대한 URL을 자동으로 다시 덮어 찾게 하여 해당 자산에 대한 요청은 항상 원본에서 CDN. 이러한 URL에는 자산이 요청될 때 SharePoint Online에서 자동으로 생성해야 하는 토큰이 포함되어 있기 때문에 개인 출처의 CDN 자산에 대한 URL을 수동으로 빌드할 수 없습니다.

비공개 출처의 자산에 대한 액세스는 원점에 대한 사용자 권한을 기반으로 동적으로 생성된 토큰으로 보호됩니다. 이 토큰은 다음 섹션에 설명된 주의를 하여 보호됩니다. 콘텐츠를 렌더링하려면  사용자에게 원본에 대한 읽기 CDN 있어야 합니다.

다음 다이어그램은 개인 출처의 자산이 SharePoint 페이지를 요청하는 워크플로를 보여 주며,

![워크플로 다이어그램: Office 365 CDN 원본에서 자산 검색](../media/O365-CDN/o365-cdn-private-steps-transparent.png "워크플로: 개인 Office 365 CDN 자산 검색")

#### <a name="token-based-authorization-in-private-origins"></a>비공개 원본의 토큰 기반 권한 부여

온라인에서 개인 출처의 자산에 Office 365 CDN 액세스는 SharePoint 통해 부여됩니다. 원본으로 지정된 폴더 또는 라이브러리에 대한 액세스 권한이 이미 있는 사용자에게는 사용 권한 수준에 따라 파일에 액세스할 수 있는 토큰이 자동으로 부여됩니다. 이러한 액세스 토큰은 생성 후 30~90분 동안 유효하여 토큰 재생 공격을 방지할 수 있습니다.

액세스 토큰이 생성된 후 SharePoint Online은 두 개의 권한 부여 매개  변수(edge 인증 토큰)와 _oat(원본_ 인증 토큰)이 포함된 클라이언트에 사용자 지정 URI를 반환합니다. 각 토큰의 구조는 _에포치<_ 형식의 >__< 서명의 만료 >. 예:

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> 토큰을 소유하는 모든 사람은 해당 토큰의 리소스에 액세스할 CDN. 그러나 이러한 액세스 토큰을 포함하는 URL은 HTTPS를 통해만 공유되기 때문에 토큰이 만료되기 전에 최종 사용자가 URL을 명시적으로 공유하지 않는 한 권한이 없는 사용자는 자산에 액세스할 수 없습니다.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>개인 출처의 자산에 대해 항목 수준 권한이 지원되지 않습니다.

온라인에서는 개인 SharePoint 자산에 대한 항목 수준 권한을 지원하지 않습니다. 예를 들어 에 있는 파일의 경우 다음과 같은 조건에 따라 파일에 효과적으로 `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` 액세스할 수 있습니다.

|사용자  |권한  |효과적인 액세스  |
|---------|---------|---------|
|사용자 1     |folder1에 액세스할 수 있습니다.         |사용자 image1.jpg 액세스할 수 CDN         |
|사용자 2     |folder1에 액세스할 수 없습니다.         |에서 image1.jpg 액세스할 수 CDN         |
|사용자 3     |folder1에 액세스할 수 없지만 온라인에서 폴더 1에 액세스할 수 있는 명시적 image1.jpg SharePoint         |image1.jpg Online에서 직접 자산 SharePoint 액세스할 수 있지만 자산 관리에서 액세스할 CDN         |
|사용자 4     |folder1에 대한 액세스 권한이 있지만 image1.jpg Online에서 SharePoint 거부되었습니다.         |SharePoint Online에서 자산에 액세스할 수 없지만 CDN Online의 파일에 대한 액세스가 거부되어도 자산에 액세스할 SharePoint 있습니다.         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>문제 해결 Office 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>자산이 관리 에지에서 제공되고 CDN?

페이지에 CDN 자산에 대한 링크를 추가한 후 페이지로 이동한 후 이미지를 마우스 오른쪽 단추로 클릭하고 이미지 URL을 검토하여 CDN 자산이 페이지에서 제공되고 있는 것을 확인할 수 있습니다.

브라우저의 개발자 도구를 사용하여 페이지의 각 자산에 대한 URL을 보거나 타사 네트워크 추적 도구를 사용할 수도 있습니다.

> [!NOTE]
> Fiddler와 같은 네트워크 도구를 사용하여 SharePoint 페이지에서 자산을 렌더링하는 것 외의 자산을 테스트하는 경우 URL이 SharePoint Online 테넌트의 루트 URL인 GET 요청에 참조자 헤더 "Referer: " 를 수동으로 추가해야 `https://yourdomain.sharepoint.com` 합니다.

온라인에서 CDN 참조가 있어야 하기 때문에 웹 브라우저에서 직접 SharePoint 없습니다. 그러나 CDN 자산 URL을 SharePoint 페이지에 추가한 다음 브라우저에서 페이지를 열면 페이지에 CDN 자산이 렌더링됩니다.

앱 브라우저에서 개발자 도구를 사용하는 Microsoft Edge 자세한 내용은 개발자 Microsoft Edge [참조하세요.](/microsoft-edge/devtools-guide)

CDN 사용 현황 확인 및 최적의 네트워크 연결 확인을 참조하여 SharePoint 개발자 패턴 및 사례 [YouTube](https://aka.ms/sppnp-videos) 채널에서 호스트되는 짧은 비디오를 시청하세요 [CDN.](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>새 원본의 자산을 사용할 수 없는 이유는 무엇입니까?
새 원본의 자산은 등록이 CDN 원본에서 원본 저장소로 업로드되는 데 시간이 걸리기 때문에 즉시 사용할 수 CDN 않습니다. 자산 구성에서 자산을 사용할 수 있는 데 CDN 시간은 자산의 수와 파일 크기에 따라 다를 수 있습니다.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>클라이언트 쪽 웹 파트 또는 SharePoint 프레임워크 솔루션이 작동하지 않습니다.

공용 원본에 Office 365 CDN 사용하도록 설정하면 CDN 원본이 자동으로 생성됩니다.

+ */MASTERPAGE
+ */스타일 라이브러리
+ */CLIENTSIDEASSETS

*/clientsideassets 원본이 없는 경우 SharePoint 프레임워크 솔루션이 실패하고 경고 또는 오류 메시지가 생성되지 않습니다. _-NoDefaultOrigins_ 매개 변수를 CDN 사용하도록 설정한 경우 또는 원본이 수동으로 삭제된 $true 원본이 누락될 수 있습니다.

다음 PowerShell 명령에 원본이 있는지 확인할 수 있습니다.

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

또는 CLI를 사용하여 Office 365 있습니다.

```cli
spo cdn origin list
```

PowerShell에서 원본을 추가합니다.

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

CLI의 원본을 Office 365:

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>어떤 PowerShell 모듈 및 CLI 셸을 사용하여 작업해야 Office 365 CDN?

온라인 관리 셸 PowerShell 모듈 또는  Office 365 CDN **CLI를** 사용하여 SharePoint 선택할 Office 365 있습니다.

+ [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [CLI Office 365 설치](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>참고 항목

[콘텐츠 배달 네트워크](./content-delivery-networks.md)

[Office 365의 네트워크 계획 및 성능 조정](./network-planning-and-performance.md)

[SharePoint Performance Series - Office 365 CDN 비디오 시리즈](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
