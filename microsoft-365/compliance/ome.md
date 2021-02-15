---
title: 메시지 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: 조직 내부 및 외부 사용자 간에 암호화된 전자 메일 메시지를 보내고 받는 방법을 학습합니다.
ms.openlocfilehash: f601618c3ad44361794720852b391949901122f2
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709624"
---
# <a name="message-encryption"></a>메시지 암호화

전자 메일을 통해 재무 데이터, 법적 계약, 기밀 제품 정보, 매출 보고서 및 매출 예상, 환자 건강 정보 또는 고객 및 직원 정보와 같은 중요한 정보를 교환하는 경우가 많습니다. 따라서 사서함이 잠재적으로 중요한 정보를 대량 포함하는 리포지토리가 될 뿐 아니라 정보 유출이 조직에 심각한 위협이 될 수 있습니다.

Office 365 메시지 암호화를 사용하여 조직은 조직 내부 및 외부 사용자 간에 암호화된 전자 메일 메시지를 보내고 받을 수 있습니다. Office 365 메시지 암호화는 Outlook.com Yahoo!, Gmail 및 기타 전자 메일 서비스와 함께 작동합니다. 전자 메일 메시지 암호화를 사용하면 받는 사람만 메시지 콘텐츠를 볼 수 있습니다.

## <a name="how-office-365-message-encryption-works"></a>Office 365 메시지 암호화의 작동 방식

이 문서의 나머지 기능은 새로운 OME 기능에 적용됩니다.

Office 365 메시지 암호화는 Azure Information Protection의 일부인 Microsoft Azure RMS(Azure 권한 관리)를 바탕으로 구축된 온라인 서비스입니다. 여기에는 전자 메일을 보호하는 데 도움이 되는 암호화, ID 및 권한 부여 정책이 포함됩니다. 권한 관리 템플릿, 전달 금지 옵션 [](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)및 암호화 전용 옵션을 사용하여 메시지를 [암호화할 수 있습니다.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

그러면 사용자는 이러한 옵션을 사용하여 전자 메일 메시지와 다양한 첨부 파일을 암호화할 수 있습니다. 지원되는 첨부 파일 형식의 전체 목록은 전자 메일 메시지에 대한 IRM 소개에서 ["메시지에 첨부된 경우 IRM 정책에서](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)다루는 파일 형식"을 참조하세요.

관리자는 이 보호를 적용하는 메일 흐름 규칙을 정의할 수도 있습니다. 예를 들어 특정 받는 사람에게 주소가 지정되거나 제목 줄에 특정 단어가 포함된 모든 메시지를 암호화해야 하는 규칙을 만들고 받는 사람이 메시지 내용을 복사하거나 인쇄할 수 없다고 지정할 수도 있습니다.

이전 버전의 OME와 달리 새로운 기능은 조직 내부에서 메일을 보내든 Microsoft 365 외부의 받는 사람에게든 통합된 보낸 사람 환경을 제공합니다. 또한 Outlook 2016 또는 웹에서 Outlook의 Microsoft 365 계정으로 전송된 보호된 전자 메일 메시지를 받는 사람은 메시지를 보기 위해 추가 작업을 수행하지 필요가 없습니다. 매끄럽게 작동합니다. 다른 전자 메일 클라이언트 및 전자 메일 서비스 공급자를 사용하는 받는 사람도 개선된 환경을 제공합니다. 자세한 내용은 [Office 365의](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) 보호된 메시지에 대해 알아보고 보호된 메시지를 [여는 방법을 참조하세요.](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)

이전 버전의 OME와 새 OME 기능 간의 차이점에 대한 자세한 목록은 OME 버전 [비교를 참조하세요.](ome-version-comparison.md)

암호화 메일 흐름 규칙과 일치하는 전자 메일 메시지를 보내는 경우 메시지가 전송되기 전에 암호화됩니다. Outlook 클라이언트를 사용하여 메일을 읽는 모든 Microsoft 365 최종 사용자는 보낸 사람과 같은 조직에 있지 않은 경우에도 암호화되고 권한으로 보호된 메일에 대한 기본 동급 읽기 환경을 받을 수 있습니다. 지원되는 Outlook 클라이언트에는 Outlook 데스크톱, Outlook Mac, iOS 및 Android의 Outlook 모바일 및 웹용 Outlook(이전의 Outlook Web App)이 포함됩니다.

Outlook.com, Gmail 및 Yahoo 계정으로 전송된 암호화되거나 권한으로 보호된 메일을 받는 암호화된 메시지의 받는 사람은 Microsoft 계정, Gmail 또는 Yahoo 자격 증명을 사용하여 쉽게 인증할 수 있는 OME 포털로 연결되는 래퍼 메일을 받게 됩니다.

Outlook이 아니라 클라이언트에서 암호화되거나 권한으로 보호된 메일을 읽은 최종 사용자는 OME 포털을 사용하여 받은 암호화된 및 권한으로 보호된 메시지를 볼 수도 있습니다.

보호된 메일의 보낸 사람이 GCC High에 있으며 받는 사람이 상용 사용자, Outlook.com 사용자 및 Gmail과 같은 다른 전자 메일 공급자의 사용자를 포함하여 GCC High 외부에 있는 경우 받는 사람은 래퍼 메일을 수신합니다. 래퍼 메일은 받는 사람이 메시지를 읽고 회신할 수 있는 OME 포털로 받는 사람을 보냅니다. 그렇지 않은 경우 보낸 사람 및 받는 사람이 모두 GCC High 환경에 있는 경우 동일한 조직에 있지 않은 경우에도 Outlook 클라이언트를 사용하여 메일을 읽는 받는 사람은 암호화되고 권한으로 보호된 메일에 대한 기본 최고 수준의 읽기 환경을 받게 됩니다. GCC High의 다양한 경험에 대한 자세한 내용은 OME 버전 [비교를 참조하세요.](ome-version-comparison.md)

OME를 사용하여 암호화할 수 있는 메시지 및 첨부 파일에 대한 크기 제한에 대한 자세한 내용은 [Exchange Online 제한을 참조하세요.](https://technet.microsoft.com/library/exchange-online-limits.aspx)

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Office 365 고급 메시지 암호화가 OME 위에 작동하는 방식

Office 365 고급 메시지 암호화를 사용하면 여러 브랜징 템플릿을 만들 수 있으므로 받는 사람 메일에 대한 제어를 미세 조정할 수 있으며 다양한 조직 구조를 지원하기 위한 사용자 지정 브랜드 환경을 만들 수 있습니다.

Microsoft 365의 고급 메시지 암호화를 사용하면 암호화된 전자 메일에 대한 외부 받는 사람의 액세스를 보다 유연하게 제어해야 하는 준수 의무를 충족할 수 있습니다. Office 365의 고급 메시지 암호화를 사용하면 관리자는 보안 웹 포털을 통해 암호화된 전자 메일에 대한 액세스가 만료되어 보호를 강화하는 중요한 정보 유형(예: PII, 재무 또는 상태 정보)을 감지하는 자동 정책으로 조직 외부에서 공유되는 중요한 전자 메일을 제어할 수 있습니다. 관리자는 언제든지 전자 메일에 대한 액세스를 해지하여 Microsoft 365 웹 포털을 통해 액세스하는 암호화된 전자 메일을 추가로 제어할 수 있습니다.

메시지 해지 및 만료는 사용자가 조직 외부의 받는 사람에게 보내는 전자 메일에만 사용할 수 있습니다. 또한 받는 사람은 웹 포털을 통해 전자 메일에 액세스해야 합니다. 받는 사람이 포털을 사용하여 전자 메일을 받되도록 래퍼를 적용하는 사용자 지정 브랜드 템플릿을 설정해야 합니다. 그런 다음 메일 흐름 규칙에 브랜드 템플릿을 적용합니다. 고급 메시지 암호화에 대한 자세한 내용은 [Office 365 고급 메시지 암호화를 참조하세요.](ome-advanced-message-encryption.md)

## <a name="defining-rules-for-office-365-message-encryption"></a>Office 365 메시지 암호화에 대한 규칙 정의

Office 365 메시지 암호화에 대한 새 기능을 사용하도록 설정하는 한 가지 방법은 Exchange Online 및 Exchange Online Protection 관리자가 메일 흐름 규칙을 정의하는 것입니다. 이러한 규칙은 전자 메일 메시지를 암호화해야 하는 조건에 따라 결정됩니다. 규칙에 대해 암호화 작업을 설정하면 규칙 조건과 일치하는 메시지가 전송되기 전에 암호화됩니다.

메일 흐름 규칙은 유연하며 단일 규칙에서 특정 보안 요구 사항을 충족할 수 있도록 조건을 결합할 수 있습니다. 예를 들어 지정된 키워드를 포함하며 외부 받는 사람에게 주소가 지정된 모든 메시지를 암호화하는 규칙을 만들 수 있습니다. Office 365 메시지 암호화에 대한 새로운 기능은 암호화된 전자 메일 받는 사람의 응답도 암호화합니다.

새 OME 기능을 활용하기 위해 메일 흐름 규칙을 만드는 방법에 대한 자세한 내용은 [Office 365](define-mail-flow-rules-to-encrypt-email.md)메시지 암호화에 대한 규칙 정의를 참조하십시오.

## <a name="get-started-with-the-new-ome-capabilities"></a>새 OME 기능 시작

조직 내에서 새로운 OME 기능을 사용할 준비가 되면 새 [Office 365](set-up-new-message-encryption-capabilities.md)메시지 암호화 기능 설정을 참조하세요.

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>암호화된 전자 메일 메시지 보내기, 보기 및 회신

Office 365 메시지 암호화를 사용하여 사용자는 Outlook 및 웹용 Outlook에서 암호화된 전자 메일을 보낼 수 있습니다. 또한 관리자는 키워드 일치 또는 기타 조건에 따라 전자 메일을 자동으로 암호화하기 위해 Microsoft 365에서 메일 흐름 규칙을 설정할 수 있습니다.

조직에 있는 암호화된 메시지의 받는 사람은 PC용 Outlook, Mac용 Outlook, 웹용 Outlook, iOS용 Outlook 및 Android용 Outlook을 비롯한 모든 버전의 Outlook에서 해당 메시지를 원활하게 읽을 수 있습니다. 다른 전자 메일 클라이언트에서 암호화된 메시지를 받는 사용자는 OME 포털에서 메시지를 볼 수 있습니다.

암호화된 메시지를 보내고 보는 방법에 대한 자세한 지침은 다음 문서를 참조하세요.

|이 문서 읽기...|If you are...|
|:-----|:-----|
|[Office 365의 보호된 메시지에 대해 자세히](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|암호화된 메시지의 작동 방식과 사용 가능한 옵션에 대해 자세히 알아보고자 하는 최종 사용자입니다.|
|[보호된 메시지를 여는 방법](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|사용자에게 전송된 보호된 메시지를 읽은 최종 사용자입니다. 이 문서에는 Gmail 및 Yahoo! accounts.|
|[Outlook에서 암호화된 메시지 보내기, 보기 및 회신](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|Outlook에서 암호화된 메시지를 보내거나 보거나 회신하려는 최종 사용자입니다. 조직의 구성원이 아니어도 Outlook에서 전송된 암호화된 메시지에 대한 알림이 계속 수신됩니다. 이 문서에서는 Office 365에서 보낸 암호화된 메시지를 보고 회신하는 방법에 대한 지침을 제공합니다.|
|[디지털 서명되거나 암호화된 메시지 보내기](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Mac용 Outlook을 사용하여 암호화된 메시지를 보내거나 보거나 회신하려는 최종 사용자입니다. 또한 이 문서에서는 S/MIME과 같이 OME가 아니라 다른 암호화 방법을 사용하는 방법에 대해 다 사용합니다.|
|[Android 장치에서 암호화된 메시지 보기](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Android 장치에서 Office 365 메시지 암호화로 암호화된 메시지를 받은 최종 사용자는 무료 OME 뷰어 앱을 사용하여 메시지를 보고 암호화된 회신을 보낼 수 있습니다. 이 문서에서는 방법을 설명합니다.|
|[iPhone 또는 iPad에서 암호화된 메시지 보기](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|iPhone 또는 iPad에서 Office 365 메시지 암호화로 암호화된 메시지를 받은 최종 사용자는 무료 OME 뷰어 앱을 사용하여 메시지를 보고 암호화된 회신을 보낼 수 있습니다. 이 문서에서는 방법을 설명합니다.|
||
