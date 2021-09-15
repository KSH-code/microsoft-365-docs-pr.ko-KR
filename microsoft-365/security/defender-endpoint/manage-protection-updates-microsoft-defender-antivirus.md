---
title: 업데이트 수신 방법 및 Microsoft Defender 바이러스 백신 관리
description: 보호 업데이트를 받는 방법에 대한 Microsoft Defender 바이러스 백신 관리합니다.
keywords: 업데이트, 보안 기준, 보호, 변경 순서, ADL, MMPC, UNC, 파일 경로, 공유, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: c303251ff8a6e37ac351e57dc18a1ca3dcee8751
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59356816"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>Microsoft Defender 바이러스 백신 보호 업데이트의 출처 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

바이러스 백신 보호를 최신 상태로 유지하는 것이 중요합니다. 다음 두 가지 구성 요소로 보호 업데이트를 관리할 수 Microsoft Defender 바이러스 백신.

- *업데이트가* 다운로드되는 위치 및
- *업데이트가* 다운로드되고 적용될 때

이 문서에서는 업데이트를 다운로드할 위치를 지정하는 방법에 대해 설명하고 있습니다(이를 변경 순서라고도 합니다). 업데이트가 [Microsoft Defender 바이러스 백신](manage-updates-baselines-microsoft-defender-antivirus.md) 방법 및 업데이트의 다른 측면(예: 업데이트 계획)을 구성하는 방법에 대한 개요는 Microsoft Defender 바이러스 백신 업데이트 관리 및 기준 적용 항목을 참조하세요.

> [!IMPORTANT]
> Microsoft Defender 바이러스 백신 보안 인텔리전스 업데이트는 Windows 업데이트 및 2019년 10월 21일 월요일부터 전달됩니다. 모든 보안 인텔리전스 업데이트는 SHA-2 전용으로 서명됩니다. 보안 인텔리전스를 업데이트하려면 SHA-2를 지원하기 위해 장치를 업데이트해야 합니다. 자세한 내용은 Windows [및 WSUS에 대한 2019 SHA-2 코드 서명 지원 요구 사항을 참조합니다.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)

<a id="fallback-order"></a>

## <a name="fallback-order"></a>Fallback order

일반적으로 네트워크 구성에 따라 기본 원본에서 업데이트를 개별적으로 다운로드하고 그 다음에 다른 원본을 우선 순위대로 다운로드하도록 끝점을 구성합니다. 업데이트는 사용자가 지정한 순서대로 원본에서 얻습니다. 원본을 사용할 수 없는 경우 목록의 다음 원본이 즉시 사용됩니다.

업데이트가 게시될 때 업데이트 크기를 최소화하기 위해 일부 논리가 적용됩니다. 대부분의 경우 장치에서 최신 업데이트와 현재 설치된 업데이트(델타라고도 지칭)의 차이점만 다운로드되고 적용됩니다. 그러나 델타 크기는 다음 두 가지 주요 요인에 따라 결정됩니다.

- 장치에서 마지막 업데이트의 사용 기한입니다. 및
- 업데이트를 다운로드하고 적용하는 데 사용되는 원본입니다.

끝점의 업데이트가 오래될수록 다운로드가 커집니다. 그러나 다운로드 빈도도 고려해야 합니다. 업데이트 일정이 잦을수록 네트워크 사용량이 증가할 수 있는 반면 일정이 적을수록 다운로드당 파일 크기가 커집니다.

끝점에서 업데이트를 받을 위치를 지정할 수 있는 위치는 5개입니다.

- [Microsoft 업데이트](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows 서버 업데이트 서비스](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus) <sup> [[1](#fn1)]<sup></sup>  
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [네트워크 파일 공유](#unc-share)
- [맬웨어 및 Microsoft Defender 바이러스 백신 Microsoft 맬웨어 방지에 대한 보안 인텔리전스 업데이트](https://www.microsoft.com/wdsi/defenderupdates) <sup> [[2](#fn1)]<sup></sup>

  (<a id="fn1">1)</a>Intune 내부 정의 업데이트 서버 - SCCM/SUP을 사용하여 Microsoft Defender 바이러스 백신에 대한 정의 업데이트를 다운로드하고 클라이언트 장치에서 차단된 Windows 업데이트에 액세스해야 하는 경우 공동 관리로 전환하고 끝점 보호 작업을 Intune으로 오프로드할 수 있습니다. Intune에 구성된 맬웨어 방지 정책에는 '내부 정의 업데이트 서버'에 대한 옵션이 있습니다. 이 옵션은 업데이트 원본으로 사내 WSUS를 사용하도록 구성할 수 있습니다. 이렇게 하면 공식 WU 서버의 업데이트가 엔터프라이즈에 대해 승인되는 업데이트를 제어할 수 있으며, 네트워크 트래픽을 공식 UPdates 네트워크로 프록시하고 Windows 도움이 됩니다.

  (<a id="fn1">2)</a>정책 및 레지스트리에 MMPC(Microsoft 맬웨어 보호 센터 보안 인텔리전스) 이전 이름으로 나열될 수 있습니다.

Microsoft 업데이트는 최상의 보호 수준을 보장하기 위해 빠른 릴리스를 허용합니다. 즉, 자주 더 작은 다운로드가 가능합니다. Windows 서버 업데이트 서비스, Microsoft Endpoint Configuration Manager 및 Microsoft 보안 인텔리전스 업데이트 원본은 덜 자주 업데이트를 제공합니다. 따라서 델타가 커서 더 큰 다운로드가 생성될 수 있습니다.

> [!IMPORTANT]
> Windows Server Update Service 또는 Microsoft Update 이후에 [Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx) 보안 인텔리전스 페이지 업데이트를 폴백 원본으로 설정한 경우 현재 업데이트가 최신 버전이 아니면 보안 인텔리전스 업데이트에서만 업데이트가 다운로드됩니다. 기본적으로 이 날짜는 7일 연속으로 Windows 서버 업데이트 서비스 또는 Microsoft 업데이트 서비스에서 업데이트를 적용할 수 없습니다.
> 그러나 보호가 기한이 지난 것으로 보고되기 전까지의 일 수를 설정할 [수 있습니다.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)<p>
> 2019년 10월 21일 월요일부터 보안 인텔리전스 업데이트는 SHA-2 전용으로 서명됩니다. 최신 보안 인텔리전스 업데이트를 다운로드하려면 SHA-2를 지원하기 위해 장치를 업데이트해야 합니다. 자세한 내용은 Windows [및 WSUS에 대한 2019 SHA-2 코드 서명 지원 요구 사항을 참조합니다.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)

각 원본에는 다음 표에 설명된 바와 같이 네트워크 구성 방식과 업데이트를 게시하는 정도에 따라 달라지는 일반적인 시나리오가 있습니다.

<br/><br/>

|위치|샘플 시나리오|
|---|---|
|Windows 서버 업데이트 서비스|서버 업데이트 Windows 사용하여 네트워크의 업데이트를 관리하고 있습니다.|
|Microsoft 업데이트|끝점이 Microsoft 업데이트에 직접 연결하게 하려는 경우 이 기능은 엔터프라이즈 네트워크에 불규칙하게 연결되는 끝점이나 업데이트 관리에 Windows 서버 업데이트 서비스를 사용하지 않는 경우 유용할 수 있습니다.|
|파일 공유|인터넷에 연결되지 않은 장치(예: VM)가 있습니다. 인터넷에 연결된 VM 호스트를 사용하여 VM이 업데이트를 받을 수 있는 네트워크 공유에 대한 업데이트를 다운로드할 수 있습니다. [VDI(가상](deployment-vdi-microsoft-defender-antivirus.md) 데스크톱 인프라) 환경에서 파일 공유를 사용하는 방법에 대한 자세한 내용은 VDI 배포 가이드를 참조하세요.|
|Microsoft Endpoint Manager|를 사용하여 Microsoft Endpoint Manager 끝점을 업데이트합니다.|
|맬웨어 및 Microsoft Defender 바이러스 백신 Microsoft 맬웨어 방지(이전의 MMPC)에 대한 보안 인텔리전스 업데이트|[SHA-2를 지원하기 위해](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)장치가 업데이트되어 있는지 확인 Microsoft Defender 바이러스 백신 보안 인텔리전스 업데이트는 Windows 업데이트를 통해 전달됩니다. 2019년 10월 21일 월요일부터 보안 인텔리전스 업데이트는 SHA-2만 서명됩니다. <br/>최근 감염으로 인하여 최신 보호 업데이트를 다운로드하거나 VDI 배포에 대한 강력한 기본 이미지를 [프로비전하는 데 도움이 됩니다.](deployment-vdi-microsoft-defender-antivirus.md) 이 옵션은 일반적으로 기본 원본이 아닌 최종 대체 원본으로만 사용해야 합니다. 지정된 일 수 동안 Windows 서버 업데이트 서비스 또는 Microsoft 업데이트에서 업데이트를 다운로드할 수 없는 경우만 [사용됩니다.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)|

그룹 정책, 업데이트 원본, PowerShell cmdlet 및 WMI에서 업데이트 Microsoft Endpoint Configuration Manager 순서를 관리할 수 있습니다.

> [!IMPORTANT]
> 서버 Windows 서비스를 다운로드 위치로 설정하는 경우 위치를 지정하는 데 사용하는 관리 도구에 관계없이 업데이트를 승인해야 합니다. Windows 서버 업데이트 서비스를 사용하여 자동 승인 규칙을 설정할 수 있습니다. 이 규칙은 업데이트가 적어도 Windows 때 유용할 수 있습니다. 자세한 내용은 독립 실행형 서버 업데이트 서비스에서 끝점 보호 Windows [동기화를 참조하세요.](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

이 문서의 절차에서는 먼저 주문을 설정하는 방법을 설명한  다음 파일 공유 옵션을 사용하도록 설정한 경우 설정하는 방법을 설명합니다.

## <a name="use-group-policy-to-manage-the-update-location"></a>그룹 정책을 사용하여 업데이트 위치 관리

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**

4. 트리를 확장하여 서명 **Windows 구성 Windows Defender** 구성 요소를 \>  \> **확장하고** 다음 설정을 구성합니다.

   1. 보안 인텔리전스 업데이트 다운로드를 위한 원본 순서 정의 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.** 

   2. 다음 스크린샷과 같이 소스 순서를 단일 파이프로 구분하여 입력합니다( 예: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` ).

      :::image type="content" source="../../media/wdav-order-update-sources.png" alt-text="그룹 정책 설정에서 원본 순서를 나열합니다.":::

   3. **확인** 을 선택합니다. 이렇게 하면 보호 업데이트 원본의 순서가 설정됩니다.

   4. 보안 인텔리전스 업데이트 다운로드를 위한 파일 **공유** 정의 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**

   5. 파일 공유 원본을 지정합니다. 원본이 여러 개 있는 경우 각 원본을 사용할 순서대로 단일 파이프로 구분하여 입력합니다. 경로를 [나타 내는](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) 데 표준 UNC 주석을 사용 합니다( 예: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` ). 경로를 입력하지 않는 경우 VM에서 업데이트를 다운로드할 때 이 원본을 건너뜁니다.

   6. **확인** 을 클릭합니다. 이렇게 하면 원본이 원본 순서 **정의...** 그룹 정책 설정에서 참조될 때 파일 공유의 순서가 설정됩니다.

> [!NOTE]
> Windows 10 버전 1703에서 1809까지의 정책 경로는 Windows **Components > Microsoft Defender 바이러스 백신 > Signature Updates** for Windows 10, version 1903인 경우 정책 경로는 Windows **Components > Microsoft Defender 바이러스 백신 > Security Intelligence Updates입니다.**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Configuration Manager를 사용하여 업데이트 위치 관리

보안 [인텔리전스](/configmgr/protect/deploy-use/endpoint-definition-updates) 업데이트 구성(Endpoint Protection 현재 분기)에 대한 자세한 Microsoft Endpoint Manager 구성을 참조하세요.

## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>PowerShell cmdlet을 사용하여 업데이트 위치 관리

다음 PowerShell cmdlet을 사용하여 업데이트 순서를 설정할 수 있습니다.

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```

자세한 내용은 다음 문서를 참조하세요.

- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [PowerShell cmdlet을 사용하여 구성 및 실행 Microsoft Defender 바이러스 백신](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender cmdlet](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>WMI(Windows 관리 명령)를 사용하여 업데이트 위치 관리

다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

자세한 내용은 다음 문서를 참조하세요.

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>MDM(모바일 장치 관리)을 사용하여 업데이트 위치 관리

MDM 구성에 대한 자세한 내용은 정책 [CSP - Defender/SignatureUpdateFallbackOrder를](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) 참조합니다.

## <a name="what-if-were-using-a-third-party-vendor"></a>타사 공급업체를 사용 중이면 어떻게 하나요?

이 문서에서는 사용자에 대한 업데이트를 구성하고 관리하는 방법을 Microsoft Defender 바이러스 백신. 그러나 타사 공급업체를 사용하여 이러한 작업을 수행할 수 있습니다.

예를 들어 Contoso가 Fabrikam을 고용하여 보안 솔루션을 관리했다고 가정해 Microsoft Defender 바이러스 백신. Fabrikam은 일반적으로 Windows [관리](./use-wmi-microsoft-defender-antivirus.md)계측, [PowerShell cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md) [](./command-line-arguments-microsoft-defender-antivirus.md) 또는 Windows 명령줄을 사용하여 패치 및 업데이트를 배포합니다.

> [!NOTE]
> Microsoft는 타사 솔루션을 관리하기 위한 타사 솔루션을 테스트하지 Microsoft Defender 바이러스 백신.

<a id="unc-share"></a>

## <a name="create-a-unc-share-for-security-intelligence-updates"></a>보안 인텔리전스 업데이트용 UNC 공유 만들기

네트워크 파일 공유(UNC/매핑된 드라이브)를 설정하여 예약된 작업을 사용하여 MMPC 사이트에서 보안 인텔리전스 업데이트를 다운로드합니다.

1. 공유를 프로비전하고 업데이트를 다운로드할 시스템에서 스크립트를 저장할 폴더를 생성합니다.

    ```console
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. 서명 업데이트를 저장할 폴더를 생성합니다.

    ```console
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. 에서 PowerShell 스크립트를 [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4.](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)

4. 수동 **다운로드를 클릭합니다.**

5. 원시 **nupkg 파일 다운로드를 클릭합니다.**

6. 파일을 추출합니다.

7. 파일을 SignatureDownloadCustomTask.ps1 C:\Tool\PS-Scripts\ 폴더에 복사합니다.

8. 명령줄을 사용하여 예약된 작업을 설정할 수 있습니다.

   > [!NOTE]
   > 업데이트 유형에는 전체 업데이트와 델타의 두 가지 유형이 있습니다.

   - x64 델타의 경우:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - x64 전체:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - x86 델타의 경우:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - x86 전체:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   > [!NOTE]
   > 예약된 작업이 만들어지면 작업 스케줄러의 Microsoft\Windows\Windows Defender

9. 각 작업을 수동으로 실행하고 다음 폴더에 데이터(mpam-d.exe, mpam-fe.exe 및 nis_full.exe)가 있는지 확인합니다(다른 위치를 선택했습니다).

   - C:\Temp\TempSigs\x86
   - C:\Temp\TempSigs\x64

   예약된 작업이 실패하면 다음 명령을 실행합니다.

    ```console
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```

    > [!NOTE]
    > 실행 정책으로 인해 문제가 될 수도 있습니다.

10. C:\Temp\TempSigs(예: 서버\업데이트)를 포인터로 설정하는 \\ 공유를 생성합니다.

    > [!NOTE]
    > 인증된 사용자는 최소한 "읽기" 액세스 권한이 있어야 합니다.

11. 정책의 공유 위치를 공유로 설정

    > [!NOTE]
    > 경로에 x64(또는 x86) 폴더를 추가하지 않습니다. 이 mpcmdrun.exe 자동으로 추가됩니다.

## <a name="related-articles"></a>관련 문서

- [배포 Microsoft Defender 바이러스 백신](deploy-manage-report-microsoft-defender-antivirus.md)
- [업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md)
- [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md)
- [모바일 장치 및 VM에 대한 업데이트 관리](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
