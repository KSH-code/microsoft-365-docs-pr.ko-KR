---
title: 사용자에 대한 구성 가능한 설정 Microsoft Managed Desktop
description: 구성 가능한 설정에 대한 범주 Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215205"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>구성 가능한 설정 참조 - Microsoft Managed Desktop

이 항목에서는 고객이 이러한 설정을 사용하여 구성할 수 있는 설정 범주를 Microsoft Managed Desktop. 각 설정 범주에는 요구 사항, 모범 사례 및 설정 범주를 사용자 지정하는 방법에 대한 정보가 포함되어 있습니다. 

## <a name="desktop-background-picture"></a>바탕 화면 배경 그림
조직의 디바이스에 대한 데스크톱 배경 Microsoft Managed Desktop 사용자 지정할 수 있습니다. 이를 사용하여 회사 브랜드 또는 마케팅 자료를 적용할 수 있습니다. 

### <a name="requirements"></a>요구 사항

데스크톱 배경 그림에 대해 다음 요구 사항을 충족해야 합니다.
- 그림 파일 형식 - .jpg, jpeg 또는 .png
- 파일 위치 - 신뢰할 수 있는 보안 http(https) 위치에 호스트 
- 허용되지 않습니다. Http 및 파일 공유(unc) 위치가 지원되지 않습니다. 

### <a name="customize-and-deploy-desktop-background-picture"></a>데스크톱 배경 사진 사용자 지정 및 배포

**사용자 지정 데스크톱 배경 그림을 추가합니다.**
1. 로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.
2. Microsoft Managed Desktop 를 찾아 를 **설정.**
3. 작업 **설정** 바탕 화면 배경 **그림 을 선택합니다.** 
4. 사용할 그림의 위치를 입력합니다. 
5. 단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다. 

## <a name="browser-start-pages"></a>브라우저 시작 페이지
사용자가 브라우저 시작 페이지를 시작할 때 개별 탭에서 브라우저 Microsoft Edge. 사용자가 자주 사용하는 사이트 집합을 쉽게 열 수 있도록 하려는 경우 각 사이트에 대해 브라우저 시작 페이지를 추가합니다. 

### <a name="requirements"></a>요구 사항

브라우저 시작 페이지에 대한 인트라넷 또는 인터넷 사이트의 FQDN(정식 도메인 이름)을 제공해야 합니다. 내부 사이트가 구성된 경우 사용자가 사무실에 있을 때 또는 VPN 연결로 연결된 경우 내부 네트워크에 연결되어 있을 때만 이러한 사이트에 대한 액세스가 허용됩니다. 

### <a name="customize-and-deploy-browser-start-pages"></a>브라우저 시작 페이지 사용자 지정 및 배포

**브라우저 시작 페이지를 추가하는 경우**
1. 로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.
2. Microsoft Managed Desktop 를 찾아 를 **설정.**
3. 작업 **설정** 시작 페이지에서 **브라우저 시작 페이지를 선택합니다.** 
4. 시작 **페이지 추가를 선택합니다.**
5. 브라우저 **시작 페이지 추가에서** 사용할 사이트의 URL을 입력한 다음 시작 페이지 **추가를 선택합니다.** 
6. 추가 브라우저 시작 페이지에 대해 1-5단계를 반복합니다. 
7. 단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.

## <a name="enterprise-mode-site-list-location"></a>Enterprise 모드 사이트 목록 위치

Microsoft Edge 호환성 문제가 있는 것으로 알고 있는 특정 웹 사이트 및 앱이 있는 경우 Enterprise 모드 사이트 목록을 사용하여 Internet Explorer 11을 사용하여 웹 사이트가 자동으로 열리게 할 수 있습니다. 또한 인트라넷 사이트가 Microsoft Edge 제대로 작동하지 않는 경우 모든 인트라넷 사이트가 Internet Explorer 11을 사용하여 열리게 설정할 수 있습니다. Enterprise 모드를 사용하면 Microsoft Edge 브라우저로 계속 사용할 수 있는 동시에 앱이 Internet Explorer 11에서 계속 작동할 수 있습니다. 엔터프라이즈 모드 사이트 목록에 대한 자세한 내용은 Enterprise 모드 및 Enterprise 사이트 목록을 [참조하세요.](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode) 

엔터프라이즈 모드 https:// 호스팅한 내부 공유의 위치를 지정할 수 있습니다. 

### <a name="requirements"></a>요구 사항

엔터프라이즈 모드 사이트 목록 파일에 대해 다음 요구 사항을 충족해야 합니다.
- 파일 형식 - 파일 요구 사항을 충족하는 [XML 파일](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- 파일 위치 - 내부 https 위치에 파일을 호스트합니다. 
- 허용되지 않습니다. *//sharename과* 같은 내부 파일 공유에서 호스팅이 허용되지 않습니다.

### <a name="best-practices"></a>모범 사례

이러한 모범 사례는 고객이 IT 인프라를 현대화하기 위한 의사 결정을 내리는 데 도움을 줄 수 있도록 제공됩니다.
- **제한된 수의** 사이트를 선택 - Microsoft Managed Desktop Microsoft Edge 브라우저를 사용하여 조직의 전반적인 보안과 사용자의 사용성을 향상합니다. 이 목록의 대부분의 사이트는 많은 보안 기능을 포함하지 않는 이전 버전의 브라우저가 필요한 레거시 웹앱용입니다. 
- **대체 고려** - 이전 브라우저가 필요하지 않은 다른 사이트 또는 웹앱을 고려하세요. 또는 새 브라우저를 사용할 수 있도록 사이트를 업데이트하는 것이 좋습니다. 최신 브라우저는 최신 기술을 사용하며 보안을 향상시키는 데 도움이 됩니다.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>사이트 모드 목록 Enterprise 사용자 지정 및 배포

**엔터프라이즈 사이트 모드 목록 위치를 추가하는 경우**

1. 로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.
2. Microsoft Managed Desktop 를 찾아 를 **설정.**
3. 설정  작업 영역에서 Enterprise **사이트 목록 위치 를 선택합니다.** 
4. 사이트 목록의 https 위치를 입력합니다. 
5. 단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.

## <a name="trusted-sites"></a>신뢰할 수 있는 사이트

신뢰할 수 있는 사이트를 사용하면 서로 다른 사이트에 대해 보안 영역 또는 사이트를 사용할 수 있는 위치를 사용자 지정할 수 있습니다. 보안 영역은 다음과 같습니다. 
- 영역 1 - 로컬 인트라넷 영역
- 영역 2 - 신뢰할 수 있는 사이트 영역
- 영역 3 - 인터넷 영역
- 영역 4 - 제한된 사이트 영역

### <a name="requirements"></a>요구 사항

신뢰할 수 있는 각 사이트에 대해 인트라넷 또는 인터넷 사이트에 대한 FQDN(FQDN)을 제공합니다. 

### <a name="customize-and-deploy-trusted-sites"></a>신뢰할 수 있는 사이트 사용자 지정 및 배포

**신뢰할 수 있는 사이트를 추가하는 경우**

1. 로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.
2. Microsoft Managed Desktop 를 찾아 를 **설정.**
3. 작업 **설정** 에서 신뢰할 **수** 있는 사이트 를 선택한 다음 신뢰할 수 있는 사이트 추가 **를 선택합니다.** 
4. 신뢰할 **수 있는 사이트 추가에서** URL을 입력하고 보안 영역, 신뢰할 수 있는 사이트 **추가를 선택합니다.** 
5. 추가할 신뢰할 수 있는 각 사이트에 대해 1-4단계를 반복합니다. 
6. 단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.

**신뢰할 수 있는 사이트를 제거하려면**

1. 로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.
2. Microsoft Managed Desktop 를 찾아 를 **설정.**
3. 작업 **설정** 신뢰할 수 있는 **사이트를 선택합니다.** 
4. 삭제할 사이트를 선택하고 삭제 를 **선택합니다.** 
5. 삭제할 신뢰할 수 있는 각 사이트에 대해 1-4단계를 반복합니다. 
6. 단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.

## <a name="proxy"></a>프록시
조직의 네트워크 프록시 설정을 관리할 수 있습니다. 프록시 서버 및 포트 번호를 추가한 다음 프록시 사이트 예외를 추가합니다. Microsoft Managed Desktop 서비스에 필요한 기본 프록시 예외 집합이 포함됩니다. 기본 제외 목록은 서비스에서만 수정할 Microsoft Managed Desktop 있습니다.  자세한 내용은 에 [대한 네트워크 구성을 Microsoft Managed Desktop.](../get-ready/network.md) 

Microsoft Managed Desktop 포털에 추가하는 프록시 사이트 예외는 Microsoft Managed Desktop 서비스에 포함된 기본 프록시 예외에 추가됩니다. 

> [!NOTE]
> 기본 프록시 예외 목록 업데이트는 항상 고객 배포보다 우선합니다. 즉, 기본 프록시 예외 목록에 대한 배포가 있는 경우 단계적 배포가 일시 중지됩니다.  

### <a name="requirements"></a>요구 사항

프록시 서버 및 프록시 사이트 예외에 대해 이러한 요구 사항을 충족해야 합니다.
- 유효한 서버 주소 및 포트 번호
- URL은 유효한 http 사이트가 되어야 합니다. 

### <a name="customize-and-deploy-proxies"></a>사용자 지정 및 배포

**개별 프록시 사이트 예외를 추가합니다.**

1. 로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.
2. Microsoft Managed Desktop 를 찾아 를 **설정.**
3. 작업 **설정** 에서 프록시 를 **선택합니다.** 
4. 프록시 서버에 **대한 주소** 및 **포트** 번호를 입력한 다음 프록시 예외 **추가 를 선택합니다.** 
5. 유효한 http 사이트의 URL을 입력한 다음 프록시 예외 **추가 를 선택합니다.** 
6. 추가할 신뢰할 수 있는 각 사이트에 대해 1-5단계를 반복합니다. 
7. 단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.

## <a name="additional-resources"></a>추가 리소스
- [구성 가능한 설정 개요](config-setting-overview.md) 
- [구성 가능한 설정 배포](config-setting-deploy.md)