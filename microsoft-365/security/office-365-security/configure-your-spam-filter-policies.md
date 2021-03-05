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
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online Protection(EOP)에서 스팸 방지 정책을 보고, 만들고 수정하고 삭제하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9808a60d0d6c18ee183524e2ad10ed6b2a749db4
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406105"
---
# <a name="configure-anti-spam-policies-in-eop"></a>EOP에서 스팸 방지 정책 구성하기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 경우, 인바운드 전자 메일 메시지가 EOP를 통해 자동으로 스팸으로부터 보호됩니다. EOP는 스팸에 대한 조직의 전반적인 방어책의 일부로 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용합니다. 자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.

관리자는 기본 스팸 방지 정책을 보고, 편집하고, 구성할 수 있습니다. 세분성을 높이기 위해 사용자 지정 스팸 방지 정책을 만들어 조직의 특정 사용자, 그룹 또는 도메인에 적용할 수도 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.

보안 및 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직의 경우 Exchange Online PowerShell; Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 스팸 방지 정책을 구성할 수 있습니다.

스팸 방지 정책의 기본 요소는 다음과 같습니다.

- **스팸 필터 정책**: 스팸 필터링 결과와 알림 옵션에 대한 작업을 지정합니다.
- **스팸 필터 규칙**: 스팸 필터 정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.

보안 및 준수 센터에서 스팸 방지 정책을 관리하면, 두 가지 요소의 차이는 명확하지 않습니다.

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

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.
  - 스팸 방지 정책을 추가, 수정 및 삭제하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원이어야 합니다.
  - 스팸 방지 정책에 대한 읽기 전용 액세스를 위해서는 **전체 읽기 권한자** 또는 **보안 읽기 권한자** 역할 그룹의 구성원이어야 합니다.

  자세한 내용은 [Exchange Online의 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.

- 스팸 방지 정책에 대한 권장 설정은 [EOP 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)을 참조하세요.

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>보안 및 준수 센터를 사용하여 스팸 방지 정책 만들기

보안 및 준수 센터에서 사용자 지정 스팸 방지 정책을 만들면, 같은 이름을 사용하여 스팸 필터 규칙과 관련된 스팸 필터 정책이 동시에 만들어집니다.

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.

2. **스팸 방지 설정** 페이지에서 **정책 만들기** 탭을 선택합니다.

3. 열리는 **새 스팸 필터 정책** 플라이아웃에서 다음 설정을 구성합니다.

   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다. `\ % & * + / = ? { } | < > ( ) ; : , [ ] "` 문자를 사용하지 마세요.

      이전에 EAC(Exchange 관리 센터)에서 이러한 문자가 포함된 스팸 방지 정책을 만들었다면 PowerShell에서 스팸 방지 정책의 이름을 바꾸어야 합니다. 자세한 내용은 이 문서 뒷부분의 [PowerShell을 사용하여 스팸 필터 규칙 수정](#use-powershell-to-modify-spam-filter-rules) 섹션을 참조하세요.

   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

4. (선택 사항) **스팸 및 대량 작업** 섹션을 확장하고, 다음 설정을 확인하거나 구성합니다.

   - **들어오는 스팸 및 대량 전자 메일에 대해 수행할 작업 선택**: 다음 스팸 필터링 결과를 기반으로 메시지에 수행할 작업을 선택하거나 검토합니다.

     - **스팸**
     - **높은 정확도의 스팸**
     - **피싱 전자 메일**
     - **높은 정확도의 피싱 전자 메일**
     - **대량 전자 메일**

     스팸 필터링 결과에 사용 가능한 작업은 다음 표에 설명되어 있습니다.

     - 확인 표시( ![확인 표시](../../media/checkmark.png)) 작업을 사용할 수 있음을 의미합니다(모든 스팸 필터링 결과에 모든 작업을 사용할 수 있는 것은 아님).
     - 확인 표시 후 별표(<sup>\*</sup>)는 스팸 필터링 결과에 대한 기본 작업을 나타냅니다.

     ****

     |조치|스팸|높음<br>신뢰 수준<br>스팸|피싱<br>전자 메일|높음<br>신뢰 수준<br>피싱<br>전자 메일|대량<br>전자 메일|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**정크 메일 폴더로 메시지 이동**: 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1</sup>|![확인 표시](../../media/checkmark.png)<sup>\*</sup>|![확인 표시](../../media/checkmark.png)<sup>\*</sup>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)<sup>\*</sup>|
     |**X-헤더 추가**: 메시지 헤더에 X-헤더를 추가하고, 메시지를 사서함에 배달합니다. <p> 나중에 **이 X-헤더 텍스트를 추가** 상자에서 X-헤더 필드 이름(값 아님)을 입력합니다. <p> **스팸** 및 **높은 정확도의 스팸** 결과의 경우, 메시지가 정크 메일 폴더로 이동됩니다.<sup>1, 2</sup>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)<sup>\*</sup>|
     |**텍스트를 제목 줄 앞에 추가**: 메시지의 제목 줄 앞에 텍스트를 추가합니다. 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1,2</sup> <p> **이 텍스트를 제목 줄 앞에 추가** 상자에 텍스트를 입력합니다.|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)|
     |**전자 메일 주소로 메시지 리디렉션**: 메시지를 의도된 받는 사람 대신 다른 받는 사람에게 보냅니다. <p> 나중에 **이 전자 메일 주소로 메시지 리디렉션** 상자에 받는 사람을 지정합니다.|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
     |**메시지 삭제**: 모든 첨부 파일을 포함하여 전체 메시지를 자동으로 삭제합니다.|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)|
     |**메시지 격리**: 메시지를 의도된 받는 사람에게 보내는 대신 격리로 보냅니다. <p> 나중에 **격리** 상자에 메시지가 격리되는 기간을 지정합니다.|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)<sup>\*</sup>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
     |**작업 없음**|||||![확인 표시](../../media/checkmark.png)|
     |

     > <sup>1</sup> Exchange Online에서 사서함에 정크 메일 규칙이 활성화되어 있으면 메시지는 정크 메일 폴더로 이동합니다(기본적으로 활성화되어 있음). 자세한 내용은 [Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.
     >
     > EOP로 온-프레미스 Exchange 사서함을 보호하는 독립 실행형 EOP 환경에서는 EOP 스팸 필터링 결과를 변환하여 정크 메일 규칙에 따라 메시지를 정크 메일 폴더로 이동하기 위해 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.
     >
     > <sup>2</sup> 메일 흐름 규칙에서 해당 값을 조건으로 사용하여 메시지를 필터링하거나 경로 지정할 수 있습니다.

   - **임계값 선택**: **대량 전자 메일** 스팸 필터링 결과(지정된 값 이상, 이하 혹은 같음)에 지정된 작업을 트리거하는 메시지의 BCL(대량 불만 수준)을 지정합니다. 값이 높을수록 메시지가 덜 바람직함을 나타냅니다(스팸과 유사할 가능성 높음). 기본값은 7입니다. 자세한 내용은 [EOP에서의 BCL(대량 불만 수준)](bulk-complaint-level-values.md) 및 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조하세요.

     기본적으로 PowerShell 전용 설정 _MarkAsSpamBulkMail_ 은 스팸 방지 정책에서 `On` 상태입니다. 이 설정은 **대량 전자 메일** 필터링 결과의 결과에 크게 영향을 미칩니다.

     - **_MarkAsSpamBulkMail_ 이 켜짐**: 임곗값보다 큰 BCL은 **스팸** 필터링 결과에 해당하는 SCL 6으로 변환되고, 메시지에 대한 **대량 전자 메일** 필터링 결과에 대한 작업이 수행됩니다.

     - **_MarkAsSpamBulkMail_ 이 꺼짐**: 메시지에는 BCL이 찍히지만 **대량 전자 메일** 필터링 결과에 대해 수행되는 _작업은 없습니다._ 실제로 BCL 임곗값과 **대량 전자 메일** 필터링 결과 작업은 관련이 없습니다.

   - **격리**: 스팸 필터링 결과에 대한 작업으로 **메시지 격리** 를 선택한 경우, 메시지를 격리할 기간을 지정합니다. 격리 기간이 만료되면 메시지가 삭제됩니다. 기본값은 30일입니다. 유효한 값은 1~30일입니다. 격리에 대한 자세한 내용은 다음 항목을 참조하세요.

     - [EOP에서 격리된 메시지](quarantine-email-messages.md)
     - [EOP에서 관리자 권한으로 격리된 메시지 및 파일 관리하기](manage-quarantined-messages-and-files.md)
     - [EOP에서 사용자 권한으로 격리된 메시지 찾기 및 해제하기](find-and-release-quarantined-messages-as-a-user.md)

   - **이 X-헤더 텍스트 추가**: 이 상자는 필수이며, **X-헤더 추가** 를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다. 사용자가 지정하는 값은 메시지 헤더에 추가되는 헤더 필드 *이름* 입니다. 헤더 필드 *값* 은 항상 `This message appears to be spam`입니다.

     최대 길이는 255자이며, 값에는 공백이나 콜론(:)이 포함될 수 없습니다.

     예를 들어 값 `X-This-is-my-custom-header`을(를) 입력하면 메시지에 추가되는 X-헤더는 `X-This-is-my-custom-header: This message appears to be spam.`입니다.

     공백이나 콜론(:)을 포함하는 값을 입력하면 입력하는 값이 무시되고, 기본 X 머리글이 메시지(`X-This-Is-Spam: This message appears to be spam.`)에 추가됩니다.

   - **이 텍스트를 제목 줄 앞에 추가**: 이 상자는 필수이며, **텍스트를 제목 줄 앞에 추가** 를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다. 메시지의 제목 줄의 시작 부분에 추가할 텍스트를 입력하세요.

   - **이 전자 메일 주소로 리디렉션**: 이 상자는 필수이며, 스팸 필터링 결과 작업으로 **메시지를 전자 메일 주소로 리디렉션** 을 선택한 경우에만 사용할 수 있습니다. 메시지를 배달하려는 전자 메일 주소를 입력하세요. 세미콜론(;)으로 구분하여 여러 값을 입력할 수 있습니다.

   - **보안 팁**: 기본적으로 보안 팁은 활성화되어 있지만, **켬** 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다. 보안 팁에 대한 자세한 내용은 [전자 메일 메시지 보안 팁](safety-tips-in-office-365.md)을 참조하세요.

   **제로 아워 자동 제거** 설정: ZAP는 Exchange Online 사서함에 이미 배달된 메시지를 검색하여 작업을 수행합니다. ZAP에 대한 자세한 내용은 [제로 아워 자동 제거 - 스팸 및 맬웨어로부터 보호](zero-hour-auto-purge.md)를 참조하세요.

   - **스팸 ZAP**: 기본적으로 ZAP에는 스팸 검색이 활성화되어 있지만, **켬** 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.

   - **피싱 ZAP**: 기본적으로 ZAP에는 피싱 검색이 활성화되어 있지만, **켬** 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.

5. (선택 사항) **허용 목록** 섹션을 확장하여 스팸 필터링을 건너뛰도록 허용된 전자 메일 주소나 전자 메일 도메인을 기준으로 메시지를 보낸 사람을 구성합니다.

   > [!CAUTION]
   >
   > - 여기에 도메인을 추가하기 전에 신중하게 생각하세요. 자세한 내용은 [EOP에서 안전한 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.
   >
   > - 허용 도메인(소유하고 있는 도메인) 또는 공통 도메인(예: microsoft.com 또는 office.com)을 허용된 도메인 목록에 추가하지 않도록 하세요. 이를 통해 침입자가 스팸 필터링을 우회하는 전자 메일을 조직에 보낼 수 있습니다.

   - **허용할 보낸 사람**: **편집** 을 클릭합니다. 표시되는 **허용되는 보낸 사람 목록** 플라이아웃에서 다음을 수행합니다.

      a. 보낸 사람의 전자 메일 주소를 입력합니다. 여러 개인 전자 메일 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.

      b. 이 ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 을 클릭하여 보낸 사람을 추가합니다.

      필요한 만큼 이 단계를 반복합니다.

      사용자가 추가한 보낸 사람은 플라이아웃의 **허용되는 보낸 사람** 섹션에 표시됩니다. 보낸 사람을 삭제하려면 ![제거 아이콘](../../media/scc-remove-icon.png)을 클릭합니다.

      작업을 마쳤으면 **저장** 을 클릭합니다.

   - **허용할 도메인**: **편집** 을 클릭합니다. 표시되는 **허용되는 도메인 목록** 플라이아웃에서 다음 단계를 수행합니다.

      a. 도메인을 입력합니다. 여러 개의 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.

      b. 이 ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 을 클릭하여 도메인을 추가합니다.

      필요한 만큼 이 단계를 반복합니다.

      사용자가 추가한 도메인은 플라이아웃의 **허용되는 도메인** 섹션에 표시됩니다. 도메인을 삭제하려면 ![제거 아이콘](../../media/scc-remove-icon.png)을 클릭합니다.

      작업을 마쳤으면 **저장** 을 클릭합니다.

6. (선택 사항) **차단 목록** 섹션을 확장하여 항상 높은 정확도의 스팸으로 표시되는 전자 메일 주소나 전자 메일 도메인을 기준으로 메시지를 보낸 사람을 구성합니다.

   > [!NOTE]
   > 수동으로 도메인을 차단하는 것은 위험하지 않지만, 관리 작업 부하가 늘어날 수 있습니다. 자세한 내용은 [EOP에서 차단할 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조하세요.

   - **차단할 보낸 사람**: **편집** 을 클릭합니다. 표시되는 **차단되는 보낸 사람 목록** 플라이아웃에서 다음 단계를 수행합니다.

      a. 보낸 사람의 전자 메일 주소를 입력합니다. 여러 개인 전자 메일 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다. 와일드카드(*)는 허용되지 않습니다.

      b. 이 ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 을 클릭하여 보낸 사람을 추가합니다.

      필요한 만큼 이 단계를 반복합니다.

      추가한 보낸 사람은 플라이아웃의 **차단되는 보낸 사람** 섹션에 표시됩니다. 보낸 사람을 삭제하려면 ![제거 단추](../../media/scc-remove-icon.png)를 클릭합니다.

      작업을 마쳤으면 **저장** 을 클릭합니다.

   - **차단할 도메인**: **편집** 을 클릭합니다. 표시되는 **차단되는 도메인 목록** 플라이아웃에서 다음을 수행합니다.

      a. 도메인을 입력합니다. 여러 개의 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다. 와일드카드(*)는 허용되지 않습니다.

      b. 이 ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 을 클릭하여 도메인을 추가합니다.

      필요한 만큼 이 단계를 반복합니다.

      사용자가 추가한 도메인은 플라이아웃의 **차단되는 도메인** 목록에 표시됩니다. 도메인을 삭제하려면 ![제거 단추](../../media/scc-remove-icon.png)를 클릭합니다.

      작업을 마쳤으면 **저장** 을 클릭합니다.

7. (선택 사항) **국제 스팸** 섹션을 확장하여 스팸 필터링으로 차단되는 전자 메일 언어나 원본 국가를 구성합니다.

   - **다음 언어로 작성된 전자 메일 메시지 필터링**: 이 설정은 기본적으로 비활성화되어 있습니다(**상태: 끔**). **편집** 을 클릭합니다. 표시되는 **국제 스팸 설정** 플라이아웃에서 다음 설정을 구성합니다.

     - **다음 언어로 작성된 전자 메일 메시지 필터링**: 확인란을 선택하여 해당 설정을 사용하도록 설정합니다. 이 설정을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.

     - 상자를 클릭하여 언어의 *이름* 을 입력하기 시작합니다. 해당 ISO 639-2 언어 코드와 함께 지원되는 언어의 필터링된 목록이 표시됩니다. 원하는 언어를 찾았으면 선택합니다. 필요한 만큼 이 단계를 반복합니다.

       선택한 언어 목록이 플라이아웃에 표시됩니다. 언어를 삭제하려면 다음을 클릭합니다. ![제거 단추](../../media/scc-remove-icon.png).

     작업을 마쳤으면 **저장** 을 클릭합니다.

   - **다음 국가나 지역에서 보낸 전자 메일 메시지 필터링**: 이 설정은 기본적으로 비활성화되어 있습니다(**상태: 꺼짐**). 이 설정을 사용하도록 설정하려면 **편집** 을 클릭합니다. 표시되는 **국제 스팸 설정** 플라이아웃에서 다음 설정을 구성합니다.

     - **다음 국가나 지역에서 보낸 전자 메일 메시지 필터링**: 확인란을 선택하여 해당 설정을 사용하도록 설정합니다. 이 설정을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.

     - 상자를 클릭하고, 국가나 지역의 *이름* 을 입력하기 시작합니다. 해당하는 두 자로 된 ISO 3166-1 국가 코드와 함께 지원되는 국가의 필터링된 목록이 표시됩니다. 원하는 국가나 지역을 찾았으면 선택합니다. 필요한 만큼 이 단계를 반복합니다.

       선택한 국가 목록이 플라이아웃에 표시됩니다. 국가나 지역을 삭제하려면 다음을 클릭합니다. ![제거 단추](../../media/scc-remove-icon.png).

     작업을 마쳤으면 **저장** 을 클릭합니다.

8. 선택적 **스팸 속성** 섹션에는 기본적으로 꺼져 있는 ASF(고급 스팸 필터) 설정이 포함되어 있습니다. ASF 설정은 더 이상 사용되지 않으며, 해당 기능은 필터링 스택의 다른 부분에 통합됩니다. 모든 ASF 설정을 스팸 방지 정책에서 해제하는 것이 좋습니다.

   이러한 설정에 대한 자세한 내용은 [EOP에서 고급 스팸 필터 설정](advanced-spam-filtering-asf-options.md)을 참조하세요.

9. (필수 사항) **적용 대상** 섹션을 확장하여 정책을 적용할 내부 받는 사람을 식별합니다.

    조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

    사용 가능한 모든 조건을 보려면 **조건 추가** 를 세 번 클릭하는 것이 가장 쉽습니다. ![제거 단추](../../media/scc-remove-icon.png)를 클릭하여 구성하지 않을 조건을 제거할 수 있습니다.

    - **받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다. **태그 추가** 상자를 클릭하여 도메인을 확인하고 선택합니다. 두 개 이상의 도메인을 사용할 수 있는 경우, **태그 추가** 상자를 다시 클릭하여 추가 도메인을 선택합니다.

    - **받는 사람은**: 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다. **태그 추가** 를 클릭하고, 입력을 시작하여 목록을 필터링합니다. **태그 추가** 를 다시 클릭하여 추가 받는 사람을 선택합니다.

    - **받는 사람은 다음의 구성원**: 조직에서 그룹을 하나 이상 지정합니다. **태그 추가** 를 클릭하고, 입력을 시작하여 목록을 필터링합니다. **태그 추가** 를 다시 클릭하여 추가 받는 사람을 선택합니다.

    - **다음의 경우 제외**: 규칙에 대한 예외를 추가하려면 **조건 추가** 를 세 번 클릭하여 사용 가능한 모든 예외를 표시합니다. 설정 및 동작은 조건과 정확히 같습니다.

10. 작업을 마쳤으면 **저장** 을 클릭합니다.

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>보안 및 준수 센터를 사용하여 스팸 방지 정책 보기

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.

2. **스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 스팸 방지 정책을 확장합니다.

   - **기본 스팸 필터 정책** 이라는 기본 정책.

   - **유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 사용자가 만든 사용자 지정 정책.

3. 주요 정책 설정은 표시되는 확장된 정책 세부 정보에 표시됩니다. 자세한 내용을 보려면 **정책 편집** 을 클릭합니다.

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>보안 및 준수 센터를 사용하여 스팸 방지 정책 수정하기

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.

2. **스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 스팸 방지 정책을 확장합니다.

   - **기본 스팸 필터 정책** 이라는 기본 정책.

   - **유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 사용자가 만든 사용자 지정 정책.

3. **정책 편집** 을 클릭합니다.

사용자 지정 스팸 방지 정책의 경우, 플라이아웃에서 표시되는 사용 가능한 설정은 [보안 및 준수 센터를 사용하여 스팸 방지 정책 만들기](#use-the-security--compliance-center-to-create-anti-spam-policies)에서 설명한 것과 같습니다.

**기본 스팸 필터 정책** 이라는 기본 스팸 방지 정책의 경우, **적용 대상** 섹션을 사용할 수 없으며(이 정책은 모든 사용자에게 적용됨) 정책의 이름을 바꿀 수 없습니다.

정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.

### <a name="enable-or-disable-anti-spam-policies"></a>스팸 방지 정책 활성화 또는 비활성화하기

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.

2. **스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 사용자가 만든 사용자 지정 정책을 확장합니다(**유형** 의 열 값은 **사용자 지정 스팸 방지 정책**).

3. 표시되는 확장된 정책 세부 정보에서 **켬** 열에 있는 값을 확인합니다.

   토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다. ![토글 끔](../../media/scc-toggle-off.png)

   토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다. ![토글 켬](../../media/scc-toggle-on.png)

기본 스팸 방지 정책은 사용하지 않도록 설정할 수 없습니다.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>사용자 지정 스팸 방지 정책의 우선순위 설정하기

기본적으로 만들어진 순서에 따라 스팸 방지 정책에 우선순위가 지정됩니다(새 정책은 이전 정책 보다 우선순위가 낮음). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

사용자 지정 스팸 방지 정책은 처리되는 순서로 표시됩니다(첫 번째 정책에는 **우선순위** 값 0이 표시됨). **기본 스팸 필터 정책** 이라는 기본 스팸 방지 정책은 우선순위 값이 **가장 낮음** 이며 변경할 수 없습니다.

 **참고**: 보안 및 준수 센터에서는 스팸 방지 정책을 만든 후에만 우선순위를 변경할 수 있습니다. PowerShell에서 사용자는 기존 규칙의 우선순위에 영향을 줄 수 있는 스팸 필터 규칙을 만들 때 기본 우선순위를 재정의할 수 있습니다.

정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.

2. **스팸 방지 설정** 페이지에서 **유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 정책을 찾습니다. **우선순위** 열의 값을 확인합니다.

   - 우선순위가 가장 높은 사용자 지정 스팸 방지 정책의 값은 ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **0** 입니다.

   - 우선순위가 가장 낮은 사용자 지정 스팸 방지 정책의 값은 ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) **n**(예: ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) **3**)입니다.

   - 사용자 지정 스팸 방지 정책이 세 개 이상 있는 경우, 가장 높은 우선순위와 가장 낮은 우선순위 사이의 정책 값은 ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png)![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **n** 입니다(예: ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png)![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. 이 ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) 또는 ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) 을 클릭하여 우선 순위 목록에서 사용자 지정 스팸 방지 정책을 위나 아래로 이동합니다.

### <a name="configure-end-user-spam-notifications"></a>최종 사용자 스팸 알림 구성하기

스팸 필터링 결과에서 메시지를 격리하는 경우, 받는 사람에게 전송된 메시지에 일어난 자세한 내용을 알릴 수 있도록 최종 사용자 스팸 알림을 구성할 수 있습니다. 이 알림에 대한 자세한 내용은 [EOP에서 최종 사용자 스팸 알림](use-spam-notifications-to-release-and-report-quarantined-messages.md)을 참조하세요.

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.

2. **스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 스팸 방지 정책을 확장합니다.

   - **기본 스팸 필터 정책** 이라는 기본 정책.

   - **유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 사용자가 만든 사용자 지정 정책.

3. 표시되는 확장된 정책 세부 정보에서 **최종 사용자 스팸 알림 구성** 을 클릭합니다.

4. 열리는 **\<Policy Name\>** 대화 상자에서 다음 설정을 구성합니다.

   - **최종 사용자 스팸 알림 사용 설정**: 확인란을 선택하여 알림을 사용하도록 설정 알림을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.

   - **최종 사용자 스팸 알림 보내기 간격(일)**: 알림을 보내는 빈도를 선택합니다. 기본값은 3일입니다. 1~15일을 입력할 수 있습니다.

     24시간 내에 다음 시간에 시작하는 최종 사용자 스팸 알림의 3가지 주기가 있습니다(01:00 UTC, 08:00 UTC 및 16:00 UTC).

     > [!NOTE]
     > 이전 주기 중에 알림이 누락되면 다음 주기가 알림을 푸시합니다. 이로 인해 당일에 여러 알림이 표시될 수 있습니다.

   - **알림 언어**: 드롭다운을 클릭하고. 목록에서 사용 가능한 언어를 선택합니다. 기본적인 값은 **기본값** 이고 이는 영어를 의미합니다.

   작업을 마쳤으면 **저장** 을 클릭합니다.

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>보안 및 준수 센터를 사용하여 스팸 방지 정책 제거하기

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.

2. **스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 삭제하려는 사용자 지정 정책을 확장합니다(**유형** 열은 **사용자 지정 스팸 방지 정책**).

3. 표시되는 확장된 정책 세부 정보에서 **정책 삭제** 를 클릭합니다.

4. 표시되는 경고 대화 상자에서 **예** 를 클릭합니다.

기본 정책은 제거할 수 없습니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 스팸 방지 정책 구성

앞서 설명한 것 처럼 스팸 방지 정책은 스팸 필터 정책 및 스팸 필터 규칙으로 구성됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙 사이의 차이가 명확합니다. **\*-HostedContentFilterPolicy** cmdlet을 사용하여 스팸 필터 정책을 관리하고, **\*-HostedContentFilterRule** cmdlet을 사용하여 스팸 필터 규칙을 관리합니다.

- PowerShell에서는 먼저 스팸 필터 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 스팸 필터 규칙을 만듭니다.
- PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙의 설정을 따로 수정합니다.
- PowerShell에서 스팸 필터 정책을 제거하면 상응하는 스팸 필터 규칙은 자동으로 제거되지 않으며 그 반대의 경우도 마찬가지입니다.

다음 스팸 방지 정책 설정은 PowerShell에서만 사용할 수 있습니다.

- 기본적으로 `On` 상태인 _MarkAsSpamBulkMail_ 매개 변수. 이 설정의 효과는 이 문서의 앞부분에 있는 [보안 및 준수 센터를 사용하여 스팸 방지 정책 만들기](#use-the-security--compliance-center-to-create-anti-spam-policies) 섹션에서 설명했습니다.

- 최종 사용자 스팸 격리 알림을 위한 다음 설정:

  - _DownloadLink_ 매개 변수는 Outlook용 정크 메일 보고 도구에 대한 링크를 표시하거나 숨깁니다.

  - _EndUserSpamNotificationCustomSubject_ 매개 변수는 알림의 제목 줄을 사용자 지정하는 데 사용할 수 있습니다.

### <a name="use-powershell-to-create-anti-spam-policies"></a>PowerShell을 사용하여 스팸 방지 정책 만들기

PowerShell에서 스팸 방지 정책을 만드는 작업은 2단계 프로세스입니다.

1. 스팸 필터 정책을 만듭니다.
2. 규칙이 적용되는 스팸 필터 정책을 지정하는 스팸 필터 규칙을 만듭니다.

 **참고:**

- 새 스팸 필터 규칙을 만들어 연결되지 않은 기존 스팸 필터 정책을 할당할 수 있습니다. 스팸 필터 규칙은 둘 이상의 스팸 필터 정책에 연결할 수 없습니다.

- 정책을 만들 때까지 보안 및 준수 센터에서 사용할 수 없는 PowerShell의 새 스팸 필터 정책에 대해 다음 설정을 구성할 수 있습니다.

  - 비활성화된 새 정책을 만듭니다(**New-HostedContentFilterRule** cmdlet에서 `$false`를 _Enabled_).
  - **New-HostedContentFilterRule** cmdlet에서 정책을 만드는 동안 우선 순위(_우선 순위_ _\<Number\>_)를 설정하세요.

- 스팸 필터 규칙에 정책을 할당할 때까지 PowerShell에서 만든 새로운 스팸 필터 정책은 보안 및 준수 센터에 표시되지 않습니다.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>1단계: PowerShell을 사용하여 스팸 필터 정책 만들기

스팸 필터 정책을 만들려면 다음 구문을 사용하세요.

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 스팸 필터 정책을 만드는 예제입니다.

- 스팸 필터링 결과가 스팸이거나 높은 정확도의 스팸인 경우 메시지를 격리합니다.

- BCL 6은 대량 전자 메일 스팸 필터링 결과 작업을 트리거합니다.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **New-Set-hostedcontentfilterpolicy** 및 **Set-Set-hostedcontentfilterpolicy** 에는 이전 _ZapEnabled_ 매개 변수와 최신 _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수가 포함되어 있습니다. _ZapEnabled_ 매개 변수는 2020년 2월부터 더 이상 사용되지 않습니다. _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수는 _ZapEnabled_ 매개 변수에서 값을 상속하는 데 사용됩니다. 그러나 명령에 _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수를 사용하거나 보안 및 준수 센터의 스팸 방지 정책에서 **Spam ZAP** 또는 **Phish ZAP** 설정을 사용하는 경우, _ZapEnabled_ 매개 변수의 값은 무시됩니다. 즉, _ZapEnabled_ 매개 변수를 사용하지 않도록 하세요. _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수를 대신 사용하세요.

자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)를 참조하세요.

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

자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule)을 참조하세요.

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

자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)를 참조하세요.

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

자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule)을 참조하세요.

### <a name="use-powershell-to-modify-spam-filter-policies"></a>PowerShell을 사용하여 스팸 필터 정책 수정하기

다음과 같은 항목 외에 PowerShell에서 스팸 필터 정책을 수정할 때 이 문서 앞부분의 [1단계 : PowerShell을 사용하여 스팸 필터 정책 만들기](#step-1-use-powershell-to-create-a-spam-filter-policy) 섹션에 설명된 대로 정책을 만들 때 같은 설정을 사용할 수 있습니다.

- 지정된 정책을 기본 정책으로 바꾸는 _MakeDefault_ 스위치(모든 사용자에게 적용, 항상 우선순위가 **가장 낮으며** 삭제할 수 없음)는 PowerShell에서 스팸 필터 정책을 수정할 때만 사용할 수 있습니다.

- 스팸 필터 정책 이름을 바꿀 수 없습니다(**Set-HostedContentFilterPolicy** cmdlet에 _Name_ 매개 변수가 없음). 보안 및 준수 센터에서 스팸 방지 정책의 이름을 바꿀 경우 스팸 필터 _규칙_ 이름만 변경됩니다.

스팸 필터 정책을 수정하려면 다음 구문을 사용하세요.

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)를 참조하세요.

### <a name="use-powershell-to-modify-spam-filter-rules"></a>PowerShell을 사용하여 스팸 필터 규칙 수정하기

PowerShell에서 스팸 필터 규칙을 수정할 때 사용할 수 없는 유일한 설정은 비활성화된 규칙을 만들 수 있는 _Enabled_ 매개 변수입니다. 기존 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.

그렇지 않으면 PowerShell에서 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다. 이 문서 앞부분의 [2단계: PowerShell을 사용하여 스팸 필터 규칙 만들기](#step-2-use-powershell-to-create-a-spam-filter-rule) 섹션에 설명된 대로 규칙을 만들 때 같은 설정을 사용할 수 있습니다.

스팸 필터 규칙을 수정하려면 다음 구문을 사용하세요.

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

다음은 보안 및 준수 센터에서 문제를 일으킬 수 있는 `{Fabrikam Spam Filter}`(이)라는 기존 스팸 필터 규칙의 이름을 바꾸는 예제입니다.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule)을 참조하세요.

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

자세한 구문 및 매개 변수 정보는 [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule)과 [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule)을 참조하세요.

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

자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy)를 참조하세요.

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

자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule)을 참조하세요.

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>GTUBE 메시지를 보내서 스팸 정책 설정을 테스트합니다.

> [!NOTE]
> 이 단계는 GTUBE 메시지를 보내는 전자 메일 조직이 아웃바운드 스팸을 검사하지 않는 경우에만 작동합니다. 검사하는 경우에는 테스트 메시지를 보낼 수 없습니다.

GTUBE(원치 않는 대량 전자 메일용 제네릭 테스트)는 조직에서 스팸 방지 설정을 확인하기 위해 테스트 메시지에 포함하는 텍스트 문자열입니다. GTUBE 메시지는 맬웨어 설정을 테스트하기 위한 EICAR(European Institute for Computer Antivirus Research) 텍스트 파일과 유사합니다.

공백이나 줄 바꿈 없이 다음 GTUBE 텍스트를 전자 메일 메시지의 한 줄에 포함합니다.

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>허용/차단 목록

필터가 메시지를 빠뜨리거나 시스템에서 메시지를 확인하는 데 시간이 걸리는 경우가 있습니다. 이 경우 스팸 방지 정책에는 현재 결과를 재정의 하는데 사용 할 수 있는 허용 및 차단 목록이 있습니다. 수행할 작업이 필터링 스택에서 수행되고 있어야 하므로 목록을 관리할 수 없고 일시적이기 때문에 이 옵션은 드물게 사용됩니다.

> [!TIP]
> 조직이 서비스에서 제공하는 결과에 동의하지 경우가 있습니다. 이 경우 허용 또는 차단 목록을 영구적으로 유지할 수 있습니다. 하지만 도메인을 허용 목록에 오래 동안 유지할 경우 보낸 사람에게 도메인을 인증하는지 확인하고, 확인하지 않을 경우 DMARC 거부로 설정하도록 요청해야 합니다.
