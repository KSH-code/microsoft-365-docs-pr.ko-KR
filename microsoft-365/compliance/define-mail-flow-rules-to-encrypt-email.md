---
title: 전자 메일 메시지를 암호화하는 메일 흐름 규칙 정의
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkMAC
description: 관리자는 메일 흐름 규칙(전송 규칙)을 만들어 전자 메일을 사용하여 메시지를 암호화하고 암호 해독하는 방법을 Office 365 메시지 암호화.
ms.openlocfilehash: 73ff2ae12d6d0857760909c43cf12c4bbd84c13b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206148"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>전자 메일 메시지를 암호화하는 메일 흐름 규칙 정의

전송 규칙을 관리하는 Exchange Online 메일 흐름 규칙(전송 규칙)을 만들어 보내고 받는 전자 메일 메시지를 보호할 수 있습니다. 조직 내부 또는 조직에서 보낸 암호화된 메시지에 대한 답장에서 오는 암호화된 메시지에서 암호화를 제거하고 발신 전자 메일 메시지를 암호화하는 규칙을 설정할 수 있습니다. EAC(Exchange 관리 센터) 또는 PowerShell을 사용하여 Exchange Online 규칙을 만들 수 있습니다. 전체 암호화 규칙 외에도 최종 사용자에 대한 개별 메시지 암호화 옵션을 사용할지 여부를 선택할 수도 있습니다.

조직 외부의 보낸 사람으로부터의 인바운드 메일을 암호화할 수 없습니다.

최근에 Active Directory RMS에서 Azure Information Protection으로 마이그레이션한 경우 기존 메일 흐름 규칙을 검토하여 새 환경에서 계속 작동하도록 해야 합니다. 또한 Azure Information Protection을 통해 사용할 수 있는 새로운 OME(Office 365 메시지 암호화) 기능을 활용하려면 기존 메일 흐름 규칙을 업데이트해야 합니다. 그렇지 않으면 사용자는 새로운 원활한 OME 환경 대신 이전 HTML 첨부 파일 형식을 사용하는 암호화된 메일을 계속 받게 됩니다. 아직 OME를 설정하지 않은 경우 자세한 내용은 [Set up new Office 365 메시지 암호화 capabilities을](set-up-new-message-encryption-capabilities.md) 참조하십시오.

메일 흐름 규칙을 구성하는 구성 요소 및 메일 흐름 규칙의 작동 방식에 대한 자세한 내용은 에서 메일 흐름 [규칙(전송 규칙)을 Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Azure Information Protection에서 메일 흐름 규칙이 작동되는 방법에 대한 자세한 내용은 Azure Information Protection 레이블에 Exchange Online 메일 흐름 [규칙 구성을 참조하세요.](/azure/information-protection/deploy-use/configure-exo-rules)

> [!IMPORTANT]
> 하이브리드 Exchange 환경의 경우, 전자 메일이 OME를 통해 라우팅되는 경우만 OME를 사용하여 암호화된 메일을 보내고 받을 수 Exchange Online. 하이브리드 Exchange 환경에서 OME를 구성하려면 먼저 하이브리드 [](/Exchange/exchange-hybrid) 구성 마법사를 사용하여 하이브리드를 [](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) 구성한 다음 Office 365 서버에서 전자 메일 서버로 흐르도록 메일을 구성하고 전자 메일 서버에서 전자 메일 서버로 흐르도록 메일을 [Office 365.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365) 메일이 전자 메일을 통과하도록 구성한 Office 365 이 지침을 사용하여 OME에 대한 메일 흐름 규칙을 구성할 수 있습니다.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>새 OME 기능을 사용하여 전자 메일 메시지를 암호화하는 메일 흐름 규칙 만들기

EAC를 사용하여 새 OME 기능을 사용하여 메시지 암호화를 트리거하기 위한 메일 흐름 규칙을 정의할 수 있습니다.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>EAC를 사용하여 새 OME 기능을 사용하여 전자 메일 메시지 암호화 규칙 만들기

1. 웹 브라우저에서 전역 관리자 권한이 부여된 직장 또는 학교 계정을 사용하여 에 [Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 관리 **타일을** 선택하세요.

3. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>, choose **Admin centers** \> **Exchange.**

4. EAC에서 메일 흐름 **규칙으로** \> **이동하고** 새 새 **아이콘을** ![ 선택합니다.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**새 규칙을 만드시다.** EAC 사용에 대한 자세한 내용은 에서 Exchange [관리 센터를 Exchange Online.](/exchange/exchange-admin-center)

5. **이름에** 규칙의 이름(예: 사용자에 대한 메일 암호화)을 DrToniRamos@hotmail.com.

6. 다음의 경우 이 **규칙 적용에서** 조건을 선택하고 필요한 경우 값을 입력합니다. 예를 들어 DrToniRamos@hotmail.com에 보내는 메시지를 암호화하려면 다음을 수행합니다.

   1. **다음의 경우 이 규칙 적용** 에서 **받는 사람이 다음과 같음** 을 선택합니다.

   2. 연락처 목록에서 기존 이름을 선택하거나 **이름 확인** 상자에 새 전자 메일 주소를 입력합니다.

      - 기존 이름을 선택하려면 목록에서 이름을 선택한 다음 **확인** 을 클릭합니다.

      - 새 이름을 입력하려면 이름 확인란에  전자 메일 주소를 입력한 다음 이름 **확인을** \> **선택합니다.**

7. 조건을 더 추가하려면 추가 **옵션을** 선택한 다음 조건 **추가를** 선택하고 목록에서 선택합니다.

   예를 들어 받는 사람이 조직 외부에 있는 경우만 규칙을 적용하려면 조건 추가를 선택한 **다음** 받는 사람이 **외부/내부** 조직 외부에 있습니다 확인 \> **을** \> **선택합니다.**

8. 새 OME 기능을 사용하여 암호화를 사용하도록 설정하려면  다음 **작업에서** 메시지 보안 수정을 선택한 다음 메시지 보안 Office 365 메시지 암호화 및 권한 보호 **적용을 선택합니다.** 목록에서 RMS 템플릿을 선택하고 **저장을** 선택한 다음 확인 을 **선택합니다.**
  
  서식 파일 목록에는 모든 기본 템플릿 및 옵션과 기본 서식 파일에서 사용하기 위해 만든 모든 사용자 지정 템플릿이 Office 365. 목록이 비어 있는 경우 Set up new Office 365 메시지 암호화 [capabilities에](set-up-new-message-encryption-capabilities.md)설명된 새 기능을 Office 365 메시지 암호화 합니다. 기본 템플릿에 대한 자세한 내용은 Azure Information Protection용 템플릿 구성 및 [관리를 참조하세요.](/information-protection/deploy-use/configure-policy-templates) 전달 금지 **옵션에** 대한 자세한 내용은 전자 메일에 [대해 전달 금지 옵션을 참조하세요.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) 암호화 전용 옵션에 대한 **자세한** 내용은 전자 메일의 암호화 [전용 옵션을 참조하세요.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

  다른 작업을 **지정하려는** 경우 추가 작업을 선택할 수 있습니다.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>EAC를 사용하여 새 OME 기능을 사용하기 위해 기존 메일 흐름 규칙 업데이트

1. 웹 브라우저에서 전역 관리자 권한이 부여된 직장 또는 학교 계정을 사용하여 에 [Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 관리 **타일을** 선택하세요.

3. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>, choose **Admin centers** \> **Exchange.**

4. EAC에서 **메일 흐름** \> **규칙** 으로 이동합니다.

5. 메일 흐름 규칙 목록에서 새 OME 기능을 사용하기 위해 수정할 규칙을 선택한  다음 편집 편집 ![ 아이콘을 선택합니다. ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)

6. 새 OME 기능을 사용하여 암호화를 사용하도록 설정하려면  다음 **작업에서** 메시지 보안 수정을 선택한 다음 메시지 보안 Office 365 메시지 암호화 및 권한 보호 **적용을 선택하세요.** 목록에서 RMS 템플릿을 선택하고 저장을 선택한 **다음** 확인 을 **선택합니다.**

   서식 파일 목록에는 모든 기본 템플릿 및 옵션과 기본 서식 파일에서 사용하기 위해 만든 모든 사용자 지정 템플릿이 Office 365. 목록이 비어 있는 경우 Azure Information Protection을 Office 365 메시지 암호화 기본 제공되는 새 Office 365 메시지 암호화 기능 설정에 설명된 새 기능을 사용하여 새 기능을 설정해야 [합니다.](set-up-new-message-encryption-capabilities.md) 기본 템플릿에 대한 자세한 내용은 Azure Information Protection용 템플릿 구성 및 [관리를 참조하세요.](/information-protection/deploy-use/configure-policy-templates) 전달 금지 옵션에 대한 자세한 내용은 전자 메일에 [대해 전달 금지 옵션을 참조하세요.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) 암호화 전용 옵션에 대한 자세한 내용은 전자 메일에 대한 [암호화 전용 옵션을 참조하세요.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   다른 작업을 **지정하려는** 경우 추가 작업을 선택할 수 있습니다.

7. 다음 **작업 수행 목록에서** 메시지 보안 수정에 할당된 모든 작업을 제거합니다. 이전 버전의  \> **OME 를 적용합니다.**

8. **저장** 을 선택합니다.

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>새 OME 기능이 있는 전자 메일 메시지에 대한 암호화를 제거하는 메일 흐름 규칙 만들기

EAC를 사용하여 새 OME 기능을 사용하여 메시지 암호화 제거를 트리거하는 메일 흐름 규칙을 정의할 수 있습니다.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>EAC를 사용하여 새 OME 기능이 있는 전자 메일 메시지에서 암호화를 제거하는 규칙 만들기

조직에서 적용한 암호화를 제거할 수 있습니다.

1. 웹 브라우저에서 전역 관리자 권한이 부여된 직장 또는 학교 계정을 사용하여 에 [Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 관리 **타일을** 선택하세요.

3. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>, choose **Admin centers** \> **Exchange.**

4. EAC에서 메일 흐름 **규칙으로** \> **이동하고** 새 새 **아이콘을** ![ 선택합니다.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**새 규칙을 만드시다.** EAC 사용에 대한 자세한 내용은 에서 Exchange [관리 센터를 Exchange Online.](/exchange/exchange-admin-center)

5. **이름에** 규칙의 이름(예: 보낸 메일에서 암호화 제거)을 입력합니다.

6. 다음의 경우 이 규칙 **적용에서** 암호화를 메시지에서 제거해야 하는 조건을 선택합니다. 추가 **보낸 사람이 메일을** 보내기 위해 조직 내부에 위치하거나 받는 사람이 조직 내부에서 메일을 받을 수 \>    \>  있습니다.

7. 다음 **작업에서** **메시지** 보안 수정 및 권한 보호 제거를 Office 365 메시지 암호화 \> **선택합니다.**

8. **저장** 을 선택합니다.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>새 기능을 Office 365 메시지 암호화 메일 흐름 규칙 만들기

아직 조직을 새 OME 기능으로 이동하지 않은 경우 조직에 적절한 새 OME 기능으로 이동하는 계획을 세우는 것이 좋습니다. 자세한 내용은 Azure Information Protection을 Office 365 메시지 암호화 새로운 Office 365 메시지 암호화 기능 [설치를 참조하세요.](set-up-new-message-encryption-capabilities.md) 그렇지 않으면 새 OME 기능을 사용하지 Office 365 메시지 암호화 메일 흐름 규칙 [정의를 참조합니다.](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)

## <a name="related-content"></a>관련 콘텐츠

[Office 365의 암호화](encryption.md)

[새로운 Office 365 메시지 암호화 기능 설정](set-up-new-message-encryption-capabilities.md)

[암호화된 메시지에 브랜딩 추가](add-your-organization-brand-to-encrypted-messages.md)

[메일 흐름 규칙(전송 규칙) Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
