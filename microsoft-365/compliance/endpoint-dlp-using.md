---
title: 끝점 데이터 손실 방지 사용
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: DLP(데이터 손실 방지) 정책을 구성하여 Microsoft 365 끝점 데이터 손실 방지(EPDLP) 위치를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: eb42d43db8edf0bad02e66a5ee4e2853b8d42878
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756028"
---
# <a name="using-endpoint-data-loss-prevention"></a>끝점 데이터 손실 방지 사용

이 문서에서는 장치를 위치로 사용하는 DLP 정책을 만들고 수정하는 4가지 시나리오를 안내합니다.

## <a name="dlp-settings"></a>DLP 설정

시작하기 전에 DLP 설정을 지정해야 합니다. 설정은 장치의 모든 DLP 정책에 적용됩니다. 적용되는 정책을 만들려면 다음을 반드시 구성해야 합니다.

- 클라우드 송신 제한 사항
- 허용되지 않는 앱 제한 사항

또는

- 모니터링에서 잡음이 있는 파일 경로를 제외하려는 경우

  > [!div class="mx-imgBorder"]
  > ![DLP 설정](../media/endpoint-dlp-1-using-dlp-settings.png).

### <a name="advanced-classification-scanning-and-protection"></a>고급 분류 검색 및 보호

#### <a name="get-registered"></a>등록하기

이 기능에 액세스하려면 Microsoft에 테넌트를 등록해야 합니다. [등록하기](https://aka.ms/Ignite2021DLP)를 참조하세요.

사용하도록 설정하면 **고급 분류 검색 및 보호** 를 통해 고급 Microsoft 365 클라우드 기반 데이터 분류 서비스가 항목을 검색하고 분류하고 결과를 로컬 시스템에 반환할 수 있습니다. 즉, DLP 정책에서 [정확한 데이터 일치](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 분류, [명명된 항목(미리보기)](named-entities-learn.md#learn-about-named-entities-preview) 분류 기술을 활용할 수 있습니다.

고급 분류에서 콘텐츠는 스캔 및 분류를 위해 로컬 장치에서 클라우드 서비스로 전송됩니다. 대역폭 사용이 우려되는 경우 24시간 동안 사용할 수 있는 양에 대해 장치별로 적용되는 이 전역 설정에서 제한을 설정할 수 있습니다. 대역폭 사용 제한을 설정하고 이를 초과하면 DLP가 사용자 콘텐츠를 클라우드로 보내는 것을 중지하고 데이터 분류가 장치에서 로컬로 계속됩니다. 누적 대역폭 사용률이 롤링 24시간 제한 아래로 떨어지면 클라우드 서비스와의 통신이 다시 시작됩니다.

대역폭 사용률이 문제가 되지 않는 경우 제한을 설정하고 무제한 사용을 허용할 수 없습니다.

> [!NOTE]
> DLP 정책 평가는 사용자 콘텐츠가 전송되지 않는 경우에도 항상 클라우드에서 발생합니다.

### <a name="endpoint-dlp-windows-10-and-macos-settings"></a>Endpoint DLP Windows 10 및 macOS 설정

macOS 지원에 액세스하려면 Microsoft에 테넌트를 등록해야 합니다. [등록하기](https://aka.ms/Ignite2021DLP)를 참조하세요.

|설정 |Windows 10, 1809 이상  |macOS Catalina 10.15 이상(미리 보기)  |메모  |
|---------|---------|---------|---------|
|파일 경로 제외     |지원         |지원         |macOS에는 기본적으로 켜져 있는 권장 제외 목록이 포함되어 있습니다.          |
|허용되지 않는 앱     |지원         |지원         |         |
|허용되지 않는 Bluetooth 앱    |지원         |지원되지 않음         |         |
|중요한 항목에 대한 브라우저 및 도메인 제한      |지원         |지원         |         |
|엔드포인트 DLP에 대한 추가 설정     |지원         |지원         |macOS 장치에는 기본 비즈니스 근거만 지원됩니다.         |
|장치에 대한 파일 활동 항상 감사     |지원         |지원         |         |



### <a name="file-path-exclusions"></a>파일 경로 제외

[규정 준수 센터](https://compliance.microsoft.com) > **데이터 손실 방지** > **Endpoint DLP 설정** > **파일 경로 제외** 를 엽니다.

지나치게 잡음이 많거나 관심 있는 파일을 포함하지 않으므로 장치에서 DLP 모니터링, DLP 경고, DLP 정책 적용에서 특정 경로를 제외하고자 할 수 있습니다. 해당 위치에서 파일을 감사하지 않으며 해당 위치에서 만들어지거나 수정된 모든 파일에 DLP 정책 적용이 적용되지 않습니다. DLP 설정에서 경로 제외를 구성할 수 있습니다.

#### <a name="windows-10-devices"></a>Windows 10 장치

이 논리를 사용하여 Windows 10 장치에 대한 제외 경로를 구성할 수 있습니다.

- ‘\로 끝나는 올바른 파일 경로입니다. 이는 폴더 바로 아래에 있는 파일만을 의미합니다. <br/>예시: C:\Temp\

- 폴더 바로 아래에 있는 파일 외에 하위 폴더 아래에 있는 파일만 의미하는 '\*'로 끝나는 유효한 파일 경로입니다. <br/>예시: C:\Temp\*

- '\' 또는 '\*' 없이 끝나는 유효한 파일 경로는 폴더 및 모든 하위 폴더 바로 아래에 있는 모든 파일을 의미합니다. <br/>예시: C:\Temp

- 각 면의 '\' 사이에 와일드카드가 있는 경로입니다. <br/>예시: C:\Users\*\Desktop\

- 정확한 하위 폴더 수를 제공하기 위해 각 면의 '\' 사이에 와일드카드와 '(숫자)'가 있는 경로입니다. <br/>예시: C:\Users\*(1)\Downloads\

- 시스템 환경 변수를 사용하는 경로입니다. <br/>예시: %SystemDrive%\Test\*

- 위의 모든 것을 혼합한 것입니다. <br/>예시: %SystemDrive%\Users\*\Documents\*(2)\Sub\

#### <a name="macos-devices-preview"></a>macOS 장치(미리 보기)

Windows 10 장치와 유사하게 macOS 장치에 대한 고유한 제외를 추가할 수 있습니다.

- 파일 경로 정의는 대소문자를 구분하지 않으므로 `User`은(는) `user`과(와) 동일합니다.

- 와일드카드 값이 지원됩니다. 따라서 경로 정의는 경로 중간 또는 경로 끝에 `*`을(를) 포함할 수 있습니다. 예: `/Users/*/Library/Application Support/Microsoft/Teams/*`

#####  <a name="recommended-file-path-exclusions-preview"></a>권장 파일 경로 제외(미리 보기)

성능상의 이유로 Endpoint DLP에는 macOS 장치에 대한 권장 파일 경로 제외 목록이 포함되어 있습니다. 이러한 제외는 기본적으로 켜져 있습니다. 원하는 경우 **Mac용 권장 파일 경로 제외 포함** 토글을 토글하여 비활성화할 수 있습니다. 목록에는 다음이 포함됩니다.

- /Applications/*
- /System/*
- /usr/*
- /Library/*
- /private/*
- /opt/*
- /Users/*/Library/Application Support/Microsoft/Teams/*

### <a name="unallowed-apps"></a>허용되지 않는 앱

허용되지 않는 앱은 DLP로 보호된 파일에 액세스할 수 없도록 만든 애플리케이션 목록입니다. Windows 10 및 macOS 장치(미리 보기)에서 사용할 수 있습니다.

정책의 **허용되지 않은 앱에 의한 액세스** 설정이 켜져 있고 허용되지 않은 목록에 있는 앱이 보호된 파일에 액세스하려고 하면 활동이 허용, 차단 또는 차단되지만 사용자는 제한을 재정의할 수 있습니다. 모든 활동을 감사하며 활동 탐색기에서 검토할 수 있습니다.

> [!IMPORTANT]
> 실행 파일 이름(예: 브라우저.exe)은 포함해야 하지만 실행 파일 경로는 포함하지 않아야 합니다.

#### <a name="macos-devices-preview"></a>macOS 장치(미리 보기)

Windows 장치와 마찬가지로 이제 macOS 앱이 **허용되지 않는 앱** 목록에서 중요한 데이터에 액세스하는 것을 방지할 수 있습니다. 

> [!NOTE]
> 플랫폼 간 앱은 실행 중인 OS에 따라 고유한 경로로 입력해야 합니다.

Mac 앱의 전체 경로를 찾으려면:
1. macOS 장치에서 **활동 모니터** 를 엽니다. 제한하려는 프로세스를 찾아 두 번 클릭합니다.

2. **파일 및 포트 열기** 탭을 선택합니다.
  
3. 앱 이름은 전체 경로의 끝에 있습니다.


#### <a name="protect-sensitive-data-from-cloud-synchronization-apps"></a>클라우드 동기화 앱에서 중요한 데이터 보호

*onedrive.exe* 와 같은 클라우드 동기화 앱이 중요한 항목을 클라우드에 동기화하지 못하도록 하려면 클라우드 동기화 앱을 **허용되지 않는 앱** 목록에 추가하세요. 허용되지 않은 클라우드 동기화 앱이 차단 DLP 정책으로 보호되는 항목에 액세스하려고 하면 DLP가 반복적인 알림을 생성할 수 있습니다. **허용되지 않는 앱** 에서 **자동 격리** 옵션을 사용하도록 설정하면 이러한 반복 알림을 방지할 수 있습니다.  

##### <a name="auto-quarantine-preview"></a>자동 격리(미리 보기)

> [!NOTE]
> 자동 격리는 Windows 10만 지원됩니다.

활성화하면 허용되지 않은 앱이 DLP로 보호되는 중요한 항목에 액세스하려고 할 때 자동 격리가 시작됩니다. 자동 격리는 중요한 항목을 관리자가 구성한 폴더로 이동하고 원본 위치에 자리 표시자 **.txt** 파일을 남길 수 있습니다. 항목이 이동된 위치 및 기타 관련 정보를 사용자에게 알리도록 자리 표시자 파일의 텍스트를 구성할 수 있습니다.  

자동 격리를 사용하여 사용자와 관리자에 대한 DLP 알림의 끝없는 체인을 방지할 수 있습니다. [시나리오 4: 자동 격리를 사용하여 클라우드 동기화 앱에서 DLP 알림 반복 방지(미리 보기)](#scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview)를 참조하세요.

### <a name="unallowed-bluetooth-apps"></a>허용되지 않는 Bluetooth 앱

특정 Bluetooth 앱을 통해 정책에 의해 보호되는 파일을 전송하지 못하게 합니다.

### <a name="browser-and-domain-restrictions-to-sensitive-data"></a>중요한 데이터에 대한 브라우저 및 도메인 제한

정책과 일치하는 중요한 파일을 무제한 클라우드 서비스 도메인에 공유하지 못하도록 제한합니다.

#### <a name="unallowed-browsers"></a>허용되지 않는 브라우저

클라우드 서비스 제한에 업로드가 차단 또는 재설정을 차단하는 것으로 설정되어 있는 적용된 DLP 정책의 조건과 일치하는 파일에 액세스하지 못하도록 차단된 실행 파일 이름으로 식별되는 브라우저를 추가합니다. 이 브라우저가 파일에 액세스하지 못하도록 차단되면 최종 사용자에게 Edge Chromium를 통해 파일을 열도록 요청하는 알림 메시지가 표시됩니다.

#### <a name="service-domains"></a>서비스 도메인

정책으로 보호되는 중요한 파일을 Microsoft Edge의 특정 서비스 도메인에 업로드할 수 있는지 여부를 제어할 수 있습니다.

목록 모드가 **차단** 으로 설정되어 있으면 사용자는 해당 도메인에 중요한 항목을 업로드할 수 없습니다. 항목이 DLP 정책과 일치하여 업로드 작업이 차단되면 DLP가 경고를 생성하거나 중요한 항목의 업로드를 차단합니다.

목록 모드가 **허용** 으로 설정되어 있으면 사용자는 해당 도메인에 **_오직_** 중요한 항목만을 업로드할 수 있으며 다른 모든 도메인에 대한 업로드 액세스는 허용되지 않습니다.

> [!IMPORTANT]
> 서비스 제한 모드를 "허용"으로 설정한 경우 제한이 적용되기 전에 하나 이상의 서비스 도메인을 구성해야 합니다.

### <a name="additional-settings-for-endpoint-dlp"></a>끝점 DLP에 대한 추가 설정

#### <a name="business-justification-in-policy-tips"></a>정책 팁의 비즈니스 타당성

DLP 정책 팁 알림에서 사용자가 비즈니스 타당성 옵션과 상호 작용하는 방법을 제어할 수 있습니다. 이 옵션은 사용자가 DLP 정책에서 **재정의로 차단** 설정으로 보호되는 활동을 수행하는 경우 나타납니다. 전역 설정입니다. 다음 옵션 중 하나를 선택할 수 있습니다.

- **기준 옵션 및 사용자 지정 텍스트 상자 표시**: 기본적으로 사용자는 기본 제공 근거를 선택하거나 자신의 텍스트를 입력할 수 있습니다.
- **기본 옵션 표시**: 사용자는 기본 제공 근거만 선택할 수 있습니다.
- **사용자 지정 텍스트 상자 표시**: 사용자는 자신의 근거만 입력할 수 있습니다. 텍스트 상자만 최종 사용자 정책 팁 알림에 표시됩니다. 

##### <a name="customizing-the-options-in-the-drop-down-menu"></a>드롭다운 메뉴에서 옵션 사용자 지정 중

**옵션 드롭다운 메뉴 사용자 지정** 을 선택하여 사용자가 정책 알림 팁과 상호 작용할 때 표시되는 최대 5개의 사용자 지정된 옵션을 만들 수 있습니다. 


|옵션 |기본 텍스트  |
|---------|---------|
|옵션 1    | **이 작업은 설정된 비즈니스 워크플로의 일부입니다**. 또는 사용자 지정된 텍스트를 입력할 수 있습니다.        |
|옵션 2  |**관리자가 이 작업을 승인했거나** 사용자 지정된 텍스트를 입력할 수 있습니다.         |
|옵션 3   |**긴급 액세스가 필요합니다. 관리자에게 따로 알려드리거나** 사용자 지정된 텍스트를 입력할 수 있습니다.          |
|가양성 옵션 표시     |**이 파일의 정보는 중요하지 않습니다** 또는 사용자 지정된 텍스트를 입력할 수 있습니다.          |
|옵션 5    |**기타** 또는 사용자 지정된 텍스트를 입력할 수 있습니다.         |

<!--See, [Scenario 5: Configure a policy to use the customized business justification](#scenario-5-configure-a-policy-to-use-the-customized-business-justification)-->

### <a name="always-audit-file-activity-for-devices"></a>장치에 대한 파일 활동 항상 감사

기본적으로 장치가 온보딩되면 Office, PDF 및 CSV 파일에 대한 활동이 자동으로 감사되고 활동 탐색기에서 검토할 수 있게 됩니다. 온보딩된 장치가 활성 정책에 포함된 경우에만 이 활동을 감사하려면 이 기능을 끄세요.

온보딩된 장치에 대한 파일 활동은 활성 정책에 포함된지의 여부에 상관없이 항상 감사됩니다.

## <a name="tying-dlp-settings-together"></a>DLP 설정 함께 연결

끝점 DLP 및 Edge Chromium 웹 브라우저를 사용하여 중요한 항목이 허용되지 않는 클라우드 앱 및 서비스에 대한 의도하지 않은 공유를 제한할 수 있습니다. Edge Chromium은 항목이 끝점 DLP 정책으로 제한되는 경우에 대해 이해하고 액세스 제한을 적용합니다.

올바르게 구성된 DLP 정책 및 Edge Chromium 브라우저에서 끝점 DLP를 위치로 사용하는 경우 이러한 설정에 정의된 허용되지 않는 브라우저는 DLP 정책 컨트롤과 일치하는 중요한 항목에 액세스할 수 없습니다. 대신 사용자는 DLP 부과 제한 사항을 이해하고 DLP 정책의 조건이 충족될 때 활동을 차단하거나 제한할 수 있는 Edge Chromium을 사용하도록 리디렉션됩니다.

이 제한을 사용하려면 중요한 3가지 부분을 구성해야 합니다.

1. 중요한 항목이 공유되지 않도록 하려는 위치(서비스, 도메인, IP 주소)를 지정합니다.

2. DLP 정책이 일치하는 경우 특정 중요한 항목에 액세스할 수 없는 브라우저를 추가합니다.

3. **클라우드 서비스 업로드** 와 **허용되지 않은 브라우저에서 액세스** 설정을 사용하여 업로드가 해당 위치로 제한되어야 하는 중요한 항목의 종류를 정의하는 DLP 정책 구성

새 서비스, 앱 및 정책을 계속 추가하여 비즈니스 요구 사항을 충족하고 중요한 데이터를 보호하는 데 필요한 제한을 확장하고 강화할 수 있습니다. 

이 구성은 사용자가 중요하지 않은 항목에 액세스하고 공유하지 못하도록 하는 불필요한 제한을 피하는 동시에 데이터를 안전하게 유지하는 데도 도움이 됩니다.

## <a name="endpoint-dlp-policy-scenarios"></a>끝점 DLP 정책 시나리오

끝점 DLP 기능과 해당 기능이 DLP 정책에 나오는 방법에 대한 자세한 내용은 다음 몇 가지 시나리오를 참조하세요.

> [!IMPORTANT]
> 이러한 끝점 DLP 시나리오는 DLP 정책을 만들고 조정하는 공식 절차가 아닙니다. 일반적으로 DLP 정책을 사용해야 하는 경우 다음 항목을 참조하세요.

>- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
>- [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)
>- [템플릿에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)
>- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>시나리오 1: 템플릿으로 정책 만들기, 감사 전용

이 시나리오에서는 이미 장치가 온보딩되어 활동 탐색기에 보고되어 있어야 합니다. 아직 장치를 온보딩하지 않은 경우 [끝점 데이터 손실 방지(미리 보기)](endpoint-dlp-getting-started.md)를 참조하세요.

1. [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.

2. **정책 만들기** 를 선택합니다.

3. 이 시나리오에서는 **개인 정보** 를 선택한 다음 **미국 PII(개인 식별 정보) 데이터** 를 선택하고 **다음** 을 선택합니다.

4. **장치** 를 제외한 모든 위치에서 **상태** 필드를 해제로 전환합니다. **다음** 을 선택합니다.

5. 기본 설정인 **템플릿에서 설정 검토 및 사용자 지정** 선택을 그대로 사용하고 **다음** 을 선택합니다.

6. 기본 설정인 **보호 작업** 값을 적용하고 **다음** 을 선택합니다.

7. **Windows 장치에서 활동 감사 또는 제한** 을 선택하고 작업을 **감사 전용** 으로 유지합니다. **다음** 을 선택합니다.

8. 기본 설정인 **먼저 테스트하고 싶습니다** 값을 적용하고 **테스트 모드에서 정책 팁 표시** 를 선택합니다. **다음** 을 선택합니다.

9. 설정을 검토하고 **제출** 을 선택합니다.

10. 새 DLP 정책이 정책 목록에 표시됩니다.

11. 모니터링되는 끝점에서 데이터에 대한 활동 탐색기를 확인합니다. 장치에 대한 위치 필터를 설정하고 정책을 추가한 다음 정책 이름을 기준으로 필터링하여 정책의 영향을 확인합니다. 필요한 경우 [활동 탐색기로 시작](data-classification-activity-explorer.md)을 참조하세요.

12. 조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다. 이 경우 정책이 트리거되어야 합니다.

13. 이벤트에 대한 활동 탐색기를 확인합니다.

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>시나리오 2: 기존 정책 수정, 알림 설정

1. [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.

2. 시나리오 1에서 만든 **미국 PII(개인 식별 정보) 데이터** 정책을 선택합니다.

3. **정책 편집** 을 선택합니다.

4. **고급 DLP 규칙** 페이지로 이동하여 **적은 양의 콘텐츠가 미국 개인 식별 정보를 감지함** 을 수정합니다.

5. **사고 보고서** 섹션이 나올 때까지 아래로 스크롤한 다음 **켜기** 에 대한 **규칙 일치 오류가 발생하면 관리자에게 알림 보내기** 를 설정합니다. 전자 메일 알림은 관리자와 받는 사람 목록에 추가된 모든 사용자에게 자동으로 전달됩니다. 

   > [!div class="mx-imgBorder"]
   > ![turn-on-incident-reports.](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. 이 시나리오의 목적을 위해 **활동이 규칙에 일치할 때마다 알림 보내기** 를 선택합니다.

7. **저장** 을 선택합니다.

8. **다음** 을 선택하여 이전 설정을 모두 유지한 다음 정책 변경 **제출** 을 선택합니다.

9. 조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다. 이 경우 정책이 트리거되어야 합니다.

10. 이벤트에 대한 활동 탐색기를 확인합니다.

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>시나리오 3: 기존 정책 수정, 재정의 허용으로 작업 차단

1. [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.

2. 시나리오 1에서 만든 **미국 PII(개인 식별 정보) 데이터** 정책을 선택합니다.

3. **정책 편집** 을 선택합니다.

4. **고급 DLP 규칙** 페이지로 이동하여 **적은 양의 콘텐츠가 미국 개인 식별 정보를 감지함** 을 수정합니다.

5. 아래로 스크롤하여 **Windows 장치에서 활동 감사 또는 제한** 섹션으로 이동하여 각 활동에 대한 해당 작업을 **재정의로 차단** 으로 설정합니다.

   > [!div class="mx-imgBorder"]
   > ![재정의 작업으로 차단 설정](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png).
   
6. **저장** 을 선택합니다.

7. **대량의 콘텐츠가 미국 개인 식별 가능한 정보를 감지함** 에 대해 4-7단계를 반복합니다.

8. **다음** 을 선택하여 이전 설정을 모두 유지한 다음 정책 변경 **제출** 을 선택합니다.

9. 조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다. 이 경우 정책이 트리거되어야 합니다.

   클라이언트 장치에 다음과 같은 팝업이 표시됩니다.

   > [!div class="mx-imgBorder"]
   > ![끝점 DLP 클라이언트가 차단 재정의 알림.](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. 이벤트에 대한 활동 탐색기를 확인합니다.

### <a name="scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview"></a>시나리오 4: 자동 격리를 사용하여 클라우드 동기화 앱에서 DLP 알림 반복 방지(미리 보기)

#### <a name="before-you-begin"></a>시작하기 전에

이 시나리오에서는 **극비** 민감도 레이블이 있는 파일을 OneDrive에 동기화하는 것이 차단됩니다. 이것은 여러 구성 요소와 절차가 있는 복잡한 시나리오입니다. 다음이 필요합니다.

- 대상 AAD 사용자 계정 및 이미 로컬 OneDrive 폴더를 OneDrive 클라우드 저장소와 동기화하고 있는 온보드 Windows 10 컴퓨터.
- 대상 Windows 10 컴퓨터에 설치된 Microsoft Word
- 민감도 레이블이 구성 및 게시되었습니다. [민감도 레이블 시작하기](get-started-with-sensitivity-labels.md#get-started-with-sensitivity-labels) 및 [민감도 레이블 및 해당 정책 만들기 및 구성](create-sensitivity-labels.md#create-and-configure-sensitivity-labels-and-their-policies)을 참조하세요.

세 가지 절차가 있습니다.

1. 엔드포인트 DLP 자동 격리 설정을 구성합니다.
2. **극비** 민감도 레이블이 있는 중요한 항목을 차단하는 정책을 만듭니다.
3. 정책의 대상이 되는 Windows 10 장치에서 Word 문서를 만들고 레이블을 적용한 다음 동기화 중인 사용자 계정 로컬 OneDrive 폴더에 복사합니다.  

#### <a name="configure-endpoint-dlp-unallowed-app-and-auto-quarantine-settings"></a>Endpoint DLP 허용되지 않는 앱 및 자동 격리 설정 구성

1. [Endpoint DLP 설정](https://compliance.microsoft.com/datalossprevention?viewid=globalsettings)을 엽니다.

2. **허용되지 않는 앱** 을 확장합니다.

3. **허용되지 않는 앱 추가 또는 수정** 을 선택하고 *OneDrive* 를 표시 이름으로 추가하고 실행 파일 이름 *onedrive.exe* 를 추가하여 onedrive.exe가 **극비** 레이블이 있는 항목에 액세스하지 못하도록 합니다.

4. **자동 격리** 및 **저장** 을 선택합니다.

5. **자동 격리 설정** 에서 **자동 격리 설정 편집** 을 선택합니다.

6. **허용되지 않는 앱에 대한 자동 격리** 를 사용하도록 설정합니다.

7. 원래 중요한 파일을 이동할 로컬 시스템의 폴더 경로를 입력합니다. 예를 들면 다음과 같습니다.
   
**'%homedrive%%homepath%\Microsoft DLP\Quarantine'** 은 사용자 이름 *이사야 랑거* 에 대해 이동된 항목을 

*C:\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive* 폴더로 이동하고 원본 파일 이름에 날짜 및 시간 스탬프를 추가합니다.

> [!NOTE]
> DLP 자동 격리는 허용되지 않는 각 앱의 파일에 대한 하위 폴더를 생성합니다. 따라서 허용되지 않는 앱 목록에 *메모장* 과 *OneDrive* 가 모두 있는 경우 **\OneDrive** 에 대한 하위 폴더와 **\Notepad** 에 대한 다른 하위 폴더가 생성됩니다.

8. **다음 텍스트가 포함된 .txt 파일로 파일 바꾸기** 를 선택하고 자리 표시자 파일에 원하는 텍스트를 입력합니다. 예를 들어 *auto quar 1.docx* 라는 파일의 경우, 다음과 같이 작업을 수행합니다.
    
**%%FileName%%에는 조직에서 DLP(데이터 손실 방지) 정책 %%PolicyName%%으로 보호하는 중요한 정보가 포함되어 있으며 격리 폴더: %%QuarantinePath%%로 이동되었습니다.** 

이 메시지가 포함된 .txt 파일을 남깁니다.

*auto quar 1.docx에는 조직에서 DLP(데이터 손실 방지) 정책으로 보호하는 중요한 정보가 포함되어 있으며 격리 폴더: C:\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive\auto quar 1_20210728_151541.docx로 이동되었습니다.*

9. **저장** 을 선택합니다.

#### <a name="configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential"></a>민감도 레이블이 극비인 파일의 OneDrive 동기화를 차단하는 정책 구성

1. [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.

2. **정책 만들기** 를 선택합니다.

3. 이 시나리오에서는 **사용자 지정** 을 선택한 다음 **사용자 지정 정책** 을 선택하고 **다음** 을 선택합니다.

4. **이름** 및 **설명** 필드를 채우고 **다음** 을 선택합니다.

5. **장치** 를 제외한 모든 위치에서 **상태** 필드를 해제로 전환합니다. 이를 테스트하려는 특정 최종 사용자 계정이 있는 경우 범위에서 해당 계정을 선택해야 합니다. **다음** 을 선택합니다.

6. 기본 **고급 DLP 규칙 만들기 또는 사용자 지정** 선택 항목을 수락하고 **다음** 을 선택합니다.

7. 이 값으로 다음과 같이 규칙을 만듭니다.
    1. **이름** > *시나리오 4 자동 격리*
    1. **조건** > **콘텐츠 포함** > **민감도 레이블** > **기밀**
    1.  **작업** > **Windows 장치의 활동을 감사 또는 제한** > **허용되지 않는 앱의 액세스** > **차단**. 이 시나리오의 목적을 위해 다른 모든 활동을 지우세요.
    1. **사용자 알림** > **켜짐**
    1. **엔드포인트 장치** > 아직 활성화되지 않은 경우 **활동 시 사용자에게 정책 팁 알림 표시** 를 선택합니다.
    
8. **저장** 및 **다음** 을 선택합니다.

9. **즉시 켜기** 를 선택합니다. **다음** 을 선택합니다.

10. 설정을 검토하고 **제출** 을 선택합니다.

> [!NOTE]
> 새 정책이 복제되고 대상 Windows 10 컴퓨터에 적용되는 데 최소 1시간이 걸립니다.

11. 새 DLP 정책이 정책 목록에 표시됩니다.

#### <a name="test-auto-quarantine-on-the-windows-10-device"></a>Windows 10 장치에서 자동 격리 테스트

1. [민감도 레이블이 기밀인 파일의 OneDrive 동기화를 차단하는 정책 구성](#configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential) 5단계에서 지정한 사용자 계정으로 Windows 10 컴퓨터에 로그인합니다.

2. 콘텐츠가 OneDrive에 동기화되지 않는 폴더를 만듭니다. 예를 들면 다음과 같습니다.

    *C:\auto-quarantine 원본 폴더*

3. Microsoft Word를 열고 자동 격리 원본 폴더에 파일을 만듭니다. **극비** 민감도 레이블을 적용합니다. [Office에서 파일 및 이메일에 민감도 레이블 적용](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)을 참조하세요.

4. 방금 만든 파일을 OneDrive 동기화 폴더에 복사합니다. 작업이 허용되지 않으며 파일이 격리될 것임을 알리는 사용자 알림 알림이 표시되어야 합니다. 예를 들어 사용자 이름이 *Isaiah Langer* 이고 제목이 *auto-quarantine doc 1.docx* 인 문서의 경우 다음 메시지가 표시됩니다.

![지정된 파일에 대해 OneDrive 동기화 작업이 허용되지 않으며 파일이 격리될 것임을 나타내는 데이터 손실 방지 사용자 알림 팝업.](../media/auto-quarantine-user-notification-toast.png)

메시지는 다음과 같습니다.

"이 앱으로 자동 격리 문서 1.docx를 여는 것은 허용되지 않습니다. 파일은 'C:\Users\IsaLanger\Microsoft DLP\OneDrive'로 격리됩니다"

5. **닫기** 선택

6. 자리 표시자 .txt 파일을 엽니다. 이름은 **auto-quarantine doc 1.docx_ *date_time*.txt** 입니다. 

7. 격리 폴더를 열고 원본 파일이 있는지 확인합니다.
 
8. 모니터링되는 끝점에서 데이터에 대한 활동 탐색기를 확인합니다. 장치에 대한 위치 필터를 설정하고 정책을 추가한 다음 정책 이름을 기준으로 필터링하여 정책의 영향을 확인합니다. 필요한 경우 [활동 탐색기로 시작](data-classification-activity-explorer.md)을 참조하세요.

9. 이벤트에 대한 활동 탐색기를 확인합니다.

## <a name="see-also"></a>참고 항목

- [끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md)
- [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
- [엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)
- [Windows 10 컴퓨터용 온보딩 도구 및 방법](/microsoft-365/compliance/dlp-configure-endpoints)
- [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure Active Directory(AAD) 가입](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium 기반 새 Microsoft Edge 다운로드](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)
- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)
