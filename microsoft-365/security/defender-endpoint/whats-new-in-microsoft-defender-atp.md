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
ms.openlocfilehash: 62f62e421c789f419eeabe174b0d05ae36e3dd4b
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60042605"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender의 새로운 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

다음 기능은 Microsoft Defender for Endpoint의 최신 릴리스에서 미리 보기로 제공되거나 일반적으로 사용할 수 Windows 10 및 Windows 서버입니다.

미리 보기 기능에 대한 자세한 내용은 미리 보기 [기능을 참조하세요.](preview.md)


> [!TIP]
> RSS 피드: 다음 URL을 복사하여 피드 읽기에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다.
>
> ```https
> https://docs.microsoft.com/api/search/rss?search=%22features+are+generally+available+%28GA%29+in+the+latest+release+of+Microsoft+Defender+for+Endpoint%22&locale=en-us&facet=
> ```


다른 Microsoft Defender 보안 제품과 함께 새로운 제품에 대한 자세한 내용은 다음을 참조하세요.

- [Microsoft 365 Defender의 새로운 기능](../defender/whats-new.md)
- [Microsoft Defender for Office 365](../office-365-security/whats-new-in-defender-for-office-365.md)
- [ID용 Microsoft Defender의 새로운](/defender-for-identity/whats-new)
- [새로운 Microsoft Cloud App Security](/cloud-app-security/release-notes)

다른 운영 체제의 끝점용 Microsoft Defender에 대한 자세한 내용은
- [MacOS의 끝점용 Defender의 새로운](mac-whatsnew.md)
- [iOS의 끝점용 Defender의 새로운](ios-whatsnew.md)
- [Linux의 끝점용 Defender의 새로운](linux-whatsnew.md)


## <a name="august-2021"></a>2021년 8월

- (미리 보기) [끝점 계획 1용 Microsoft Defender ](defender-endpoint-plan-1.md) <br/>Defender for Endpoint Plan 1(미리 보기)은 차세대 보호, 공격 표면 감소, 중앙 집중식 관리 및 보고, API를 포함하는 끝점 보호 솔루션입니다. Defender for Endpoint Plan 1(미리 보기)은 엔드포인트 보호 기능을 사용해 보고, Microsoft 365 E3 아직 추가하지 않은 고객을 위한 새로운 Microsoft 365 E5. 

   자세한 내용은 끝점 계획 [1용 Microsoft Defender(미리 보기)를 참조합니다.](defender-endpoint-plan-1.md) [끝점용 기존 Defender](microsoft-defender-endpoint.md) 기능을 끝점 계획 2용 Defender라고 합니다. 

- (미리 보기) [웹 콘텐츠 필터링](web-content-filtering.md)<br>  웹 콘텐츠 필터링은 끝점용 Microsoft Defender의 웹 보호 기능의 일부입니다. 이를 통해 조직은 해당 콘텐츠 범주에 따라 웹 사이트에 대한 액세스를 추적하고 규제할 수 있습니다. 이러한 웹 사이트 중 상당수는 악의적이지 않은 경우 규정 준수 규정, 대역폭 사용량 또는 기타 문제로 문제가 될 수 있습니다.

## <a name="july-2021"></a>2021년 7월

- (미리 보기) [장치 상태 및 준수 보고서](machine-reports.md) <br>  장치 상태 및 준수 보고서는 조직의 장치에 대한 높은 수준의 정보를 제공합니다.

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
- [다음을 사용하여 변조 방지 Microsoft Defender 보안 센터](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) <br> 테넌트 연결이라는 방법을 사용하여 Windows 10, Windows Server 2016, Windows Server 2019 및 Windows Server 2022에서 변조 보호 설정을 관리할 *수 있습니다.*


## <a name="january-2021"></a>2021년 1월

- [Windows Virtual Desktop](https://azure.microsoft.com/services/virtual-desktop/) <br> 끝점용 Microsoft Defender는 이제 가상 데스크톱에 Windows 추가합니다.
