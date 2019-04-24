---
title: Microsoft Managed Desktop에 대 한 구성 가능한 설정 참조
description: Microsoft Managed Desktop에서 구성 가능한 설정에 대 한 범주 설정
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 296602422cf4d590ae17335d7a0bbbc939d929ed
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278321"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>구성 가능한 설정 참조-Microsoft Managed Desktop

이 항목에서는 고객이 Microsoft Managed Desktop을 사용 하 여 구성할 수 있는 설정 범주를 나열 합니다. 각 설정 범주에는 요구 사항, 모범 사례 및 설정 범주를 사용자 지정 하는 방법에 대 한 정보가 포함 됩니다. 

## <a name="desktop-background-picture"></a>바탕 화면 배경 그림
조직의 Microsoft Managed desktop 장치에 대 한 바탕 화면 배경 그림을 사용자 지정할 수 있습니다. 회사 브랜드 또는 마케팅 자료를 적용 하는 데 사용할 수 있습니다. 

### <a name="requirements"></a>요구 사항

데스크톱 배경 사진에 대해 다음 요구 사항을 충족 해야 합니다.
- 그림 파일 형식-.jpg, jpeg 또는 .png
- 파일 위치-신뢰할 수 있는 보안 http (https) 위치의 호스트입니다. 
- 허용 되지 않음-Http 및 파일 공유 (unc) 위치는 지원 되지 않습니다. 

### <a name="customize-and-deploy-desktop-background-picture"></a>데스크톱 배경 그림 사용자 지정 및 배포

**사용자 지정 바탕 화면 배경 그림을 추가 하려면**
1. [Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인
2. **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3. **구성 가능한** 작업 영역에서 **바탕 화면 배경 그림**을 선택 합니다. 
4. 사용 하려는 사진의 위치를 입력 합니다. 
5. **단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다. 

## <a name="browser-start-pages"></a>브라우저 시작 페이지
사용자가 Microsoft Edge를 시작 하면 브라우저 시작 페이지가 개별 탭에 열립니다. 사용자가 자주 사용 하는 사이트 집합을 쉽게 열 수 있도록 하려면 각 사이트에 대해 브라우저 시작 페이지를 추가 합니다. 

### <a name="requirements"></a>요구 사항

브라우저 시작 페이지에 대 한 인트라넷 또는 인터넷 사이트의 FQDN (정규화 된 도메인 이름)을 제공 해야 합니다. 내부 사이트가 구성 된 경우 사용자에 게는 이러한 사이트에 대 한 액세스가 사무실에서 또는 VPN 연결로 연결 된 경우 내부 네트워크에 연결 된 경우에만 허용 된다는 것을 알 수 있습니다. 

### <a name="customize-and-deploy-browser-start-pages"></a>브라우저 시작 페이지 사용자 지정 및 배포

**브라우저 시작 페이지를 추가 하려면**
1. [Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인
2. **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3. **구성 가능한** 작업 영역에서 **브라우저 시작 페이지**를 선택 합니다. 
4. **시작 페이지 추가**를 선택 합니다.
5. **브라우저 시작 추가 페이지**에서 사용 하려는 사이트의 URL을 입력 하 고 **시작 페이지 추가**를 선택 합니다. 
6. 추가 브라우저 시작 페이지에 대해 1-5 단계를 반복 합니다. 
7. **단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.

## <a name="enterprise-mode-site-list-location"></a>엔터프라이즈 모드 사이트 목록 위치

Microsoft Edge와의 호환성 문제가 있다는 것을 알고 있는 특정 웹 사이트 및 앱이 있는 경우 엔터프라이즈 모드 사이트 목록을 사용 하 여 Internet Explorer 11을 사용 하 여 웹 사이트를 자동으로 열 수 있습니다. 또한 인트라넷 사이트가 Microsoft Edge에서 제대로 작동 하지 않을 것을 알고 있는 경우 Internet Explorer 11을 사용 하 여 모든 인트라넷 사이트를 자동으로 열도록 설정할 수 있습니다. 엔터프라이즈 모드를 사용 하는 경우에도 Microsoft Edge를 기본 브라우저로 계속 사용할 수 있고, 앱이 Internet Explorer 11에서 계속 작동 하도록 할 수도 있습니다. 엔터프라이즈 모드 사이트 목록에 대 한 자세한 내용은 [엔터프라이즈 모드 및 엔터프라이즈 모드 사이트 목록을](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)참조 하세요. 

https://위치를 지정 하거나 엔터프라이즈 모드 사이트 목록을 호스팅한 내부 공유 위치를 지정할 수 있습니다. 

### <a name="requirements"></a>요구 사항

엔터프라이즈 모드 사이트 목록 파일에 대해 다음 요구 사항을 충족 해야 합니다.
- 파일 형식- [파일 요구 사항을](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file) 충족 하는 XML 파일
- 파일 위치-내부 https 위치에 호스트 파일을 배치 합니다. 
- 허용 안 됨-/ *sharename*과 같은 내부 파일 공유에서 호스트할 수 없습니다.

### <a name="best-practices"></a>모범 사례

고객이 IT 인프라를 modernize 위해 결정을 내리는 데 도움이 되는 모범 사례가 제공 됩니다.
- **제한 된 수의 사이트 선택** -microsoft Managed Desktop은 microsoft Edge를 기본 브라우저로 사용 하 여 사용자의 조직 및 유용성에 대 한 전반적인 보안을 향상 시킵니다. 이 목록에 있는 대부분의 사이트는 보안 기능을 많이 포함 하지 않는 이전 버전의 브라우저가 필요한 레거시 웹 앱에 대 한 것입니다. 
- **** 다른 사이트 또는 이전 브라우저가 필요 하지 않은 웹 앱을 고려 하세요. 또는 최신 브라우저를 사용할 수 있도록 사이트를 업데이트 하는 것이 좋습니다. 최신 버전의 브라우저에서는 최근 기술을 사용 하 여 보안을 향상 시킬 수 있습니다.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>엔터프라이즈 사이트 모드 목록 위치 사용자 지정 및 배포

**엔터프라이즈 사이트 모드 목록 위치를 추가 하려면**

1.  [Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인
2.  **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3.  **구성 가능한** 작업 영역에서 **엔터프라이즈 모드 사이트 목록 위치**를 선택 합니다. 
4.  사이트 목록에 대 한 https 위치를 입력 합니다. 
5.  **단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.

## <a name="trusted-sites"></a>신뢰할 수 있는 사이트

신뢰할 수 있는 사이트에서는 각 사이트에 대해 보안 영역 또는 사이트를 사용할 수 있는 위치를 사용자 지정할 수 있습니다. 보안 영역에는 다음이 포함 됩니다. 
- 영역 1-로컬 인트라넷 영역
- 영역 2-신뢰할 수 있는 사이트 영역
- 영역 3-인터넷 영역
- 영역 4-제한 된 사이트 영역

### <a name="requirements"></a>요구 사항

신뢰할 수 있는 각 사이트에 대 한 인트라넷 또는 인터넷 사이트의 FQDN (정규화 된 도메인 이름)을 제공 합니다. 

### <a name="customize-and-deploy-trusted-sites"></a>신뢰할 수 있는 사이트 사용자 지정 및 배포

**신뢰할 수 있는 사이트를 추가 하려면**

1. [Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인
2. **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3. **구성 가능한** 작업 영역에서 **신뢰할 수**있는 사이트를 선택 하 고 **신뢰할 수 있는 사이트로 추가**를 선택 합니다. 
4. **신뢰할 수 있는 사이트 추가**에서 URL을 입력 하 고 보안 영역을 선택한 다음 **신뢰할 수 있는 사이트 추가**를 선택 합니다. 
5. 추가 하려는 각 신뢰할 수 있는 사이트에 대해 1-4 단계를 반복 합니다. 
6. **단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.

**신뢰할 수 있는 사이트를 제거 하려면**

1. [Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인
2. **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3. **구성 가능한** 작업 영역에서 **신뢰할 수 있는 사이트**를 선택 합니다. 
4. 삭제할 사이트를 선택 하 고 **삭제**를 선택 합니다. 
5. 삭제 하려는 각 신뢰할 수 있는 사이트에 대해 1-4 단계를 반복 합니다. 
6. **단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.

## <a name="proxy"></a>프록시와
조직에 대 한 네트워크 프록시 설정을 관리할 수 있습니다. 프록시 서버 및 포트 번호를 추가한 다음 프록시 사이트 예외를 추가 합니다. Microsoft Managed Desktop에는 서비스가 작동 하는 데 필요한 기본 프록시 예외 집합이 포함 되어 있습니다. 기본 제외 목록은 Microsoft Managed Desktop service를 통해서만 수정할 수 있습니다.  자세한 내용은 [Microsoft Managed Desktop의 네트워크 구성을](../get-ready/network.md)참조 하세요. 

microsoft managed desktop portal에서 추가 하는 프록시 사이트 예외는 microsoft managed desktop service에 포함 된 기본 프록시 예외에 추가 됩니다. 

> [!NOTE]
> 기본 프록시 예외 목록의 업데이트는 항상 고객 배포에 우선 합니다. 즉, 기본 프록시 예외 목록에 대 한 배포가 있으면 미리 구성 된 배포가 일시 중지 됩니다.  

### <a name="requirements"></a>요구 사항

프록시 서버 및 프록시 사이트 예외에 대해 다음 요구 사항을 충족 해야 합니다.
- 유효한 서버 주소 및 포트 번호 여야 합니다.
- url은 유효한 http 사이트 여야 합니다. 

### <a name="customize-and-deploy-proxies"></a>프록시 사용자 지정 및 배포

**개별 프록시 사이트 예외를 추가 하려면**

1. [Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인
2. **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3. **구성 가능한** 작업 영역에서 **프록시**를 선택 합니다. 
4. 프록시 서버의 **주소** 와 **포트 번호** 를 입력 하 고 **프록시 예외 추가**를 선택 합니다. 
5. 유효한 http 사이트의 URL을 입력 하 고 **프록시 예외 추가**를 선택 합니다. 
6. 추가 하려는 각 신뢰할 수 있는 사이트에 대해 1-5 단계를 반복 합니다. 
7. **단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.

## <a name="additional-resources"></a>추가 리소스
- [구성 가능한 설정 개요](config-setting-overview.md) 
- [구성 가능한 설정 배포](config-setting-deploy.md)
