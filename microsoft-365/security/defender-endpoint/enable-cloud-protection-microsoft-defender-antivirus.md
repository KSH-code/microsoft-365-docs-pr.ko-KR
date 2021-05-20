---
title: Microsoft Defender 바이러스 백신 클라우드 로 배달된 보호 기능 켜기
description: 빠르고 고급 보호 기능을 통해 클라우드로 제공되는 보호 기능을 켭니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, 클라우드, 첫눈에 차단
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572060"
---
# <a name="turn-on-cloud-delivered-protection"></a>클라우드 제공 보호 켜기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Microsoft Defender 바이러스 백신 클라우드 서비스는 네트워크 및 끝점에 업데이트된 보호를 제공하는 메커니즘입니다. 클라우드 서비스라고 하지만 클라우드에 저장된 파일을 보호하는 것은 아닙니다. 오히려 분산 리소스와 머신 러닝을 사용하여 기존 보안 인텔리전스 업데이트보다 훨씬 빠른 속도로 엔드포인트에 대한 보호를 제공합니다.

Microsoft Defender 바이러스 백신 여러 탐지 및 예방 기술을 사용하여 정확하고 실시간으로 지능형 보호를 제공합니다. [엔드포인트 차세대 보호를 위한 Microsoft Defender의 핵심에 있는 첨단 기술을 알아보십시오.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

다음과 같은 여러 가지 방법으로 클라우드로 제공되는 보호 기능을 켜거나 끌 Microsoft Defender 바이러스 백신 수 있습니다.

- Microsoft Intune
- Microsoft Endpoint Manager 
- 그룹 정책
- 파워쉘 cmdlets.

 또한 Windows 보안 앱을 통해 개별 클라이언트에서 켜거나 끌 수도 있습니다.

클라우드로 제공되는 보호 에 대한 개요는 [microsoft 클라우드에서 제공하는 보호 사용을](cloud-protection-microsoft-defender-antivirus.md) 참조Microsoft Defender 바이러스 백신

엔드포인트가 클라우드 제공 보호 서비스에 연결할 수 있도록 특정 네트워크 연결 요구 사항에 대한 자세한 내용은 [네트워크 연결 구성 및 유효성을 검사합니다.](configure-network-connections-microsoft-defender-antivirus.md)

> [!NOTE]
> Windows 10 이 항목에 설명된 **기본** 및 **고급** 보고 옵션 간에는 차이가 없습니다. 이는 레거시 구분이며 두 설정을 선택하면 동일한 수준의 클라우드 전달 보호가 발생합니다. 공유되는 정보의 유형이나 양에는 차이가 없습니다. 당사가 수집하는 내용에 대한 자세한 내용은 [Microsoft 개인 정보 보호 정책을](https://go.microsoft.com/fwlink/?linkid=521839)참조하십시오.

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Intune을 사용하여 클라우드 로 배달된 보호 기능을 켭니다.

1. Microsoft Endpoint Manager 관리 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 센터()로 이동하여 로그인합니다.

2. **홈** 창에서 **프로파일을 > 장치 구성을 선택합니다.**

3. 구성할 **장치 제한** 프로필 유형을 선택합니다. 새 **장치 제한** 프로필 유형을 만들어야 하는 경우 Microsoft Intune 장치 제한 [설정 구성을](/intune/device-restrictions-configure)참조하십시오.

4. **속성**  >  **구성 설정 선택:**  >  Microsoft Defender 바이러스 백신 편집할 수 **있습니다.**

5. **클라우드제공 보호** 스위치에서 **사용 가능을 선택합니다.**

6. 샘플 제출 드롭다운 **전에 프롬프트 사용자에서** **모든 데이터 보내기를 자동으로 선택합니다.**

설정을 만들고 구성하는 방법을 포함하여 Intune 장치 프로필에 대한 자세한 내용은 [장치 프로필에 Microsoft Intune 무엇입니까?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Microsoft Endpoint Manager 사용하여 클라우드 로 배달된 보호 기능을 켭니다.

1. Microsoft Endpoint Manager 관리 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 센터()로 이동하여 로그인합니다.

2. **엔드포인트 보안**  >  **바이러스 백신을 선택합니다.**

3. 바이러스 백신 프로파일을 선택합니다. 아직 프로필이 없거나 새 프로필을 만들려는 경우 [Microsoft Intune 장치 제한 설정 구성을](/intune/device-restrictions-configure)참조하십시오.

4. **속성을 선택합니다.** 그런 다음 **구성 설정** 옆에 **편집을 선택합니다.**

5. **클라우드 보호를** 확장한 다음 **클라우드에서 제공하는 보호 수준** 목록에서 다음 중 하나를 선택합니다.
   - **높음**: 강력한 수준의 감지를 적용합니다.
   - **높음 :** **높은** 수준을 사용하고 추가 보호 조치를 적용합니다(고객 성능에 영향을 미칠 수 있음).
   - **무관용**: 알 수 없는 모든 실행판을 차단합니다.

6. **검토 + 저장을** 선택한 다음 **저장을 선택합니다.**

Microsoft Endpoint Configuration Manager 구성에 대한 자세한 내용은 [맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스 입니다.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>그룹 정책을 사용하여 클라우드 로 배달된 보호 기능을 켭니다.

1. 그룹 정책 관리 장치에서 [그룹 정책 관리 콘솔을](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 **편집을 선택합니다.**

2. 그룹 **정책 관리 편집기에서** **컴퓨터 구성으로** 이동합니다.

3. **관리 템플릿을 선택합니다.**

4. 트리를 **맵> Microsoft Defender 바이러스 백신 > Windows 구성 요소로** 확장

5. 두 번 클릭 **마이크로 소프트 맵가입**. 옵션이 켜져 있는지 확인하고 기본 MAPS 또는 고급 **지도로** **설정합니다.** **확인** 을 선택합니다.

6. **추가 분석이 필요한 경우 파일 샘플 보내기를** 두 번 클릭합니다. 첫 번째 옵션이 **활성화로** 설정되어 있고 다른 옵션이 중 하나에 설정되어 있는지 확인합니다.

    1. **안전한 샘플 보내기** (1)
    2. **모든 샘플 보내기** (3)

        >[!NOTE]
        > **안전한 샘플 보내기(1)** 옵션은 대부분의 샘플이 자동으로 전송된다는 것을 의미합니다. 개인 정보가 포함될 가능성이 있는 파일은 여전히 프롬프트되고 추가 확인이 필요합니다.
        > **항상 프롬프트(0)로** 옵션을 설정하면 장치의 보호 상태가 낮아집니다. **절대 보내지 마십시오** (2)로 설정하면 엔드포인트에 대한 Microsoft Defender의 [첫눈에 블록](configure-block-at-first-sight-microsoft-defender-antivirus.md) 기능이 작동하지 않습니다.

7. **확인** 을 선택합니다.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>PowerShell cmdlet을 사용하여 클라우드 로 전달된 보호 기능을 켭니다.

다음 cmdlets는 클라우드 로 배달된 보호를 켤 수 있습니다.

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Microsoft Defender 바이러스 백신 PowerShell을 사용하는 방법에 대한 자세한 내용은 [powerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 및 수비수 cmdlet을 구성하고](use-powershell-cmdlets-microsoft-defender-antivirus.md) [실행하십시오.](/powershell/module/defender/) [정책 CSP - Defender는](/windows/client-management/mdm/policy-csp-defender) [-submitSamples동의에](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)대한 자세한 정보도 있습니다.

>[!NOTE]
> **-SubmitSamples동의(기본** 설정) 또는 .를 설정할 수도 `SendSafeSamples` `NeverSend` `AlwaysPrompt` 있습니다. `SendSafeSamples`설정은 대부분의 샘플이 자동으로 전송된다는 것을 의미합니다. 개인 정보가 포함될 가능성이 있는 파일은 여전히 프롬프트되고 추가 확인이 필요합니다.

>[!WARNING]
> 설정 **-제출견본에동의하거나** `NeverSend` 장치의 보호 수준을 낮출 `AlwaysPrompt` 것입니다. 또한 `NeverSend` 엔드포인트용 Microsoft Defender의 [첫눈에 블록](configure-block-at-first-sight-microsoft-defender-antivirus.md) 기능이 작동하지 않는다는 의미로 설정합니다.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>wMI(Windows 관리 지침)를 사용하여 클라우드 로 배달된 보호 기능을 켭니다.

다음 속성에 [ **MSFT_MpPreference** 클래스의 **설정** 방법을](/previous-versions/windows/desktop/defender/set-msft-mppreference) 사용합니다.

```WMI
MAPSReporting
SubmitSamplesConsent
```

허용된 매개 변수에 대한 자세한 내용은 [Windows Defender WMIv2 API를 참조하십시오.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Windows 보안 앱을 통해 개별 클라이언트에 클라우드로 제공되는 보호 기능 설정

> [!NOTE]
> Microsoft MAPS 그룹 정책 **설정을 보고하기 위한 로컬 설정 구성이** **비활성화된** 것으로 설정된 경우 Windows 설정 **클라우드 기반 보호** 설정이 회색으로 지정되고 사용할 수 없습니다. 설정이 Windows 설정에서 업데이트되기 전에 먼저 그룹 정책 개체를 통해 수행한 변경을 개별 엔드포인트에 배포해야 합니다.

1. 작업 표시줄에서 쉴드 아이콘을 선택하거나 Defender의 시작 메뉴를 검색하여 Windows 보안 앱을 **엽니다.**

2. 바이러스 **& 위협 보호** 타일(또는 왼쪽 메뉴 표시줄의 쉴드 아이콘)을 선택한 다음 **바이러스 & 위협 보호 설정** 레이블을 선택합니다.

    ![Windows 보안 앱의 바이러스 및 위협 방지 설정 레이블 스크린샷](images/defender/wdav-protection-settings-wdsc.png)

3. 클라우드 **기반 보호** 및 **자동 샘플 제출이** On으로 전환되어 있는지 **확인합니다.**

> [!NOTE]
> 자동 샘플 제출이 그룹 정책으로 구성된 경우 설정이 회색으로 지정되고 사용할 수 없습니다.

## <a name="related-articles"></a>관련 문서

- [클라우드 차단 제한 시간 구성](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [첫눈에 블록 구성](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Microsoft Intune Endpoint Protection Windows PC를 보호하는 데 도움이 됩니다.](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [수비수 cmdlets](/powershell/module/defender/)
- [microsoft 클라우드 제공 보호 Microsoft Defender 바이러스 백신 사용](cloud-protection-microsoft-defender-antivirus.md)
- [맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
