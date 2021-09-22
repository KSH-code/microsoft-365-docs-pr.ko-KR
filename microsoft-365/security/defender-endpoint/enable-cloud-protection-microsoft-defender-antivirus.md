---
title: 클라우드에서 클라우드 보호 Microsoft Defender 바이러스 백신
description: 빠르고 고급 보호 기능을 활용하기 위해 클라우드 보호를 켜야 합니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, 클라우드, 한시적 차단
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 08/31/2021
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 4018adc6fcf19e072f8c82292d488a6bbfa344d4
ms.sourcegitcommit: b295c60d5aa69781a20c59b9cdf2ed91c62b21af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2021
ms.locfileid: "59480799"
---
# <a name="turn-on-cloud-protection-in-microsoft-defender-antivirus"></a>클라우드에서 클라우드 보호 Microsoft Defender 바이러스 백신

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 바이러스 백신

[Microsoft Defender 바이러스 백신](cloud-protection-microsoft-defender-antivirus.md) 클라우드 보호는 정확하고 실시간, 지능적인 보호를 제공합니다. 클라우드 보호는 기본적으로 사용하도록 설정되어 있습니다. 그러나 조직의 요구에 맞게 클라우드 보호를 구성할 수 있습니다.

## <a name="methods-to-configure-cloud-protection"></a>클라우드 보호를 구성하는 방법

다음 방법 Microsoft Defender 바이러스 백신 사용하여 클라우드 보호를 설정하거나 해제할 수 있습니다.

- Microsoft Endpoint Manager 및 Configuration Manager를 Microsoft Intune 포함
- 그룹 정책
- PowerShell cmdlet

또한 앱 앱을 사용하여 개별 끝점에서 클라우드 보호를 켜거나 Windows 보안 있습니다. 

끝점이 클라우드 보호 서비스에 연결할 수 있도록 하는 특정 네트워크 연결 요구 사항에 대한 자세한 내용은 네트워크 연결 구성 및 유효성 [검사를 참조하세요.](configure-network-connections-microsoft-defender-antivirus.md)

> [!NOTE]
> 이 Windows 10 이 항목에 설명된 기본  및  고급 보고 옵션 간에는 차이가 없습니다. 이는 레거시 구분으로, 두 설정을 선택하면 동일한 수준의 클라우드 보호가 됩니다. 공유되는 정보의 유형이나 양에는 차이가 없습니다. 수집하는 정보에 대한 자세한 내용은 Microsoft 개인 정보 취급 [방침을 참조하세요.](https://go.microsoft.com/fwlink/?linkid=521839)

## <a name="use-intune-to-turn-on-cloud-protection"></a>Intune을 사용하여 클라우드 보호 켜기

1. Microsoft Endpoint Manager 관리 센터()로 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 이동하여 로그인합니다.

2. 홈 **창에서** 장치 구성 및 > **선택합니다.**

3. 구성할 **장치 제한 프로필** 유형을 선택합니다. 새 장치 제한 프로필  유형을 만들어야 하는 경우 에서 장치 제한 설정 [구성을 Microsoft Intune.](/intune/device-restrictions-configure)

4. 속성 **구성** \> **설정: 편집 Microsoft Defender 바이러스 백신.** \> 

5. 클라우드 제공 **보호 스위치에서** 사용 을 **선택합니다.**

6. 샘플 **제출 전에** 사용자에게 확인 드롭다운에서 자동으로 모든 데이터 **보내기 를 선택합니다.**

설정을 만들고 구성하는 방법을 포함하여 Intune 장치 프로필에 대한 자세한 내용은 [What are Microsoft Intune device profiles?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-protection"></a>클라우드 Microsoft Endpoint Manager 사용하여 클라우드 보호 켜기

1. Microsoft Endpoint Manager 관리 센터()로 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 이동하여 로그인합니다.

2. 끝점 **보안 바이러스 백신** \> **을 선택 합니다.**

3. 바이러스 백신 프로필을 선택합니다. (아직 프로필이 없는 경우 또는 새 프로필을 만들하려는 경우 에서 장치 제한 설정 [구성을 Microsoft Intune.](/intune/device-restrictions-configure)

4. 속성을 **선택합니다.** 그런 다음 구성 설정 **옆에 있는** 편집 을 **선택합니다.**

5. 클라우드 **보호를 확장하고**  클라우드 제공 보호 수준 목록에서 다음 중 하나를 선택합니다.
   - **높음:** 강력한 수준의 검색을 적용합니다.
   - **High plus:** **높음** 수준을 사용하며 추가 보호 조치를 적용합니다(클라이언트 성능에 영향을 줄 수 있습니다).
   - **허용 오차** 없음: 알 수 없는 모든 실행을 차단합니다.

6. 검토 **+ 저장을 선택한** 다음 저장을 **선택합니다.**

맬웨어 방지 정책을 구성하는 방법에 Microsoft Endpoint Configuration Manager 맬웨어 방지 정책을 만들고 배포하는 [방법: 클라우드 보호 서비스를 참조하세요.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

## <a name="use-group-policy-to-turn-on-cloud-protection"></a>그룹 정책을 사용하여 클라우드 보호 켜기

1. 그룹 정책 관리 장치에서 그룹 정책 관리 콘솔을 [열고](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 관리 **템플릿 을 선택합니다.**

4. MAPS에서 구성 **Windows**  >  **트리를 Microsoft Defender 바이러스 백신 > 확장합니다.**

5. **Microsoft MAPS에 가입을 두 번 클릭합니다.** 옵션이 켜져 있으며 기본 **MAPS** 또는 고급 **지도로 설정되어 있는지 확인** **확인** 을 선택합니다.

6. 추가 분석이 필요한 경우 파일 샘플 **보내기 를 두 번 클릭합니다.** 첫 번째 옵션이 **사용으로** 설정되어 있으며 다른 옵션이 다음 중 하나로 설정되어 있는지 확인합니다.

   - **안전한 샘플 보내기(1)**
   - **모든 샘플 보내기(3)**

   >[!NOTE]
   > 안전한 **샘플 보내기(1)** 옵션은 대부분의 샘플이 자동으로 전송됩니다. 개인 정보를 포함할 수 있는 파일은 계속 묻는 메시지를 표시하며 추가 확인이 요구됩니다.
   > 옵션을 항상  프롬프트(0)로 설정하면 장치의 보호 상태가 낮아지게 됩니다. 보내지 **않습니다(2)로** 설정하면 [](configure-block-at-first-sight-microsoft-defender-antivirus.md) 끝점용 Microsoft Defender의 즉시 차단 기능이 작동하지 않습니다.

7. **확인** 을 선택합니다.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-protection"></a>PowerShell cmdlet을 사용하여 클라우드 보호 켜기

다음 cmdlet은 클라우드 보호를 켜면 됩니다.

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 [및 Defender cmdlet](/powershell/module/defender/)구성 및 실행을 참조하세요. [정책 CSP - Defender에는](/windows/client-management/mdm/policy-csp-defender) [-SubmitSamplesConsent에](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)대한 자세한 정보도 있습니다.

> [!IMPORTANT]
> **-SubmitSamplesConsent를** (기본값, 권장 설정) 또는 로 설정할 `SendSafeSamples` `NeverSend` 수 `AlwaysPrompt` 있습니다. 이 `SendSafeSamples` 설정은 대부분의 샘플이 자동으로 전송됩니다. 개인 정보가 포함될 가능성이 높은 파일은 계속하라는 메시지가 표시되고 확인이 요구됩니다.
> 및 `NeverSend` `AlwaysPrompt` 설정은 장치의 보호 수준을 낮출 수 있습니다. 또한 이 `NeverSend` 설정은 [](configure-block-at-first-sight-microsoft-defender-antivirus.md) 끝점용 Microsoft Defender의 즉시 차단 기능이 작동하지 않습니다.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-protection"></a>WMI(Windows 관리 지침)를 사용하여 클라우드 보호 켜기

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/defender/set-msft-mppreference) 클래스의 Set 메서드를 사용합니다.

```WMI
MAPSReporting
SubmitSamplesConsent
```

허용되는 매개 변수에 대한 자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-protection-on-individual-clients-with-the-windows-security-app"></a>앱 앱으로 개별 클라이언트에 Windows 보안 켜기

> [!NOTE]
> Microsoft **MAPS** 보고를 위한 로컬 설정 다시 설정 구성 그룹 정책 설정을  사용 안 하도록 설정한 경우 Windows 설정 클라우드 기반 보호 설정은 회색으로 표시되어 사용할 수 없습니다. 설정이 Windows 설정에서 업데이트되기 전에 먼저 그룹 정책 개체를 통해 수행한 변경을 개별 엔드포인트에 배포해야 합니다.

1. 작업 Windows 보안 방패 아이콘을 선택하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.

2. 바이러스 & **위협** 방지 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택한 다음 바이러스 & **보호 설정 레이블을** 선택합니다.

    :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="바이러스 및 위협 방지 & 스크린샷":::

3. 클라우드 **기반** 보호 및  자동 샘플 제출이 켜기 로 전환된지 **확인**

   > [!NOTE]
   > 그룹 정책을 사용하여 자동 샘플 제출을 구성한 경우 설정은 회색으로 회색으로 설정되고 사용할 수 없습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft 클라우드 보호를 사용하여 Microsoft Defender 바이러스 백신](cloud-protection-microsoft-defender-antivirus.md)

- [맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

- [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리](use-powershell-cmdlets-microsoft-defender-antivirus.md)
