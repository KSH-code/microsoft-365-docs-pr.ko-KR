---
title: Microsoft Defender 오프라인 Windows
description: 앱의 Microsoft Defender 오프라인 바로 사용할 Windows Defender 바이러스 백신 있습니다. 네트워크에서 배포되는 방법을 관리할 수도 있습니다.
keywords: 검사, defender, 오프라인
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 12023c7655a8978e5e0ae54b8a2831edda9b9d9e
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60883584"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Microsoft Defender 오프라인 검사의 결과 실행 및 검토

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 오프라인 신뢰할 수 있는 환경에서 검색을 부팅하고 실행할 수 있는 맬웨어 방지 검사 도구입니다. 검사는 일반 Windows 커널 외부에서 실행되어 MBR(마스터 부트 레코드)을 감염 또는 덮어 Windows 셸을 무시하려는 맬웨어를 대상으로 할 수 있습니다.

맬웨어 Microsoft Defender 오프라인 의심하거나 맬웨어 발생 후 끝점을 완전히 정리하려는 경우 이 방법을 사용할 수 있습니다.

Windows 10 Windows 11 Microsoft Defender 오프라인 앱에서 직접 한 번의 클릭으로 Windows 보안 수 [있습니다.](microsoft-defender-security-center-antivirus.md) 이전 버전의 Windows 사용자는 부팅 가능한 미디어에 Microsoft Defender 오프라인 끝점을 다시 시작하고 부팅 가능한 미디어를 로드해야 합니다.

## <a name="prerequisites-and-requirements"></a>선행 조건 및 요구 사항

Microsoft Defender 오프라인 Windows 10 Windows 11 하드웨어 요구 사항이 Windows 10.

요구 사항 및 Windows 10 Windows 11 자세한 내용은 다음 항목을 참조하십시오.

- [최소 하드웨어 요구 사항](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [하드웨어 구성 요소 지침](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender 오프라인 프로세서가 있는 컴퓨터나 ARM 서버 주식 보관 Windows 지원되지 않습니다.

끝점에서 Microsoft Defender 오프라인 관리자 권한으로 로그인해야 합니다.

## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender 오프라인 업데이트

Microsoft Defender 오프라인 끝점에서 사용할 수 있는 최신 보호 업데이트를 사용하는지 확인합니다. 업데이트될 때마다 Windows Defender 바이러스 백신 업데이트됩니다.

> [!NOTE]
> 오프라인 검색을 실행하기 전에 Microsoft Defender AV 보호를 업데이트해야 합니다. 그룹 정책을 사용하여 강제로 업데이트를 수행하거나 일반적으로 끝점에 업데이트를 배포하거나 에서 수동으로 최신 보호 [업데이트를 다운로드하여](https://www.microsoft.com/security/portal/definitions/adl.aspx)설치할 Microsoft 맬웨어 보호 센터.

자세한 내용은 [보안 Microsoft Defender 바이러스 백신 업데이트](manage-protection-updates-microsoft-defender-antivirus.md) 관리 항목을 참조하세요.

## <a name="usage-scenarios"></a>사용 시나리오

버전 Windows 10 1607에서 오프라인 검색을 수동으로 강제할 수 있습니다. 또는 Windows Defender 실행해야 Microsoft Defender 오프라인 경우 끝점에서 사용자에게 메시지를 표시하는 메시지가 표시될 수 있습니다.

오프라인 검사 수행의 필요성은 끝점을 관리하는 데 Microsoft Endpoint Manager 오프라인 검사에도 공개됩니다.

프롬프트는 다음과 유사한 알림을 통해 발생할 수 있습니다.

:::image type="content" source="../../media/notification.png" alt-text="실행 알림은 Microsoft Defender 오프라인.":::

또한 사용자는 클라이언트 내에서 Windows Defender 알림을 하게 됩니다.

Configuration Manager에서 Monitoring > **Overview > Security > Endpoint Protection Status로**> System Center Endpoint Protection 있습니다.

Microsoft Defender 오프라인 검사는 오프라인 검사가  필요하여 맬웨어 수정 **상태 아래에 표시됩니다.**

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender 오프라인 검사가 필요합니다.":::

## <a name="configure-notifications"></a>알림 구성

Microsoft Defender 오프라인 알림은 다른 Microsoft Defender AV 알림과 동일한 정책 설정으로 구성됩니다.

앱의 알림에 Windows Defender 끝점에 나타나는 알림 구성 항목을 [참조하세요.](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>검사 실행

> [!IMPORTANT]
> 이 Microsoft Defender 오프라인 파일을 저장하고 실행 중인 프로그램을 종료해야 합니다. Microsoft Defender 오프라인 검사는 실행하는 데 15분 정도 걸립니다. 검사가 완료되면 끝점이 다시 시작됩니다. 검사는 일반적인 운영 환경 외부에서 Windows 수행됩니다. 사용자 인터페이스는 사용자 인터페이스가 사용자 인터페이스에서 수행한 일반 검사와 Windows Defender. 검사가 완료되면 끝점이 다시 시작되어 Windows 로드됩니다.

다음을 사용하여 Microsoft Defender 오프라인 실행할 수 있습니다.

- PowerShell
- WMI(Windows Management Instrumentation)
- 앱 Windows 보안 앱



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>PowerShell cmdlet을 사용하여 오프라인 검사 실행

다음 cmdlet을 사용 합니다.

```PowerShell
Start-MpWDOScan
```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>WMI(Windows 관리 명령)를 사용하여 오프라인 검사 실행

MSFT_MpWDOScan [**클래스를**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 사용하여 오프라인 검색을 실행합니다.

다음 WMI 스크립트 코드는 즉시 Microsoft Defender 오프라인 실행하여 끝점을 다시 시작하고 오프라인 검색을 실행한 다음 다시 시작하여 Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start
```

자세한 내용은 다음을 참조하세요.

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Windows Defender 앱을 사용하여 오프라인 검사 실행

1. 작업 표시줄에서 방패 아이콘을 클릭하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 클릭한 다음 **고급 검사 레이블을** 클릭합니다.

3. 검색 **Microsoft Defender 오프라인 선택하고** 지금 **스캔 을 클릭합니다.**

    > [!NOTE]
    > 버전 Windows 10 1607에서는 Windows 설정 Update &  security Windows Defender 또는 Windows Defender 클라이언트에서 오프라인 검색을 실행할 수 \>  \>  있습니다.

## <a name="review-scan-results"></a>검사 결과 검토

Microsoft Defender 오프라인 검사 결과가 앱의 검사 기록 [섹션에 Windows 보안 표시됩니다.](microsoft-defender-security-center-antivirus.md)

## <a name="related-articles"></a>관련 문서

- [검사 및 수정 결과 사용자 지정, 시작 및 검토](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)