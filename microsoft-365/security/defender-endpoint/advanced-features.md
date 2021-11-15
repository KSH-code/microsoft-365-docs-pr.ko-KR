---
title: 끝점용 Microsoft Defender의 고급 기능 구성
description: 끝점용 Microsoft Defender에서 파일 차단과 같은 고급 기능을 켜야 합니다.
keywords: 고급 기능, 설정, 파일 차단, 자동화된 조사, 자동 해결, skype, ID에 대한 Microsoft Defender, office 365, Azure Information Protection, intune
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ba613d2368bbb7cbefdaaaea30595bdc235a41ef
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963230"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>끝점용 Defender의 고급 기능 구성

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedfeats-abovefoldlink)

사용하는 Microsoft 보안 제품에 따라 일부 고급 기능을 사용하여 Endpoint용 Defender를 통합할 수 있습니다.

## <a name="enable-advanced-features"></a>고급 기능 사용

1. 탐색 창에서 **끝점 고급 설정** \> **를** \> **선택합니다.**
2. 구성할 고급 기능을 선택하고 설정 및 해제  간에 설정을 **전환합니다.**
3. 기본 **설정 저장을 클릭합니다.**

다음 고급 기능을 사용하여 잠재적으로 악의적인 파일로부터 더 잘 보호하고 보안 조사 중에 더 나은 통찰력을 얻습니다.

## <a name="automated-investigation"></a>자동화된 조사

이 기능을 켜서 서비스의 자동화된 조사 및 수정 기능을 활용합니다. 자세한 내용은 자동화된 [조사를 참조하세요.](automated-investigations.md)

## <a name="live-response"></a>라이브 응답

적절한 권한이 있는 사용자가 디바이스에서 라이브 응답 세션을 시작할 수 있도록 이 기능을 켜야 합니다.

역할 할당에 대한 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)

## <a name="live-response-for-servers"></a>서버에 대한 실시간 응답

적절한 사용 권한이 있는 사용자가 서버에서 라이브 응답 세션을 시작할 수 있도록 이 기능을 켜야 합니다.

역할 할당에 대한 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)

## <a name="live-response-unsigned-script-execution"></a>라이브 응답 부호 없는 스크립트 실행

이 기능을 사용하도록 설정하면 라이브 응답 세션에서 부호 없는 스크립트를 실행할 수 있습니다.

## <a name="always-remediate-pua"></a>항상 PUA 재구성

PUA(잠재적으로 원치 않는 응용 프로그램)는 컴퓨터의 실행 속도가 느려지거나 예기치 않은 광고를 표시하거나, 최악의 경우 예기치 않게 또는 원치 않는 다른 소프트웨어를 설치할 수 있는 소프트웨어 범주입니다.

장치에 PUA 보호가 구성되어 있지 않은 경우에도 잠재적으로 원치 않는 응용 프로그램(PUA)이 테넌트의 모든 디바이스에서 수정될 수 있도록 이 기능을 켜야 합니다. 이렇게 하면 사용자가 장치에 원치 않는 응용 프로그램을 설치하지 못하도록 보호할 수 있습니다. 끄면 장치 구성에 따라 수정이 달라집니다.

## <a name="restrict-correlation-to-within-scoped-device-groups"></a>범위가 지정되는 장치 그룹 내에서 상관 관계 제한

이 구성은 로컬 SOC 작업에서 경고 상관 관계만 액세스할 수 있는 장치 그룹으로 제한하는 시나리오에 사용할 수 있습니다. 이 설정을 켜면 장치 그룹 간 경고로 구성된 인시던트는 더 이상 단일 인시던트로 간주되지 않습니다. 그러면 로컬 SOC가 관련된 장치 그룹 중 하나에 액세스할 수 있으므로 인시던트에 대해 조치를 취할 수 있습니다. 그러나 전역 SOC는 하나의 인시던트가 아닌 장치 그룹으로 여러 가지 다른 인시던트가 표시됩니다. 이 설정을 설정하는 것이 전체 조직에서 인시던트 상관 관계의 이점을 중시하지 않는 한 켜지 않는 것이 좋습니다.

> [!NOTE]
> 이 설정을 변경하면 향후 경고 상관 관계에만 영향을 미치게 됩니다.

## <a name="enable-edr-in-block-mode"></a>차단 EDR 사용

차단 모드의 끝점 감지 및 응답(EDR)은 수동 모드에서 실행되는 경우에도 Microsoft Defender 바이러스 백신 아티팩트로부터 보호합니다. 이 기능을 EDR 차단 모드에서는 디바이스에서 감지되는 악의적인 아티팩트 또는 동작을 차단합니다. EDR 차단 모드에서는 장면 뒤에서 작동하여 위반 후 감지된 악성 아티팩트를 수정합니다.

## <a name="autoresolve-remediated-alerts"></a>수정된 경고 자동 해결

테넌트가 생성되거나 Windows 10, 버전 1809 자동화된 분석 결과 상태가 "위협 없음" 또는 "수정"인 경고를 해결하도록 기본적으로 자동화된 조사 및 수정 기능이 구성됩니다. 경고를 자동으로 해결하지 못하게 하려는 경우 기능을 수동으로 해제해야 합니다.

> [!TIP]
> 해당 버전 이전에 만든 테넌트의 경우 고급 기능 페이지에서 이 기능을 수동으로 [켜야](https://security.microsoft.com//preferences2/integration) 합니다.

> [!NOTE]
>
> - 자동 해결 작업의 결과는 장치에서 발견된 활성 경고를 기반으로 하는 장치 위험 수준 계산에 영향을 줄 수 있습니다.
> - 보안 운영 분석가가 경고의 상태를 수동으로 "진행 중" 또는 "해결"으로 설정하면 자동 확인 기능이 덮어지지 않습니다.

## <a name="allow-or-block-file"></a>파일 허용 또는 차단

차단은 조직에서 다음 요구 사항을 충족하는 경우만 사용할 수 있습니다.

- 활성 Microsoft Defender 바이러스 백신 맬웨어 방지 솔루션으로 사용
- 클라우드 기반 보호 기능이 사용하도록 설정되어 있습니다.

이 기능을 사용하면 네트워크에서 잠재적으로 악의적인 파일을 차단할 수 있습니다. 파일을 차단하면 조직의 장치에서 파일을 읽거나 쓰거나 실행할 수 없습니다.

파일 허용 **또는 차단을** 설정하려면

1. 탐색 창에서 끝점 **일반 설정** 허용 또는 차단 파일을 \>  \>  \>  \> **선택합니다.**

1. 설정과 끄기 **간에 설정을** **전환합니다.**
 
    :::image type="content" source="../../media/alloworblockfile.png" alt-text="파일 차단 기능에 대한 고급 설정의 이미지입니다.":::

1. 페이지 **아래쪽의** 기본 설정 저장을 선택합니다.

이 기능을 켜면 파일 [](respond-file-alerts.md#allow-or-block-file) 프로필 페이지의  표시기 추가 탭을 통해 파일을 차단할 수 있습니다.

## <a name="custom-network-indicators"></a>사용자 지정 네트워크 표시기

이 기능을 켜면 IP 주소, 도메인 또는 URL에 대한 표시기를 만들어 사용자 지정 표시기 목록에 따라 허용할지 차단할지 여부를 결정할 수 있습니다.

이 기능을 사용하려면 장치에서 버전 1709 이상 또는 Windows 10 실행되고 있어야 Windows 11. 또한 맬웨어 방지 플랫폼의 차단 모드 및 버전 4.18.1906.3 이상에서 네트워크 보호를 사용할 수도 있습니다. 자세한 내용은 [KB](https://go.microsoft.com/fwlink/?linkid=2099834)4052623.

자세한 내용은 [지표 관리를 참조하세요.](manage-indicators.md)

> [!NOTE]
> 네트워크 보호는 끝점 데이터용 Defender에 대해 선택한 위치 외부에 있을 수 있는 위치에서 요청을 처리하는 신뢰도 서비스를 활용합니다.

## <a name="tamper-protection"></a>변조 방지
일부 종류의 사이버 공격 중에 악의적인 공격자는 컴퓨터의 바이러스 백신 보호와 같은 보안 기능을 사용하지 않도록 설정하려고 합니다. 악의적인 공격자들은 데이터에 더 쉽게 액세스하거나, 맬웨어를 설치하거나, 데이터, ID 및 장치를 악용하기 위해 보안 기능을 사용하지 않도록 설정하는 것을 좋아합니다.

변조 방지는 기본적으로 Microsoft Defender 바이러스 백신 앱 및 방법을 통해 보안 설정이 변경되지 않도록 합니다.

이 기능은 조직에서 클라우드 기반 보호를 Microsoft Defender 바이러스 백신 경우 사용할 수 있습니다. 자세한 내용은 클라우드 제공 보호를 통해 Microsoft Defender 바이러스 백신 [차세대 기술 사용을 참조하세요.](cloud-protection-microsoft-defender-antivirus.md)

변조 방지 기능을 설정하여 보안 솔루션 및 해당 필수 기능에 대한 원치 않는 변경을 방지합니다.

## <a name="show-user-details"></a>사용자 세부 정보 표시

이 기능을 켜서 사용자 세부 정보를 볼 수 있도록 Azure Active Directory. 세부 정보에는 사용자 계정 엔터티를 조사할 때 사용자의 사진, 이름, 직위 및 부서 정보가 포함됩니다. 다음 보기에서 사용자 계정 정보를 찾을 수 있습니다.

- 보안 운영 대시보드
- 경고 큐
- 장치 세부 정보 페이지

자세한 내용은 사용자 계정 [조사를 참조하세요.](investigate-user.md)

## <a name="skype-for-business-integration"></a>비즈니스용 Skype 통합

비즈니스용 Skype 통합을 사용하도록 설정하면 사용자와 통신할 수 있는 비즈니스용 Skype, 전자 메일 또는 휴대폰을 사용할 수 있습니다. 이는 사용자와 통신하고 위험을 완화해야 하는 경우 도움이 될 수 있습니다.

> [!NOTE]
> 장치가 네트워크에서 격리되는 경우 네트워크에서 연결이 끊어진 동안 사용자에게 통신을 허용하는 Outlook 및 Skype 통신을 사용하도록 선택할 수 있는 팝업이 있습니다. 이 설정은 장치가 Skype Outlook 통신에 적용됩니다.

## <a name="microsoft-defender-for-identity-integration"></a>Microsoft Defender for Identity 통합

Id에 대한 Microsoft Defender와의 통합을 통해 다른 Microsoft Id 보안 제품으로 직접 피벗할 수 있습니다. Microsoft Defender for Identity는 손상된 계정 및 관련 리소스에 대한 더 많은 정보를 통해 조사를 보강합니다. 이 기능을 사용하도록 설정하면 식별 시점에서 네트워크를 통해 피벗하여 장치 기반 조사 기능을 향상할 수 있습니다.

> [!NOTE]
> 이 기능을 사용하려면 적절한 라이선스가 필요합니다.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 위협 인텔리전스 연결

이 기능은 활성 사용자 또는 위협 인텔리전스 추가 Office 365 E5 사용할 수 있습니다. 자세한 내용은 E5 제품 Office 365 Enterprise 참조하세요.

이 기능을 켜면 Microsoft Defender의 데이터를 통합하여 Office 365 Microsoft 365 Defender 사서함 및 Windows 전체에서 포괄적인 보안 조사를 Office 365 수 있습니다.

> [!NOTE]
> 이 기능을 사용하려면 적절한 라이선스가 필요합니다.

위협 인텔리전스에서 상황 Office 365 통합을 받으하려면 보안 및 준수 대시보드에서 끝점에 대한 Defender 설정을 & 합니다. 자세한 내용은 위협 조사 및 [응답을 참조하세요.](/microsoft-365/security/office-365-security/office-365-ti)

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Microsoft 위협 전문가 - 대상 공격 알림

Microsoft Threat Expert 구성 요소 2개 중 대상 공격 알림은 일반 공급 중입니다. 전문가 요구 시 기능은 여전히 미리 보기 상태입니다. 미리 보기를 적용하고 응용 프로그램이 승인된 경우 전문가 요구 시 기능만 사용할 수 있습니다. 끝점 포털의 경고 대시보드를 Microsoft 위협 전문가 및 구성하는 경우 전자 메일을 통해 대상 공격 알림을 받을 수 있습니다.

> [!NOTE]
> Defender for endpoint의 Microsoft 위협 전문가 기능은 에 대한 E5 라이선스로 사용할 [Enterprise Mobility + Security.](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

이 설정을 사용하도록 설정하면 끝점용 Defender 신호가 클라우드 응용 Microsoft Cloud App Security 더 심층적으로 표시될 수 있습니다. 전달된 데이터는 사용자 데이터와 동일한 위치에 저장되고 Cloud App Security 처리됩니다.

> [!NOTE]
> 이 기능은 Enterprise Mobility + Security Windows 10 버전 1709(OS 빌드 16299.1085(KB4493441), [](https://support.microsoft.com/help/4493441)Windows 10 버전 1803(OS 빌드 17134.704 및 [KB4493464)을](https://support.microsoft.com/help/4493464)실행하는 디바이스에서 사용할 수 Windows 10, 버전 1809 [](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)  (OS 빌드 17763.379 [및 KB4489899](https://support.microsoft.com/help/4489899)), 이후 버전 Windows 10 또는 Windows 11.

## <a name="microsoft-secure-score"></a>Microsoft 보안 점수

Microsoft Defender for Endpoint 신호를 보안 센터의 Microsoft 보안 점수로 Microsoft 365 전달합니다. 이 기능을 켜면 Microsoft 보안 점수가 장치의 보안 상태와 관련한 가시성을 확보할 수 있습니다. 전달된 데이터는 Microsoft 보안 점수 데이터와 동일한 위치에 저장되고 처리됩니다.

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Microsoft Defender for Identity 포털에서 끝점에 대한 Microsoft Defender 통합 사용

Id에 대한 Microsoft Defender에서 상황에 맞는 장치 통합을 받으기 위해 Microsoft Defender for Identity 포털에서 기능을 사용하도록 설정해야 합니다.

1. 전역 관리자 또는 보안 관리자 역할로 ID 포털에 Microsoft [Defender에](https://portal.atp.azure.com/) 로그인합니다.

2. 인스턴스 **만들기 를 클릭합니다.**

3. 통합 설정을 **으로 전환하고** 저장을 **클릭합니다.**

두 포털에서 통합 단계를 완료한 후 장치 세부 정보 또는 사용자 세부 정보 페이지에서 관련 알림을 볼 수 있습니다.

## <a name="web-content-filtering"></a>웹 컨텐츠 필터링

원치 않는 콘텐츠가 포함된 웹 사이트에 대한 액세스를 차단하고 모든 도메인에서 웹 활동을 추적합니다. 차단할 웹 콘텐츠 범주를 지정하려는 경우 웹 콘텐츠 필터링 [정책을 만들어야 합니다.](https://security.microsoft.com/preferences2/web_content_filtering_policy) 끝점용 Microsoft Defender 보안 기준을 배포할 때 차단 모드에서 네트워크 [보호를 설정해야 합니다.](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Microsoft 준수 센터와 끝점 경고 공유

끝점 보안 경고 및 해당 평가 상태를 Microsoft 규정 준수 센터에 전달하여 경고를 통해 내부자 위험 관리 정책을 향상하고 내부 위험을 발생시키는 위험을 해결한 후 손상을 일으킬 수 있습니다. 전달된 데이터는 처리되고 사용자 데이터와 동일한 위치에 Office 365 저장됩니다.

내부자 위험 [](/microsoft-365/compliance/insider-risk-management-settings#indicators) 관리 설정에서 보안 정책 위반 표시기를 구성한 후 끝점용 Defender 경고는 해당 사용자의 내부자 위험 관리와 공유됩니다.

## <a name="microsoft-intune-connection"></a>Microsoft Intune 연결

장치 위험 기반 [조건부 액세스를](/intune/what-is-intune) Microsoft Intune 끝점용 [Defender를](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)통합할 수 있습니다. 이 [기능을 켜면](configure-conditional-access.md)끝점 장치 정보에 대한 Defender를 Intune과 공유하여 정책 적용을 강화할 수 있습니다.

> [!IMPORTANT]
> 이 기능을 사용하려면 Intune 및 Endpoint용 Defender에서 통합을 사용하도록 설정해야 합니다. 특정 단계에 대한 자세한 내용은 [Configure Conditional Access in Defender for Endpoint을 참조하세요.](configure-conditional-access.md)

이 기능은 다음의 경우만 사용할 수 있습니다.

- E5 및 Enterprise Mobility + Security E3 및 Windows E5용 Microsoft 365 Enterprise 테넌트
- Intune에서 관리하는 Microsoft Intune Azure AD에 가입된 Windows 활성 [환경입니다.](/azure/active-directory/devices/concept-azure-ad-join/)

### <a name="conditional-access-policy"></a>조건부 액세스 정책

Intune 통합을 사용하도록 설정하면 Intune에서 클래식 CA(조건부 액세스) 정책을 자동으로 생성합니다. 이 클래식 CA 정책은 상황 보고서를 Intune으로 설정하기 위한 전제입니다. 삭제하면 안 됩니다.

> [!NOTE]
> Intune에서 만든 클래식 CA 정책은 [](/azure/active-directory/conditional-access/overview/)끝점을 구성하는 데 사용되는 최신 조건부 액세스 정책과는 별개입니다.

## <a name="device-discovery"></a>장치 검색

추가 어플라이언스 또는 번거로운 프로세스 변경 없이도 회사 네트워크에 연결된 관리되지 않는 장치를 찾을 수 있습니다. 온보드 장치를 사용하여 네트워크에서 관리되지 않는 장치를 찾고 취약성 및 위험을 평가할 수 있습니다. 자세한 내용은 장치 [검색을 참조하세요.](device-discovery.md)

> [!NOTE]
> 항상 필터를 적용하여 관리되지 않는 장치를 장치 인벤토리 목록에서 제외할 수 있습니다. API 쿼리의 등록 상태 열을 사용하여 관리되지 않는 장치를 필터링할 수도 있습니다.

## <a name="preview-features"></a>미리 보기 기능

Endpoint용 Defender 미리 보기 릴리스의 새로운 기능에 대해 자세히 알아보습니다. 미리 보기 환경을 켜서 예정된 기능을 사용해 하세요.

예정된 기능에 액세스할 수 있습니다. 기능은 일반적으로 사용 가능하기 전에 전반적인 환경을 개선하는 데 도움이 되기 위해 피드백을 제공할 수 있습니다.

## <a name="download-quarantined-files"></a>quarantined files 다운로드

보안 및 규격 위치에 보관된 파일을 백업하여 해당 파일을 검지에서 직접 다운로드할 수 있습니다. 파일 **다운로드 단추는** 항상 파일 페이지에서 사용할 수 있습니다. 이 설정은 기본적으로 켜져 있습니다. [요구 사항에 대해 자세히 알아보시다](respond-file-alerts.md#download-quarantined-files)

## <a name="related-topics"></a>관련 주제

- [데이터 보존 설정 업데이트](data-retention-settings.md)
- [경고 알림 구성](configure-email-notifications.md)
