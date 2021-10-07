---
title: 제어된 폴더 액세스 사용자 지정
description: 제어된 폴더 액세스로 보호해야 하는 다른 폴더를 추가하거나 중요한 파일의 변경 내용을 잘못 차단하는 앱을 허용합니다.
keywords: 제어된 폴더 액세스, windows 10, windows defender, 랜섬웨어, 보호, 파일, 폴더, 사용자 지정, 폴더 추가, 앱 추가, 허용, 실행 파일 추가
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 88ecdbdc5055a954a2bd163697eac144edf0b2bc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178470"
---
# <a name="customize-controlled-folder-access"></a>제어된 폴더 액세스 사용자 지정

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

제어된 폴더 액세스는 랜섬웨어와 같은 악성 앱 및 위협으로부터 중요한 데이터를 보호하는 데 도움이 됩니다. 제어된 폴더 액세스는 Windows Server 2019, Windows Server 2022 및 Windows 10 지원됩니다. 이 문서에서는 제어된 폴더 액세스 기능을 사용자 지정하는 방법을 설명하고 다음 섹션을 포함합니다.

- [추가 폴더 보호](#protect-additional-folders)
- [보호된 폴더에 액세스할 수 있도록 허용해야 하는 앱 추가](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [서명된 실행 파일이 보호된 폴더에 액세스하도록 허용](#allow-signed-executable-files-to-access-protected-folders)
- [알림 사용자 지정](#customize-the-notification)

> [!IMPORTANT]
> 제어된 폴더 액세스는 악성으로 감지된 활동이 앱을 모니터링합니다. 경우에 따라 합법적인 앱이 파일을 변경하지 않습니다. 제어된 폴더 액세스가 조직의 생산성에 영향을 미치는 경우 감사 [](audit-windows-defender.md) 모드에서 이 기능을 실행하여 영향을 완전히 평가할 수 있습니다.

## <a name="protect-additional-folders"></a>추가 폴더 보호

제어된 폴더 액세스는 문서, 사진, 영화 등의 폴더를 비롯한 여러 시스템 폴더 및 기본 위치에 **적용됩니다.** 보호할 다른 폴더를 추가할 수 있지만 기본 목록에서 기본 폴더를 제거할 수는 없습니다.

제어된 폴더 액세스에 다른 폴더를 추가하면 기본 Windows 라이브러리에 파일을 저장하지 않는 경우나 라이브러리의 기본 위치를 변경한 경우에 유용할 수 있습니다.

네트워크 공유 및 매핑된 드라이브를 지정할 수 있습니다. 환경 변수 및 와일드카드가 지원됩니다. 와일드카드 사용에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에 와일드카드 사용을 [참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

Windows 보안, 그룹 정책, PowerShell cmdlet 또는 모바일 장치 관리 구성 서비스 공급자를 사용하여 보호된 폴더를 추가 및 제거할 수 있습니다.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>앱 Windows 보안 사용하여 추가 폴더 보호

1. 작업 Windows 보안 방패 아이콘을 선택하거나 작업 표시줄에서 보안을 검색하여  시작 메뉴.

2. 바이러스 **& 보호를** 선택한 다음 **아래로 스크롤하여 랜섬웨어 보호 섹션으로 스크롤합니다.**

3. **랜섬웨어 보호 관리를** 선택하여 **랜섬웨어** 보호 창을 여는 방법을 선택합니다.

4. 제어된 **폴더 액세스 섹션에서** 보호된 폴더 **를 선택합니다.**

5. 사용자 **액세스** 제어 프롬프트에서 **예를** 선택 합니다. 보호된 **폴더 창이** 표시됩니다.

6. 보호된 **폴더 추가를 선택하고** 프롬프트에 따라 폴더를 추가합니다.

### <a name="use-group-policy-to-protect-additional-folders"></a>그룹 정책을 사용하여 추가 폴더 보호

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)을 엽니다. 

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**

3. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성** 정책 관리 \>  \> **템플릿으로 이동하십시오.**

4. Exploit Guard **제어된 폴더 Windows Microsoft Defender 바이러스 백신** Windows Defender 구성 요소를 \>  \>  \> **확장합니다.** <br/>**참고:** 이전 버전의 Windows 에 를 표시하지 않고 Windows Defender 바이러스 백신 수 **Microsoft Defender 바이러스 백신.** 

5. 보호된 폴더 구성을 두 번 **클릭한** 다음 옵션을 사용으로 **설정합니다.** **표시를** 선택하고 보호할 각 폴더를 지정합니다.

6. 일반적으로 그룹 정책 개체를 배포합니다.

### <a name="use-powershell-to-protect-additional-folders"></a>PowerShell을 사용하여 추가 폴더 보호

1. 목록에서 **PowerShell을** 시작 메뉴 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**

2. 다음 PowerShell cmdlet을 입력하고 폴더의 경로(예: )로 `<the folder to be protected>` `"c:\apps\"` 대체합니다.

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. 보호할 각 폴더에 대해 2단계를 반복합니다. 보호된 폴더는 앱의 Windows 보안 표시됩니다.

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="cmdlet이 표시된 PowerShell 창":::

> [!IMPORTANT]
> 를 사용하지 말고 목록에 `Add-MpPreference` 앱을 추가하거나 추가하는 데 사용하세요. `Set-MpPreference` `Set-MpPreference`cmdlet을 사용하여 기존 목록을 덮어 습니다.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>MDM CSP를 사용하여 추가 폴더 보호

[./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) CSP(구성 서비스 공급자)를 사용하여 앱이 보호된 폴더를 변경할 수 있도록 합니다.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>특정 앱이 제어된 폴더를 변경할 수 있도록 허용

특정 앱이 항상 안전한 것으로 간주되는지 지정하고 보호된 폴더의 파일에 대한 쓰기 권한을 부여할 수 있습니다. 앱 허용은 사용자가 알고 신뢰하는 특정 앱이 제어된 폴더 액세스 기능으로 차단되는 경우 유용할 수 있습니다.

> [!IMPORTANT]
> 기본적으로 Windows 목록에 친숙한 것으로 간주되는 앱을 추가합니다. 자동으로 추가되는 이러한 앱은 Windows 보안 또는 연결된 PowerShell cmdlet을 사용하여 기록되지 않습니다. 대부분의 앱을 추가할 필요가 없습니다. 앱이 차단되고 있으며 신뢰할 수 있는지 확인할 수 있는 앱만 추가합니다.

앱을 추가할 때 앱의 위치를 지정해야 합니다. 해당 위치에 있는 앱만 보호된 폴더에 액세스할 수 있습니다. 이름이 같은 앱이 다른 위치에 있는 경우 앱이 허용 목록에 추가되지 않습니다. 제어된 폴더 액세스로 차단될 수 있습니다.

허용된 응용 프로그램 또는 서비스는 시작된 후에만 제어된 폴더에 대한 쓰기 권한이 있습니다. 예를 들어 업데이트 서비스는 중지했다가 다시 시작할 때까지 허용된 후에도 이벤트를 계속 트리거합니다.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>보안 Windows Defender 사용하여 특정 앱 허용

1. 보안의 시작 Windows 보안 검색하여 앱 앱을 열 **수 있습니다.**

2. 바이러스 & **위협** 방지 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택한 다음 **랜섬웨어** 보호 관리를 선택합니다.

3. 제어된 **폴더 액세스 섹션에서** 제어된 폴더 액세스를 **통해 앱 허용을 선택합니다.**

4. 허용된 **앱 추가를 선택하고** 프롬프트에 따라 앱을 추가합니다.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="허용된 앱 단추를 추가합니다.":::

### <a name="use-group-policy-to-allow-specific-apps"></a>그룹 정책을 사용하여 특정 앱 허용

1. 그룹 정책 관리 장치에서 그룹 정책 관리 콘솔을 [열고](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**

2. **그룹 정책 관리 편집기** 에서 **컴퓨터 구성** 으로 이동하여 **관리 템플릿** 을 선택합니다.

3. Exploit Guard **제어된 폴더 Windows Microsoft Defender 바이러스 백신** Windows Defender 구성 요소를 \>  \>  \> **확장합니다.**

4. 허용되는 응용 프로그램 **구성 설정을 두** 번 클릭하고 옵션을 사용으로 **설정합니다.** 표시를 **선택하고** 각 앱을 입력합니다.

### <a name="use-powershell-to-allow-specific-apps"></a>PowerShell을 사용하여 특정 앱 허용

1. 목록에서 **PowerShell을** 시작 메뉴 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**
2. 다음 cmdlet을 입력합니다.

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    예를 들어 *C:\apps* test.exe있는 실행 파일을 추가하는 경우 cmdlet은 다음과 같습니다. 

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   계속 사용하여 목록에 앱을 `Add-MpPreference -ControlledFolderAccessAllowedApplications` 더 추가합니다. 이 cmdlet을 사용하여 추가된 앱은 앱의 Windows 보안 표시됩니다.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="앱을 허용하는 PowerShell cmdlet입니다.":::

> [!IMPORTANT]
> 목록에 `Add-MpPreference` 앱을 추가하거나 추가하는 데 사용할 수 있습니다. `Set-MpPreference`cmdlet을 사용하여 기존 목록을 덮어 습니다.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>MDM CSP를 사용하여 특정 앱 허용

[./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) CSP(구성 서비스 공급자)를 사용하여 앱이 보호된 폴더를 변경할 수 있도록 합니다.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>서명된 실행 파일이 보호된 폴더에 액세스하도록 허용

Microsoft Defender for Endpoint 인증서 및 파일 표시기는 서명된 실행 파일이 보호된 폴더에 액세스할 수 있도록 허용할 수 있습니다. 구현에 대한 자세한 내용은 [인증서를 기반으로 지표 만들기를 참조합니다.](indicator-certificates.md)

> [!Note]
> Powershell을 포함한 스크립팅 엔진에는 적용되지 않습니다.

## <a name="customize-the-notification"></a>알림 사용자 지정

규칙이 트리거된 후 앱 또는 파일을 차단할 때 알림을 사용자 지정하는 데 대한 자세한 내용은 [Configure alert notifications in Microsoft Defender for Endpoint을 참조하세요.](configure-email-notifications.md)

## <a name="see-also"></a>참고 항목

- [제어된 폴더 액세스를 사용하여 중요한 폴더 보호](controlled-folders.md)
- [제어된 폴더 액세스 사용](enable-controlled-folders.md)
- [공격 표면 감소 규칙 평가](evaluate-attack-surface-reduction.md)
