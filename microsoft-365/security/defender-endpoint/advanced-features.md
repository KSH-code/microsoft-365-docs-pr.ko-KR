---
title: 끝점용 Microsoft Defender의 고급 기능 구성
description: 끝점용 Microsoft Defender에서 파일 차단과 같은 고급 기능을 켜야 합니다.
keywords: 고급 기능, 설정, 파일 차단, 자동화된 조사, 자동 해결, skype, ID에 대한 Microsoft Defender, office 365, Azure Information Protection, intune
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ed6f6b42570a908a1f4a83d46ef5b2de0c558692
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199744"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>끝점용 Defender의 고급 기능 구성

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

사용하는 Microsoft 보안 제품에 따라 일부 고급 기능을 사용하여 Endpoint용 Defender를 통합할 수 있습니다.

## <a name="enable-advanced-features"></a>고급 기능 사용

1. 탐색 창에서 기본 **설정** 고급 기능  >  **을 선택합니다.**
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

## <a name="autoresolve-remediated-alerts"></a>수정된 경고 자동 해결

Windows 10 버전 1809 이상에서 만든 테넌트의 경우 자동화된 분석 결과 상태가 "위협 없음" 또는 "수정"인 경고를 해결하도록 기본적으로 자동화된 조사 및 수정 기능이 구성됩니다.  경고를 자동으로 해결하지 못하게 하려는 경우 기능을 수동으로 해제해야 합니다.

> [!TIP]
> 해당 버전 이전에 만든 테넌트의 경우 고급 기능 페이지에서 이 기능을 수동으로 [켜야](https://securitycenter.windows.com/preferences2/integration) 합니다.

> [!NOTE]
>
> - 자동 해결 작업의 결과는 장치에서 발견된 활성 경고를 기반으로 하는 장치 위험 수준 계산에 영향을 줄 수 있습니다.
> - 보안 운영 분석가가 경고의 상태를 수동으로 "진행 중" 또는 "해결"으로 설정하면 자동 확인 기능이 덮어지지 않습니다.

## <a name="allow-or-block-file"></a>파일 허용 또는 차단

차단은 조직에서 다음 요구 사항을 충족하는 경우만 사용할 수 있습니다.

- Microsoft Defender 바이러스 백신을 활성 맬웨어 방지 솔루션으로 사용
- 클라우드 기반 보호 기능이 사용하도록 설정되어 있습니다.

이 기능을 사용하면 네트워크에서 잠재적으로 악의적인 파일을 차단할 수 있습니다. 파일을 차단하면 조직의 장치에서 파일을 읽거나 쓰거나 실행할 수 없습니다.

파일 허용 **또는 차단을** 설정하려면

1. 탐색 창에서 설정 고급 **기능** 파일 허용 또는  >    >  **차단을 선택합니다.**

1. 설정과 끄기 **간에 설정을** **전환합니다.**

    ![파일 차단 기능에 대한 고급 설정 이미지](images/atp-preferences-setup.png)

1. 페이지 **아래쪽의** 기본 설정 저장을 선택합니다.

이 기능을 켜면 파일 [](respond-file-alerts.md#allow-or-block-file) 프로필 페이지의  표시기 추가 탭을 통해 파일을 차단할 수 있습니다.

## <a name="custom-network-indicators"></a>사용자 지정 네트워크 표시기

이 기능을 켜면 IP 주소, 도메인 또는 URL에 대한 표시기를 만들어 사용자 지정 표시기 목록에 따라 허용 또는 차단할지 여부를 결정할 수 있습니다.

이 기능을 사용하려면 장치에서 Windows 10 버전 1709 이상을 실행해야 합니다. 또한 맬웨어 방지 플랫폼의 차단 모드 및 버전 4.18.1906.3 이상에서도 네트워크 보호 기능을 사용할 수 [있습니다. KB 4052623을](https://go.microsoft.com/fwlink/?linkid=2099834)참조하세요.

자세한 내용은 [지표 관리를 참조하세요.](manage-indicators.md)

> [!NOTE]
> 네트워크 보호는 끝점 데이터용 Defender에 대해 선택한 위치 밖에 있을 수 있는 위치에서 요청을 처리하는 신뢰도 서비스를 활용합니다.

## <a name="show-user-details"></a>사용자 세부 정보 표시

Azure Active Directory에 저장된 사용자 세부 정보를 볼 수 있도록 이 기능을 켜십시오. 세부 정보에는 사용자 계정 엔터티를 조사할 때 사용자의 사진, 이름, 직위 및 부서 정보가 포함됩니다. 다음 보기에서 사용자 계정 정보를 찾을 수 있습니다.

- 보안 운영 대시보드
- 경고 큐
- 장치 세부 정보 페이지

자세한 내용은 사용자 계정 [조사를 참조하세요.](investigate-user.md)

## <a name="skype-for-business-integration"></a>비즈니스용 Skype 통합

비즈니스용 Skype 통합을 사용하도록 설정하면 비즈니스용 Skype, 전자 메일 또는 전화를 사용하여 사용자와 통신할 수 있습니다. 이는 사용자와 통신하고 위험을 완화해야 하는 경우 도움이 될 수 있습니다.

> [!NOTE]
> 장치가 네트워크에서 격리되는 경우 Outlook 및 Skype 통신을 사용하도록 선택할 수 있는 팝업이 있습니다. 그러면 네트워크에서 연결이 끊어진 동안 사용자에게 통신할 수 있습니다. 이 설정은 장치가 고리 모드에 있는 경우 Skype 및 Outlook 통신에 적용됩니다.

## <a name="azure-advanced-threat-protection-integration"></a>Azure Advanced Threat Protection 통합

Azure Advanced Threat Protection과의 통합을 통해 다른 Microsoft ID 보안 제품으로 직접 피벗할 수 있습니다. Azure Advanced Threat Protection은 손상된 계정 및 관련 리소스에 대한 추가 정보를 사용하여 조사를 강화합니다. 이 기능을 사용하도록 설정하면 식별 시점에서 네트워크를 통해 피벗하여 장치 기반 조사 기능을 향상할 수 있습니다.

> [!NOTE]
> 이 기능을 사용하려면 적절한 라이선스가 필요합니다.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 위협 인텔리전스 연결

이 기능은 활성 Office 365 E5 또는 위협 인텔리전스 추가 기능이 있는 경우만 사용할 수 있습니다. 자세한 내용은 Office 365 Enterprise E5 제품 페이지를 참조하세요.

이 기능을 켜면 Office 365 Advanced Threat Protection의 데이터를 Microsoft Defender 보안 센터에 통합하여 Office 365 사서함 및 Windows 장치에서 포괄적인 보안 조사를 실시할 수 있습니다.

> [!NOTE]
> 이 기능을 사용하려면 적절한 라이선스가 필요합니다.

Office 365 위협 인텔리전스에서 상황에 맞는 장치 통합을 받으하려면 보안 및 준수 대시보드에서 끝점에 대한 Defender 설정을 & 합니다. 자세한 내용은 위협 조사 및 [응답을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

## <a name="microsoft-threat-experts"></a>Microsoft 위협 전문가

Microsoft Threat Expert 구성 요소 2개 중 대상 공격 알림은 일반 공급 중입니다. 전문가 요구 시 기능은 여전히 미리 보기 상태입니다. 미리 보기를 신청하고 응용 프로그램이 승인된 경우 전문가 요구 시 기능만 사용할 수 있습니다. Endpoint 포털의 경고 대시보드에 대한 Defender를 통해 Microsoft 위협 전문가로부터 대상 공격 알림을 받을 수 있으며, 구성하는 경우 전자 메일을 통해 받을 수 있습니다.

> [!NOTE]
> Endpoint용 Defender의 Microsoft Threat Experts 기능은 Enterprise Mobility + Security에 대한 E5 [라이선스로 사용할 수 있습니다.](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

이 설정을 사용하도록 설정하면 끝점용 Defender 신호가 Microsoft Cloud App Security로 전달되어 클라우드 응용 프로그램 사용 현황에 대한 더 깊은 가시성을 제공합니다. 전달된 데이터는 Cloud App Security 데이터와 동일한 위치에 저장 및 처리됩니다.

> [!NOTE]
> 이 기능은 Windows 10 버전 1709(OS 빌드 16299.1085 및 [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10을 실행하는 장치에서 [Enterprise Mobility + Security에](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) 대한 E5 라이선스로 사용할 수 있습니다. 버전 1803(OS 빌드 17134.704( [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, 버전 1809(OS 빌드 17763.379 및 [KB4489899)](https://support.microsoft.com/help/4489899)이상 Windows 10 버전.

## <a name="azure-information-protection"></a>Azure Information Protection

이 설정을 켜면 신호를 Azure Information Protection으로 전달할 수 있습니다. 이 기능을 사용하면 데이터 소유자와 관리자가 온보더된 디바이스의 보호된 데이터와 장치 위험 등급을 쉽게 사용할 수 있습니다.

## <a name="microsoft-secure-score"></a>Microsoft Secure Score

끝점용 Microsoft Defender 신호를 Microsoft 365 보안 센터의 Microsoft 보안 점수로 전달합니다. 이 기능을 켜면 Microsoft 보안 점수가 장치의 보안 상태와 관련한 가시성을 확보할 수 있습니다. 전달된 데이터는 Microsoft 보안 점수 데이터와 동일한 위치에 저장되고 처리됩니다.

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Microsoft Defender for Identity 포털에서 끝점에 대한 Microsoft Defender 통합 사용

Id에 대한 Microsoft Defender에서 상황에 맞는 장치 통합을 받으기 위해 Microsoft Defender for Identity 포털에서 기능을 사용하도록 설정해야 합니다.

1. 전역 관리자 또는 보안 관리자 역할로 ID 포털에 Microsoft [Defender에](https://portal.atp.azure.com/) 로그인합니다.

2. 인스턴스 **만들기 를 클릭합니다.**

3. 통합 설정을 **으로 전환하고** 저장을 **클릭합니다.**

두 포털에서 통합 단계를 완료한 후 장치 세부 정보 또는 사용자 세부 정보 페이지에서 관련 알림을 볼 수 있습니다.

## <a name="microsoft-intune-connection"></a>Microsoft Intune 연결

끝점용 Defender를 [Microsoft Intune과](https://docs.microsoft.com/intune/what-is-intune) 통합하여 장치 위험 기반 조건부 액세스를 사용하도록 [설정할 수 있습니다.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune) 이 [기능을 켜면](configure-conditional-access.md)끝점 장치 정보에 대한 Defender를 Intune과 공유하여 정책 적용을 강화할 수 있습니다.

> [!IMPORTANT]
> 이 기능을 사용하려면 Intune 및 Endpoint용 Defender에서 통합을 사용하도록 설정해야 합니다. 특정 단계에 대한 자세한 내용은 [Configure Conditional Access in Defender for Endpoint을 참조하세요.](configure-conditional-access.md)

이 기능은 다음이 있는 경우만 사용할 수 있습니다.

- Enterprise Mobility + Security E3 및 Windows E5(또는 Microsoft 365 Enterprise E5)에 대한 사용이 허가된 테넌트
- Intune에서 관리하는 Windows 10 장치 [Azure AD에](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)가입된 활성 Microsoft Intune 환경.

### <a name="conditional-access-policy"></a>조건부 액세스 정책

Intune 통합을 사용하도록 설정하면 Intune에서 클래식 CA(조건부 액세스) 정책을 자동으로 생성합니다. 이 클래식 CA 정책은 상황 보고서를 Intune으로 설정하기 위한 전제입니다. 삭제하면 안 됩니다.

> [!NOTE]
> Intune에서 만든 클래식 CA 정책은 [](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)끝점을 구성하는 데 사용되는 최신 조건부 액세스 정책과는 별개입니다.

## <a name="preview-features"></a>미리 보기 기능

Endpoint용 Defender 미리 보기 릴리스의 새로운 기능에 대해 알아보고 미리 보기 환경을 켜서 예정된 기능을 처음 사용해 볼 수 있습니다.

예정된 기능에 액세스할 수 있습니다. 기능은 일반적으로 사용 가능하기 전에 전반적인 환경을 개선하는 데 도움이 되기 위해 피드백을 제공할 수 있습니다.

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Microsoft 준수 센터와 끝점 경고 공유

끝점 보안 경고 및 해당 평가 상태를 Microsoft 규정 준수 센터에 전달하여 경고를 통해 내부자 위험 관리 정책을 향상하고 내부 위험을 발생시키는 위험을 해결한 후 손상을 일으킬 수 있습니다. 전달된 데이터는 처리되고 Office 365 데이터와 동일한 위치에 저장됩니다.

내부자 위험 [](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) 관리 설정에서 보안 정책 위반 표시기를 구성한 후 끝점용 Defender 경고는 해당 사용자의 내부자 위험 관리와 공유됩니다.

## <a name="related-topics"></a>관련 항목

- [데이터 보존 설정 업데이트](data-retention-settings.md)
- [경고 알림 구성](configure-email-notifications.md)
