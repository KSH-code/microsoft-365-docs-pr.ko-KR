---
title: Microsoft Defender 바이러스 백신 가상 데스크톱 인프라 배포 가이드
description: 보호와 성능 Microsoft Defender 바이러스 백신 균형을 유지하기 위해 가상 데스크톱 환경에 배포하는 방법을 학습합니다.
keywords: vdi, hyper-v, vm, 가상 컴퓨터, windows defender, 바이러스 백신, av, 가상 데스크톱, rds, 원격 데스크톱
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 08/31/2021
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 512781d9c3812b8da515f5dacdfedd52d2c3480c
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491484"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>VDI(가상 데스크톱 인프라) 환경에서 Microsoft Defender 바이러스 백신의 배포 가이드

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

표준 사내 또는 하드웨어 구성 외에도 RDS(원격 데스크톱) Microsoft Defender 바이러스 백신 VDI(가상 데스크톱 인프라) 환경에서도 사용할 수 있습니다.

Microsoft 원격 데스크톱 VDI 지원에 대한 자세한 내용은 [Azure](/azure/virtual-desktop) Virtual Desktop 설명서를 참조하세요.

Azure 기반 가상 컴퓨터의 경우 [Azure Defender에서 Endpoint Protection 설치를 참조하세요.](/azure/security-center/security-center-install-endpoint-protection)

VIS에서 실행되는 VM에 업데이트를 쉽게 배포할 수 있는 기능을 사용하여 이 가이드를 단축하여 빠르고 쉽게 컴퓨터의 업데이트를 다운로드하는 방법에 대해 중점적으로 설명했습니다. 업데이트가 호스트 서버의 구성 요소 비트로 확장된 다음 켜져 있는 경우 VM으로 직접 다운로드하기에 골든 이미지를 정기적으로 만들고 봉인할 필요가 없습니다.

이 가이드에서는 다음 방법을 포함하여 최적의 보호 및 성능을 위해 VM을 구성하는 방법을 설명합니다.

- [보안 인텔리전스 업데이트에 대한 전용 VDI 파일 공유 설정](#set-up-a-dedicated-vdi-file-share)
- [예약된 검사 임의화](#randomize-scheduled-scans)
- [빠른 검사 사용](#use-quick-scans)
- [알림 방지](#prevent-notifications)
- [업데이트할 때마다 검사가 발생하지 않도록 설정](#disable-scans-after-an-update)
- [한동안 오프라인 상태인 기한이 지난 컴퓨터 또는 컴퓨터 검색](#scan-vms-that-have-been-offline)
- [제외 적용](#exclusions)

성능 테스트 및 자체 VDI에서 바이러스 백신 성능을 테스트하는 방법에 대한 지침과 함께 새로운 공유 보안 [인텔리전스](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)업데이트 기능을 Microsoft Defender 바이러스 백신 가상 데스크톱 인프라에서 백서 응용 프로그램을 다운로드할 수도 있습니다.

> [!IMPORTANT]
> VDI는 Windows Server 2012 또는 Windows Server 2016 호스트할 수 있습니다. 이전 버전의 VDI에서는 사용할 수 없는 보호 기술 및 기능이 늘어나기 때문에 VM(가상 컴퓨터)은 Windows 10 1607 이상을 실행해야 Windows.
>
> Microsoft Defender AV가 Insider Preview, 빌드 18323 이상에서 가상 Windows 10 성능 및 기능이 개선되었습니다. Insider Preview 빌드를 사용하려면 이 가이드에서 확인할 것입니다. 이 버전을 지정하지 않으면 최상의 보호 및 성능을 위해 필요한 최소 버전은 Windows 10 1607입니다.

## <a name="set-up-a-dedicated-vdi-file-share"></a>전용 VDI 파일 공유 설정

Windows 10 버전 1903에서는 다운로드한 보안 인텔리전스 업데이트의 포장을 풀고 호스트 컴퓨터로 오프로드하여 개별 컴퓨터의 이전 CPU, 디스크 및 메모리 리소스를 절약하는 공유 보안 인텔리전스 기능을 도입했습니다. 이 기능은 이전 버전 1703 이상에서 Windows 10 기능이 지원되었습니다. 이 기능은 그룹 정책 또는 PowerShell을 사용하여 설정할 수 있습니다.

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>그룹 정책을 사용하여 공유 보안 인텔리전스 기능을 사용하도록 설정할 수 있습니다.

1. 그룹 정책 관리 컴퓨터에서 그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 관리 **템플릿 을 클릭합니다.**

4. 보안 인텔리전스 **Windows 구성 Microsoft Defender 바이러스 백신** \>  \> **확장합니다.**

5. VDI 클라이언트의 보안 인텔리전스 위치 정의를 두 번 **클릭한** 다음 옵션을 사용으로 **설정합니다.** 필드가 자동으로 나타납니다.

6. Enter `\\<sharedlocation\>\wdav-update` (이 값에 대한 도움말은 다운로드 및 포장 [풀기 참조).](#download-and-unpackage-the-latest-updates)

7. **확인** 을 클릭합니다.

8. 테스트할 VM에 GPO를 배포합니다.

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>PowerShell을 사용하여 공유 보안 인텔리전스 기능을 사용하도록 설정

다음 cmdlet을 사용하여 기능을 사용하도록 설정할 수 있습니다. 그런 다음 일반적으로 PowerShell 기반 구성 정책을 VM에 푸시할 때 이 정책을 푸시해야 합니다.

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

사용할 [내용은 다운로드](#download-and-unpackage-the-latest-updates) 및 포장 풀기 \<shared location\> 섹션을 참조하세요.

## <a name="download-and-unpackage-the-latest-updates"></a>최신 업데이트 다운로드 및 포장 풀기

이제 새 업데이트 다운로드 및 설치를 시작할 수 있습니다. 아래에서 샘플 PowerShell 스크립트를 만들 수 있습니다. 이 스크립트는 새 업데이트를 다운로드하고 VM을 준비하는 가장 쉬운 방법입니다. 그런 다음 예약된 작업을 사용하여 관리 컴퓨터의 특정 시간에서 실행될 스크립트를 설정해야 합니다. 또는 Azure, Intune 또는 SCCM에서 PowerShell 스크립트를 사용하는 데 익숙한 경우 해당 스크립트를 사용할 수도 있습니다.

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

예약된 작업을 하루 한 번 실행하여 패키지를 다운로드하고 패키지를 언팩할 때마다 VM이 새 업데이트를 받게 할 수 있습니다.
하루 한 번부터 시작하는 것이 되지만 영향을 이해하기 위해 빈도를 늘리거나 줄이면서 실험해 보아야 합니다.

보안 인텔리전스 패키지는 일반적으로 3~4시간마다 한 번씩 게시됩니다. 빈도를 4시간보다 짧게 설정하면 관리 컴퓨터의 네트워크 오버헤드가 증가하여 이점이 없습니다.

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>PowerShell 스크립트를 실행하기 위해 예약된 작업 설정

1. 관리 컴퓨터의 관리 시작 메뉴 작업 스케줄러 **를 입력합니다.** 작업을 열고 사이드 패널에서 **작업 만들기...를** 선택합니다.

2. 보안 인텔리전스 **unpacker로 이름을 입력합니다.** 트리거 **탭으로** 이동하여 새로 **추가...를 선택합니다.** \> **매일** 을 선택하고 **확인 을 선택합니다.**

3. 작업 **탭으로 이동하여** 새로 추가...를 **선택합니다.** 프로그램/스크립트 필드에 **PowerShell을** **입력합니다.** 인수 `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` **추가 필드에 입력합니다.** **확인** 을 선택합니다.

4. 원하는 경우 추가 설정을 구성하도록 선택할 수 있습니다.

5. **확인을** 선택하여 예약된 작업을 저장합니다.

작업을 마우스 오른쪽 단추로 클릭하고 실행을 클릭하여 수동으로 업데이트를 시작할 **수 있습니다.**

### <a name="download-and-unpackage-manually"></a>수동으로 다운로드 및 포장 풀기

모든 작업을 수동으로 수행하려면 스크립트의 동작을 복제하기 위해 수행해야 할 작업을 다음과 같습니다.

1. 인텔리전스 업데이트를 저장하기 위해 라는 시스템 루트에 새 폴더를 만들 수 있습니다(예: `wdav_update` 폴더 `c:\wdav_update` 만들기).

2. GUID 이름으로 wdav_update 하위폴더 만들기 `{00000000-0000-0000-0000-000000000000}`

   예를 들면 다음과 같습니다. `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > 스크립트에서 GUID의 마지막 12자리 숫자가 매월 새 폴더가 만들어지기 위해 파일을 다운로드한 연도, 월, 일 및 시간으로 설정됩니다. 파일을 매시간 동일한 폴더로 다운로드할 수 있도록 변경할 수 있습니다.

3. GUID 폴더로 보안 인텔리전스 [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  패키지를 다운로드합니다. 파일의 이름을 로 지정해야 `mpam-fe.exe` 합니다.

4. cmd 프롬프트 창을 열고 만든 GUID 폴더로 이동합니다. **/X** 추출 명령을 사용하여 파일을 추출합니다(예: `mpam-fe.exe /X` ).

   > [!NOTE]
   > VM은 추출된 업데이트 패키지를 통해 새 GUID 폴더를 만들 때마다 또는 기존 폴더가 추출된 새 패키지로 업데이트될 때마다 업데이트된 패키지를 선택합니다.

## <a name="randomize-scheduled-scans"></a>예약된 검사 임의화

실시간 보호 및 검사 외에도 예약된 [검사가 실행됩니다.](configure-real-time-protection-microsoft-defender-antivirus.md)

검사 자체의 시작 시간은 예약된 검사 **정책(ScheduleDay,** **ScheduleTime** 및 **ScheduleQuickScanTime)을 기반으로 합니다.** 임의 설정으로 인해 Microsoft Defender 바이러스 백신 설정된 시간부터 4시간 이내에 각 컴퓨터의 검색이 시작됩니다.

예약된 [검사에](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 사용할 수 있는 다른 구성 옵션에 대한 검사 예약을 참조하세요.

## <a name="use-quick-scans"></a>빠른 검사 사용

예약된 검사 중에 수행할 검사 유형을 지정할 수 있습니다. 빠른 검사는 맬웨어가 활성화해야 하는 모든 장소를 검색하도록 디자인된 기본 접근 방식입니다. 다음 절차에서는 그룹 정책을 사용하여 빠른 검색을 설정하는 방법을 설명합니다.

1. 그룹 정책 편집기에서  검사에서 관리 템플릿 Windows \> **구성** \> **Microsoft Defender 바이러스 백신** \> **로 이동하십시오.**

2. 예약된 **검사에** 사용할 검사 유형 지정을 선택한 다음 정책 설정을 편집합니다.

3. 정책을 **사용으로 설정하고** 옵션 에서 빠른 검사 **를 선택합니다.**

4. **확인** 을 선택합니다.

5. 평소와 같이 그룹 정책 개체를 배포합니다.

## <a name="prevent-notifications"></a>알림 방지

경우에 따라 Microsoft Defender 바이러스 백신 전송되거나 여러 세션에서 유지될 수 있습니다. 이 문제를 최소화하기 위해 사용자 인터페이스를 Microsoft Defender 바이러스 백신 있습니다. 다음 절차에서는 그룹 정책을 사용하여 알림을 표시하지 않습니다.

1. 그룹 정책 편집기에서 클라이언트 **인터페이스의** Windows 구성 \> **Microsoft Defender 바이러스 백신** \> **로 이동하십시오.**

2. 모든 **알림 표시 안 를 선택한** 다음 정책 설정을 편집합니다.

3. 정책을 **사용으로 설정하고** 확인 을 **선택합니다.**

4. 평소와 같이 그룹 정책 개체를 배포합니다.

알림을 표시하지 Microsoft Defender 바이러스 백신 검사가 수행되거나 수정 작업이 수행될 Windows 10 알림 센터에 알림이 표시되지 않습니다. 그러나 보안 운영 팀의 검색 결과는 검색 포털에서 Microsoft 365 Defender [표시됩니다.](microsoft-defender-security-center.md)

> [!TIP]
> 관리 센터를 Windows 10 다음 단계 중 하나를 수행합니다.
>
> - 작업 표시줄의 오른쪽 끝에서 작업 센터 아이콘을 선택합니다.
> - 로고 Windows 단추 + A를 누릅니다.
> - 터치 스크린 디바이스에서 화면 오른쪽 가장자리에서 스와이프합니다.

## <a name="disable-scans-after-an-update"></a>업데이트 후 검사 사용 안

업데이트 후 검색을 사용할 수 않도록 하면 업데이트를 받은 후 검사가 실행되지 않습니다. 빠른 검사도 실행한 경우 기본 이미지를 만들 때 이 설정을 적용할 수 있습니다. 이렇게 하면 새로 업데이트된 VM이 기본 이미지를 만들 때 이미 검사한 검사로 다시 검색하지 못하게 할 수 있습니다.

> [!IMPORTANT]
> 업데이트 후 검색을 실행하면 최신 보안 인텔리전스 업데이트로 VM을 보호하는 데 도움이 됩니다. 이 옵션을 설정하면 VM의 보호 수준이 낮아지며, 기본 이미지를 처음 만들거나 배포할 때만 사용할 수 있습니다.

1. 그룹 정책 편집기에서 보안 **인텔리전스 Windows 구성** \> **Microsoft Defender 바이러스 백신** \> **로 이동하세요.**

2. 보안 **인텔리전스 업데이트 후 검사 켜기 를 선택한** 다음 정책 설정을 편집합니다.

3. 정책을 사용 안 **으로 설정**

4. **확인** 을 선택합니다.

5. 평소와 같이 그룹 정책 개체를 배포합니다.

이 정책은 업데이트 후 즉시 검사가 실행되지 않도록 합니다.

## <a name="scan-vms-that-have-been-offline"></a>오프라인 상태인 VM 검사

1. 그룹 정책 편집기에서 검사에서 Windows **구성** \> **Microsoft Defender 바이러스 백신** \> **로 이동하십시오.**

2. 빠른 **추가 검사 켜기 를 선택한** 다음 정책 설정을 편집합니다.

3. 정책을 사용으로 **설정합니다.**

4. **확인** 을 선택합니다.

5. 일반적으로 그룹 정책 개체를 배포합니다.

이 정책은 VM이 연속으로 두 개 이상의 예약된 검사가 누락된 경우 강제로 검색을 실행합니다.

## <a name="enable-headless-ui-mode"></a>헤드리스 UI 모드 사용

1. 그룹 정책 편집기에서 클라이언트 **인터페이스의** Windows 구성 \> **Microsoft Defender 바이러스 백신** \> **로 이동하십시오.**

2. 헤드리스 **UI 모드 사용 을 선택하고** 정책을 편집합니다.

3. 정책을 사용으로 **설정합니다.**

4. **확인** 을 클릭합니다.

5. 일반적으로 그룹 정책 개체를 배포합니다.

이 정책은 조직의 Microsoft Defender 바이러스 백신 사용자 인터페이스 전체를 숨길 수 있습니다.

## <a name="exclusions"></a>제외

제외는 필요에 맞게 추가, 제거 또는 사용자 지정될 수 있습니다.

자세한 내용은 [Configure Microsoft Defender 바이러스 백신 exclusions on Windows 참조하세요.](configure-exclusions-microsoft-defender-antivirus.md)

## <a name="additional-resources"></a>추가 리소스

- [기술 Community 블로그: 비영구 Microsoft Defender 바이러스 백신 VDI 컴퓨터용 구성](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [원격 데스크톱 서비스 및 VDI의 TechNet 포럼](https://social.technet.microsoft.com/Forums/windowsserver/home?forum=winserverTS)
- [SignatureDownloadCustomTask PowerShell 스크립트](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)
