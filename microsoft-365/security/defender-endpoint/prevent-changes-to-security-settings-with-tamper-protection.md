---
title: 변조 방지를 사용하여 보안 설정 보호
ms.reviewer: shwjha, hayhov
manager: dansimp
description: 변조 방지를 사용하여 악성 앱이 중요한 보안 설정을 변경하지 못하게 합니다.
keywords: 맬웨어, defender, 바이러스 백신, 변조 방지
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 147247435564133502f33d33799d05ef809e0427
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691382"
---
# <a name="protect-security-settings-with-tamper-protection"></a>변조 방지를 사용하여 보안 설정 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

변조 보호는 다음 Windows 버전 중 하나를 실행하는 장치에 사용할 수 있습니다.

- Windows 10
- Windows Server 2019
- Windows Server, 버전 1803 이상
- Windows Server 2016

## <a name="overview"></a>개요

일부 종류의 사이버 공격 중에 악의적인 공격자는 컴퓨터의 바이러스 백신 보호와 같은 보안 기능을 사용하지 않도록 설정하려고 합니다. 악의적인 공격자들은 데이터에 더 쉽게 액세스하거나, 맬웨어를 설치하거나, 데이터, ID 및 장치를 악용하기 위해 보안 기능을 사용하지 않도록 설정하는 것을 좋아합니다. 변조 방지는 이러한 종류의 발생을 방지하는 데 도움이 됩니다.

변조 방지를 통해 악성 앱은 다음 작업을 수행할 수 없습니다.

- 바이러스 및 위협 방지를 사용 안 하게
- 실시간 보호를하지 않습니다.
- 동작 모니터링 끄기
- 바이러스 백신 비활성화(예: IOfficeAntivirus(IOAV))
- 클라우드 제공 보호를 사용 안 하게
- 보안 인텔리전스 업데이트 제거

### <a name="how-it-works"></a>작동 방식

변조 보호는 기본적으로 Microsoft Defender 바이러스 백신을 잠그고 다음과 같은 앱 및 방법을 통해 보안 설정이 변경되지 않도록 합니다.

- Windows 장치의 레지스트리 편집기에서 설정 구성
- PowerShell cmdlet을 통해 설정 변경
- 그룹 정책을 통해 보안 설정 편집 또는 제거

변조 방지는 보안 설정을 볼 수 있도록 방지하지 않습니다. 또한 변조 방지는 타사 바이러스 백신 앱이 Windows 보안 앱에 등록되는 방식에 영향을 주지 않습니다. 조직에서 Windows 10 Enterprise E5를 사용하는 경우 개별 사용자는 변조 방지 설정을 변경할 수 없습니다. 이러한 경우 변조 보호는 보안 팀에서 관리합니다.

### <a name="what-do-you-want-to-do"></a>무슨 작업을 하고 싶으십니까?

| 이 작업을 수행하기 위해... | 이 섹션을 참조하세요. |
|:---|:---|
| Microsoft Defender 보안 센터에서 변조 보호 켜기(또는 끄기) <p>테넌트 전체에서 변조 보호 관리 | [Microsoft Defender 보안 센터를 사용하여 조직의 변조 보호 관리](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| Intune을 사용하여 조직 전체 또는 일부에 대해 변조 보호 설정(또는 해제)을 끄기 <p>조직의 변조 방지 설정 미세 조정 | [Intune을 사용하여 조직의 변조 방지 관리](#manage-tamper-protection-for-your-organization-using-intune) |
| Configuration Manager를 통해 조직에 대한 변조 보호 설정(또는 해제)을 끄기 | [Configuration Manager 버전 2006에서 테넌트 첨부를 사용하여 조직의 변조 방지 관리](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| 개별 장치에 대한 변조 보호 켜기(또는 끄기) | [개별 장치에서 변조 보호 관리](#manage-tamper-protection-on-an-individual-device) |
| 장치에서의 변조 시도에 대한 세부 정보 보기 | [변조 시도에 대한 정보 보기](#view-information-about-tampering-attempts) |
| 보안 권장 사항 검토 | [보안 권장 사항 검토](#review-your-security-recommendations) |
| FAQ(질문과 대답) 목록 검토 | [FAQ 찾아보기](#view-information-about-tampering-attempts) |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a>Microsoft Defender 보안 센터를 사용하여 조직의 변조 보호 관리

Microsoft Defender 보안 센터( )를 사용하여 테넌트에 대해 변조 보호를 설정하거나 해제할 수 [https://securitycenter.windows.com](https://securitycenter.windows.com) 있습니다. 다음은 유의해야 할 몇 가지 사항입니다.

- 현재 Microsoft Defender 보안 센터에서 변조 보호를 관리하는 옵션은 기본적으로 새 배포에 대해 설정되어 있습니다. 기존 배포의 경우 옵트인(opt in)을 통해 변조 보호를 사용할 수 있습니다. 조만에 이 방법을 기본 방법으로 만들 계획입니다. (옵트인(opt in)하려면 Microsoft Defender 보안 센터에서 설정을 **선택합니다.**  >  **고급 기능**  >  **변조 방지**.) 

- Microsoft Defender 보안 센터를 사용하여 변조 방지를 관리할 때 Intune 또는 테넌트 연결 방법을 사용할 필요가 없습니다.

- Microsoft Defender 보안 센터에서 변조 보호를 관리하는 경우 이 설정은 테넌트 전체에 적용되고 Windows 10, Windows Server 2016 또는 Windows Server 2019를 실행하는 모든 장치에 영향을 미치게 됩니다. 변조 방지를 미세 조정하려면(예: 일부 장치에 대해 변조 보호를 설정하고 다른 장치에는 사용하지 않는 경우) 테넌트 연결과 함께 [Intune](#manage-tamper-protection-for-your-organization-using-intune) 또는 [Configuration Manager를 사용 합니다.](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)

- 하이브리드 환경이 있는 경우 Intune에 구성된 변조 보호 설정이 Microsoft Defender 보안 센터에 구성된 설정보다 우선합니다. 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a>Microsoft Defender 보안 센터에서 변조 보호를 관리하기 위한 요구 사항

- 전역 관리자, [](/microsoft-365/security/defender-endpoint/assign-portal-access)보안 관리자 또는 보안 작업과 같은 적절한 권한이 있어야 합니다.

- Windows 장치에서 다음 Windows 버전 중 하나를 실행해야 합니다.
   - Windows 10
   - [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
   - Windows Server, 버전 [1803](/windows/release-health/status-windows-10-1803) 이상
   - [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
   - 릴리스에 대한 자세한 내용은 [Windows 10 릴리스 정보를 참조하세요.](/windows/release-health/release-information)

- 디바이스를 [끝점용 Microsoft Defender에 온보딩해야 합니다.](/microsoft-365/security/defender-endpoint/onboarding)

- 장치에서 맬웨어 방지 플랫폼 버전 4.18.2010.7 이상 및 맬웨어 방지 엔진 버전 1.1.17600.5 이상을 사용하고 있어야 합니다. ([Microsoft Defender 바이러스 백신 업데이트를 관리하고 기준을](manage-updates-baselines-microsoft-defender-antivirus.md)적용합니다.)

- [클라우드 제공 보호를](enable-cloud-protection-microsoft-defender-antivirus.md) 켜야 합니다.

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a>Microsoft Defender 보안 센터에서 변조 보호 켜기(또는 끄기) 

![Microsoft Defender 보안 센터에서 변조 보호 켜기](images/mde-turn-tamperprotect-on.png)

1. Microsoft Defender 보안 센터()로 이동하여 [https://securitycenter.windows.com](https://securitycenter.windows.com) 로그인합니다.

2. 설정을 **선택합니다.**

3. 일반 **고급**  >  **기능으로 이동한** 다음 변조 방지를 켜야 합니다.

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a>Intune을 사용하여 조직의 변조 방지 관리

조직의 보안 팀에 포함된 구독에 [Intune이](/intune/fundamentals/what-is-intune)포함되어 있는 경우 [Microsoft Endpoint Manager](https://endpoint.microsoft.com) 관리 센터 포털에서 조직에 대한 변조 보호를 설정하거나 해제할 수 있습니다. 변조 방지 설정을 미세 조정하려면 Intune을 사용합니다. 예를 들어 일부 장치에서 변조 방지를 사용하도록 설정하려는 경우 Intune을 사용 합니다.

### <a name="requirements-for-managing-tamper-protection-in-intune"></a>Intune에서 변조 방지를 관리하기 위한 요구 사항

- 전역 관리자, [](/microsoft-365/security/defender-endpoint/assign-portal-access)보안 관리자 또는 보안 작업과 같은 적절한 권한이 있어야 합니다.

- 조직에서 [Intune을 사용하여 장치를 관리합니다.](/intune/fundamentals/what-is-device-management) ([Intune 라이선스가](/intune/fundamentals/licenses) 필요합니다. Intune은 Microsoft 365 E5에 포함되어 있습니다.)

- Windows 장치에서 Windows 10 OS [1709,](/windows/release-health/status-windows-10-1709) [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) 이상을 실행해야 합니다. 릴리스에 대한 자세한 내용은 [Windows 10 릴리스 정보를 참조하세요.](/windows/release-health/release-information)

- 버전 1.287.60.0 이상으로 업데이트된 보안 인텔리전스와 함께 Windows 보안을 사용하고 있어야 합니다. [](https://www.microsoft.com/wdsi/definitions)

- 장치는 맬웨어 방지 플랫폼 버전 4.18.1906.3 이상 및 맬웨어 방지 엔진 버전 1.1.15500.X 이상을 사용하고 있어야 합니다. ([Microsoft Defender 바이러스 백신 업데이트를 관리하고 기준을](manage-updates-baselines-microsoft-defender-antivirus.md)적용합니다.)

### <a name="turn-tamper-protection-on-or-off-in-intune"></a>Intune에서 변조 보호 켜기(또는 끄기)

![Intune을 통해 변조 보호 켜기](images/turnontamperprotect-MEM.png)

1. [Microsoft Endpoint Manager](https://endpoint.microsoft.com) 관리 센터로 이동하여 직장 또는 학교 계정으로 로그인합니다.

2. 장치 **구성**  >  **프로필을 선택합니다.**

3. 다음 설정을 포함하는 프로필을 만들 수 있습니다.
    - **플랫폼: Windows 10 이상**
    - **프로필 유형: 끝점 보호**
    - **범주: Microsoft Defender 보안 센터**
    - **변조 방지: 사용**

4. 프로필을 하나 이상의 그룹에 할당합니다.

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a>Windows OS 1709, 1803 또는 1809를 사용하나요?

Windows 10 OS [1709, 1803](/windows/release-health/status-windows-10-1709)또는 [1809를](/windows/release-health/status-windows-10-1809-and-windows-server-2019)사용하는 경우  Windows 보안 앱에서 변조 보호가 표시되지 않습니다. [](/windows/release-health/status-windows-10-1803) 대신 PowerShell을 사용하여 변조 방지를 사용할지 여부를 결정할 수 있습니다.

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a>PowerShell을 사용하여 변조 방지가 켜져 있는지 확인

1. 앱 Windows PowerShell 를 하세요.

2. [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet을 사용 합니다.

3. 결과 목록에서 를 `IsTamperProtected` 검색합니다. true 값은  변조 방지를 사용할 수 있는 것입니다.

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>Configuration Manager 버전 2006을 사용하여 조직의 변조 보호 관리

[Configuration Manager 버전 2006을](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)사용하는 경우 테넌트 연결 이라는 방법을 사용하여 Windows 10, Windows Server 2016 및 Windows Server 2019에서 변조 보호 설정을 관리할 수 *있습니다.* 테넌트 연결 기능을 사용하면 Microsoft Endpoint Manager 관리 센터에 On-premises-only Configuration Manager 장치를 동기화한 다음 끝점 보안 구성 정책을 디바이스의 모든 & 있습니다.

![Endpoint Manager의 Windows 보안 환경](images/win-security- exp-policy-endpt-security.png)

> [!NOTE]
> 이 절차를 사용하여 Windows 10 및 Windows Server 2019를 실행하는 장치로 변조 보호를 확장할 수 있습니다. 이 절차에 언급된 리소스의 선행 절차 및 기타 정보를 검토해야 합니다.

1. 테넌트 연결 설정 이에 대한 도움말은 Microsoft Endpoint Manager 테넌트 연결: 장치 동기화 및 장치 [작업을 참조하세요.](/mem/configmgr/tenant-attach/device-sync-actions)

2. Microsoft [Endpoint Manager 관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431) **끝점** 보안 바이러스 백신으로 이동한 다음  >  + 정책 **만들기 를 선택하세요.**<br/> 
   - 플랫폼 **목록에서** **Windows 10 및 Windows Server(ConfigMgr)를 선택합니다.**  
   - 프로필 **목록에서** Windows 보안 환경(미리 **보기)을 선택합니다.** <br/>

3. 디바이스 컬렉션에 정책을 배포합니다.

### <a name="need-help-with-this-method"></a>이 메서드에 대한 도움이 필요하세요? 

다음 리소스를 참조하십시오.

- [Microsoft Intune의 Windows 보안 환경 프로필 설정](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [기술 커뮤니티 블로그: Configuration Manager 테넌트 연결 클라이언트에 대한 변조 방지 발표](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>개별 장치에서 변조 보호 관리

> [!NOTE]
> 변조 방지 블록은 레지스트리를 통해 Microsoft Defender 바이러스 백신 설정을 수정하려고 시도합니다.
>
> 변조 방지가 이러한 설정을 수정하는 타사 보안 제품 또는 엔터프라이즈 설치 스크립트를 방해하지 않도록 보장하려면 **Windows 보안으로** 이동하여 보안 인텔리전스를 버전 1.287.60.0 이상으로 업데이트합니다.  (보안 [인텔리전스 업데이트 참조)](https://www.microsoft.com/wdsi/definitions)
>
> 이 업데이트를 만든 후 변조 보호는 레지스트리 설정을 계속 보호하며 로그는 오류를 반환하지 않고 수정을 시도합니다.

가정용 사용자 또는 보안 팀에서 관리하는 설정이 없는 경우 Windows 보안 앱을 사용하여 변조 방지를 관리할 수 있습니다. 변조 방지와 같은 보안 설정을 변경하려면 장치에 적절한 관리자 권한이 있어야 합니다.

Windows 보안 앱에 표시하는 내용은 다음과 같습니다.

![Windows 10 Home에서 변조 보호 설정](images/tamperprotectionturnedon.png)

1. 시작 **을** 선택하고 보안 입력을 *시작합니다.* 검색 결과에서 **Windows 보안 을 선택합니다.**

2. 바이러스 **& 위협 방지 바이러스**& 설정을  >  **선택합니다.**

3. 변조 **보호를 설정** 또는 **해제로** **설정**



## <a name="view-information-about-tampering-attempts"></a>변조 시도에 대한 정보 보기

변조 시도는 일반적으로 더 큰 사이버 공격을 나타냅니다. 악의적인 악의적인 악의적인 는 보안 설정을 변하지 않고 유지하려는 시도입니다. 조직의 보안 팀의 일부인 경우 이러한 시도에 대한 정보를 확인한 다음 적절한 조치를 취하여 위협을 완화할 수 있습니다.

변조 시도가 감지되면 [Microsoft Defender](/microsoft-365/security/defender-endpoint/portal-overview) 보안 센터()에서 경고가 [https://securitycenter.windows.com](https://securitycenter.windows.com) 표시됩니다.

![Microsoft Defender 보안 센터](images/tamperattemptalert.png)

[끝점용](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) Microsoft Defender의 엔드포인트 감지 및 응답 및 고급 헌팅 기능을 사용하여 보안 운영 팀은 이러한 시도를 조사하고 해결할 수 있습니다. [](/microsoft-365/security/defender-endpoint/advanced-hunting-overview)

## <a name="review-your-security-recommendations"></a>보안 권장 사항 검토

변조 방지는 위협 및 [& 관리 기능과 통합됩니다.](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [보안 권장 사항에는](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 변조 방지가 설정되어 있는지 확인이 포함됩니다. 예를 들어 다음 이미지와 같이 변조에서 검색할 수 있습니다. 

![변조 방지 결과 보안 권장 사항](/images/securityrecs-tamperprotect.jpg)

결과에서 변조 보호  켜기 를 선택하여 자세한 내용을 알아보고 켜면 됩니다.

![변조 방지 켜기](images/tamperprotectsecurityrecos.png)

위협 및 취약성 & 자세한 내용은 Microsoft Defender 보안 센터의 위협 & 취약성 관리를 [참조합니다.](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a>변조 방지를 구성하는 Windows OS 버전은 어느 것인가요?

Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)이상과 [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).

테넌트 연결과 함께 Configuration Manager 버전 2006을 사용하는 경우 변조 방지를 Windows Server 2019로 확장할 수 있습니다. 테넌트 연결: 관리 센터에서 끝점 보안 바이러스 백신 정책 만들기 및 배포(미리 [보기)를 참조하세요.](/mem/configmgr/tenant-attach/deploy-antivirus-policy)

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a>변조 방지는 타사 바이러스 백신 등록에 영향을 미치나요?

아니요. 타사 바이러스 백신 제품은 Windows 보안 응용 프로그램에 계속 등록됩니다.

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>장치에서 Microsoft Defender 바이러스 백신이 활성화되지 않은 경우 어떻게 하나요?

끝점용 Microsoft Defender에 온보딩된 장치에는 Microsoft Defender 바이러스 백신이 수동 모드로 실행됩니다. 변조 보호는 서비스 및 해당 기능을 계속 보호합니다. 

### <a name="how-can-i-turn-tamper-protection-onoff"></a>변조 보호를 켜고 끄는 방법

가정용 사용자인 경우 개별 장치에서 변조 보호 [관리를 참조하세요.](#manage-tamper-protection-on-an-individual-device)

끝점용 Microsoft [Defender를](/microsoft-365/security/defender-endpoint)사용하는 조직인 경우 다른 끝점 보호 기능을 관리하는 방법과 유사한 Intune에서 변조 보호를 관리할 수 있습니다. 이 문서의 다음 섹션을 참조하세요. 

- [Intune을 사용하여 변조 방지 관리](#manage-tamper-protection-for-your-organization-using-intune)
- [Configuration Manager, 버전 2006을 사용하여 변조 보호 관리](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Microsoft Defender](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 보안 센터를 사용하여 변조 보호 관리(현재 미리 보기)

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a>Intune에서 변조 보호를 구성하면 그룹 정책을 통해 Microsoft Defender 바이러스 백신을 관리하는 방법에 어떤 영향을 미치나요?

일반 그룹 정책은 변조 방지에 적용되지 않습니다. 변조 방지가 설정될 때 Microsoft Defender 바이러스 백신 설정에 대한 변경 내용은 무시됩니다. 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a>끝점용 Microsoft Defender의 경우 전체 조직을 대상으로 하는 Intune에서 변조 보호를 구성하고 있습니까?

Intune 또는 Microsoft Endpoint Manager에서 변조 보호 구성은 전체 조직 및 특정 장치 및 사용자 그룹을 대상으로 할 수 있습니다.

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager에서 변조 보호를 구성할 수 있나요?

테넌트 첨부를 사용하는 경우 Microsoft Endpoint Configuration Manager를 사용할 수 있습니다. 다음 리소스를 참조하십시오.
- [Configuration Manager 버전 2006을 사용하여 조직의 변조 보호 관리](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [기술 커뮤니티 블로그: Configuration Manager 테넌트 연결 클라이언트에 대한 변조 방지 발표](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Windows E3 등록이 있습니다. Intune에서 변조 보호 구성을 사용할 수 있나요?

현재 Intune에서 변조 보호를 구성하는 것은 [끝점용 Microsoft Defender가 있는 고객만 사용할 수 있습니다.](/microsoft-365/security/defender-endpoint)

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>장치에서 변조 방지를 사용하도록 설정한 경우 Intune, Microsoft Endpoint Configuration Manager 및 Windows Management Instrumentation에서 끝점용 Microsoft Defender 설정을 변경하려고 할 경우 어떻게 하나요?

변조 방지로 보호되는 기능은 변경할 수 없습니다. 이러한 변경 요청은 무시됩니다.

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>엔터프라이즈 고객입니다. 로컬 관리자가 장치에서 변조 보호를 변경할 수 있나요?

아니요. 로컬 관리자는 변조 방지 설정을 변경하거나 수정할 수 없습니다.

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>장치가 끝점용 Microsoft Defender를 사용하여 온보딩된 후 오프보드 상태로 넘어가면 어떻게 하나요?

장치가 끝점용 Microsoft Defender에서 오프보딩된 경우 변조 방지가 켜져 있습니다. 이는 관리되지 않는 장치의 기본 상태입니다. 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a>Microsoft Defender 보안 센터에서 변조 보호 상태 변경에 대한 경고가 있나요?

예. 경고는 경고 [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **에 표시됩니다.**

보안 운영 팀은 다음 예와 같은 헌팅 쿼리를 사용할 수도 있습니다.

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

[변조 시도에 대한 정보를 을 를 으로 본다.](#view-information-about-tampering-attempts)

## <a name="see-also"></a>참고 항목

[Microsoft Intune용 Endpoint Protection을 통해 Windows PC 보안 지원](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[끝점용 Microsoft Defender 개요 보기](/microsoft-365/security/defender-endpoint)

[함께 사용: Microsoft Defender 바이러스 백신 및 끝점용 Microsoft Defender](why-use-microsoft-defender-antivirus.md)