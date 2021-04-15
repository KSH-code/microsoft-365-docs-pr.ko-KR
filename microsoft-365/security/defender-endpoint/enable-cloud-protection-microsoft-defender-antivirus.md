---
title: Microsoft Defender 바이러스 백신에서 클라우드 제공 보호 켜기
description: 클라우드 제공 보호 기능을 켜고 빠르고 고급 보호 기능을 활용합니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, 클라우드, 중지 시 차단
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9f949a4cb54ca5dd64a2648bb05a5cb9ad50e44d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764966"
---
# <a name="turn-on-cloud-delivered-protection"></a>클라우드 제공 보호 켜기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

> [!NOTE]
> Microsoft Defender 바이러스 백신 클라우드 서비스는 네트워크 및 끝점에 업데이트된 보호를 제공하는 메커니즘입니다. 클라우드 서비스라고 하지만 단순히 클라우드에 저장된 파일을 보호하는 것은 아니며, 대신 분산 리소스 및 기계 학습을 사용하여 기존 보안 인텔리전스 업데이트보다 훨씬 빠른 속도로 끝점에 보호 기능을 제공합니다.

Microsoft Defender 바이러스 백신은 여러 감지 및 방지 기술을 사용하여 정확하고 실시간, 지능적인 보호를 제공합니다. 엔드포인트 차세대 보호를 위한 Microsoft Defender의 핵심에 있는 고급 [기술에 대해 알아가세요.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)
![Microsoft Defender AV 엔진 목록](images/microsoft-defender-atp-next-generation-protection-engines.png)  

Microsoft Defender 바이러스 백신 클라우드 제공 보호를 여러 가지 방법으로 설정하거나 해제할 수 있습니다.

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- 그룹 정책
- PowerShell cmdlet.

 Windows 보안 앱을 사용하여 개별 클라이언트에서 켜거나 끄는 방법도 있습니다.

Microsoft Defender 바이러스 백신 클라우드 [제공](cloud-protection-microsoft-defender-antivirus.md) 보호 개요는 Microsoft 클라우드 제공 보호 사용을 참조하세요.

끝점이 클라우드 제공 보호 서비스에 연결할 수 있도록 하는 특정 네트워크 연결 요구 사항에 대한 자세한 내용은 네트워크 연결 구성 및 유효성 [검사를 참조하세요.](configure-network-connections-microsoft-defender-antivirus.md)

> [!NOTE]
> Windows 10에서는 이 항목에 설명된  기본 및 고급 보고 옵션 간에 차이가 없습니다.  이는 레거시 구분으로, 두 설정을 선택하면 동일한 수준의 클라우드 제공 보호가 됩니다. 공유되는 정보의 유형이나 양에는 차이가 없습니다. 수집하는 정보에 대한 자세한 내용은 Microsoft 개인 정보 취급 [방침을 참조하세요.](https://go.microsoft.com/fwlink/?linkid=521839)

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Intune을 사용하여 클라우드 제공 보호 켜기

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.
2. 홈 **창에서** 장치 구성 및 > **선택합니다.**
3. 구성할 **장치 제한 프로필** 유형을 선택합니다. 새 장치 제한 프로필  유형을 만들어야 하는 경우 Microsoft Intune에서 장치 제한 설정 [구성을 참조하세요.](/intune/device-restrictions-configure)
4. 속성 **구성**  >  **설정 선택:** Microsoft  >  **Defender 바이러스 백신 편집**.
5. 클라우드 제공 **보호 스위치에서** 사용 을 **선택합니다.**
6. 샘플 **제출 전에** 사용자에게 확인 드롭다운에서 자동으로 모든 데이터 **보내기 를 선택합니다.**

설정을 만들고 구성하는 방법을 포함하여 Intune 장치 프로필에 대한 자세한 내용은 [Microsoft Intune](/intune/device-profiles) 장치 프로필이란?을 참조하세요.

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Microsoft Endpoint Manager를 사용하여 클라우드 제공 보호 켜기

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.
2. 끝점 **보안 바이러스 백신**  >  **을 선택 합니다.**
3. 바이러스 백신 프로필을 선택합니다. (아직 프로필이 없는 경우 또는 새 프로필을 만들하려는 경우 Microsoft Intune에서 장치 제한 설정 [구성을 참조하세요.](/intune/device-restrictions-configure)
4. 속성을 **선택합니다.** 그런 다음 구성 설정 **옆에 있는** 편집 을 **선택합니다.**
5. 클라우드 **보호를 확장하고**  클라우드 제공 보호 수준 목록에서 다음 중 하나를 선택합니다.
    1. **높음:** 강력한 수준의 검색을 적용합니다.
    2. **High plus:** **높음** 수준을 사용하며 추가 보호 조치를 적용합니다(클라이언트 성능에 영향을 줄 수 있습니다).
    3. **허용 오차** 없음: 알 수 없는 모든 실행을 차단합니다.
6. 검토 **+ 저장을 선택한** 다음 저장을 **선택합니다.**

Microsoft Endpoint Configuration Manager를 구성하는 방법에 대한 자세한 내용은 맬웨어 방지 정책을 만들고 배포하는 [방법: 클라우드 보호 서비스를 참조하세요.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>그룹 정책을 사용하여 클라우드 제공 보호 켜기

1. 그룹 정책 관리 장치에서 그룹 정책 관리 콘솔을 [열고](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 관리 **템플릿 을 선택합니다.**

4. **MAPS에서 Microsoft Defender** 바이러스 > Windows 구성 > 확장

5. **Microsoft MAPS에 가입을 두 번 클릭합니다.** 옵션이 켜져 있으며 기본 **MAPS** 또는 고급 **지도로 설정되어 있는지 확인** **확인** 을 선택합니다.

6. 추가 분석이 필요한 경우 파일 샘플 **보내기 를 두 번 클릭합니다.** 첫 번째 옵션이 **사용으로** 설정되어 있으며 다른 옵션이 다음 중 하나로 설정되어 있는지 확인합니다.

    1. **안전한 샘플 보내기(1)**
    2. **모든 샘플 보내기(3)**

        >[!NOTE]
        > 안전한 **샘플 보내기(1)** 옵션은 대부분의 샘플이 자동으로 전송됩니다. 개인 정보를 포함할 수 있는 파일은 계속 묻는 메시지를 표시하며 추가 확인이 요구됩니다.

        > [!WARNING]
        > 옵션을 항상  프롬프트(0)로 설정하면 장치의 보호 상태가 낮아지게 됩니다. 보내지 **않습니다(2)로** 설정하면 [](configure-block-at-first-sight-microsoft-defender-antivirus.md) 끝점용 Microsoft Defender의 즉시 차단 기능이 작동하지 않습니다.

7. **확인** 을 선택합니다.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>PowerShell cmdlet을 사용하여 클라우드 제공 보호 켜기

다음 cmdlet은 클라우드 제공 보호를 켜는 기능을 사용할 수 있습니다.

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Microsoft Defender 바이러스 백신에서 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 Defender cmdlet 구성 및 [실행을 참조하세요.](/powershell/module/defender/) [정책 CSP - Defender에는](/windows/client-management/mdm/policy-csp-defender) [-SubmitSamplesConsent에](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)대한 자세한 정보도 있습니다.

>[!NOTE]
> **-SubmitSamplesConsent를** (기본 설정) 또는 로 설정할 `SendSafeSamples` `NeverSend` 수도 `AlwaysPrompt` 있습니다. 이 `SendSafeSamples` 설정은 대부분의 샘플이 자동으로 전송됩니다. 개인 정보를 포함할 수 있는 파일은 계속 묻는 메시지를 표시하며 추가 확인이 요구됩니다.

>[!WARNING]
> **-SubmitSamplesConsent를** 설정하거나 장치의 보호 수준을 `NeverSend` `AlwaysPrompt` 낮출 수 있습니다. 또한 이를 로 설정하면 `NeverSend` 끝점용 Microsoft [](configure-block-at-first-sight-microsoft-defender-antivirus.md) Defender의 즉시 차단 기능이 작동하지 않습니다.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>WMI(Windows Management Instruction)를 사용하여 클라우드 제공 보호 켜기

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/defender/set-msft-mppreference) 클래스의 Set 메서드를 사용합니다.

```WMI
MAPSReporting
SubmitSamplesConsent
```

허용되는 매개 변수에 대한 자세한 내용은 [WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) api Windows Defender 참조하세요.

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Windows 보안 앱을 통해 개별 클라이언트에서 클라우드 제공 보호 켜기

> [!NOTE]
> Microsoft **MAPS** 보고에 대한 로컬 설정 다시 지정 그룹 정책 설정을 **사용** 안 하도록 설정한 경우 Windows 설정의 클라우드 기반 보호 설정은 회색으로 표시되어 사용할 수 없습니다.  그룹 정책 개체를 통해 변경한 내용은 먼저 개별 끝점에 배포해야 설정이 Windows 설정에서 업데이트됩니다.

1. 작업 표시줄에서 방패 아이콘을 선택하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.

2. 바이러스 & **위협** 방지 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택한 다음 바이러스 & **보호 설정 레이블을** 선택합니다.

    ![Windows 보안 앱의 바이러스 & 보호 설정 레이블 스크린샷](images/defender/wdav-protection-settings-wdsc.png)

3. 클라우드 **기반** 보호 및  자동 샘플 제출이 켜기 로 전환된지 **확인**

> [!NOTE]
> 그룹 정책을 사용하여 자동 샘플 제출을 구성한 경우 설정은 회색으로 회색으로 설정되고 사용할 수 없습니다.

## <a name="related-articles"></a>관련 문서

- [클라우드 차단 시간 제한 기간 구성](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [최초 차단 구성](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Microsoft Intune용 Endpoint Protection으로 Windows PC](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)보안 지원 ]
- [Defender cmdlet](/powershell/module/defender/)
- [Microsoft Defender 바이러스 백신에서 Microsoft 클라우드 제공 보호 사용](cloud-protection-microsoft-defender-antivirus.md)
- [맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)