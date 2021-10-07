---
title: Mac용 Office의 네트워크 요청
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: 이 문서에서는 응용 프로그램이 도달하려고 시도하는 끝점 Mac용 Office URL 및 제공된 서비스에 대해 설명합니다.
ms.openlocfilehash: 37071b0aaf9e6f172d99a10cb4a1506f1627ef03
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177078"
---
# <a name="network-requests-in-office-for-mac"></a>Mac용 Office의 네트워크 요청

Mac용 Office 응용 프로그램은 macOS 플랫폼에서 기본 앱 환경을 제공합니다. 각 앱은 네트워크 액세스를 사용할 수 없는 경우의 상태 등 다양한 시나리오에서 작동하도록 디자인되었습니다. 컴퓨터에 연결되어 있는 경우 응용 프로그램은 일련의 웹 기반 서비스에 자동으로 연결하여 향상된 기능을 제공합니다. 다음 정보는 응용 프로그램이 도달하려고 시도하는 끝점 및 URL과 제공된 서비스에 대해 설명합니다. 이 정보는 네트워크 구성 문제를 해결하고 네트워크 프록시 서버에 대한 정책을 설정할 때 유용합니다. 이 문서의 세부 정보는 Microsoft Office 365 컴퓨터의 끝점을 포함하는 Office 365 [URL](urls-and-ip-address-ranges.md)및 주소 범위 문서를 보완하기 위해 Windows. 이 문서의 정보는 소매점에서 일회용 구매 또는 볼륨 라이선스 계약을 통해 사용할 수 있는 mac 및 Mac용 Office 2016용 Office 2019에도 적용됩니다. 

  
이 문서의 대부분은 해당 끝점에서 제공하는 서비스 또는 기능에 대한 네트워크 URL, 유형 및 설명을 자세히 설명하는 표입니다. 각 Office 앱의 서비스 및 끝점 사용이 다를 수 있습니다. 다음 앱은 아래 표에 정의되어 있습니다.
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
URL 형식은 다음과 같이 정의됩니다.
  
- ST: Static - URL이 클라이언트 응용 프로그램에 하드 코딩됩니다.
    
- SS: Semi-Static - URL은 웹 페이지 또는 리디디터의 일부로 인코딩됩니다.
    
- CS: Config Service - URL은 Office 구성 서비스의 일부로 반환됩니다.

    
## <a name="office-for-mac-default-configuration"></a>Mac용 Office 구성

 **설치 및 업데이트**
  
다음 네트워크 끝점은 Microsoft Mac용 Office(Content Delivery Network)에서 CDN.
  
|**URL**|**유형**|**설명**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365 설치 포털 전달 링크 서비스를 최신 설치 패키지로 전달합니다.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |설치 패키지의 Content Delivery Network.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |설치 패키지의 Content Delivery Network.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Microsoft 자동 업데이트용 관리 제어 끝점  <br/> |
   
 **첫 번째 앱 실행**
  
다음 네트워크 끝점은 네트워크 끝점을 처음 시작하면 Office 앱. 이러한 끝점은 사용자에게 향상된 Office 기능을 제공하고, 라이선스 유형(볼륨 라이선스 설치 포함)에 관계없이 URL에 연락합니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |'플라이트' 구성 - 기능 광원 및 실험을 허용합니다.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |'플라이트' 네트워크 구성 테스트  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |'플라이트' 네트워크 구성 테스트  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Configuration Service - 서비스 끝점의 마스터 목록입니다.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office 규칙 원격 분석 다운로드 - 원격 분석 서비스에 업로드할 데이터 및 이벤트에 대해 클라이언트에 알릴 수 있습니다.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote 원격 분석 서비스  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office 원격 분석 업로드 보고 - "하트비트" 및 클라이언트에서 발생하는 오류 이벤트가 원격 분석 서비스에 업로드됩니다.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office Template Service - 사용자에게 온라인 문서 서식 파일을 제공합니다.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office 템플릿 다운로드 - Storage PNG 템플릿 이미지입니다.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |앱에 대한 Office 구성입니다.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office 문서 통합 서비스 카탈로그(서비스 및 끝점 목록) 및 Home Realm Discovery.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Home Realm Discovery v2(15.40 이상)에 대한 리소스  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 자동 업데이트 매니페스트 - 사용 가능한 업데이트가 있는지 확인  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Microsoft Ajax JavaScript 라이브러리  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |구성 및 리소스에 대한 Office 앱입니다.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X 키  <br/> |SS  <br/> |Bing 구성 및 리소스에 Office 앱을 매핑합니다.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X 키  <br/> |SS  <br/> |구성 Graph 리소스에 Office 앱을 사용할 수 있습니다.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |새로운 콘텐츠 OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |새 콘텐츠 OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |새로운 새로운 OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |앱 내 지원 서비스.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |전자 메일 계정 검색 서비스.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook AutoDiscovery  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook 서비스에 대한 Microsoft 365 끝점입니다.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |추가 기능의 Outlook 아이콘입니다.  <br/> |
   
> [!NOTE]
> Office Configuration Service는 Mac용이 아닌 모든 Microsoft Office 클라이언트에 대한 자동 검색 서비스 역할을 합니다. 응답에서 반환된 끝점은 반정적이기 때문에 변경이 매우 까다로우지만 가능할 수 있습니다. 
  
 **로그인**
  
클라우드 기반 저장소에 로그인할 때 다음 네트워크 끝점에 연결됩니다. 계정 유형에 따라 다른 서비스에 문의할 수 있습니다. 예제:
  
- **MSA: Microsoft 계정** - 일반적으로 소비자 및 소매 시나리오에 사용됩니다. 
    
- **OrgID: 조직 계정** - 일반적으로 상업적 시나리오에 사용됩니다. 
    
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Windows 권한 부여 서비스  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365 OrgID(로그인 서비스)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |MSA(Microsoft 계정 로그인 서비스)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |MSA(Microsoft 계정 로그인 서비스 도우미)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365 OrgID(로그인 브랜딩)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |문서 및 장소 Storage 로케이터  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |MRU(최근에 사용한 문서 서비스)  <br/> |
   
> [!NOTE]
> 구독 기반 및 일반 정품 라이선스의 경우 두 라이선스 모두에 로그인하면 제품이 정품 인증되고 구독과 같은 클라우드 리소스에 액세스할 OneDrive. 볼륨 라이선스 설치의 경우 사용자에게 로그인하라는 메시지가 계속 표시되지만(기본적으로) 제품이 이미 정품 인증되어 있는 경우 클라우드 리소스에 액세스하는 데만 필요합니다. 
  
 **제품 정품 인증**
  
다음 네트워크 끝점은 구독 및 Microsoft 365 정품 인증에 적용됩니다. 특히 볼륨 라이선스 설치에는 적용되지 않습니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Office Licensing Service  <br/> |
   
 **새로운 콘텐츠**
  
다음 네트워크 끝점은 Microsoft 365 구독에만 적용됩니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |새로운 JSON 페이지 콘텐츠입니다.  <br/> |
   
 **리서치 도구**
  
다음 네트워크 끝점은 Microsoft 365 구독에만 적용됩니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |리서치자 웹 서비스  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |리서치자 정적 콘텐츠  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |리서치자 콘텐츠 공급자  <br/> |
   
 **스마트 조회**
  
다음 네트워크 끝점은 Microsoft 365 정품 인증 및 정품 인증 모두에 적용됩니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights 웹 서비스  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |JQuery 라이브러리  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |JavaScript 라이브러리 지원  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights 콘텐츠 공급자  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Insights 콘텐츠 공급자  <br/> |
   
 **PowerPoint Designer**
  
다음 네트워크 끝점은 Microsoft 365 구독에만 적용됩니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint 디자이너 웹 서비스  <br/> |
   
 **PowerPoint QuickStarter**
  
다음 네트워크 끝점은 Microsoft 365 구독에만 적용됩니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint QuickStarter 웹 서비스  <br/> |
   
 **스마일/희미하게 보내기**
  
다음 네트워크 끝점은 Microsoft 365 정품 인증 및 정품 인증 모두에 적용됩니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |스마일 서비스 보내기  <br/> |
   
 **고객 지원에 문의**
  
다음 네트워크 끝점은 Microsoft 365 정품 인증 및 정품 인증 모두에 적용됩니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |고객 지원 서비스  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |앱 내 지원 서비스  <br/> |
   
 **PDF로 저장**
  
다음 네트워크 끝점은 Microsoft 365 정품 인증 및 정품 인증 모두에 적용됩니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Word 문서 변환 서비스(PDF)  <br/> |
   
 **Office 앱(일명 추가 기능)**
  
다음 네트워크 끝점은 앱 추가 기능을 신뢰할 Microsoft 365 구독 및 정품/Office 정품 인증 모두에 적용됩니다.
  
|**URL**|**앱**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Office 앱 저장소 구성  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia 앱 리소스  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing 앱 리소스 매핑  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X 키  <br/> |SS  <br/> |앱 Graph 사람  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office 리디렉션 서비스  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office JavaScript 라이브러리  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |앱용 원격 분석 Office 서비스  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Microsoft Ajax JavaScript 라이브러리  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Microsoft Ajax JavaScript 라이브러리  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office JavaScript 라이브러리  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |지원 리소스  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |지원 리소스  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |지원 리소스  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |JavaScript 라이브러리  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |오류 보고  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |글꼴 리소스  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |원격 분석 서비스  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |원격 분석 보고  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store 자산 라이브러리  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia 페이지 리소스  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia 미디어 리소스  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia 샌드박스 프레임  <br/> |
|```https://*.virtualearth.net/```  <br/> |X 키  <br/> |SS  <br/> |지도 서식 파일  <br/> |
   
 **안전 링크**
  
다음 네트워크 끝점은 Office 구독용 모든 Microsoft 365 적용됩니다.
  
|**URL**|**유형**|**설명**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft 금고 Link Service  <br/> |
   
 **크래시 보고**
  
다음 네트워크 끝점은 Office 정품 인증 및 정품 Microsoft 365 정품 인증 모두에 적용됩니다. 프로세스가 예기치 않게 충돌하면 보고서가 생성되어 Watson 서비스로 전송됩니다.
  
|**URL**|**유형**|**설명**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Microsoft 오류 보고 서비스  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Office 공동 작업 Insights 서비스  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>네트워크 요청 및 트래픽 줄이기 옵션

기본 구성 Mac용 Office 기능과 컴퓨터의 최신 유지 모두에서 최상의 사용자 환경을 제공합니다. 일부 시나리오에서는 응용 프로그램이 네트워크 끝점에 연결하지 못하게 할 수 있습니다. 이 섹션에서는 이를 위한 옵션에 대해 설명합니다.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>클라우드 서비스 및 Sign-In 사용 안 Office Add-Ins
  
볼륨 라이선스 고객에게는 클라우드 기반 저장소에 문서를 저장하는 데 대한 엄격한 정책이 있을 수 있습니다. 다음과 같은 응용 프로그램당 기본 설정을 통해 MSA/OrgID 로그인을 사용하지 않도록 설정하고 추가 Office 액세스할 수 있습니다.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

사용자가 Sign-In 함수에 액세스하려고 하면 네트워크 연결이 없는 오류가 표시됩니다. 이 기본 설정은 온라인 제품 정품 인증도 차단하기 때문에 볼륨 라이선스 설치에만 사용해야 합니다. 특히 이 기본 설정을 사용하는 경우 Office 응용 프로그램에서 다음 끝점에 액세스하지 못하게 됩니다.
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- 위의 '로그인' 섹션에 나열된 모든 끝점
    
- 위의 '스마트 Lookup' 섹션에 나열된 모든 끝점
    
- 위의 '제품 정품 인증' 섹션에 나열된 모든 끝점
    
- 위의 'Office 앱(Office 추가 기능) 섹션에 나열된 모든 끝점입니다.
    
사용자에 대한 전체 기능을 다시 설정하려면 기본 설정을 '2'로 설정하거나 제거합니다.
  
> [!NOTE]
> 이 기본 설정에는 Mac용 Office 15.25 [160726] 이상이 필요합니다. 
  
### <a name="telemetry"></a>원격 분석 
  
Mac용 Office 주기적으로 원격 분석 정보를 Microsoft로 다시 전송합니다. 데이터가 'Nexus' 끝점에 업로드됩니다. 원격 분석 데이터는 엔지니어링 팀이 각 팀의 상태 및 예기치 않은 동작을 평가하는 데 Office 앱. 원격 분석에는 두 가지 범주가 있습니다.
  
- **하트비트에는** 버전 및 라이선스 정보가 포함되어 있습니다. 이 데이터는 앱 실행 시 즉시 전송됩니다. 
    
- **사용법에는** 앱이 사용되는 방식과 치명적이지 않은 오류에 대한 정보가 포함되어 있습니다. 이 데이터는 60분마다 전송됩니다. 
    
Microsoft는 개인 정보를 매우 심각하게 처리합니다. 에서 Microsoft의 데이터 수집 정책에 대해 읽을 수 [https://privacy.microsoft.com](https://privacy.microsoft.com) 있습니다. 응용 프로그램에서 '사용' 원격 분석 전송을 차단하기 위해 **SendAllTelemetryEnabled** 기본 설정을 조정할 수 있습니다. 기본 설정은 응용 프로그램당하며 macOS 구성 프로필을 통해 설정하거나 터미널에서 수동으로 설정할 수 있습니다. 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

하트비트 원격 분석은 항상 전송됩니다.
  
### <a name="crash-reporting"></a>크래시 보고
  
치명적인 응용 프로그램 오류가 발생하면 응용 프로그램이 예기치 않게 종료되고 충돌 보고서가 'Watson' 서비스에 업로드됩니다. 크래시 보고서는 응용 프로그램이 크래시까지 처리하고 있는 단계 목록인 통화 스택으로 구성됩니다. 이 단계는 엔지니어링 팀이 실패한 정확한 기능과 그 이유를 식별하는 데 도움이 됩니다.
  
문서 내용에 따라 응용 프로그램이 중단되는 경우도 있습니다. 앱에서 문서를 원인으로 식별하는 경우 사용자에게 통화 스택과 함께 문서를 보낼 수 있는지 묻습니다. 사용자는 이 질문에 대한 정보를 토로한 선택을 할 수 있습니다. IT 관리자는 문서 전송에 대한 엄격한 요구 사항을 충족해야 할 수 있으며 문서를 보내지 못하도록 사용자를 대신하여 결정을 내릴 수 있습니다. 문서가 전송되지 않도록 설정하고 사용자에게 메시지를 표시하지 않도록 다음 기본 설정을 설정할 수 있습니다.
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> **SendAllTelemetryEnabled를** **FALSE로** 설정하면 해당 프로세스에 대한 모든 크래시 보고를 사용할 수 없습니다. 사용 현황 원격 분석 없이 크래시 보고를 사용하도록 설정하려면 다음 기본 설정을 설정할 수 있습니다. ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>업데이트
  
Microsoft는 Mac용 Office 정기적으로(일반적으로 한 번씩) 업데이트가 릴리스됩니다. 사용자와 IT 관리자는 최신 보안 수정이 설치되도록 컴퓨터를 최신으로 유지하는 것이 가장 권장됩니다. IT 관리자가 컴퓨터 업데이트를 면밀하게 제어하고 관리하려는 경우 자동 업데이트 프로세스가 제품 업데이트를 자동으로 검색하고 제공하는 것을 방지하기 위해 다음 기본 설정을 설정할 수 있습니다.
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>방화벽/프록시를 사용하여 요청 차단
  
조직에서 방화벽 또는 프록시 서버를 통해 URL 요청을 차단하는 경우 이 문서에 나열된 URL을 허용된 것으로 구성하거나 40X 응답(예: 403 또는 404)으로 나열된 차단을 구성해야 합니다. 40X 응답을 사용하면 Office 응용 프로그램에서 리소스에 액세스할 수 없는 것을 허용하고 단순히 연결을 끊는 것보다 더 빠른 사용자 환경을 제공할 수 있습니다. 이로 인해 클라이언트가 다시 시도하게 됩니다.
  
프록시 서버에 인증이 필요한 경우 407 응답이 클라이언트에 반환됩니다. 최상의 환경을 위해 NTLM 및 Kerberos 서버 작업을 위한 특정 수정 Mac용 Office 포함하기 위해 빌드 15.27 이상을 사용하고 있습니다.
  
  
## <a name="see-also"></a>참고 항목

[Office 365 URL 및 IP 주소 범위](urls-and-ip-address-ranges.md)

