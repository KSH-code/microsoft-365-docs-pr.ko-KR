---
title: 스팸 필터 정책 구성하기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online Protection(EOP)에서 스팸 방지 정책을 보고, 만들고 수정하고 삭제하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ff568ffb32a6feb3ef8eba46cad1127dcead0465
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553895"
---
# <a name="configure-anti-spam-policies-in-eop"></a>EOP에서 스팸 방지 정책 구성하기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 경우, 인바운드 전자 메일 메시지가 EOP를 통해 자동으로 스팸으로부터 보호됩니다. EOP는 스팸에 대한 조직의 전반적인 방어책의 일부로 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용합니다. 자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.

관리자는 기본 스팸 방지 정책을 보고, 편집하고, 구성할 수 있습니다(삭제는 할 수 없음). 세분성을 높이기 위해 사용자 지정 스팸 방지 정책을 만들어 조직의 특정 사용자, 그룹 또는 도메인에 적용할 수도 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.

Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직의 경우 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 스팸 방지 정책을 구성할 수 있습니다.

스팸 방지 정책의 기본 요소는 다음과 같습니다.

- **스팸 필터 정책**: 스팸 필터링 결과와 알림 옵션에 대한 작업을 지정합니다.
- **스팸 필터 규칙**: 스팸 필터 정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.

Microsoft 365 Defender 포털에서 스팸 방지 정책을 관리할 경우 이 두가지 요소의 차이점은 명확하지 않습니다.

- 스팸 방지 정책을 만드는 경우에는 사용자가 같은 이름을 사용하여 동시에 스팸 필터 규칙과 관련 스팸 필터 정책을 작성하게 됩니다.
- 스팸 방지 정책을 수정하는 경우, 이름, 우선 순위, 사용 또는 사용 안 함 및 받는 사람 필터와 관련된 설정은 스팸 필터 규칙을 수정합니다. 다른 모든 설정은 관련 스팸 필터 정책을 수정합니다.
- 스팸 방지 정책을 제거하면, 스팸 필터 규칙과 관련 스팸 필터 정책이 제거됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다. 자세한 내용은 이 문서의 뒷부분에 나오는 [Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 스팸 방지 정책 구성](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) 섹션을 참조하세요.

모든 조직에는 다음과 같은 속성을 포함하는 기본 제공되는 Default 스팸 방지 정책이 있습니다.

- 정책과 연결된 스팸 필터 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 스팸 필터 정책이 적용됩니다.
- 정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨). 사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.
- 그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.

스팸 필터링의 효율성을 높이려면 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 스팸 방지 정책을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다. **스팸 방지 정책** 페이지로 직접 이동하려면 <https://security.microsoft.com/antispam>을(를) 사용합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.
  - 스팸 방지 정책을 추가, 수정 및 삭제하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원이어야 합니다.
  - 스팸 방지 정책에 대한 읽기 전용 액세스를 위해서는 **전체 읽기 권한자** 또는 **보안 읽기 권한자** 역할 그룹의 구성원이어야 합니다.

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.

- 스팸 방지 정책에 대한 권장 설정은 [EOP 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)을 참조하세요.

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a>Microsoft 365 Defender 포털을 사용해 스팸 방지 정책 만들기

Microsoft 365 Defender 포털에서 사용자 지정 스팸 방지 정책을 만들면 같은 이름을 사용하여 스팸 필터 규칙과 관련 스팸 필터 정책이 동시에 만들어집니다.

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. **스팸 방지 정책** 페이지에서 ![아이콘 만들기](../../media/m365-cc-sc-create-icon.png) **정책 만들기** 를 클릭한 다음 드롭다운 목록에서 **인바운드** 를 선택합니다.

3. 정책 마법사가 열립니다. **정책 이름 페이지** 에서 다음 설정을 구성합니다.
   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.
   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 표시되는 **사용자, 그룹 및 도메인** 페이지에서 정책이 적용되는 내부 받는 사람(받는 사람 조건)을 식별합니다.
   - **사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.
   - **그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.
   - **도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.

   적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다. 이 프로세스를 필요한 만큼 반복합니다. 기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

   사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다. 사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.

   동일한 조건의 여러 값은 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 서로 다른 조건은 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

   - **다음 사용자, 그룹 및 도메인 제외**: 해당 정책의 적용 대상인 내부의 받는 사람에게 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다. 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 표시되는 **대량 전자 메일 임계값 및 스팸 속성** 페이지에서 다음 설정을 구성합니다.

   - **대량 메일 임계값**: 다음 페이지에서 구성하는 **대량 전자 메일** 스팸 필터링 결과(지정된 값 이상, 이하 혹은 같음)에 지정된 작업을 트리거하는 메시지의 BCL(대량 불만 수준)을 지정합니다. 값이 높을수록 메시지가 덜 바람직함을 나타냅니다(스팸과 유사할 가능성 높음). 기본값은 7입니다. 자세한 내용은 [EOP에서의 BCL(대량 불만 수준)](bulk-complaint-level-values.md) 및 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조하세요.

     기본적으로 PowerShell 전용 설정 _MarkAsSpamBulkMail_ 은 스팸 방지 정책에서 `On` 상태입니다. 이 설정은 **대량** 필터링 결과의 결과에 크게 영향을 미칩니다.

     - **_MarkAsSpamBulkMail_ 이 켜짐**: 임곗값보다 큰 BCL은 **스팸** 필터링 결과에 해당하는 SCL 6으로 변환되고, 메시지에 대한 **대량** 필터링 결과에 대한 작업이 수행됩니다.
     - **_MarkAsSpamBulkMail_ 이 꺼짐**: 메시지에는 BCL이 찍히지만 **대량** 필터링 결과에 대해 수행되는 _작업은 없습니다._ 실제로 BCL 임곗값과 **대량** 필터링 결과 작업은 관련이 없습니다.

   - **스팸 점수 증가**, **스팸으로 표시**<sup>\*</sup>및 **테스트 모드**: 기본적으로 꺼져있는 고급 스팸 필터(ASF) 설정이 포함되어 있습니다. ASF 설정은 더 이상 사용되지 않으며, 해당 기능은 필터링 스택의 다른 부분에 통합됩니다. 모든 ASF 설정을 스팸 방지 정책에서 해제하는 것이 좋습니다.

     이러한 설정에 대한 자세한 내용은 [EOP에서 고급 스팸 필터 설정](advanced-spam-filtering-asf-options.md)을 참조하세요.

      <sup>\*</sup> **특정 언어** 를 포함하며 **이러한 국가에서** 는 ASF 설정의 일부가 아닙니다.

   - **특정 언어 포함**: 상자를 클릭하고 선택하거나 드롭다운 목록에서 **켜짐** 또는 **꺼짐** 을 선택합니다. 이 기능을 켜면 상자가 나타납니다. 상자에 언어 이름을 입력하기 시작합니다. 지원되는 언어의 필터링된 목록이 표시됩니다. 원하는 언어를 찾았으면 선택합니다. 필요한 만큼 이 단계를 반복합니다. 기존 값을 제거하려면 제거 ![제거 아이콘](../../media/m365-cc-sc-remove-selection-icon.png)을 클릭합니다. 값 옆에 있습니다.

   - **이러한 국가에서** _: 상자를 클릭하고 드롭다운 목록에서 _ *켜기** 또는 **끄기** 를 입력합니다. 이 기능을 켜면 상자가 나타납니다. 상자에 국가 이름을 입력하기 시작합니다. 지원되는 국가의 필터링된 목록이 표시됩니다. 원하는 국가를 찾으면 선택합니다. 필요한 만큼 이 단계를 반복합니다. 기존 값을 제거하려면 제거 ![제거 아이콘](../../media/m365-cc-sc-remove-selection-icon.png)을 클릭합니다. 값 옆에 있습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

6. 표시되는 **작업** 페이지에서 다음 설정을 구성합니다.

   - **메시지 작업**: 다음 스팸 필터링 결과에 따라 메시지에 대해 수행할 작업을 선택하거나 검토합니다.
     - **스팸**
     - **높은 정확도의 스팸**
     - **피싱**
     - **높은 정확도 피싱**
     - **대량 전자 메일**

     스팸 필터링 결과에 사용 가능한 작업은 다음 표에 설명되어 있습니다.

     - 확인 표시( ![확인 표시입니다.](../../media/checkmark.png)) 작업을 사용할 수 있음을 의미합니다(모든 결과에 모든 작업을 사용할 수 있는 것은 아님).
     - 확인 표시 후 별표(<sup>\*</sup>)는 스팸 필터링 결과에 대한 기본 작업을 나타냅니다.

     <br>

     ****

     |조치|스팸|높음<br>신뢰 수준<br>스팸|피싱|높음<br>신뢰 수준<br>피싱|대량|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**정크 메일 폴더로 메시지 이동**: 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1</sup>|![확인 표시입니다.](../../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../../media/checkmark.png)<sup>\*</sup>|![확인 표시입니다.](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)<sup>\*</sup>|
     |**X-헤더 추가**: 메시지 헤더에 X-헤더를 추가하고, 메시지를 사서함에 배달합니다. <p> 나중에 **이 X-헤더 텍스트를 추가** 상자에서 X-헤더 필드 이름(값 아님)을 입력합니다. <p> **스팸** 및 **높은 정확도의 스팸** 결과의 경우, 메시지가 정크 메일 폴더로 이동됩니다.<sup>1, 2</sup>|![확인 표시입니다.](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)|
     |**텍스트를 제목 줄 앞에 추가**: 메시지의 제목 줄 앞에 텍스트를 추가합니다. 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1,2</sup> <p> **이 텍스트를 제목 줄 앞에 추가** 상자에 텍스트를 입력합니다.|![확인 표시입니다.](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)|
     |**전자 메일 주소로 메시지 리디렉션**: 메시지를 의도된 받는 사람 대신 다른 받는 사람에게 보냅니다. <p> 나중에 **이 전자 메일 주소로 메시지 리디렉션** 상자에 받는 사람을 지정합니다.|![확인 표시입니다.](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
     |**메시지 삭제**: 모든 첨부 파일을 포함하여 전체 메시지를 자동으로 삭제합니다.|![확인 표시입니다.](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)|
     |**메시지 격리**: 메시지를 의도된 받는 사람에게 보내는 대신 격리로 보냅니다. <p> 나중에 **격리** 상자에 메시지가 격리되는 기간을 지정합니다. <p> 표시되는 **정책 선택** 상자에서 스팸 필터 평가 결과에 대해 격리된 메시지에 적용할 [격리 정책](quarantine-policies.md)을 지정합니다. 자세한 내용은 [정책 격리](quarantine-policies.md)를 참조하세요.<sup>3</sup>|![확인 표시입니다.](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)<sup>\*</sup>|![확인 표시](../../media/checkmark.png)<sup>\*</sup>|![확인 표시](../../media/checkmark.png)|
     |**작업 없음**|||||![확인 표시](../../media/checkmark.png)|
     |

     > <sup>1</sup> EOP는 이제 자체 메일 흐름 전달 에이전트를 사용하여 정크 이메일 규칙을 사용하는 대신 정크 이메일 폴더로 메시지를 라우팅합니다. **Set-MailboxJunkEmailConfiguration** cmdlet의 _Enabled_ 매개 변수는 더 이상 메일 흐름에 영향을 미치지 않습니다. 자세한 내용은 [Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.
     >
     > EOP가 온-프레미스 Exchange 사서함을 보호하는 하이브리드 환경에서는 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다. 이러한 메일 흐름 규칙은 EOP 스팸 필터링 판정을 변환하므로 사서함의 정크 메일 규칙이 메시지를 정크 메일 폴더로 이동할 수 있습니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 전달하도록 EOP 구성](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)을 참조하세요.
     >
     > <sup>2</sup> 메일 흐름 규칙에서 해당 값을 조건으로 사용하여 메시지를 필터링하거나 경로 지정할 수 있습니다.
     >
     > <sup>3</sup> 빈 **정책 선택** 값이란 특정 평가 결과에 대한 기본 격리 정책이 사용됨을 의미합니다. 나중에 스팸 방지 정책을 편집하거나 설정을 보면 기본 격리 정책 이름이 표시됩니다. 스팸 필터 평가 결과에 사용되는 기본 격리 정책에 대한 자세한 내용은 [이 표](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features)를 참조하세요.

   - **이 많은 일수 동안 스팸을 격리 상태로 유지**: 스팸 필터링 결과에 대한 작업으로 **메시지 격리** 를 선택한 경우, 메시지를 격리할 기간을 지정합니다. 격리 기간이 만료되면 메시지가 삭제됩니다. 기본값은 30일입니다. 유효한 값은 1~30일입니다. 격리에 대한 자세한 내용은 다음 게시물을 참조하세요.
     - [EOP에서 격리된 메시지](quarantine-email-messages.md)
     - [EOP에서 관리자 권한으로 격리된 메시지 및 파일 관리하기](manage-quarantined-messages-and-files.md)
     - [EOP에서 사용자 권한으로 격리된 메시지 찾기 및 해제하기](find-and-release-quarantined-messages-as-a-user.md)

   - **이 X-헤더 텍스트 추가**: 이 상자는 필수이며, **X-헤더 추가** 를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다. 사용자가 지정하는 값은 메시지 헤더에 추가되는 헤더 필드 *이름* 입니다. 헤더 필드 *값* 은 항상 `This message appears to be spam`입니다.

     최대 길이는 255자이며, 값에는 공백이나 콜론(:)이 포함될 수 없습니다.

     예를 들어 값 `X-This-is-my-custom-header`을(를) 입력하면 메시지에 추가되는 X-헤더는 `X-This-is-my-custom-header: This message appears to be spam.`입니다.

     공백이나 콜론(:)을 포함하는 값을 입력하면 입력하는 값이 무시되고, 기본 X 머리글이 메시지(`X-This-Is-Spam: This message appears to be spam.`)에 추가됩니다.

   - **이 텍스트를 제목 줄 앞에 추가**: 이 상자는 필수이며, **텍스트를 제목 줄 앞에 추가** 를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다. 메시지의 제목 줄의 시작 부분에 추가할 텍스트를 입력하세요.

   - **이 전자 메일 주소로 리디렉션**: 이 상자는 필수이며, 스팸 필터링 결과 작업으로 **메시지를 전자 메일 주소로 리디렉션** 을 선택한 경우에만 사용할 수 있습니다. 메시지를 배달하려는 전자 메일 주소를 입력하세요. 세미콜론(;)으로 구분하여 여러 값을 입력할 수 있습니다.

   - **보안 팁 사용**: 기본적으로 보안 팁은 활성화되어 있지만, 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.

   - **제로 아워 자동 제거(ZAP) 사용**: ZAP는 Exchange Online 사서함에 이미 배달된 메시지를 검색하여 작업을 수행합니다. 자세한 내용은 [제로 아워 자동 제거 - 스팸 및 맬웨어로부터 보호](zero-hour-auto-purge.md)를 참조하세요.

     ZAP는 기본적으로 켜져 있습니다. ZAP가 켜져 있으면 다음 설정을 사용할 수 있습니다.

     - **피싱 메시지에 대한 ZAP 사용**: 기본적으로 ZAP는 피싱 검색에 대해 사용하도록 설정되지만 확인란의 선택을 취소하여 사용하지 않도록 설정할 수 있습니다.
     - **스팸 메시지에 대한 ZAP 사용**: 기본적으로 ZAP는 스팸 검색에 대해 사용하도록 설정되지만 확인란의 선택을 취소하여 사용하지 않도록 설정할 수 있습니다.

   > [!NOTE]
   > 최종 사용자 스팸 알림은 스팸 방지 정책 평가 결과뿐만 아니라 지원되는 모든 보호 기능에 대한 격리 메시지에 대한 정보가 포함된 격리 정책의 _격리 알림_ 으로 대체되었습니다. 자세한 내용은 [정책 격리](quarantine-policies.md)를 참조하세요.

   작업을 마친 후 **다음** 을 클릭합니다.

7. 표시되는 **허용 및 차단 목록** 플라이아웃에서 스팸 필터링을 건너뛸 수 있는 전자 메일 주소 또는 전자 메일 도메인별로 메시지 보낸 사람을 구성할 수 있습니다.

   **허용** 섹션에서 허용된 보낸 사람 및 허용된 도메인을 구성할 수 있습니다. **차단된** 섹션에서 차단된 보낸 사람 및 차단된 도메인을 추가할 수 있습니다.

   > [!IMPORTANT]
   >
   > 허용된 도메인 목록에 도메인을 추가하기 전에 신중하게 생각하세요. 자세한 내용은 [EOP에서 안전한 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.
   >
   > 자신의 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 또는 공통 도메인(예: microsoft.com 또는 office.com)을 허용된 도메인 목록에 추가하지 않도록 하세요. 이러한 도메인이 스팸 필터링을 우회하도록 허용된다면, 공격자는 손쉽게 이 신뢰할 수 있는 도메인을 스푸핑하는 메시지를 조직에 보낼 수 있습니다.
   >
   > 차단된 도메인 목록에 도메인을 추가하여 수동으로 도메인을 차단하는 것은 위험하지 않지만, 관리 작업 부하가 늘어날 수 있습니다. 자세한 내용은 [EOP에서 차단할 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조하세요.
   >
   > 필터가 메시지를 빠뜨리거나 필터링 평가에 동의하지 않거나 시스템에서 메시지를 확인하는 데 시간이 걸리는 경우가 있습니다. 이러한 경우 허용 목록 및 차단 목록을 사용하여 현재 필터링 결과를 재정의할 수 있습니다. 그러나 이러한 목록은 일시적으로 사용해야 합니다. longs 목록은 관리할 수 없게 될 수 있으며 필터링 스택은 예상되는 작업을 수행해야 합니다. 허용된 도메인을 오랫동안 유지하려는 경우 보낸 사람에게 도메인이 인증되었는지 확인하고 도메인이 인증되지 않은 경우 DMARC 거부로 설정하도록 지시해야 합니다.

   목록에 항목을 추가하는 단계는 동일합니다.

   1. 구성할 목록의 링크를 클릭합니다.
      - **허용된** \> **보낸 사람**: **보낸 사람 관리(nn)** 를 클릭합니다.
      - **허용된** \> **도메인**: **도메인 허용** 을 클릭합니다.
      - **차단된** \> **보낸 사람**: **보낸 사람 관리(nn)** 를 클릭합니다.
      - **차단된** \> **도메인**: **도메인 차단** 을 클릭합니다.

   2. 표시되는 플라이아웃에서 다음 단계를 수행합니다.
      1. ![아이콘 만들기](../../media/m365-cc-sc-create-icon.png) **보낸 사람 추가** 또는 **도메인 추가** 를 클릭합니다.
      2. 표시되는 **보낸 사람 추가** 또는 **도메인 추가** 플라이아웃에서 보낸 사람의 전자 메일 주소를 **보낸 사람** 상자에 입력하거나 **도메인** 상자에 도메인을 입력합니다. 입력할 때 값이 상자 아래에 나타납니다. 전자 메일 주소 또는 도메인 입력을 마쳤으면 상자 아래의 값을 선택합니다.
      3. 이전 단계를 필요한 횟수만큼 반복합니다. 기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

      완료되면 **보낸 사람 추가** 또는 **도메인 추가** 를 클릭합니다.

      기본 플라이아웃으로 돌아가서 추가한 보낸 사람 또는 도메인이 페이지에 나열됩니다. 이 페이지에서 항목을 제거하려면 다음 단계를 수행합니다.

      1. 목록에서 하나 이상의 항목을 선택합니다. **검색** 상자를 사용하여 목록에서 값을 찾을 수도 있습니다.
      2. 항목을 하나 이상 선택한 후 삭제 아이콘 ![삭제 아이콘.](../../media/m365-cc-sc-delete-icon.png) 나타납니다.
      3. 삭제 아이콘을 클릭합니다. ![삭제 아이콘.](../../media/m365-cc-sc-delete-icon.png) 선택한 항목을 제거합니다.

      작업을 마친 후 **다음** 을 클릭합니다.

      **허용 및 차단 목록** 페이지로 돌아가서, 읽을 때 **다음** 클릭하여 계속합니다.

8. 표시되는 **검토** 페이지에서 설정을 검토합니다. 각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다. 또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.

   작업을 마쳤으면 **닫기** 를 클릭합니다.

9. 표시되는 확인 페이지에서 **완료** 를 클릭합니다.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a>Microsoft 365 Defender 포털을 사용해 스팸 방지 정책 보기

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. **스팸 방지 정책** 페이지에서 다음 값 중 하나를 찾습니다.
   - **유형** 값은 **사용자 지정 스팸 방지 정책** 입니다.
   - **이름** 값은 **스팸 방지 인바운드 정책(기본값)** 입니다.

   스팸 방지 정책 목록에는 다음 속성이 표시됩니다.

   - **이름**
   - **상태**
   - **우선 순위**
   - **유형**

3. 이름을 클릭하여 스팸 방지 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a>Microsoft 365 Defender 포털을 사용해 스팸 방지 정책 수정

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. **스팸 방지 정책** 페이지에서 이름을 클릭하여 목록에서 스팸 방지 정책을 선택합니다.
   - **유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 사용자가 만든 사용자 지정 정책.
   - **스팸 방지 인바운드 정책(기본값)이라는 기본 정책** 입니다.

3. 표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다. 설정에 관한 자세한 내용은 이 문서의 이전 [Microsoft 365 Defender 포털을 사용해 스팸 방지 정책 만들기](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) 섹션을 참조하세요.

   기본 스팸 방지 정책의 경우, **적용 대상** 섹션을 사용할 수 없으며(이 정책은 모든 사용자에게 적용됨) 정책의 이름을 바꿀 수 없습니다.

정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.

### <a name="enable-or-disable-anti-spam-policies"></a>스팸 방지 정책 활성화 또는 비활성화하기

기본 스팸 방지 정책은 사용하지 않도록 설정할 수 없습니다.

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. **스팸 방지 정책** 페이지에서 이름을 클릭하여 목록에서 **사용자 지정 스팸 방지 정책** **유형 값** 이 있는 정책을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.
   - **정책 꺼짐**: 정책을 켜려면 ![켜기 아이콘.](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.
   - **정책 켜짐**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.

4. 표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.

5. 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.

기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>사용자 지정 스팸 방지 정책의 우선순위 설정하기

기본적으로 만들어진 순서에 따라 스팸 방지 정책에 우선순위가 지정됩니다(새 정책은 이전 정책 보다 우선순위가 낮음). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이거나** **우선 순위를 낮춥니다**(Microsoft 365 Defender 포털에서 **우선 순위** 번호를 직접 수정할 수 없습니다). 정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.

 **참고**:

- Microsoft 365 Defender 포털에서는 스팸 방지 정책을 만든 후에만 우선 순위를 변경할 수 있습니다. PowerShell에서 사용자는 기존 규칙의 우선순위에 영향을 줄 수 있는 스팸 필터 규칙을 만들 때 기본 우선순위를 재정의할 수 있습니다.
- 스팸 방지 정책은 표시되는 순서로 처리됩니다(첫 번째 정책에는 **우선순위** 값 0이 표시됨). 기본 스팸 방지 정책은 우선순위 값이 **가장 낮음** 이며 변경할 수 없습니다.

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. **스팸 방지 정책** 페이지에서 이름을 클릭하여 목록에서 **사용자 지정 스팸 방지 정책** **유형 값** 이 있는 정책을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃 맨 위에 현재 우선 순위 값 및 사용자 지정 정책 수를 기준으로 **우선순위 증가** 또는 **우선순위 감소** 가 표시됩니다.
   - **우선 순위** 값이 **0** 인 스팸 방지 정책에는 **우선 순위** 감소 옵션만 사용할 수 있습니다.
   - **우선 순위** 값이 가장 낮은 스팸 방지 정책(예: **3**)에는 **우선 순위 증가** 옵션만 사용할 수 있습니다.
   - 스팸 방지 정책이 세 개 이상 있는 경우 가장 높은 우선 순위 값과 가장 낮은 우선 순위 값 사이의 정책에는 **우선 순위 증가** 및 **우선 순위 감소** 옵션을 모두 사용할 수 있습니다.

   ![우선 순위 증가 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선 순위 증가** 또는 ![우선 순위 감소 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위 감소** 를 클릭하여 **우선 순위** 값을 변경합니다.

4. 작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a>Microsoft 365 Defender 포털을 사용해 사용자 지정 스팸 방지 정책 제거

Microsoft 365 Defender 포털을 사용하여 사용자 지정 스팸 방지 정책을 제거하면 스팸 필터 규칙과 해당 스팸 필터 정책이 모두 삭제됩니다. 기본 스팸 방지 정책은 제거할 수 없습니다.

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. **스팸 방지 정책** 페이지에서 이름을 클릭하여 목록에서 **사용자 지정 스팸 방지 정책** **유형 값** 이 있는 정책을 선택합니다. 표시되는 정책 세부 정보 플라이아웃 상단에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)을 클릭합니다. **추가 작업** \> ![정책 아이콘 삭제](../../media/m365-cc-sc-delete-icon.png) **정책 삭제**.

3. 확인 대화 상자가 나타나면 **예** 를 클릭합니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 스팸 방지 정책 구성

앞서 설명한 것 처럼 스팸 방지 정책은 스팸 필터 정책 및 스팸 필터 규칙으로 구성됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙 사이의 차이가 명확합니다. **\*-HostedContentFilterPolicy** cmdlet을 사용하여 스팸 필터 정책을 관리하고, **\*-HostedContentFilterRule** cmdlet을 사용하여 스팸 필터 규칙을 관리합니다.

- PowerShell에서는 먼저 스팸 필터 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 스팸 필터 규칙을 만듭니다.
- PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙의 설정을 따로 수정합니다.
- PowerShell에서 스팸 필터 정책을 제거하면 상응하는 스팸 필터 규칙은 자동으로 제거되지 않으며 그 반대의 경우도 마찬가지입니다.

다음 스팸 방지 정책 설정은 PowerShell에서만 사용할 수 있습니다.

- 기본적으로 `On` 상태인 _MarkAsSpamBulkMail_ 매개 변수. 이 설정의 효과는 이 문서 앞부분의 [Microsoft 365 Defender 포털을 사용해 스팸 방지 정책 만들기](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) 섹션에 설명되어 있습니다.
- 최종 사용자 스팸 격리 알림을 위한 다음 설정:
  - _DownloadLink_ 매개 변수는 Outlook용 정크 메일 보고 도구에 대한 링크를 표시하거나 숨깁니다.
  - _EndUserSpamNotificationCustomSubject_ 매개 변수는 알림의 제목 줄을 사용자 지정하는 데 사용할 수 있습니다.

### <a name="use-powershell-to-create-anti-spam-policies"></a>PowerShell을 사용하여 스팸 방지 정책 만들기

PowerShell에서 스팸 방지 정책을 만드는 작업은 2단계 프로세스입니다.

1. 스팸 필터 정책을 만듭니다.
2. 규칙이 적용되는 스팸 필터 정책을 지정하는 스팸 필터 규칙을 만듭니다.

 **참고:**

- 새 스팸 필터 규칙을 만들어 연결되지 않은 기존 스팸 필터 정책을 할당할 수 있습니다. 스팸 필터 규칙은 둘 이상의 스팸 필터 정책에 연결할 수 없습니다.
- 정책을 만들 때까지 Microsoft 365 Defender 포털에서 사용할 수 없는 PowerShell의 새 스팸 필터 정책에 대해서는 다음 설정을 구성할 수 있습니다.
  - 비활성화된 새 정책을 만듭니다(**New-HostedContentFilterRule** cmdlet에서 `$false`를 _Enabled_).
  - **New-HostedContentFilterRule** cmdlet에서 정책을 만드는 동안 우선 순위(_우선 순위_ _\<Number\>_)를 설정하세요.

- 스팸 필터 규칙에 정책을 할당할 때까지 PowerShell에서 만든 새로운 스팸 필터 정책은 Microsoft 365 Defender 포털에 표시되지 않습니다.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>1단계: PowerShell을 사용하여 스팸 필터 정책 만들기

스팸 필터 정책을 만들려면 다음 구문을 사용하세요.

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 스팸 필터 정책을 만드는 예제입니다.

- 스팸 필터링 평가 결과가 스팸 또는 신뢰도가 높은 스팸인 경우 메시지를 격리하고, 격리된 메시지에 대해 기본 [격리 정책](quarantine-policies.md)을 사용합니다(_SpamQuarantineTag_ 또는 _HighConfidenceSpamQuarantineTag_ 매개 변수를 사용하지 않음).
- BCL 7, 8 또는 9는 대량 전자 메일 스팸 필터링 결과 작업을 트리거합니다.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)를 참조하세요.

> [!NOTE]
> 스팸 필터 정책에 사용할 [격리 정책](quarantine-policies.md)을 지정하는 자세한 지침은 [PowerShell을 사용하여 스팸 방지 정책에서 격리 정책 지정](quarantine-policies.md#anti-spam-policies-in-powershell)을 참조하세요.

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>2단계: PowerShell을 사용하여 스팸 필터 규칙 만들기

스팸 필터 규칙을 만들려면 다음 구문을 사용하세요.

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 스팸 필터 규칙을 만드는 예제입니다.

- Contoso Executives라는 스팸 필터 정책은 규칙과 연결됩니다.
- 이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule)을 참조하세요.

### <a name="use-powershell-to-view-spam-filter-policies"></a>PowerShell을 사용하여 스팸 필터 정책 보기

모든 스팸 필터 정책의 요약 목록을 반환하려면 이 명령을 실행합니다.

```PowerShell
Get-HostedContentFilterPolicy
```

특정 스팸 필터 정책에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

다음은 Executives라는 스팸 필터 정책의 모든 속성 값을 반환하는 예제입니다.

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)를 참조하세요.

### <a name="use-powershell-to-view-spam-filter-rules"></a>PowerShell을 사용하여 스팸 필터 규칙 보기

기존 스팸 필터 규칙을 보려면 다음 구문을 사용하세요.

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

모든 스팸 필터 규칙의 요약 목록을 반환하려면 이 명령을 실행합니다.

```PowerShell
Get-HostedContentFilterRule
```

활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

특정 스팸 필터 규칙에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

다음은 Contoso Executives라는 스팸 필터 규칙의 모든 속성 값을 반환하는 예제입니다.

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule)을 참조하세요.

### <a name="use-powershell-to-modify-spam-filter-policies"></a>PowerShell을 사용하여 스팸 필터 정책 수정하기

다음과 같은 항목 외에 PowerShell에서 스팸 필터 정책을 수정할 때 이 문서 앞부분의 [1단계 : PowerShell을 사용하여 스팸 필터 정책 만들기](#step-1-use-powershell-to-create-a-spam-filter-policy) 섹션에 설명된 대로 정책을 만들 때 같은 설정을 사용할 수 있습니다.

- 지정된 정책을 기본 정책으로 바꾸는 _MakeDefault_ 스위치(모든 사용자에게 적용, 항상 우선순위가 **가장 낮으며** 삭제할 수 없음)는 PowerShell에서 스팸 필터 정책을 수정할 때만 사용할 수 있습니다.
- 스팸 필터 정책 이름을 바꿀 수 없습니다(**Set-HostedContentFilterPolicy** cmdlet에 _Name_ 매개 변수가 없음). Microsoft 365 Defender 포털에서 스팸 방지 정책의 이름을 바꿀 경우 스팸 필터 _규칙_ 이름만 변경됩니다.

스팸 필터 정책을 수정하려면 다음 구문을 사용하세요.

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)를 참조하세요.

> [!NOTE]
> 스팸 필터 정책에 사용할 [격리 정책](quarantine-policies.md)을 지정하는 자세한 지침은 [PowerShell을 사용하여 스팸 방지 정책에서 격리 정책 지정](quarantine-policies.md#anti-spam-policies-in-powershell)을 참조하세요.

### <a name="use-powershell-to-modify-spam-filter-rules"></a>PowerShell을 사용하여 스팸 필터 규칙 수정하기

PowerShell에서 스팸 필터 규칙을 수정할 때 사용할 수 없는 유일한 설정은 비활성화된 규칙을 만들 수 있는 _Enabled_ 매개 변수입니다. 기존 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.

그렇지 않으면 PowerShell에서 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다. 이 문서 앞부분의 [2단계: PowerShell을 사용하여 스팸 필터 규칙 만들기](#step-2-use-powershell-to-create-a-spam-filter-rule) 섹션에 설명된 대로 규칙을 만들 때 같은 설정을 사용할 수 있습니다.

스팸 필터 규칙을 수정하려면 다음 구문을 사용하세요.

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

이 예에서는 이름이 `{Fabrikam Spam Filter}`라는 이름의 기존 스팸 필터 규칙의 이름을 바꿉니다.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule)을 참조하세요.

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>PowerShell을 사용하여 스팸 필터 규칙 활성화 또는 비활성화하기

PowerShell에서 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하면 전체 스팸 방지 정책(스팸 필터 규칙과 할당된 스팸 필터 정책)을 사용하거나 사용하지 않도록 설정합니다. 기본 스팸 방지 정책을 사용하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용됨).

PowerShell에서 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

다음은 Marketing Department라는 스팸 필터 규칙을 사용하지 않도록 설정하는 예제입니다.

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

자세한 구문 및 매개 변수 정보는 [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule)과 [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule)을 참조하세요.

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>PowerShell을 사용하여 스팸 필터 규칙의 우선순위 설정하기

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 스팸 필터 규칙의 우선순위를 설정하려면 다음 구문을 사용하세요.

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**참고:**

- 새 규칙을 만들 때 새 규칙의 우선 순위를 설정하려면 **New-HostedContentFilterRule** cmdlet에서 _우선순위_ 매개 변수를 대신 사용하세요.
- 기본 스팸 필터 정책에는 상응하는 스팸 필터 규칙이 없으며 항상 수정할 수 없는 **가장 낮은** 우선순위 값을 갖습니다.

### <a name="use-powershell-to-remove-spam-filter-policies"></a>PowerShell을 사용하여 스팸 필터 정책 제거하기

PowerShell을 사용하여 스팸 필터 정책을 제거할 때 상응하는 스팸 필터 규칙은 제거되지 않습니다.

PowerShell에서 스팸 필터 정책을 제거하려면 다음 구문을 사용하세요.

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

다음은 Marketing Department라는 스팸 필터 정책을 제거하는 예제입니다.

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy)를 참조하세요.

### <a name="use-powershell-to-remove-spam-filter-rules"></a>PowerShell을 사용하여 스팸 필터 규칙 제거하기

PowerShell을 사용하여 스팸 필터 규칙을 제거할 때 상응하는 스팸 필터 정책은 제거되지 않습니다.

PowerShell에서 스팸 필터 규칙을 제거하려면 다음 구문을 사용하세요.

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

다음은 Marketing Department라는 스팸 필터 규칙을 제거하는 예제입니다.

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule)을 참조하세요.

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>GTUBE 메시지를 보내서 스팸 정책 설정을 테스트합니다.

> [!NOTE]
> 이 단계는 GTUBE 메시지를 보내는 전자 메일 조직이 아웃바운드 스팸을 검사하지 않는 경우에만 작동합니다. 검사를 시행하는 경우에는 테스트 메시지를 보낼 수 없습니다.

GTUBE(원치 않는 대량 전자 메일용 제네릭 테스트)는 조직에서 스팸 방지 설정을 확인하기 위해 테스트 메시지에 포함하는 텍스트 문자열입니다. GTUBE 메시지는 맬웨어 설정을 테스트하기 위한 EICAR(European Institute for Computer Antivirus Research) 텍스트 파일과 유사합니다.

공백이나 줄 바꿈 없이 다음 GTUBE 텍스트를 전자 메일 메시지의 한 줄에 포함합니다.

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
