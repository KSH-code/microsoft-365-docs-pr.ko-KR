---
title: 끝점 데이터 손실 방지 사용
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: DLP(데이터 손실 방지) 정책을 구성하여 Microsoft 365 끝점 데이터 손실 방지(EPDLP) 위치를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 6de6443dc0d276c862db43963ac28bd762e3756f
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984922"
---
# <a name="using-endpoint-data-loss-prevention"></a>끝점 데이터 손실 방지 사용

이 문서에서는 장치를 위치로 사용하는 DLP 정책을 만들고 수정하는 3가지 시나리오를 안내합니다.

## <a name="dlp-settings"></a>DLP 설정

시작하기 전에 모든 장치에 대한 DLP 정책에 적용되는 DLP 설정을 설정해야 합니다. 적용되는 정책을 만들려면 다음을 반드시 구성해야 합니다.

- 클라우드 송신 제한 사항
- 허용되지 않는 앱 제한 사항

또는

- 모니터링에서 잡음이 있는 파일 경로를 제외하려는 경우

  > [!div class="mx-imgBorder"]
  > ![DLP 설정](../media/endpoint-dlp-1-using-dlp-settings.png)

### <a name="file-path-exclusions"></a>파일 경로 제외

지나치게 잡음이 많거나 관심 있는 파일을 포함하지 않으므로 장치에서 DLP 모니터링, DLP 경고, DLP 정책 적용에서 특정 경로를 제외하고자 할 수 있습니다. 해당 위치에서 파일을 감사하지 않으며 해당 위치에서 만들어지거나 수정된 모든 파일에 DLP 정책 적용이 적용되지 않습니다. DLP 설정에서 경로 제외를 구성할 수 있습니다.

이 논리를 사용하여 제외 경로를 생성할 수 있습니다.

- ‘\로 끝나는 올바른 파일 경로입니다. 이는 폴더 바로 아래에 있는 파일만을 의미합니다. <br/>예시: C:\Temp\

- ‘\*’로 끝나는 올바른 파일 경로입니다. 이는 폴더 바로 아래에 있는 파일 외에 하위 폴더 바로 아래에 있는 파일만을 의미합니다. <br/>예시: C:\Temp\*

- ‘\’ 또는 ‘\*’로 끝나는 올바른 파일 경로입니다. 이는 폴더 및 모든 하위 폴더 바로 아래에 있는 모든 파일을 의미합니다. <br/>예시: C:\Temp

- 각 면의 '\' 사이에 와일드카드가 있는 경로입니다. <br/>예시: C:\Users\*\Desktop\

- 정확한 하위 폴더 수를 제공하기 위해 각 면의 '\' 사이에 와일드카드와 '(숫자)'가 있는 경로입니다. <br/>예시: C:\Users\*(1)\Downloads\

- 시스템 환경 변수를 사용하는 경로입니다. <br/>예시: %SystemDrive%\Test\*

- 위의 모든 것을 혼합한 것입니다. <br/>예시: %SystemDrive%\Users\*\Documents\*(2)\Sub\

### <a name="service-domains"></a>서비스 도메인

Edge Chromium이 끝점 DLP 정책 클라우드 업로드 액세스 제한을 적용할 때 참조하는 도메인을 이 목록에 추가할 수 있습니다. 

목록 모드가 **차단** 으로 설정되어 있으면 사용자는 해당 도메인에 중요한 항목을 업로드할 수 없습니다. 항목이 DLP 정책과 일치하여 업로드 작업이 차단되면 DLP가 경고를 생성하거나 중요한 항목의 업로드를 차단합니다.

목록 모드가 **허용** 으로 설정되어 있으면 사용자가 * *_오직_* _ 해당 도메인에만 중요한 항목을 업로드할 수 있으며, 다른 모든 도메인에 대한 업로드는 허용되지 않습니다.

### <a name="unallowed-apps"></a>허용되지 않는 앱

정책의 _ *허용되지 않은 앱 및 브라우저에 의한 액세스* * 설정이 켜져 있고 사용자가 이러한 앱을 사용하여 보호된 파일에 액세스하려고 하면, 활동이 허용 또는 차단되거나, 아니면 차단되지만 사용자가 제한을 재정의할 수 있습니다. 모든 활동을 감사하며 활동 탐색기에서 검토할 수 있습니다.

### <a name="unallowed-browsers"></a>허용되지 않는 브라우저

클라우드 서비스 제한에 업로드가 차단 또는 재설정을 차단하는 것으로 설정되어 있는 적용된 DLP 정책의 조건과 일치하는 파일에 액세스하지 못하도록 차단된 실행 파일 이름으로 식별되는 브라우저를 추가합니다. 이 브라우저가 파일에 액세스하지 못하도록 차단되면 최종 사용자에게 Edge Chromium를 통해 파일을 열도록 요청하는 알림 메시지가 표시됩니다.

[!IMPORTANT]
실행 파일 이름(예: 브라우저.exe)은 포함해야 하지만 실행 파일 경로는 포함하지 않아야 합니다.

## <a name="tying-dlp-settings-together"></a>DLP 설정 함께 연결

끝점 DLP 및 Edge Chromium 웹 브라우저를 사용하여 중요한 항목이 허용되지 않는 클라우드 앱 및 서비스에 대한 의도하지 않은 공유를 제한할 수 있습니다. Edge Chromium은 항목이 끝점 DLP 정책으로 제한되는 경우에 대해 이해하고 액세스 제한을 적용합니다.

올바르게 구성된 DLP 정책 및 Edge Chromium 브라우저에서 끝점 DLP를 위치로 사용하는 경우 이러한 설정에 정의된 허용되지 않는 브라우저는 DLP 정책 컨트롤과 일치하는 중요한 항목에 액세스할 수 없습니다. 대신 사용자는 Edge Chromium을 사용하도록 리디렉션되며 Edge Chromium이 DLP 적용 제한 사항을 이해하여 DLP 정책의 조건을 충족하는 경우 활동을 차단하거나 제한할 수 있습니다.

이 제한을 사용하려면 중요한 3가지 부분을 구성해야 합니다.

1. 중요한 항목이 공유되지 않도록 하려는 위치(서비스, 도메인, IP 주소)를 지정합니다.

2. DLP 정책이 일치하는 경우 특정 중요한 항목에 액세스할 수 없는 브라우저를 추가합니다.

3. **클라우드 서비스 업로드** 와 **허용되지 않은 브라우저에서 액세스** 설정을 사용하여 업로드가 해당 위치로 제한되어야 하는 중요한 항목의 종류를 정의하는 DLP 정책 구성

새 서비스, 앱 및 정책을 계속 추가하여 비즈니스 요구 사항을 충족하고 중요한 데이터를 보호하는 데 필요한 제한을 확장하고 강화할 수 있습니다. 

이 구성은 사용자가 중요하지 않은 항목에 액세스하고 공유하지 못하도록 하는 불필요한 제한을 피하는 동시에 데이터를 안전하게 유지하는 데도 도움이 됩니다.

## <a name="endpoint-dlp-policy-scenarios"></a>끝점 DLP 정책 시나리오

끝점 DLP 기능과 해당 기능이 DLP 정책에 나오는 방법에 대한 자세한 내용은 다음 몇 가지 시나리오를 참조하세요. 끝점 DLP를 일반적으로 사용할 수 있을 때 모든 끝점 DLP 콘텐츠는 기본 DLP 콘텐츠 집합에 포함됩니다.

> [!IMPORTANT]
> 이러한 끝점 DLP 시나리오는 DLP 정책을 만들고 조정하는 공식 절차가 아닙니다. 일반적으로 DLP 정책을 사용해야 하는 경우 다음 항목을 참조하세요.
>- [데이터 손실 방지의 개요](data-loss-prevention-policies.md)
>- [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)
>- [템플릿에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)
>- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>시나리오 1: 템플릿으로 정책 만들기, 감사 전용

이 시나리오에서는 이미 장치가 온보딩되어 활동 탐색기에 보고되어 있어야 합니다. 아직 장치를 온보딩하지 않은 경우 [끝점 데이터 손실 방지(미리 보기)](endpoint-dlp-getting-started.md)를 참조하세요.

1. [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.

2. **정책 만들기(미리 보기)** 를 선택합니다.

3. 이 시나리오에서는 **개인 정보** 를 선택한 다음 **미국 PII(개인 식별 정보) 데이터** 를 선태한 후 **다음** 을 선택합니다.

4. **장치** 를 제외한 모든 위치에서 **상태** 필드를 해제로 전환합니다. **다음** 을 선택합니다.

5. 기본 설정인 **템플릿에서 설정 검토 및 사용자 지정** 선택을 그대로 사용하고 **다음** 을 선택합니다.

6. 기본 설정인 **보호 작업** 값을 적용하고 **다음** 을 선택합니다.

7. **Windows 장치에서 활동 감사 또는 제한** 을 선택하고 작업을 **감사 전용** 으로 유지합니다. **다음** 을 선택합니다.

8. 기본 설정인 **먼저 테스트하고 싶습니다** 를 적용하고 **테스트 모드에서 정책 팁 표시** 를 선택합니다. **다음** 을 선택합니다.

9. 설정을 검토하고 **제출** 을 선택합니다.

10. 새 DLP 정책이 정책 목록에 표시됩니다.

11. 모니터링되는 끝점에서 데이터에 대한 활동 탐색기를 확인합니다. 장치에 대한 위치 필터를 설정하고 정책을 추가한 다음 정책 이름을 기준으로 필터링하여 정책의 영향을 확인합니다. 필요한 경우 [활동 탐색기로 시작](data-classification-activity-explorer.md)을 참조하세요.

12. 조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다. 이 경우 정책이 트리거되어야 합니다.

13. 이벤트에 대한 활동 탐색기를 확인합니다.

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>시나리오 2: 기존 정책 수정, 알림 설정

1. [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.

2. 시나리오 1에서 만든 **미국 PII(개인 식별 정보) 데이터** 정책을 선택합니다.

3. **정책 편집(미리 보기)** 을 선택합니다.

4. **고급 DLP 규칙** 페이지로 이동하여 **적은 양의 콘텐츠가 미국 개인 식별 가능한 정보를 감지함** 을 수정합니다.

5. **사고 보고서** 섹션이 나올 때까지 아래로 스크롤한 다음 **켜기** 에 대한 **규칙 일치 오류가 발생하면 관리자에게 알림 보내기** 를 설정합니다. 전자 메일 알림은 관리자와 받는 사람 목록에 추가된 모든 사용자에게 자동으로 전달됩니다. 

   > [!div class="mx-imgBorder"]
   > ![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. 이 시나리오의 목적을 위해 **활동이 규칙에 일치할 때마다 알림 보내기** 를 선택합니다.

7. **저장** 을 선택합니다.

8. **다음** 을 선택하여 이전 설정을 모두 유지한 다음 정책 변경 **제출** 을 선택합니다.

9. 조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다. 이 경우 정책이 트리거되어야 합니다.

10. 이벤트에 대한 활동 탐색기를 확인합니다.

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>시나리오 3: 기존 정책 수정, 재정의 허용으로 작업 차단

1. [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.

2. 시나리오 1에서 만든 **미국 PII(개인 식별 정보) 데이터** 정책을 선택합니다.

3. **정책 편집(미리 보기)** 을 선택합니다.

4. **고급 DLP 규칙** 페이지로 이동하여 **적은 양의 콘텐츠가 미국 개인 식별 가능한 정보를 감지함** 을 수정합니다.

5. 아래로 스크롤하여 **Windows 장치에서 활동 감사 또는 제한** 섹션으로 이동하여 각 활동에 대한 해당 작업을 **재정의로 차단** 으로 설정합니다.

   > [!div class="mx-imgBorder"]
   > ![재정의 작업으로 차단 설정](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. **저장** 을 선택합니다.

7. **대량의 콘텐츠가 미국 개인 식별 가능한 정보를 감지함** 에 대해 4-7단계를 반복합니다.

8. **다음** 을 선택하여 이전 설정을 모두 유지한 다음 정책 변경 **제출** 을 선택합니다.

9. 조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다. 이 경우 정책이 트리거되어야 합니다.

   클라이언트 장치에 다음과 같은 팝업이 표시됩니다.

   > [!div class="mx-imgBorder"]
   > ![끝점 DLP 클라이언트가 차단 재정의 알림](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. 이벤트에 대한 활동 탐색기를 확인합니다.

## <a name="see-also"></a>참고 항목

- [끝점 데이터 손실 방지(미리 보기)에 대한 자세한 정보](endpoint-dlp-learn-about.md)
- [끝점 데이터 손실 방지(미리 보기) 시작](endpoint-dlp-getting-started.md)
- [데이터 손실 방지의 개요](data-loss-prevention-policies.md)
- [DLP 정책 생성, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
- [엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)
- [Windows 10 컴퓨터용 온보딩 도구 및 방법](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure Active Directory(AAD) 가입](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium 기반 새 Microsoft Edge 다운로드](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)
- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)
