---
title: 아웃바운드 스팸 정책 구성
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 아웃바운드 전자 메일 보내기 서비스를 사용하는 경우 아웃바운드 스팸 필터링이 항상 사용하도록 설정되므로 서비스와 받는 사람을 사용하여 조직을 보호할 수 있습니다.
ms.openlocfilehash: 0fa5ec23eee6144864f16b52d452d02f38b554d7
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957343"
---
# <a name="configure-the-outbound-spam-policy"></a>아웃바운드 스팸 정책 구성

아웃바운드 전자 메일 보내기 서비스를 사용하는 경우 아웃바운드 스팸 필터링이 항상 사용하도록 설정되므로 서비스와 받는 사람을 사용하여 조직을 보호할 수 있습니다. 인바운드 필터링과 마찬가지로 아웃 바운드 스팸 필터링은 연결 필터링 및 콘텐츠 필터링으로 구성 되며 특정 컨트롤에서 아웃 바운드 메시지를 처리할 수 있습니다. 아웃 바운드 스팸 필터 정책 설정 유형:

- 기본값: 회사 전체의 아웃 바운드 스팸 필터 설정을 구성 하는 데 기본 아웃 바운드 스팸 필터 정책이 사용 됩니다. 이 정책은 이름을 바꿀 수 없으며 항상 켜져 있습니다.

- 사용자 지정: 사용자 지정 아웃 바운드 스팸 필터 정책은 세분화 하 여 조직의 특정 사용자, 그룹 또는 도메인에 적용할 수 있습니다. 사용자 지정 정책은 기본 정책보다 항상 우선합니다. 각 사용자 지정 정책의 우선 순위를 변경 하 여 사용자 지정 정책이 실행 되는 순서를 변경할 수 있습니다. 그러나 사용자가 여러 정책과 일치 하는 경우에는 가장 높은 우선 순위 (즉, 0에 가장 가까운 수) 정책만 적용 됩니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?
<a name="sectionSection0"> </a>

- 예상 완료 시간: 5분

- 이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 권한을 확인하려면 [Exchange Online의 기능 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) 항목에서 스팸 방지 항목을 참조하세요.

- 원격 PowerShell에서이 항목의 절차를 수행할 수도 있습니다. [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) cmdlet을 사용하여 설정을 검토하고 [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) cmdlet을 사용하여 아웃바운드 스팸 정책 설정을 편집할 수 있습니다.

  Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요. Exchange Online Protection PowerShell에 연결 하려면 [Exchange Online Protection powershell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)을 참조 하세요.

## <a name="use-the-security--compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>SCC (보안 & 준수 센터)를 사용 하 여 기본 아웃 바운드 스팸 정책 편집

다음 절차에 따라 기본 아웃바운드 스팸 정책을 편집합니다.

### <a name="to-configure-the-default-outbound-spam-policy"></a>기본 아웃바운드 스팸 정책을 구성하려면 다음을 수행합니다.

1. SCC에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동 합니다.

2. **아웃 바운드 스팸 필터 정책 (ALWAYS ON)** 섹션을 확장 하 고 **정책 편집**을 클릭 합니다.

3. **알림** 섹션을 확장 하 고 아웃 바운드 메시지에 대 한 다음 확인란을 선택한 다음 **사용자 추가** 를 선택 하 여 해당 대화 상자에 연결 된 전자 메일 주소나 주소를 추가 합니다. (이는 올바른 SMTP 대상으로 확인 되는 경우 메일 목록 일 수 있습니다.)

   - **의심 스러운 모든 아웃 바운드 전자 메일 메시지의 복사본을 다음 전자 메일 주소 또는 주소로 보내기**: SCL 등급에 관계 없이 필터에 의해 스팸으로 표시 된 메시지입니다. 필터에 의해 거부 되지는 않지만 높은 위험 배달 풀을 통해 라우팅됩니다. 주소가 여러 개인 경우 세미콜론으로 구분합니다. 지정 된 받는 사람은 메시지를 Bcc (숨은 참조) 주소로 받습니다 (보낸 사람 및 받는 사람 필드는 원본에 대 한 송신자 및 수신자).

   - **보낸 사람이 아웃 바운드 스팸을 보낼 수 없도록 차단 된 경우 다음 전자 메일 주소로 알림 보내기**: 세미콜론을 사용 하 여 여러 주소를 구분 합니다.

   특정 사용자가 상당량의 스팸 또는 기타 보내기 예외를 감지 하면 사용자가 전자 메일 메시지를 보낼 수 없으며 지정 된 전자 메일 주소로 알림이 전송 됩니다.

   이 설정을 사용하여 지정되는 도메인의 관리자에게는 해당 사용자의 아웃바운드 메시지가 차단되었다는 알림이 제공됩니다.  이 알림의 모양을 보려면 [보낸 사람이 보내는 아웃 바운드 스팸 차단 되 면 샘플 알림](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)을 참조하세요.

   > [!NOTE]
   > 사용자가 제한 되었음을 나타내는 시스템 경고도 생성 됩니다. 경고에 대 한 자세한 내용을 보고 사용자를 복구 하는 방법에 대 한 자세한 내용은 [스팸 메일을 보낸 후 제한 된 사용자 포털에서 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)를 참조 하세요.

4. **받는 사람 제한** 섹션을 확장 하 여 사용자가 내부 및 외부 받는 사람에 대해 하루 당 최대 수와 함께 보낼 수 있는 최대 받는 사람 수를 지정 합니다.

   > [!NOTE]
   > 모든 입력의 최대 수는 1만입니다. 자세한 내용은 [Exchange online 내에서의 수신 및 전송 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) 참조

7. 사용자가 지정 된 제한을 초과 했을 때 수행할 **작업** 을 지정 합니다.  가능한 작업은 다음과 같습니다.

   - **다음 날까지 사용자가 메일을 보낼 수 없도록**합니다.  전송 제한이 초과 되 면 (내부, 외부 또는 매일) 관리자에 대 한 경고가 생성 되며 사용자는 UTC 시간을 기준으로 다음 날까지 더 이상 전자 메일을 보낼 수 없게 됩니다. 관리자가이 블록을 무시할 수 있는 방법은 없습니다.

   - **사용자가 메일을 보낼 수 없도록 제한**합니다.  전송 제한이 초과 되는 경우 (내부, 외부 또는 매일) 관리자에 대 한 알림이 생성 되 고 사용자가 제한을 제거할 때까지 더 이상 전자 메일을 보낼 수 없게 됩니다.  이러한 경우 사용자는 [제한 된 사용자 페이지](removing-user-from-restricted-users-portal-after-spam.md)에 표시 됩니다.  목록에서 제거 된 사용자는 해당 날짜에 대해 다시 제한 되지 않습니다.

   - **작업/알림을 받지 않습니다**. 전송 제한이 초과 되 면 (내부, 외부 또는 매일) 관리자에 대 한 경고가 생성 되지만 사용자를 제한 하기 위한 조치는 수행 되지 않습니다.

6. **적용 대상** 섹션을 확장 하 고이 정책을 적용할 사용자, 그룹 및 도메인을 지정 하는 조건 기반 규칙을 만듭니다. 고유한 조건을 여러 개 만들 수 있습니다.  참고: 사용자는 여러 조건을 지정할 때 모든 조건을 충족 해야 합니다.  

   - 사용자를 선택 하려면 **보낸 사람**을 선택 합니다. 그러면 표시되는 대화 상자의 사용자 선택 목록에서 회사의 보낸 사람을 한 명 이상 선택하고 추가를 클릭합니다. 목록에 없는 보낸 사람을 추가하려면 해당 전자 메일 주소를 입력한 다음 이름 확인을 클릭합니다. 원하는 항목을 모두 선택한 후 확인을 클릭하여 주 화면으로 돌아갑니다.

   - 그룹을 선택 하려면 **보낸 사람이 구성원 인**을 선택 합니다. 그런 다음 후속 대화 상자에서 그룹을 선택하거나 지정합니다. 그런 후에 확인을 클릭하여 주 화면으로 돌아갑니다.

   - 도메인을 선택 하려면 **보낸 사람 도메인**을 선택 합니다. 그런 다음 후속 대화 상자에서 도메인을 추가합니다. 그런 후에 확인을 클릭하여 주 화면으로 돌아갑니다.

   규칙 내에서 예외를 만들 수 있습니다. 예를 들어 특정 도메인을 제외한 모든 도메인에서 보내는 메시지를 필터링할 수 있습니다. 이렇게 하려면 예외 추가를 클릭하고 다른 조건을 만들 때와 비슷한 방식으로 예외 조건을 만듭니다.

   그룹에 아웃 바운드 스팸 정책을 적용 하는 것은 메일 사용이 가능한 보안 그룹에 대해서만 지원 됩니다.

7. **저장**을 클릭합니다.

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>특정 사용자 집합에 대 한 사용자 지정 정책을 만들려면

1. SCC에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동 합니다.

2. **아웃 바운드 정책 만들기** 단추를 클릭 합니다.

3. **알림** 섹션을 확장 하 고 아웃 바운드 메시지에 대 한 다음 확인란을 선택한 다음 **사용자 추가** 를 선택 하 여 해당 대화 상자에 연결 된 전자 메일 주소나 주소를 추가 합니다.

4. 받는 사람 **제한** 섹션을 확장 하 여 내부 및 외부 받는 사람 및 하루 최대 수에 대해 사용자가 보낼 수 있는 최대 받는 사람 수를 지정 합니다.

7. 사용자가 지정 된 제한을 초과 했을 때 수행할 **작업** 을 지정 합니다.

6. **적용 대상** 섹션을 확장 하 고이 정책을 적용할 사용자, 그룹 및 도메인을 지정 하는 조건 기반 규칙을 만듭니다. 고유한 조건을 여러 개 만들 수 있습니다.  

8. **저장** 을 클릭

## <a name="for-more-information"></a>자세한 내용

[스팸 메일을 보낸 후 제한된 사용자 포털에서 사용자 제거](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[아웃바운드 메시지용 높은 위험 배달 풀](high-risk-delivery-pool-for-outbound-messages.md)

[스팸 방지 및 보호 FAQ](anti-spam-protection-faq.md)
