---
title: 엔드포인트용 Microsoft Defender(미국 정부 고객용)
description: 사용 가능한 미국 정부 고객 요구 사항 및 기능용 Microsoft Defender for Endpoint에 대해 자세히 알아보시고
keywords: government, gcc, high, requirements, capabilities, defender, defender atp, mdatp, endpoint, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 320913058f1d3cab36b3a279996443c2e4ef117f
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382916"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>엔드포인트용 Microsoft Defender(미국 정부 고객용)

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) 

Azure US Government 환경에서 구축된 미국 정부 고객을 위한 끝점용 Microsoft Defender는 Azure Commercial의 Endpoint용 Defender와 동일한 기본 기술을 사용 합니다.

이 제품은 GCC, GCC High 및 DoD 고객에게 제공되고 상업용 버전과 동일한 예방, 탐지, 조사 및 수정을 기반으로 합니다. 그러나 이 제공 기능에 대한 기능의 가용성에는 몇 가지 차이가 있습니다.

> [!NOTE]
> Commercial의 Endpoint용 Defender를 사용하는 GCC 고객인 경우 공개 설명서 페이지를 참조하세요.

## <a name="licensing-requirements"></a>라이선스 요구 사항
미국 정부 고객을 위한 끝점용 Microsoft Defender에는 다음 Microsoft 볼륨 라이선싱 제품 중 하나가 필요합니다.

### <a name="desktop-licensing"></a>데스크톱 라이선싱
GCC | GCC 높음 | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | GCC High용 Windows 10 Enterprise E5 | DOD용 Windows 10 Enterprise E5
| | GCC High용 Microsoft 365 E5 | DOD용 Microsoft 365 G5
| | GCC High용 Microsoft 365 G5 보안 | DOD용 Microsoft 365 G5 보안
끝점용 Microsoft Defender - GCC | GCC High용 끝점용 Microsoft Defender | DOD용 끝점용 Microsoft Defender

### <a name="server-licensing"></a>서버 라이선스
GCC | GCC 높음 | DoD
:---|:---|:---
Endpoint Server GCC용 Microsoft Defender | GCC High용 끝점 서버용 Microsoft Defender | DOD용 끝점 서버용 Microsoft Defender
서버용 Azure Defender | 서버용 Azure Defender - 정부 | 서버용 Azure Defender - 정부

<br />

## <a name="portal-urls"></a>포털 URL
다음은 미국 정부 고객을 위한 Microsoft Defender for Endpoint 포털 URL입니다.

고객 유형 | 포털 URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC 높음 | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>끝점 버전

### <a name="standalone-os-versions"></a>독립 실행형 OS 버전
다음 OS 버전이 지원됩니다.

OS 버전 | GCC | GCC 높음 | DoD
:---|:---|:---|:---
Windows 10 버전 [20H2(KB4586853](https://support.microsoft.com/help/4586853)사용) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 10 버전 [2004(KB4586853](https://support.microsoft.com/help/4586853)사용) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 10 버전 [1909(KB4586819](https://support.microsoft.com/help/4586819)사용) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 10 버전 [1903(KB4586819](https://support.microsoft.com/help/4586819)사용) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 10 버전 [1809(KB4586839)](https://support.microsoft.com/help/4586839) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 10 버전 [1803(KB4598245](https://support.microsoft.com/help/4598245)사용) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 10 버전 1709 | ![아니요](images/svg/check-no.svg)<br />참고: 지원되지 않습니다. | ![](images/svg/check-yes.svg) [예(KB4499147)](https://support.microsoft.com/help/4499147)<br />참고: [사용되지 않습니다.](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)업그레이드하십시오. | ![아니요](images/svg/check-no.svg)<br />참고: 지원되지 않습니다.
Windows 10 버전 1703 이전 버전 | ![아니요](images/svg/check-no.svg)<br />참고: 지원되지 않습니다. | ![아니요](images/svg/check-no.svg)<br />참고: 지원되지 않습니다. | ![아니요](images/svg/check-no.svg)<br />참고: 지원되지 않습니다.
Windows Server [2019(KB4586839](https://support.microsoft.com/help/4586839)사용) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows Server 2016 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 8 Pro | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Linux | ![예](images/svg/check-yes.svg) 미리 보기에서<br />아래 참고 사항 참조 | ![예](images/svg/check-yes.svg) 미리 보기에서<br />아래 참고 사항 참조 | ![예](images/svg/check-yes.svg) 미리 보기에서<br />아래 참고 사항 참조
macOS | ![예](images/svg/check-yes.svg) 미리 보기에서<br />아래 참고 사항 참조 | ![예](images/svg/check-yes.svg) 미리 보기에서<br />아래 참고 사항 참조 | ![예](images/svg/check-yes.svg) 미리 보기에서<br />아래 참고 사항 참조
Android | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링
iOS | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링

> [!NOTE]
> 패치가 지정된 경우 올바른 환경으로 끝점에 대한 Defender를 구성하려면 장치 온보딩 전에 패치를 배포해야 합니다.

> [!NOTE]
> Microsoft 모니터링 에이전트를 사용하여 Windows 10 또는 Windows Server 2019 이전 버전의 Windows 장치를 [온보드하려고 하나요?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) 설치 마법사를 사용하는 경우 또는 명령줄 또는 스크립트를 사용하는 경우 "Azure [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) Cloud"에서 [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) "Azure US Government"를 선택해야 합니다. "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 매개 변수를 1로 설정해야 합니다. [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)

> [!NOTE]
> You'll need version 101.25.72 and above for Linux, and version 101.25.69 and above for macOS. 미리 보기 중에 해당 버전은 "Insider Fast" 채널에서만 사용할 수 있습니다. 지침은 [Linux 소프트웨어](linux-install-manually.md#configure-the-linux-software-repository) 리포지토리 구성 또는 채널 이름 [설정(macOS)을](mac-updates.md#set-the-channel-name) 참조하세요.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>서버용 Azure Defender를 사용하는 경우 OS 버전
다음 OS 버전은 [서버용 Azure Defender를 사용할 때 지원됩니다.](https://docs.microsoft.com/azure/security-center/security-center-wdatp)

OS 버전 | GCC | GCC 높음 | DoD
:---|:---|:---|:---
Windows Server 2016 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>필수 연결 설정
프록시 또는 방화벽이 기본적으로 모든 트래픽을 차단하고 특정 도메인만 통과하도록 허용하는 경우 다운로드 가능한 시트에 나열된 도메인을 허용된 도메인 목록에 추가합니다.

다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다. 이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인하거나 해당 URL에 대한 허용 규칙을 만들 수 있습니다. 

도메인 목록의 스프레드시트 | 설명
:-----|:-----
![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지](images/mdatp-urls.png)<br/> | 서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다. <br /><br />[여기에서 스프레드시트를 다운로드합니다.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

자세한 내용은 장치 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](configure-proxy-internet.md)

> [!NOTE]
> 스프레드시트에는 상업용 URL도 포함되어 있습니다. "US Gov" 탭을 선택해야 합니다.
> 
> 필터링할 때 "US Gov"로 레이블이 붙은 레코드와 해당 지리 열에서 특정 클라우드를 찾아야 합니다.

### <a name="service-backend-ip-ranges"></a>서비스 백end IP 범위

네트워크 장치가 DNS 기반 규칙을 지원하지 않는 경우 대신 IP 범위를 사용합니다.

미국 정부 고객을 위한 끝점용 Defender는 Azure US Government 환경에서 구축되어 다음 지역에 배포됩니다.

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

Azure IP 범위 및 서비스 태그 – 미국 정부 클라우드에서 [Azure IP 범위를 찾을 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=57063)

> [!NOTE]
> 클라우드 기반 솔루션으로 IP 주소 범위는 변경될 수 있습니다. DNS 기반 규칙으로 이동하는 것이 좋습니다.

<br />

## <a name="api"></a>API
[API](apis-intro.md)설명서에 나열된 공용 URIS 대신 다음 URIS를 사용해야 합니다.

끝점 유형 | GCC | GCC High & DoD
:---|:---|:---
로그인 | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Endpoint API용 Defender | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>상업용 기능 패리티
미국 정부 고객을 위한 Endpoint용 Defender는 상업용 제품과 완전한 패리티를 택하지 않습니다. 당사의 목표는 모든 상업적 기능을 미국 정부 고객에게 제공하는 것이지만, 아직 사용할 수 없는 몇 가지 기능은 강조하고 싶을 것입니다.

2021년 3월 현재 알려진 공백입니다.

기능 이름 | GCC | GCC 높음 | DoD
:---|:---|:---|:---
자동화된 조사 및 수정: 라이브 응답 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
자동화된 조사 및 수정: Office 365 경고에 대한 응답 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링
이메일 알림 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
평가 랩 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
관리 및 API: 장치 상태 및 규정 준수 보고서 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
관리 및 API: 타사 제품과의 통합 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
관리 및 API: 스트리밍 API | ![예](images/svg/check-yes.svg) | ![아니요](images/svg/check-no.svg) 개발 중 | ![아니요](images/svg/check-no.svg) 개발 중
관리 및 API: 위협 방지 보고서 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
위협 및 취약성 관리 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
위협 분석 | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
웹 컨텐츠 필터링 | ![아니요](images/svg/check-no.svg) 개발 중 | ![아니요](images/svg/check-no.svg) 개발 중 | ![아니요](images/svg/check-no.svg) 개발 중
통합: Azure Sentinel | ![예](images/svg/check-yes.svg) | ![아니요](images/svg/check-no.svg) 개발 중 | ![아니요](images/svg/check-no.svg) 개발 중
통합: Microsoft Cloud App Security | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링
통합: Microsoft 준수 관리자 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링
통합: Id용 Microsoft Defender | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링
통합: Office 365용 Microsoft Defender | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링
통합: Microsoft Endpoint DLP | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링
통합: Microsoft Intune | ![예](images/svg/check-yes.svg) | ![아니요](images/svg/check-no.svg) 개발 중 | ![아니요](images/svg/check-no.svg) 개발 중
통합: Microsoft Power Automate & Azure Logic Apps | ![예](images/svg/check-yes.svg) | ![아니요](images/svg/check-no.svg) 개발 중 | ![아니요](images/svg/check-no.svg) 개발 중
통합: 비즈니스용 Skype/Teams | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
Microsoft 위협 전문가 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링 | ![아니요](images/svg/check-no.svg) 백로그 엔지니어링
