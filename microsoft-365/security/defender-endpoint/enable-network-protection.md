---
title: 네트워크 보호 설정 켜기
description: 그룹 정책, PowerShell 또는 모바일 장치 관리 및 구성 관리자를 사용하여 네트워크 보호를 사용하도록 설정하세요.
keywords: ANetwork 보호, 악용, 악성 웹 사이트, ip, 도메인, 사용, 켜기
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e0056f4f1517962bab3dbee4f993ce28c58dfcf9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222753"
---
# <a name="turn-on-network-protection"></a>네트워크 보호 설정 켜기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[네트워크 보호는](network-protection.md) 직원이 응용 프로그램을 사용하여 인터넷에서 피싱 사기, 악용 및 기타 악성 콘텐츠를 호스팅할 수 있는 위험한 도메인에 액세스하지 못하게 하는 데 도움이 됩니다. 테스트 [환경에서 네트워크](evaluate-network-protection.md) 보호를 감사하여 사용하도록 설정하기 전에 차단되는 앱을 볼 수 있습니다.

[네트워크 필터링 구성 옵션에 대해 자세히 알아보시다](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>네트워크 보호를 사용하도록 설정되어 있는지 확인

레지스트리 편집기를 사용하여 로컬 장치에서 네트워크 보호가 활성화되어 있는지 확인합니다.

1. 작업 **표시줄에서 시작** 단추를 선택하고 **regedit를** 입력하여 레지스트리 편집기를 여십시오.

2. 왼쪽 **HKEY_LOCAL_MACHINE** 메뉴에서 선택을 선택합니다.

3. 중첩된 메뉴를 탐색하여  Exploit Guard 네트워크 보호를 Windows Defender \>  \>  \> **Windows Defender** \> **소프트웨어** \> **정책으로 이동합니다.**

4. **EnableNetworkProtection을** 선택하여 디바이스에서 네트워크 보호의 현재 상태를 확인합니다.

   - 0 또는 **끄기**
   - 1 또는 
   - 2 또는 **감사** 모드

    ![네트워크 보호 레지스트리 키.](../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png)

## <a name="enable-network-protection"></a>네트워크 보호 사용

다음 방법을 사용하여 네트워크 보호를 사용하도록 설정하십시오.

- [PowerShell](#powershell)
- [MDM(모바일 장치 관리)](#mobile-device-management-mdm)
- [Microsoft Endpoint Manager / Intune](#microsoft-endpoint-manager-formerly-intune)
- [그룹 정책](#group-policy)

### <a name="powershell"></a>PowerShell

1. 목록에서 **powershell을** 시작 메뉴 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**
2. 다음 cmdlet을 입력합니다.

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. 선택 사항: 다음 cmdlet을 사용하여 감사 모드에서 기능을 사용하도록 설정

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    대신 `Disabled` 또는 `AuditMode` 기능을 `Enabled` 끄는 데 사용합니다.

### <a name="mobile-device-management-mdm"></a>모바일 장치 관리(MDM)

[./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) CSP(구성 서비스 공급자)를 사용하여 네트워크 보호를 사용하도록 설정하거나 감사 모드를 사용하도록 설정할 수 있습니다.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager(이전의 Intune)

1. Microsoft Endpoint Manager 센터( 에 https://endpoint.microsoft.com) 로그인합니다.

2. 장치 **구성**  >  **프로필 프로필**  >  **만들기로 이동하세요.**

3. 프로필 **만들기 플라이아웃에서** 템플릿 목록에서 **끝점** 보호를 선택한 다음 만들기를 **선택합니다.**

4. **끝점 보호**  >  **기본으로 이동하여** 프로필 이름을 입력한 후 다음 을 **선택합니다.**

5. 구성 **설정 섹션에서** 네트워크 필터링 **네트워크 Microsoft Defender Exploit Guard** 사용 또는 감사로  >    >    >   **이동합니다.** **다음** 을 선택합니다.

6. 조직에서 **요구하는** 적절한 범위 태그, **할당** 및 적용성 규칙을 선택합니다.  관리자는 더 많은 요구 사항을 설정할 수 있습니다.

7. 모든 정보를 검토한 다음 만들기를 **선택합니다.**

### <a name="group-policy"></a>그룹 정책

다음 절차에 따라 도메인에 가입된 컴퓨터 또는 독립 실행형 컴퓨터에서 네트워크 보호를 사용하도록 설정할 수 있습니다.

1. 독립 실행형 컴퓨터에서 시작으로  이동한 다음 그룹 정책 편집을 **선택합니다.**

    *-Or-*

    도메인에 가입된 그룹 정책 관리 컴퓨터에서 [](https://technet.microsoft.com/library/cc731212.aspx)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**

2. **그룹 정책 관리 편집기** 에서 **컴퓨터 구성** 으로 이동하여 **관리 템플릿** 을 선택합니다.

3. Exploit Guard **네트워크 보호를 Windows 구성** Microsoft Defender 바이러스 백신 \>  \> **Windows Defender** \> **확장합니다.**

   > [!NOTE]
   > 이전 버전의 Windows 그룹 정책 경로는 "Windows Defender 바이러스 백신"가 아니라 "Microsoft Defender 바이러스 백신"라고 말할 수 있습니다.

4. 사용자 및  앱이 위험한 웹 사이트에 액세스하지 못하게 방지 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.** 옵션 섹션에서 다음 옵션 중 하나를 지정해야 합니다.
    - **차단** - 사용자가 악성 IP 주소 및 도메인에 액세스할 수 없습니다.
    - **사용 안 하게(기본값)** - 네트워크 보호 기능이 작동하지 않습니다. 사용자가 악의적인 도메인에 액세스하는 것을 차단하지 않습니다.
    - **감사 모드** - 사용자가 악성 IP 주소 또는 도메인을 방문하면 이벤트가 Windows 기록됩니다. 그러나 사용자가 주소를 방문하지 못하도록 차단되지는 않습니다.

> [!IMPORTANT]
> 네트워크 보호를 완전히 사용하도록 설정하려면 그룹  정책 옵션을  사용으로 설정하고 옵션 드롭다운 메뉴에서 차단을 선택해야 합니다.

레지스트리 편집기를 사용하여 로컬 컴퓨터에서 네트워크 보호가 사용하도록 설정되어 있는지 확인합니다.

1. 시작을 **선택하고** **regedit를** 입력하여 **레지스트리 편집기를 열 수 있습니다.**

2. 사이트 **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**

3. **EnableNetworkProtection을 선택하고** 값을 확인 합니다.
   - 0=해제
   - 1=켜기
   - 2=감사

## <a name="see-also"></a>참고 항목

- [네트워크 보호](network-protection.md)

- [네트워크 보호 및 TCP 3차원 핸드세이크](network-protection.md#network-protection-and-the-tcp-three-way-handshake)

- [네트워크 보호 평가](evaluate-network-protection.md)

- [네트워크 보호 문제 해결](troubleshoot-np.md)
