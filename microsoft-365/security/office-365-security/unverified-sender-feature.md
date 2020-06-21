---
title: 확인 되지 않은 보낸 사람
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 피싱 메시지가 사서함, Outlook.com 및 웹용 Outlook에 도달 하지 못하도록 차단 하는 방법을 안내 합니다.
ms.openlocfilehash: ed317f5673aa37b91e8c5092eb127b8df6be944e
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754835"
---
# <a name="unverified-sender"></a>확인 되지 않은 보낸 사람

> [!NOTE]
> 이러한 업데이트는 지금 배포 되며 일부 사용자에 게는 제공 되지 않을 수 있습니다. 이 기능은 Enterprise Outlook.com 및 Enterprise Outlook Win32 데스크톱 사용자에 대해 지원 됩니다. 현재 소비자 Office 365 사용자에 게는 사용할 수 없습니다.

피싱 메시지가 사서함에 도달 하는 것을 방지 하기 위해 Office 365는 보낸 사람이 누구 인지를 확인 하 고 의심 스러운 메시지를 정크 메일로 표시 합니다.

> [!IMPORTANT]
> 메시지가 피싱 사기로 표시 되 면 Outlook은 페이지 맨 위에 경고를 표시 하지만 메시지의 모든 링크는 계속 열 수 있습니다.

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>받은 편지함에서 의심 스러운 메시지를 어떻게 확인할 수 있나요?

Outlook에서는 메시지를 보낸 사람이 식별 되지 않거나 id가 보낸 사람 주소에 표시 되는 내용과 다를 때의 표시기를 표시 합니다.

## <a name="you-see-a--in-the-sender-image"></a>보낸 사람 이미지에 '? '가 표시 됩니다.

Office 365에서 전자 메일 인증 기술을 사용 하 여 보낸 사람의 id를 확인할 수 없으면 '? '가 보낸 사람 이미지에 표시 됩니다.

![메시지가 확인 통과 되지 않음](../../media/message-did-not-pass-verification.jpg)

인증에 실패 한 모든 메시지는 악성이 아닙니다. 그러나 보낸 사람을 인식 하지 못하는 경우 인증을 받지 않는 메시지와 상호 작용할 때는 주의 해야 합니다. 또는 일반적으로 보낸 사람 이미지에 '? '가 포함 되지 않는 보낸 사람을 인식할 수 있지만이를 갑자기 보면 보낸 사람이 위장 중 이라고 표시 됩니다.

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>확인 되지 않은 보낸 사람 처리를 수신 하는 메시지를 관리 하는 방법 

Office 365 고객 인 경우 Office 365 보안 & 준수 센터를 통해이 기능을 관리할 수 있습니다.

- 보안 & 준수 센터에서 전역 또는 보안 관리자는 피싱 정책 아래의 스푸핑 방지를 통해이 기능을 설정 하거나 해제할 수 있습니다. 또한 Exchange Online PowerShell에서 **AntiPhishPolicy** cmdlet을 사용할 수 있습니다. 자세한 내용은 [Office 365 및 AntiPhishPolicy의 피싱 방지 보호](anti-phishing-protection.md) 를 참조 [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/set-antiphishpolicy)하세요.

    ![그래픽 인터페이스에서 인증 되지 않은 보낸 사람 편집](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- 관리자가 가양성을 식별 했 고 보낸 사람이 확인 되지 않은 보낸 사람 처리를 수신 하지 않아야 하는 경우 다음 작업 중 하나를 수행 하 여 위장 인텔리전스 스푸핑 허용 목록에 보낸 사람을 추가할 수 있습니다.

  - 스푸핑 인텔리전스 이해를 통해 도메인 쌍을 추가 합니다. 자세한 내용은 [연습용: 스푸핑 인텔리전스 이해](walkthrough-spoof-intelligence-insight.md)를 참조 하십시오.

  - Exchange Online PowerShell에서 **get-phishfilterpolicy** cmdlet을 통해 도메인 쌍을 추가 합니다. 자세한 내용은 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy) 및 [set UP Office 365 ATP 안티 피싱 및 피싱 방지 정책을](set-up-anti-phishing-policies.md)참조 하십시오.

또한 메일 흐름 규칙 (전송 규칙이 라고도 함) 또는 안전한 도메인 목록 (스팸 방지 정책)을 통해 메시지가 받은 편지 함으로 배달 된 경우에는 확인 되지 않은 보낸 사람 처리를 적용 하지 않습니다.

## <a name="how-to-manage-the-via-tag"></a>' Via ' 태그를 관리 하는 방법 

Office 365 고객 인 경우 확인 되지 않은 보낸 사람 처리를 관리 하는 것과 같은 방법으로 Office 365 보안 & 준수 센터를 통해이 기능을 관리할 수 있습니다. 위장 인텔리전스 스푸핑 허용 목록에 보낸 사람을 추가 하면 ' via ' 처리는 적용 되지 않습니다.

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a>Outlook.com 및 Outlook Win32 데스크톱에서 '? ' 및 ' via ' 속성을 추가 하는 데 사용 하는 기준은 무엇입니까?

보낸 사람 이미지의 '? ': Outlook.com가 SPF 또는 DKIM 인증을 통과 하 고 dmarc 전달을 수신 하거나, Office 365 스푸핑 인텔리전스에서 복합 인증을 통과 해야 합니다. 자세한 내용은 [office 365에서 스푸핑 방지](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 및 [Dkim을 사용 하 여 사용자 지정 365 도메인에서 전송 되는 아웃 바운드 전자 메일의 유효성을 검사 하](use-dkim-to-validate-outbound-email.md)는 데 도움을 주는 방법에 SPF 설정를 참조 하세요.

Via 태그의 경우: 보낸 사람 주소에 있는 도메인이 DKIM 서명 또는 SMTP 메일에서 보낸 도메인과 다른 경우 Outlook.com는 해당 두 필드 중 하나에 도메인을 표시 합니다 (DKIM 서명 우선).

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a>스푸핑 인텔리전스 스푸핑 허용 목록을 활용 하지 않고 '? '를 제거 하려면 어떻게 해야 합니까?

보낸 사람 이미지의 '? '에 대해 보낸 사람으로 서 SPF 또는 DKIM 중 하나를 사용 하 여 메시지를 인증 해야 합니다.

Via 태그: 보낸 사람으로 서, DKIM 서명 또는 SMTP 메일의 도메인은 From 주소에 있는 도메인과 같거나 그 하위 도메인 인지 확인 해야 합니다.

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a>인증을 통과 하지 못하는 모든 메시지에 대해 Outlook.com 및 Outlook Win32 데스크톱을 표시 하 시겠습니까?

꼭 필요 하지는 않습니다. Office 365에서 보낸 사람을 인증 하기 위해 메시지에 다른 속성이 있을 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Outlook.com 전자 메일 계정 보호](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Outlook.com에서 피싱을 처리 하는 방법](https://support.microsoft.com/office/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[웹용 Outlook에서 정크 메일 및 스팸 필터링](https://support.microsoft.com/office/db786e79-54e2-40cc-904f-d89d57b7f41d)
