---
title: Windows의 Microsoft Defender 바이러스 백신
description: Microsoft Defender 바이러스 백신, 내장된 맬웨어 및 바이러스 방지 기능을 관리, 구성 및 사용하는 방법에 대해 알아 보세요.
keywords: Microsoft Defender Antivirus, windows defender, antimalware, scep, system center endpoint protection, system center configuration manager, virus, malware, threat, detection, protection, security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 201f8c57057b1f8a314bdd42ba53042a4f6d00e3
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552659"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Windows의 Microsoft Defender 바이러스 백신

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 바이러스 백신

Microsoft Defender 바이러스 백신은 Windows 10 및 Windows 11 및 Windows Server 버전에서 사용할 수 있습니다.

Windows Defender 바이러스 백신은 엔드포인트용 Microsoft Defender의 차세대 보호 구성 요소입니다. 이 기능은 기계 학습, 빅데이터 분석, 심층 위협 방지 연구, Microsoft 클라우드 인프라를 결합하여 조직의 장치(또는 엔드포인트)를 보호합니다. Microsoft Defender 바이러스 백신은 Windows에 기본 제공되며, 엔드포인트용 Microsoft Defender와 함께 작동하여 장치 및 클라우드를 보호합니다.

## <a name="compatibility-with-other-antivirus-products"></a>다른 바이러스 백신 제품과의 호환성

장치에서 타사 바이러스 백신/맬웨어 방지 제품을 사용하는 경우 타사 바이러스 백신 솔루션과 함께 수동 모드에서 Microsoft Defender 바이러스 백신을 실행할 수 있습니다. 사용되는 운영 체제 및 장치가 엔드포인트용 Defender에 온보딩되었는지 여부에 따라 달라집니다. 자세한 내용은 [Microsoft Defender 바이러스 백신 호환성](microsoft-defender-antivirus-compatibility.md)을 참조하세요.

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>활성 모드, 수동 모드 및 사용 중지 모드 비교

다음 표에서는 Microsoft Defender 바이러스 백신 활성 모드, 수동 모드 또는 사용 중지 상태일 때 예상되는 사항에 대해 설명합니다.

<br/><br/>

| 모드 | 발생 작업 |
|---|---|
| 활성 모드 | 활성 모드에서 Microsoft Defender 바이러스 백신은 장치의 기본 바이러스 백신 앱으로 사용됩니다. 파일이 스캔되고, 위협이 수정되고, 검색된 위협이 조직의 보안 보고서 및 Windows 보안 앱에 나열됩니다. |
| 수동 모드 | 수동 모드에서 Microsoft Defender 바이러스 백신은 장치의 기본 바이러스 백신 앱으로 사용되지 않습니다. 파일이 스캔되고 검색된 위협이 보고되지만 위협이 Microsoft Defender 바이러스 백신에 의해 수정되지는 않습니다. <br/><br/> **중요**: Microsoft Defender 바이러스 백신은 엔드포인트용 Microsoft Defender에 온보딩된 엔드포인트에서만 수동 모드로 실행할 수 있습니다. [Microsoft Defender 바이러스 백신을 수동 모드에서 실행하기 위한 요구 사항](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode)을 참조하세요. |
| 사용 중지 또는 제거됨 | 사용 중지하거나 제거하면 Microsoft Defender 바이러스 백신이 사용되지 않습니다. 파일이 스캔되지 않으며 위협은 수정되지 않습니다. 일반적으로 Microsoft Defender 바이러스 백신을 사용 중지하거나 제거하는 것은 권장되지 않습니다. |

자세한 내용은 [Microsoft Defender 바이러스 백신 호환성](microsoft-defender-antivirus-compatibility.md)을 참조하세요.

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>장치에서 Microsoft Defender 바이러스 백신 상태 확인

장치에서 Microsoft Defender 바이러스 백신 상태를 확인하려면 Windows 보안 앱 또는 Windows PowerShell 같은 여러 방법 중 하나를 사용할 수 있습니다.

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>Windows 보안 앱을 사용하여 Microsoft Defender 바이러스 백신 상태 확인

1. Windows 장치에서 시작 메뉴를 선택하고 `Security` 입력을 시작합니다. 그런 다음 결과에서 Windows 보안 앱을 엽니다.

2. **바이러스 및 위협 방지** 를 선택합니다.

3. **바이러스 및 위협 방지 설정** 에서 **설정 관리** 를 선택합니다.

설정 페이지에 바이러스 백신/맬웨어 방지 솔루션의 이름이 표시됩니다.

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>PowerShell을 사용하여 Microsoft Defender 바이러스 백신 상태 확인

1. 시작 메뉴를 선택하고 `PowerShell` 입력을 시작합니다. 그런 다음 결과에서 Windows PowerShell을 엽니다.

2. `Get-MpComputerStatus`를 입력합니다.

3. 결과 목록에서 **AMRunningMode** 행을 확인합니다.

   - **정상** 은 Microsoft Defender 바이러스 백신이 활성 모드에서 실행 중임을 의미합니다.

   - **수동 모드** 는 Microsoft Defender 바이러스 백신이 실행 중이지만 장치의 기본 바이러스 백신/맬웨어 방지 제품이 아님을 의미합니다. 수동 모드는 엔드포인트용 Microsoft Defender에 온보딩되고 특정 요구 사항을 충족하는 장치에만 사용할 수 있습니다. 자세한 내용을 확인하려면 [Microsoft Defender 바이러스 백신을 수동 모드에서 실행하기 위한 요구 사항](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode)을 참조하세요.

   - **EDR 차단 모드** 는 Microsoft Defender 바이러스 백신이 실행 중이고 엔드포인트용 Microsoft Defender의 기능인 [차단 모드의 EDR(엔드포인트 감지 및 응답)](edr-in-block-mode.md)이 사용되고 있음을 의미합니다.

   - **SxS 수동 모드** 는 Microsoft Defender 바이러스 백신이 다른 바이러스 백신/맬웨어 방지 제품과 함께 실행되고 [제한된 정기 검사가 사용됨](limited-periodic-scanning-microsoft-defender-antivirus.md)을 의미합니다.

> [!TIP]
> Get-MpComputerStatus PowerShell cmdlet에 대한 자세한 내용은 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) 참조 문서를 확인하세요.

## <a name="get-your-antivirusantimalware-platform-updates"></a>바이러스 백신 및 맬웨어 방지 업데이트 받기

Microsoft Defender 바이러스 백신 또는 모든 바이러스 백신/맬웨어 방지 솔루션을 최신 상태로 유지하는 것이 중요합니다. Microsoft는 장치가 새로운 맬웨어 및 공격 기술로부터 보호할 수 있는 최신 기술을 갖추도록 정기적인 업데이트를 릴리스합니다. 자세한 내용은 [Microsoft Defender 바이러스 백신 업데이트 관리 및 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Windows Server의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender 바이러스 백신 관리 및 구성](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 평가](evaluate-microsoft-defender-antivirus.md)
