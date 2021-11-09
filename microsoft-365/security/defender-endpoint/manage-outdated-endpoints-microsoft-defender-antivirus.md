---
title: 최신 끝점에 Microsoft Defender AV 보호 업데이트 적용
description: 한 동안 업데이트되지 않은 끝점에 대해 업데이트를 적용하는 경우와 방법을 정의합니다.
keywords: 업데이트, 보호, 오래된, 오래된, 오래된, catch-up
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 4ead5c123920670113a336d92fb98e69fea372b9
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882264"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Microsoft Defender 바이러스 백신 업데이트 및 만료된 엔드포인트에 대한 검사 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 바이러스 백신 끝점에서 업데이트를 피할 수 있는 기간 또는 끝점에서 누락할 수 있는 검색 수를 정의할 수 있습니다. 이 기능은 장치가 회사 또는 외부 네트워크에 자주 연결되지 않는 환경이나 매일 사용되지 않는 장치에서 특히 유용합니다.

예를 들어 특정 PC를 사용하는 직원은 3일 동안 중단을 시하며 해당 시간 동안 PC에 로그온하지 않습니다.

사용자가 직장으로 돌아와 PC에 로그온하면 Microsoft Defender 바이러스 백신 즉시 최신 보호 업데이트를 확인하고 다운로드하고 검사를 실행합니다.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>한 동안 업데이트되지 않은 끝점에 대한 추가 보호 업데이트 설정

지정된 Microsoft Defender 바이러스 백신 동안 보호 업데이트를 다운로드하지 않은 경우 다음 로그온 시 최신 업데이트를 자동으로 확인하고 다운로드할 수 있습니다. 이 기능은 시작 시 자동 업데이트 다운로드를 전역적으로 사용하지 않도록 [설정한 경우 유용합니다.](manage-event-based-updates-microsoft-defender-antivirus.md)

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Configuration Manager를 사용하여 추가 보호 업데이트 구성

1. Microsoft Endpoint Manager 콘솔에서 변경할 맬웨어 방지 정책을 열고(왼쪽의 탐색 창에서 자산 및 규정 준수를  클릭한 다음 개요 Endpoint Protection 맬웨어 방지 정책)  \>  \> 

2. 보안 **인텔리전스 업데이트 섹션으로 이동하여** 다음 설정을 구성합니다.

    1. 클라이언트 **컴퓨터가** 두 개 이상의 연속으로 예약된 업데이트에 대해 오프라인 상태일 경우 보안 인텔리전스 업데이트 강제 적용을 **예로 설정하세요.**
    2. Configuration  **Manager를** 보안 인텔리전스 업데이트의 원본으로 사용하는 경우... 의 경우 Configuration Manager에서 제공한 보호 업데이트를 최신 시간으로 간주할 시간을 지정합니다. 이렇게 하면 정의된 폴백 원본 순서에 따라 다음 업데이트 [위치가 사용됩니다.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)

3. **확인** 을 클릭합니다.

4. [평소와 같이 업데이트된 정책을 배포합니다.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>그룹 정책을 사용하여 추가 업데이트 기능을 사용하도록 설정 및 구성

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**

4. 트리를 확장하여 **서명 Windows 구성 > Microsoft Defender 바이러스 백신 > 확장합니다.**

5. 추가 보안  인텔리전스 업데이트가 필요한 날짜까지의 일 수 정의 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.** Microsoft Defender AV에서 최신 보호 업데이트를 확인하고 다운로드할 일 수를 입력합니다.

6. **확인** 을 클릭합니다.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>PowerShell cmdlet을 사용하여 추가 보호 업데이트 구성

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>WMI(Windows Management Instruction)를 사용하여 추가 보호 업데이트 구성

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
SignatureUpdateCatchupInterval
```

자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>보호가 기한이 지난 것으로 보고되기 전까지의 일 수 설정

또한 이전 또는 오래된 보호로 간주되는 Microsoft Defender 바이러스 백신 일 수를 지정할 수도 있습니다. 지정된 일 수가 지난 후 클라이언트는 자체적으로 기한이 지난 것으로 보고하고 PC 사용자에게 오류를 보여 주게 됩니다. 또한 WSUS Microsoft Defender 바이러스 백신 Microsoft Update를 첫 번째 원본으로 설정한 [](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)후 MMPC를 보조 원본으로 사용하는 경우와 같이 정의된 폴백 원본 순서에 따라 다른 원본에서 업데이트를 다운로드하려고 시도할 수도 있습니다.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>그룹 정책을 사용하여 보호가 기한이 지난 것으로 간주될 날짜 수 지정

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**

4. 트리를 확장하여 서명 Windows 구성 > Microsoft Defender 바이러스 백신 > 구성 **요소를 확장하고** 다음 설정을 구성합니다.

    1. 스파이웨어  정의가 기한이 지난 것으로 간주될 날짜까지의 기간(일) 정의를 두 번 클릭하고 옵션을 사용으로 **설정합니다.** Microsoft Defender AV에서 스파이웨어 보안 인텔리전스가 최신이 아 없다고 고려할 날짜 수를 입력합니다.

    2. **확인** 을 클릭합니다.

    3. 바이러스 정의가 기한이 지난 것으로 간주될 날짜까지의 기간(일) 정의를 두 번 클릭하고 옵션을 사용으로 **설정합니다.**  Microsoft Defender AV에서 바이러스 보안 인텔리전스가 최신이 아 없다고 고려할 날짜 수를 입력합니다.

    4. **확인** 을 클릭합니다.

## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>한 동안 검색되지 않은 끝점에 대한 업데이트 검사 설정

검색을 강제 실행하기 전에 누락될 수 있는 연속 예약된 Microsoft Defender 바이러스 백신 수 있습니다.

이 기능을 사용하도록 설정하는 프로세스는 다음입니다.

1. 하나 이상의 예약된 검색을 설치합니다(예약 [검사 항목 참조).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
2. 추가 검사 기능을 사용하도록 설정할 수 있습니다.
3. 최대 검색이 발생하기 전에 건너뛴 검사 수를 정의합니다.

이 기능은 전체 검사와 빠른 검사에 모두 사용할 수 있습니다.

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>그룹 정책을 사용하여 추가 검사 기능 사용 및 구성

1. 예약된 검색을 하나 이상 설정해야 합니다.

2. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

3. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

4. 정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**

5. 트리를 **확장하여** Windows 구성 > Microsoft Defender 바이러스 백신 > 설정을 구성합니다.

    1. 예약된 빠른 검색을 설정한 경우 빠른  검색 켜기 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**
    2. 예약된 전체 검색을 설정한 경우 전체  검사 켜기 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.** **확인** 을 클릭합니다.
    3. 추가 검사가  강제로 실행되는 일 수 정의 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**
    4. 다음에 사용자가 PC에 로그온할 때 검사가 자동으로 실행되기 전에 누락될 수 있는 검사 수를 입력합니다. 실행되는 검사 유형은 예약된  검사에 사용할 검사 유형 지정(Schedule [scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 항목 참조)에 따라 결정됩니다. **확인** 을 클릭합니다.

> [!NOTE]
> 그룹 정책 설정 제목은 일 수를 참조합니다. 그러나 이 설정은 최대 검색을 실행하기 전에 검사 횟수(일 수 아)에 적용됩니다.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>PowerShell cmdlet을 사용하여 최대 검색 구성

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) Microsoft Defender 바이러스 백신.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>WMI(Windows 관리 명령)를 사용하여 최대 검색 구성

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Configuration Manager를 사용하여 추가 검사 구성

1. Microsoft Endpoint Manager 콘솔에서 변경할 맬웨어 방지 정책을 열고(왼쪽의 탐색 창에서 자산 및 규정 준수를  클릭한 다음 개요 Endpoint Protection 맬웨어 방지 정책)  \>  \> 

2. 예약된 검사 **섹션으로 이동하고** 클라이언트 컴퓨터가 오프라인 상태인 경우 선택한 검사 유형을 강제로 **검사...를** **예로 합니다.**

3. **확인** 을 클릭합니다.

4. [평소와 같이 업데이트된 정책을 배포합니다.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="related-articles"></a>관련 문서

- [배포 Microsoft Defender 바이러스 백신](deploy-manage-report-microsoft-defender-antivirus.md)
- [업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md)
- [보호 업데이트를 다운로드하고 적용해야 하는 경우 관리](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md)
- [모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
