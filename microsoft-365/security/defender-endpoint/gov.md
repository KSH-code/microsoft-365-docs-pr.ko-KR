---
title: 엔드포인트용 Microsoft Defender(미국 정부 고객용)
description: 사용 가능한 미국 정부 고객 요구 사항 및 기능용 Microsoft Defender for Endpoint에 대해 자세히 알아보시고
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft Defender for Endpoint, endpoint, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1eec095110378c74cd0a5aa8279ca591e2a15e47
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60239661"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>엔드포인트용 Microsoft Defender(미국 정부 고객용)

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Azure US Government 환경에서 구축된 미국 정부 고객을 위한 끝점용 Microsoft Defender는 Azure Commercial의 Endpoint용 Defender와 동일한 기본 기술을 사용 합니다.

이 제품은 GCC, GCC High 및 DoD 고객에게 제공되고 상업용 버전과 동일한 예방, 탐지, 조사 및 수정을 기반으로 합니다. 그러나 이 제공 기능에 대한 기능의 가용성에는 몇 가지 차이가 있습니다.

> [!NOTE]
> Commercial에서 Endpoint용 Defender를 GCC 고객인 경우 공개 설명서 페이지를 참조하세요.

## <a name="licensing-requirements"></a>라이선스 요구사항

미국 정부 고객을 위한 끝점용 Microsoft Defender에는 다음 Microsoft 볼륨 라이선싱 제품 중 하나가 필요합니다.

### <a name="desktop-licensing"></a>데스크톱 라이선싱

<br>

****

|GCC|GCC 높음|DoD|
|---|---|---|
|Microsoft 365 GCC G5|Microsoft 365 E5 대한 GCC 높음|Microsoft 365 DOD용 G5|
|Microsoft 365 G5 보안 GCC|Microsoft 365 G5 High용 GCC 보안|Microsoft 365 DOD용 G5 보안|
|끝점용 Microsoft Defender - GCC|Microsoft Defender for Endpoint for GCC High|DOD용 끝점용 Microsoft Defender|
|Windows 10 Enterprise E5 GCC|Windows 10 Enterprise E5 for GCC High|Windows 10 Enterprise DOD용 E5|
|

### <a name="server-licensing"></a>서버 라이선스

<br>

****

|GCC|GCC 높음|DoD|
|---|---|---|
|Microsoft Defender for Endpoint Server GCC|Microsoft Defender for Endpoint Server for GCC High|DOD용 끝점 서버용 Microsoft Defender|
|서버용 Azure Defender|서버용 Azure Defender - 정부|서버용 Azure Defender - 정부|
|

## <a name="portal-urls"></a>포털 URL

다음은 미국 정부 고객을 위한 Microsoft Defender for Endpoint 포털 URL입니다.

<br>

****

|고객 유형|포털 URL|
|---|---|
|GCC|<https://gcc.securitycenter.microsoft.us>|
|GCC 높음|<https://securitycenter.microsoft.us>|
|DoD|<https://securitycenter.microsoft.us>|
|

## <a name="endpoint-versions"></a>끝점 버전

### <a name="standalone-os-versions"></a>독립 실행형 OS 버전

다음 OS 버전이 지원됩니다.

OS 버전|GCC|GCC 높음|DoD
:---|:---:|:---:|:---:
Windows 11|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 10 버전 21H1 이상|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 10 버전 [20H2(KB4586853](https://support.microsoft.com/help/4586853)사용)|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 10 버전 [2004(KB4586853](https://support.microsoft.com/help/4586853)사용)|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 10 버전 [1909(KB4586819](https://support.microsoft.com/help/4586819)사용)|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 10 버전 [1903(KB4586819](https://support.microsoft.com/help/4586819)사용)|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
[Windows 10, 버전 1809(KB4586839](https://support.microsoft.com/help/4586839)사용)|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 10 버전 [1803(KB4598245](https://support.microsoft.com/help/4598245)사용)|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 10 버전 1709|![아니요.](images/svg/check-no.svg) <p> 참고: 지원되지 않습니다.|![](images/svg/check-yes.svg) [예(KB4499147)](https://support.microsoft.com/help/4499147) <p> 참고: [사용되지 않습니다.](/lifecycle/announcements/revised-end-of-service-windows-10-1709)업그레이드하십시오.|![아니요](images/svg/check-no.svg) <p> 참고: 지원되지 않습니다.
Windows 10 버전 1703 이전 버전|![아니요.](images/svg/check-no.svg) <p> 참고: 지원되지 않습니다.|![아니요](images/svg/check-no.svg) <p> 참고: 지원되지 않습니다.|![아니요](images/svg/check-no.svg) <p> 참고: 지원되지 않습니다.
Windows Server 2022|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows Server [2019(KB4586839](https://support.microsoft.com/help/4586839)사용)|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows Server 2016|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows Server 2012 R2|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 8.1 Enterprise|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 8 Pro|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows 7 SP1 Pro|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Linux|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
macOS|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Android|![아니요.](images/svg/check-no.svg) 개발 중|![아니요](images/svg/check-no.svg) 개발 중|![아니요](images/svg/check-no.svg) 개발 중
iOS|![아니요.](images/svg/check-no.svg) 개발 중|![아니요](images/svg/check-no.svg) 개발 중|![아니요](images/svg/check-no.svg) 개발 중

> [!NOTE]
> 패치가 지정된 경우 올바른 환경으로 끝점에 대한 Defender를 구성하려면 장치 온보딩 전에 패치를 배포해야 합니다.
>
> Windows 10 Windows Server 2019보다 오래된 Windows 장치를 온보드하려고 시도 [중(KB4586839](https://support.microsoft.com/help/4586839))| ![ 예. ](images/svg/check-yes.svg) | ![ 예 ](images/svg/check-yes.svg) | ![ 또는 Windows ](images/svg/check-yes.svg) 서버 2022 사용 [Microsoft Monitoring Agent?](configure-server-endpoints.md) 설치 마법사를 사용하는 경우 또는 명령줄 또는 스크립트를 사용하는 경우 "Azure [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) Cloud"에서 [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) "Azure US Government"를 선택해야 합니다. "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 매개 변수를 1로 설정해야 합니다. [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)

### <a name="os-versions-when-using-azure-defender-for-servers"></a>서버용 Azure Defender를 사용하는 경우 OS 버전

다음 OS 버전은 [서버용 Azure Defender를 사용할 때 지원됩니다.](/azure/security-center/security-center-wdatp)

OS 버전|GCC|GCC 높음|DoD
:---|:---:|:---:|:---:
Windows Server 2022|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows Server 2019|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows Server 2016|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows Server 2012 R2|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1|![예.](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)

## <a name="required-connectivity-settings"></a>필수 연결 설정

프록시 또는 방화벽이 기본적으로 모든 트래픽을 차단하고 특정 도메인만 통과하도록 허용하는 경우 다운로드 가능한 시트에 나열된 도메인을 허용된 도메인 목록에 추가합니다.

다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다. 이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인하거나 해당 URL에 대한 허용 규칙을 만들 수 있습니다. 

도메인 목록의 스프레드시트|설명
:-----|:-----
![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지입니다.](images/mdatp-urls.png)|서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다. <p> [여기에서 스프레드시트를 다운로드합니다.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

자세한 내용은 장치 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](configure-proxy-internet.md)

> [!NOTE]
> 스프레드시트에는 상업용 URL도 포함되어 있습니다. "US Gov" 탭을 선택해야 합니다.
>
> 필터링할 때 "US Gov"로 레이블이 붙은 레코드와 해당 지리 열에서 특정 클라우드를 찾아야 합니다.

## <a name="api"></a>API

[API](apis-intro.md)설명서에 나열된 공용 URIS 대신 다음 URIS를 사용해야 합니다.

<br>

****

|끝점 유형|GCC|GCC High & DoD|
|---|---|---|
|로그인|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Endpoint API용 Defender|`https://api-gcc.securitycenter.microsoft.us`|`https://api-gov.securitycenter.microsoft.us`|
|SIEM|`https://wdatp-alertexporter-us.gcc.securitycenter.windows.us`|`https://wdatp-alertexporter-us.securitycenter.windows.us`|

## <a name="feature-parity-with-commercial"></a>상업용 기능 패리티

미국 정부 고객을 위한 Endpoint용 Defender는 상업용 제품과 완전한 패리티를 택하지 않습니다. 당사의 목표는 모든 상업적 기능을 미국 정부 고객에게 제공하는 것이지만, 아직 사용할 수 없는 몇 가지 기능은 강조하고 싶을 것입니다.

알려진 간격은 다음 사항입니다.

<br>

****

|기능 이름|GCC|GCC 높음|DoD|
|---|:---:|:---:|:---:|
|네트워크 검색|![예](images/svg/check-yes.svg)|![아니요](images/svg/check-no.svg) 개발 중|![아니요](images/svg/check-no.svg) 개발 중|
|웹 컨텐츠 필터링|![아니요](images/svg/check-no.svg) 개발 중|![아니요](images/svg/check-no.svg) 개발 중|![아니요](images/svg/check-no.svg) 개발 중|
|통합: Azure Sentinel|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg) 경고 <p> ![예](images/svg/check-yes.svg) 인시던트 & 데이터: 비공개 미리 보기|![예](images/svg/check-yes.svg) 경고 <p> ![예](images/svg/check-yes.svg) 인시던트 & 데이터: 비공개 미리 보기|
|통합: Microsoft Power Automate & Azure Logic Apps|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg)|![예](images/svg/check-yes.svg) Azure Logic Apps <p> ![아니요](images/svg/check-no.svg) Power Automate: 개발 중|
|Microsoft 위협 전문가|![아니요](images/svg/check-no.svg) 백로그 엔지니어링|![아니요](images/svg/check-no.svg) 백로그 엔지니어링|![아니요](images/svg/check-no.svg) 백로그 엔지니어링|
