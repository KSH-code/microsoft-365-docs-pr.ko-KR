---
title: 엔드포인트용 Microsoft Defender의 새로운 기능
description: Microsoft Defender for Endpoint의 최신 릴리스에서 일반적으로 사용할 수 있는 기능(GA)과 Windows 10 및 Windows 서버를 참조합니다.
keywords: Endpoint용 Microsoft Defender의 새로운 기능, ga, 일반적으로 사용 가능, 기능, 사용 가능, 새로운 기능
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6f38c052c6c1755c0717d8b64987dd69b1a5826d
ms.sourcegitcommit: f2381c3bb3351235aaca977c57a46c654b9b0657
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2021
ms.locfileid: "58387143"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender의 새로운 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

다음 기능은 Microsoft Defender for Endpoint의 최신 릴리스에서 일반적으로 사용할 수 있으며 Windows 10 및 Windows 서버의 보안 기능입니다.

미리 보기 기능에 대한 자세한 내용은 미리 보기 [기능을 참조하세요.](preview.md)


> [!TIP]
> RSS 피드: 다음 URL을 복사하여 피드 읽기에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다.
>
> ```https
> https://docs.microsoft.com/api/search/rss?search=%22features+are+generally+available+%28GA%29+in+the+latest+release+of+Microsoft+Defender+for+Endpoint%22&locale=en-us&facet=
> ```

## <a name="june-2021"></a>2021년 6월

- [델타 내보내기 소프트웨어 취약성 평가](get-assessment-methods-properties.md#31-methods) API <br> 취약성 및 보안 구성 API 컬렉션의 평가 [내보내기 외에](get-assessment-methods-properties.md) 추가되었습니다. <br> 장치로 조직의 소프트웨어 취약점 평가에 대한 전체 스냅숏을 얻는 데 사용되는 전체 소프트웨어 취약점 평가(JSON 응답)와 달리 델타 내보내기 API 호출은 선택한 날짜와 현재 날짜("델타" API 호출) 사이에 수행된 변경 내용만 페치하는 데 사용됩니다. 매월 많은 양의 데이터를 사용하여 전체 내보내기 대신 신규, 고정 및 업데이트된 취약성에 대한 특정 정보만 얻을 수 있습니다. 델타 내보내기 API 호출을 사용하여 "고정된 취약성 수" 또는 "조직에 추가된 새 취약성 수"과 같은 다양한 KPI를 계산하는 데도 사용할 수 있습니다.

- 취약점 및 보안 구성 평가 [내보내기](get-assessment-methods-properties.md) API <br> 장치 기준에 따라 위협 및 취약성 관리 끌어오는 API 컬렉션을 추가합니다. 보안 구성 평가, 소프트웨어 인벤토리 평가 및 소프트웨어 취약점 평가와 같은 다양한 유형의 데이터를 얻을 수 있는 API 호출이 있습니다. 각 API 호출에는 조직의 장치에 대한 필요합니다.

- [재구성 활동](get-remediation-methods-properties.md) API <br>  테넌트에서 만든 수정 위협 및 취약성 관리 포함된 응답이 포함된 API 컬렉션을 추가합니다. 응답 정보 유형에는 ID로 하나의 수정 활동, 모든 수정 활동 및 하나의 수정 활동의 노출된 장치가 포함됩니다.

- [장치 검색](device-discovery.md) <br> 추가 어플라이언스 또는 번거로운 프로세스 변경 없이도 회사 네트워크에 연결된 관리되지 않는 장치를 찾을 수 있습니다. 온보드 장치를 사용하여 네트워크에서 관리되지 않는 장치를 찾고 취약성 및 위험을 평가할 수 있습니다. 그런 다음 검색된 장치를 온보드하여 네트워크에 관리되지 않는 끝점이 있는 경우와 관련된 위험을 줄일 수 있습니다.

   > [!IMPORTANT]
   > 표준 검색은 2021년 7월 19부터 모든 고객의 기본 모드가 됩니다. 설정 페이지를 통해 기본 모드를 유지할 수 있습니다.

- [이제 장치 그룹 정의에](/microsoft-365/security/defender-endpoint/machine-groups) 각 조건에 대한 여러 값을 포함할 수 있습니다. 여러 태그, 장치 이름 및 도메인을 단일 장치 그룹의 정의로 설정할 수 있습니다.

- [모바일 응용 프로그램 관리 지원](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> 이 향상된 기능을 통해 Microsoft Defender for Endpoint는 Intune을 사용하여 모바일 응용 프로그램을 관리할 때 관리되는 응용 프로그램 내의 조직 데이터를 보호할 수 있습니다. 모바일 응용 프로그램 관리에 대한 자세한 내용은 이 [설명서를 참조하십시오.](/microsoft-365/mem/intune/apps/mam-faq)

- [Microsoft Tunnel VPN 통합](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> Microsoft Tunnel 이제 VPN 기능이 Android용 끝점용 Microsoft Defender 앱과 통합됩니다. 이러한 통일을 통해 조직은 하나의 보안 앱으로 간소화된 최종 사용자 환경을 제공할 수 있습니다. 즉, 모바일 위협 방어와 모바일 장치에서 프레미스 리소스에 액세스하는 기능을 모두 제공하는 동시에 보안 및 IT 팀은 친숙한 동일한 관리 환경을 유지할 수 있습니다.

- [iOS에서 탈옥 검색](/microsoft-365/security/defender-endpoint/ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios) <br> iOS의 끝점에 대한 Microsoft Defender의 탈옥 감지 기능이 이제 일반적으로 사용할 수 있습니다. 이는 이미 존재하는 피싱 보호에 추가됩니다.  자세한 내용은 장치 위험 신호에 따라 조건부 액세스 정책 [설정을 참조하세요.](/microsoft-365/security/defender-endpoint/ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)


## <a name="march-2021"></a>2021년 3월
- [다음을 사용하여 변조 방지 Microsoft Defender 보안 센터](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) <br> 테넌트 연결 이라는 방법을 사용하여 Windows 10, Windows Server 2016 및 Windows Server 2019에서 변조 보호 설정을 *관리할 수 있습니다.*


## <a name="january-2021"></a>2021년 1월

- [Windows Virtual Desktop](https://azure.microsoft.com/services/virtual-desktop/) <br> 끝점용 Microsoft Defender는 이제 가상 데스크톱에 Windows 추가합니다.

## <a name="december-2020"></a>2020년 12월

- [Microsoft Defender for Endpoint(iOS용)](microsoft-defender-endpoint-ios.md) <br> 끝점용 Microsoft Defender는 이제 iOS에 대한 지원을 추가합니다. iOS에서 끝점용 Microsoft Defender를 설치, 구성, 업데이트 및 사용하는 방법을 학습합니다.

## <a name="september-2020"></a>2020년 9월

- [Microsoft Defender for Endpoint(Android용)](microsoft-defender-endpoint-android.md) <br> 끝점용 Microsoft Defender는 이제 Android에 대한 지원을 추가합니다. Android에서 끝점용 Microsoft Defender를 설치, 구성, 업데이트 및 사용하는 방법을 학습합니다.
- [macOS 취약성 관리 위협 및 제거](tvm-supported-os.md)<br> macOS용 위협 및 취약성 관리 이제 공개 미리 보기에 있으며, macOS 장치의 취약점을 지속적으로 감지하여 위험에 집중하여 수정에 우선 순위를 지정하는 데 도움을 줄 것입니다. 자세한 내용은 이 Microsoft Tech Community [게시물을 참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-for-endpoint-adds-depth-and-breadth-to-threat/ba-p/1695824)

## <a name="august-2020"></a>2020년 8월

- [Microsoft Defender for Endpoint(Android용)](microsoft-defender-endpoint-android.md) <br> 끝점용 Microsoft Defender는 이제 Android에 대한 지원을 추가합니다. Android에서 끝점용 Microsoft Defender를 설치, 구성 및 사용하는 방법을 학습합니다.

## <a name="july-2020"></a>2020년 7월

- [인증서에 대한 지표 만들기](manage-indicators.md) <br> 인증서를 허용하거나 차단하는 표시기를 생성합니다.

## <a name="june-2020"></a>2020년 6월

- [Microsoft Defender for Endpoint(Linux용)](microsoft-defender-endpoint-linux.md) <br> 이제 끝점용 Microsoft Defender에서 Linux에 대한 지원을 추가합니다. Linux에서 끝점용 Microsoft Defender를 설치, 구성, 업데이트 및 사용하는 방법을 학습합니다.

- [평가 랩의 공격 시뮬레이터](evaluation-lab.md#threat-simulator-scenarios) <br> 끝점용 Microsoft Defender는 다양한 위협 시뮬레이션 플랫폼과 파트너가 되어 포털 내에서 바로 플랫폼의 기능을 테스트할 수 있는 편리한 액세스 권한을 제공합니다.

## <a name="april-2020"></a>2020년 4월

- [위협 & 관리 API 지원](exposed-apis-list.md) <BR>조직의 & 노출 점수 또는 장치 보안 점수, 소프트웨어 및 장치 취약점 인벤토리, 소프트웨어 버전 배포, 장치 취약성 정보, 보안 권장 정보 등의 위협 요소 관리 관련 API 호출을 실행합니다. 자세한 내용은 이 Microsoft Tech Community [게시물을 참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)

## <a name="november-december-2019"></a>November-December 2019

- [Microsoft Defender for Endpoint(macOS용)](microsoft-defender-endpoint-mac.md) <BR> MacOS의 끝점용 Microsoft Defender는 Mac 장치에 차세대 보호 기능을 제공합니다. 이제 통합된 끝점 보안 플랫폼의 핵심 구성 요소를 끝점 감지 및 응답을 포함하여 Mac 장치에서 사용할 [수 있습니다.](microsoft-defender-endpoint-mac.md)

- [위협 & 관리 응용 프로그램 및 응용 프로그램 버전 종료 정보](tvm-security-recommendation.md) <BR>수명이 종료된 응용 프로그램 및 응용 프로그램 버전은 더 이상 지원되지 않는다는 것을 인식하고 제거 또는 바꾸기 작업을 취할 수 있도록 태그가 지정되거나 레이블이 지정됩니다. 이렇게 하면 패치가 없는 응용 프로그램으로 인한 다양한 취약점 노출과 관련된 위험을 완화하는 데 도움이 됩니다.

- [위협 & 관리 고급 헌팅 스마](advanced-hunting-schema-reference.md) <BR>고급 헌팅 & 위협 요소 관리 테이블을 사용하여 소프트웨어 인벤토리, 취약성 지식베이스, 보안 구성 평가 및 보안 구성 지식베이스에 대해 쿼리합니다.

 - [위협 & 관리 역할 기반 액세스 제어](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) <BR>새 사용 권한을 사용하여 권한이 부여된 사용자만 특정 데이터에 액세스하여 작업을 수행할 수 있도록 SecOps 중심 역할, 위협 & 취약성 관리 중심 역할 또는 하이브리드 역할을 만들 수 있습니다. 또한 위협 & 취약성 관리 역할이 취약성 관련 데이터만 볼 수 있는지 또는 수정 및 예외를 만들고 관리할 수 있는지 여부를 지정하여 더욱 세부적으로 관리할 수 있습니다.

- [디바이스 상태 및 규정 준수 보고서](machine-reports.md) <br/> 장치 상태 및 준수 보고서는 조직의 장치에 대한 높은 수준의 정보를 제공합니다.

## <a name="october-2019"></a>2019년 10월

- [IP 주소, URL/도메인 표시기](manage-indicators.md) <BR> 이제 자체 위협 인텔리전스를 사용하여 URL/도메인을 허용하거나 차단할 수 있습니다.

- [Microsoft 위협 전문가 - 전문가](microsoft-threat-experts.md) <BR> 이제 포털의 여러 장소에서 Microsoft 위협 전문가 수사와 관련해 도움을 줄 수 있는 옵션을 사용할 수 있습니다.

- [연결된 Azure AD 응용 프로그램](connected-applications.md)<br> 연결된 응용 프로그램 페이지에서는 조직의 끝점용 Microsoft Defender에 연결된 Azure AD 응용 프로그램에 대한 정보를 제공합니다.

- [API 탐색기](api-explorer.md)<br> API 탐색기를 사용하면 API 쿼리를 쉽게 생성 및 수행하고, 사용 가능한 모든 끝점용 Microsoft Defender API 끝점에 대한 요청을 테스트 및 전송할 수 있습니다.

## <a name="september-2019"></a>2019년 9월

- [Intune을 사용한 변조 보호 설정](prevent-changes-to-security-settings-with-tamper-protection.md) <br/> 이제 Intune(장치 관리 포털)에서 조직에 대해 변조 보호를 켜거나 Microsoft 365 수 있습니다.

- [라이브 응답](live-response.md) <BR> 원격 셸 연결을 사용하여 장치에 즉시 액세스합니다. 심층 조사 작업을 수행하고 즉각적인 대응 조치를 취하여 식별된 위협을 실시간으로 포함시킵니다.

- [평가 랩](evaluation-lab.md) <BR> 끝점용 Microsoft Defender 평가 랩은 플랫폼의 기능을 평가하고 시뮬레이션을 실행하고, 실행 중인 예방, 탐지 및 수정 기능을 보는 데 집중할 수 있도록 장치 및 환경 구성의 복잡한 문제를 없애기 위해 설계되었습니다.

- [Windows Server 2008 R2 SP1](configure-server-endpoints.md) <BR> 이제 Server 2008 R2 SP1을 Windows 수 있습니다.

## <a name="june-2019"></a>2019년 6월

- [위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md) <BR> 끝점 취약성 및 잘못된 구성의 검색, 우선 순위 지정 및 수정에 대한 위험 기반 접근 방식을 사용하는 새로운 기본 제공 기능입니다.

- [장치 상태 및 준수 보고서](machine-reports.md)  장치 상태 및 준수 보고서는 조직의 장치에 대한 높은 수준의 정보를 제공합니다.

## <a name="may-2019"></a>2019년 5월

- [위협 방지 보고서](threat-protection-reports.md)<BR>위협 방지 보고서는 조직에서 생성된 경고에 대한 높은 수준의 정보를 제공합니다.

- [Microsoft 위협 전문가](microsoft-threat-experts.md)<BR> Microsoft 위협 전문가 MICROSOFT Defender for Endpoint의 새로운 관리되는 위협 헌팅 서비스로, SOC(보안 운영 센터)가 위협을 빠르고 정확하게 식별하고 대응할 수 있도록 사전 헌팅, 우선 순위 지정 및 추가 컨텍스트 및 인사이트를 제공합니다. Microsoft 고객이 보안 운영 기능을 강화하는 데 활용할 수 있는 전문 지식과 광학 계층을 추가로 Microsoft 365.

- [지표](ti-indicator.md) <BR> 이제 표시기용 API를 일반적으로 사용할 수 있습니다.

- [상호 운용성](partner-applications.md) <BR> 끝점용 Microsoft Defender는 플랫폼의 감지, 조사 및 위협 인텔리전스 기능을 향상시키는 데 도움이 되는 타사 응용 프로그램을 지원합니다.

## <a name="april-2019"></a>2019년 4월

- [Microsoft 위협 전문가 대상 공격 알림 기능](microsoft-threat-experts.md) <BR> Microsoft 위협 전문가 표적 공격 알림 경고는 조직에 맞게 조정되어 빠르게 전달될 수 있는 많은 정보를 제공하여 타임라인, 위반 범위 및 침입 방법을 포함하여 네트워크의 중요한 위협에 관심을 집중시킵니다.

- [엔드포인트용 Microsoft Defender API](apis-intro.md)  <BR> 끝점용 Microsoft Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다. 이러한 API를 통해 워크플로를 자동화하고 끝점용 Microsoft Defender 기능을 기반으로 혁신할 수 있습니다.

## <a name="february-2019"></a>2019년 2월

- [인시던트](view-incidents-queue.md) <BR> 인시던트는 모든 관련 경고 및 관련 엔터티를 모아 더 광범위한 공격 스토리를 설명하는 Microsoft Defender for Endpoint의 새로운 엔터티로, 분석가에게 복잡한 위협의 제거에 대한 더 나은 관점을 제공합니다.

- [이전 버전의 Windows 온보딩](onboard-downlevel.md)<BR> 지원되는 버전의 Windows 끝점 센서에 센서 데이터를 보낼 수 있도록 온보딩합니다.

## <a name="october-2018"></a>2018년 10월

- [공격 표면 감소 규칙](attack-surface-reduction.md)<BR>모든 공격 표면 감소 규칙은 이제 Server 2019에서 Windows 지원됩니다.

- [제어된 폴더 액세스](enable-controlled-folders.md)<BR> 제어된 폴더 액세스는 이제 Server 2019에서 Windows 지원됩니다.

- [사용자 지정 검색](manage-indicators.md)<BR>사용자 지정 검색을 사용하면 의심스러우거나 새로운 위협과 같은 모든 종류의 동작을 모니터링하는 사용자 지정 쿼리를 만들 수 있습니다. 사용자 지정 검색 규칙을 만들어 고급 헌팅 기능을 활용하면 됩니다.

- [Azure Defender와 통합](configure-server-endpoints.md)<BR> 끝점용 Microsoft Defender는 Azure Defender와 통합하여 포괄적인 서버 보호 솔루션을 제공합니다. 이 통합을 통해 Azure Defender는 끝점용 Microsoft Defender의 기능을 활용하여 서버의 위협 감지를 Windows 있습니다.

- [MSSP(관리되는 보안 서비스 공급자) 지원](mssp-support.md)<BR> 끝점용 Microsoft Defender는 MSSP 통합을 제공하여 이 시나리오에 대한 지원을 추가합니다. 이러한 통합을 통해 MSSP는 MSSP 고객의 Microsoft Defender 보안 센터 포털에 액세스하고, 전자 메일 알림을 받고, SIEM(보안 정보 및 이벤트 관리) 도구를 통해 경고를 받을 수 있습니다.

- [이동식 장치 컨트롤](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)<BR>Microsoft Defender for Endpoint는 특정 하드웨어 ID를 허용하거나 차단하는 새로운 설정을 포함하여 이동식 장치의 위협을 방지하는 데 도움이 되는 여러 모니터링 및 제어 기능을 제공합니다.

- [iOS 및 Android 장치 지원](configure-endpoints-non-windows.md)<BR> 이제 iOS 및 Android 장치가 지원됩니다. 이 서비스를 온보드할 수 있습니다.

- [위협 분석](threat-analytics.md)<BR>
Threat Analytics는 새로운 위협 및 발생이 식별되는 즉시 끝점 연구 팀에 의해 게시된 대화형 보고서 집합입니다. 이 보고서는 보안 운영 팀이 환경에 미치는 영향을 평가하는 데 도움을 주며, 조직 탄력성 향상 및 특정 위협 방지를 위한 권장 조치를 제공합니다.

- Windows 10 버전 1809의 새로운 공격 표면 감소 규칙은 다음과 같은 두 가지입니다.
  - Adobe Reader에서 하위 프로세스를 만들지 차단
  - 통신 Office 자식 프로세스를 만들지 차단합니다.

- [Windows Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
  - AMSI(맬웨어 방지 검사 인터페이스)는 VBA 매크로에 Office 확장되었습니다. [Office VBA + AMSI: 악성 매크로에 대해 베일을 파트링합니다.](https://cloudblogs.microsoft.com/microsoftsecure/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/)
  - Microsoft Defender 바이러스 백신 버전 1809의 새로운 Windows 10 이제 샌드박스(미리 보기) 내에서 실행하여 보안을 강화할 수 있습니다. [](https://www.microsoft.com/security/blog/2018/10/26/windows-defender-antivirus-can-now-run-in-a-sandbox)
  - [검색에 대한 CPU](configure-advanced-scan-types-microsoft-defender-antivirus.md) 우선 순위 Microsoft Defender 바이러스 백신 구성합니다.

## <a name="march-2018"></a>2018년 3월

- [지능형 헌팅](advanced-hunting-overview.md)

   끝점용 Microsoft Defender의 고급 헌팅을 사용하여 데이터를 쿼리합니다.

- [공격 표면 감소 규칙](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)

  새로운 공격 표면 감소 규칙:

  - 랜섬웨어에 대한 고급 보호 사용
  - 로컬 보안 기관 하위 Windows(lsass.exe)에서 자격 증명 도용 차단
  - PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단
  - USB에서 실행된 무단 및 사인되지 않은 프로세스 차단
  - 전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단

- [자동화된 조사 및 수정](automated-investigations.md)<BR> 자동화된 조사를 사용하여 위협을 조사하고 수정합니다.

    > [!NOTE]
    > 버전 Windows 10 버전 1803 이상에서 사용할 수 있습니다.

- [조건부 액세스](conditional-access.md) <br> 조건부 액세스를 사용하도록 설정하여 사용자, 장치 및 데이터를 보다 잘 보호합니다.

- [끝점용 Microsoft Defender Community 센터](community.md)<BR>
    끝점용 Microsoft Defender Community 센터는 커뮤니티 구성원이 제품에 대한 학습, 공동 작업 및 경험을 공유할 수 있는 장소입니다.

- [제어된 폴더 액세스](enable-controlled-folders.md)<BR>
이제 제어된 폴더 액세스를 사용하여 디스크 섹터에 쓸 수 없는 프로세스를 차단할 수 있습니다.

- [Windows가 아닌 장치 온보딩](configure-endpoints-non-windows.md)<BR>
    끝점용 Microsoft Defender는 비보안 플랫폼뿐만 아니라 Windows 중앙 집중식 보안 Windows 환경을 제공합니다. 지원되는 다양한 OS(운영 체제)에서 경고를 보고 조직의 Microsoft Defender 보안 센터 보호할 수 있습니다.

- [역할 기반 액세스 컨트롤(RBAC)](rbac.md)<BR>
    RBAC(역할 기반 액세스 제어)를 사용하면 보안 작업 팀 내에 역할 및 그룹을 만들어 포털에 대한 적절한 액세스 권한을 부여할 수 있습니다.


- [Windows Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)<BR>
Microsoft Defender 바이러스 백신 서비스 간에 검색 상태를 공유하고 Microsoft 365 Microsoft Defender for Endpoint와 상호 협력합니다. 자세한 내용은 클라우드 제공 보호를 통해 Microsoft Defender 바이러스 백신 기술 사용을 [참조하세요.](cloud-protection-microsoft-defender-antivirus.md)

    이제 JS, VBS 또는 매크로와 같은 이식 가능하지 않은 실행 파일과 실행 파일을 차단할 수 있습니다. 자세한 내용은 [Enable block at first sight을 참조하세요.](configure-block-at-first-sight-microsoft-defender-antivirus.md)
