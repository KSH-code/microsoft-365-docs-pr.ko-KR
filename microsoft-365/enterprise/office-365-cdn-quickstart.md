---
title: Office 365 CDN(콘텐츠 배달 네트워크) 빠른 시작
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 CDN(콘텐츠 배달 네트워크) 빠른 시작
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921597"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 CDN(콘텐츠 배달 네트워크) 빠른 시작

기본 제공 **Office 365 CDN(콘텐츠** 배달 네트워크)을 사용하여 정적 자산(이미지, JavaScript, 스타일시트, WOFF 파일)을 호스트하여 SharePoint Online 페이지에 대한 성능을 개선할 수 있습니다. Office 365 CDN은 정적 자산을 요청하는 브라우저에 더 가깝게 캐싱하여 성능을 향상시켜 다운로드 속도를 높이고 대기 시간을 줄이는 데 기여합니다. 또한 Office 365 CDN은 향상된 압축 및 HTTP 파이프라이너를 위해 HTTP/2 프로토콜을 사용합니다. Office 365 CDN 서비스는 SharePoint Online 구독의 일부로 포함되어 있습니다.

자세한 내용은 [SharePoint Online에서 Office 365 CDN(콘텐츠](use-microsoft-365-cdn-with-spo.md)배달 네트워크) 사용을 참조하세요.

>[!NOTE]
>Office 365 CDN은 프로덕션(전 세계) 클라우드의 테넌트만 사용할 수 있습니다. 미국 정부, 중국 및 독일 클라우드의 테넌트는 현재 Office 365 CDN을 지원하지 않습니다.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>SharePoint용 페이지 진단 도구를 사용하여 CDN에 없는 항목 식별

**SharePoint용 페이지 진단** 도구 브라우저 확장을 사용하여 CDN 원본에 추가할 수 있는 SharePoint Online 페이지에 자산을 쉽게 나열할 수 있습니다.

**SharePoint용** 페이지 진단 도구는 새로운 Microsoft Edge(및 SharePoint Online 최신 포털과 클래식 게시 사이트 페이지를 모두 분석하는 Chrome 브라우저)의 브라우저 https://www.microsoft.com/edge) 확장입니다. 이 도구는 정의된 성능 기준의 집합 대비 페이지 수행 방식을 보여주는 분석된 각 페이지에 대한 보고서를 제공합니다. Sharepoint용 페이지 진단 도구에 대해 배우고 설치하려면[Sharepoint Online에 페이지 진단 도구 사용](./page-diagnostics-for-spo.md)을 참조하세요.

SharePoint Online 페이지에서 SharePoint용 페이지 진단 도구를 실행하면 진단  테스트 탭을 클릭하여 CDN에서 호스팅되지 않는 자산 목록을 볼 수 있습니다. 이러한 자산은 아래 스크린샷과 같이 **CDN(콘텐츠** 배달 네트워크) 확인 제목 아래에 나열됩니다.

![페이지 진단](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>페이지 진단 도구는 SharePoint Online에서만 사용할 수 있으며 SharePoint 시스템 페이지에서는 사용할 수 없습니다.

## <a name="cdn-overview"></a>CDN 개요

Office 365 CDN은 고속 전역 네트워크를 통해 이미지 및 javascript 파일과 같은 자주 액세스하는 개체를 배포하여 페이지 로드 시간을 줄이고 사용자가 가능한 한 가까운 호스트된 개체에 액세스할 수 있도록 하여 사용자의 성능을 최적화하도록 디자인되어 있습니다. CDN은 원점 이라는 위치에서 자산을 _페치합니다._ 원본은 URL로 액세스할 수 있는 SharePoint 사이트, 문서 라이브러리 또는 폴더일 수 있습니다.

Office 365 CDN은 다음 두 가지 기본 유형으로 구분됩니다.

- **공용 CDN은** JS(JavaScript), CSS(스타일시트), 웹 글꼴 파일(WOFF, WOFF2) 및 회사 로고와 같은 비소유 이미지에 사용할 수 있도록 디자인됩니다.
- **개인 CDN은** 이미지(PNG, JPG, JPEG 등)에 사용할 수 있도록 디자인됩니다.

조직에 대한 공개 출처 또는 비공개 출처를 둘 다 찾게 선택할 수 있습니다. 대부분의 조직에서는 둘의 조합을 구현하기로 선택합니다. 공개 옵션과 개인 옵션 모두 비슷한 성능 이점을 제공하지만 각각 고유한 특성과 장점이 있습니다. 공개 및 개인 CDN 출처에 대한 자세한 내용은 [Choose whether each origin should be public or private을 참조하세요.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>기본 구성을 사용하여 공용 및 개인 CDN을 사용하도록 설정하는 방법
테넌트 CDN 설정을 변경하기 전에 해당 설정이 조직의 규정 준수, 보안 및 개인 정보 보호 정책을 충족하는지 확인해야 합니다.

자세한 구성 설정 또는 이미 CDN을 사용하도록 설정한 경우 추가 위치(원본)를 추가하려면 SharePoint Online 관리 셸을 사용하여 [Office 365 CDN](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) 설정 및 구성 섹션을 참조하세요.

SharePoint Online 관리 셸을 사용하여 테넌트에 연결합니다.

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

조직에서 기본 구성에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

이러한 cmdlet의 출력은 다음과 같습니다.

![출력 Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>참고 항목

[SharePoint Online용 페이지 진단 도구 사용](./page-diagnostics-for-spo.md)

[sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기](use-microsoft-365-cdn-with-spo.md)

[콘텐츠 배달 네트워크](./content-delivery-networks.md)

[Office 365의 네트워크 계획 및 성능 조정](./network-planning-and-performance.md)

[SharePoint Performance Series - Office 365 CDN 비디오 시리즈](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)