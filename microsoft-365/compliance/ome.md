---
title: Office 365 메시지 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/03/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Office 365 메시지 암호화를 사용 하면 조직에서 조직 내부 및 외부의 사용자 간에 암호화 된 전자 메일 메시지를 보내고 받을 수 있습니다. 전자 메일 메시지 암호화는 의도 된 받는 사람만 메시지 콘텐츠를 볼 수 있도록 합니다.
ms.openlocfilehash: 76d3688fbc30923e204b9cba338b61bc955b8f95
ms.sourcegitcommit: d9ceaa6ec54c3760747f31accdb02f729450f324
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680097"
---
# <a name="office-365-message-encryption"></a>Office 365 메시지 암호화

전자 메일을 통해 재무 데이터, 법적 계약, 기밀 제품 정보, 매출 보고서 및 매출 예상, 환자 건강 정보 또는 고객 및 직원 정보와 같은 중요한 정보를 교환하는 경우가 많습니다. 따라서 사서함이 잠재적으로 중요한 정보를 대량 포함하는 리포지토리가 될 뿐 아니라 정보 유출이 조직에 심각한 위협이 될 수 있습니다.

Office 365 메시지 암호화를 사용 하면 조직에서 조직 내부 및 외부의 사용자 간에 암호화 된 전자 메일 메시지를 보내고 받을 수 있습니다. Office 365 메시지 암호화는 Outlook.com, Yahoo!, Gmail 및 기타 전자 메일 서비스에서 작동 합니다. 전자 메일 메시지 암호화는 의도 된 받는 사람만 메시지 콘텐츠를 볼 수 있도록 합니다.

## <a name="important-updates-to-ome-to-enhance-email-authenticity---action-required"></a>전자 메일 인증을 향상 시키기 위해 OME에 대 한 중요 업데이트-필요한 작업

2020 년 2 월부터 시작 하 여 OME에서 사용 하는 보낸 사람 주소를 변경 하 여 OME 전자 메일을 향상 시키는 OME의 향상 된 기능을 제공 합니다. 이러한 개선 사항이 없는 경우에는 보낸 사람 주소가 messaging.onmicrosoft.com 도메인에서 온 것 이므로 일부 조직에서는 OME에서 시스템 생성 메일 (예: 1 회 통과, 메일 및 포털 회신)을 거부 했습니다. 이러한 변경으로 인해 이러한 시스템 생성 메일은 onmicrosoft.com 대신 조직의 사용자 지정 도메인에서 전송 됩니다. 이러한 개선을 구현 하기 위해 메일 흐름 규칙을 업데이트 해야 합니다.

Exchange Online의 경우 이전 OME 전자 메일 주소 또는 조직 외부의 모든 주소를 찾는 각 메일 흐름 규칙을 업데이트 하 여 새 OME 주소를 확인 해야 합니다. 새 OME (일회용 pass code and portal reply) 전자 메일이 사용자 지정 도메인에서 전송 되기 때문에 조직 외부에서 들어오는 것으로 더 이상 한정 되지 않습니다.

Exchange 온-프레미스 또는 Exchange Online에서 작동 하는 타사 솔루션을 사용 하는 경우에는 새 OME 전자 메일 주소를 반영 하도록 이전의 모든 OME 규칙을 업데이트 해야 합니다. 예를 들어 이전 OME 전자 메일 주소를 프록시의 허용 목록 한 경우 프록시의 허용 목록 전자 메일 목록에 새 전자 메일을 추가 해야 합니다.

### <a name="changes-to-ome-email-addresses"></a>OME 전자 메일 주소 변경

일회용 전달 코드 발신자 주소:

- 이전 주소:``onetimepasscode@messaging.onmicrosoft.com``

- 새 주소:``onetimepasscode@<yourdomain.com>``

OME 포털에서 OME 회신:

- 이전 주소:``omeportal@messaging.onmicrosoft.com``

- 새 주소:``omeportal@<yourdomain.com>``

### <a name="errors-routing-mail-from-exchange-online-through-exchange-on-premises-to-external-recipients"></a>Exchange online에서 온-프레미스를 통해 외부 받는 사람에 게 메일을 라우팅하는 경우의 오류

Exchange Online에서 온-프레미스 Exchange를 사용 하는 조직 외부의 받는 사람에 게 메일을 라우팅하는 경우 일부 타사 시스템은 DMARC 오류를 반환 하 고 전자 메일을 수락 하지 않습니다. 예를 들어이 방식으로 메일을 라우팅하는 경우 gmail이 DMARC 오류를 반환 합니다. 이 문제를 해결 하려면 exchange 온-프레미스를 우회 하 여 Exchange Online에서 외부 받는 사람에 게 직접 전자 메일을 라우팅합니다.

## <a name="how-office-365-message-encryption-works"></a>Office 365 메시지 암호화가 작동 하는 방식

이 문서의 나머지 부분은 새로운 OME 기능에 적용 됩니다.

> [!NOTE]
> 사서함에 대 한 모든 권한이 있는 대리인은 사서함으로 전송 되는 암호화 된 메시지를 읽을 수 있습니다.

Office 365 메시지 암호화는 Azure Information Protection의 일부인 Microsoft Azure RMS (서비스 권한 관리)를 기반으로 작성 된 온라인 서비스가 됩니다. 여기에는 전자 메일을 보호 하는 데 도움이 되는 암호화, id 및 권한 부여 정책이 포함 됩니다. 권한 관리 템플릿, [전달 금지 옵션](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)및 [암호화 전용 옵션](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)을 사용 하 여 메시지를 암호화할 수 있습니다.

그러면 사용자가 이러한 옵션을 사용 하 여 전자 메일 메시지와 다양 한 Office 365 첨부 파일을 암호화할 수 있습니다. 지원 되는 첨부 파일 형식에 대 한 전체 목록은 [전자 메일 메시지에 대 한 Irm 소개에서 "irm 정책이 메시지에 첨부 될 때 확인 되는 파일 형식"](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)을 참조 하십시오.

관리자는이 보호를 적용 하는 메일 흐름 규칙을 정의할 수도 있습니다. 예를 들어 특정 받는 사람에 게 주소를 지정 하거나 제목 줄에 특정 단어를 포함 하는 모든 메시지를 암호화 해야 하는 규칙을 만들 수 있으며, 받는 사람이 메시지 내용을 복사 하거나 인쇄할 수 없도록 지정할 수도 있습니다.

이전 버전의 OME과 달리 새로운 기능은 조직 내부에서 메일을 보내는 지, 아니면 Office 365 외부의 받는 사람에 게 제공 되는지 여부에 관계 없이 통합 된 보낸 사람을 위한 환경입니다. 또한 Outlook 2016 또는 웹용 Outlook에서 Office 365 계정으로 전송 되는 보호 된 전자 메일 메시지를 받는 받는 사람은 메시지를 확인 하기 위해 추가 작업을 수행할 필요가 없습니다. 완벽 하 게 작동 합니다. 다른 전자 메일 클라이언트와 전자 메일 서비스 공급자를 사용 하는 받는 사람도 향상 된 환경을 제공 합니다. 자세한 내용은 [Office 365의 보호 된 메시지에 대 한](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) 정보 및 [보호 된 메시지를 여는 방법](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)를 참조 하십시오.

이전 버전의 OME와 새 OME 기능 간의 차이점에 대 한 자세한 목록은 [OME 버전 비교](ome-version-comparison.md)를 참조 하십시오.

다른 사용자가 암호화 메일 흐름 규칙과 일치 하는 전자 메일 메시지를 보내면 메시지가 전송 되기 전에 암호화 됩니다. 모든 Office 365 end-Outlook 클라이언트를 사용 하 여 메일을 읽는 사용자는 보낸 사람과 같은 조직에 없는 경우에도 암호화 및 권한으로 보호 되는 메일에 대 한 기본, 첫 번째 읽기 환경을 수신 합니다. 지원 되는 Outlook 클라이언트에는 Outlook 데스크톱, Outlook Mac, iOS 및 Android의 outlook 모바일 및 웹용 Outlook (이전의 Outlook Web App)이 포함 됩니다.

Outlook.com, Gmail 및 Yahoo 계정으로 전송 된 암호화 또는 권한으로 보호 된 메일을 수신 하는 암호화 된 메시지를 받는 사람은 Microsoft 계정, Gmail을 사용 하 여 쉽게 인증할 수 있는 OME 포털로 지시 하는 래퍼 메일을 받습니다. Yahoo 자격 증명

Outlook 이외의 클라이언트에서 암호화 되거나 권한으로 보호 된 메일을 읽는 최종 사용자는 OME 포털을 사용 하 여 자신이 받은 암호화 및 권한으로 보호 된 메시지를 볼 수 있습니다.

보호 된 메일을 보낸 사람이 GCC High이 고 받는 사람이 고급 Office 365 사용자, Outlook.com 사용자 및 Gmail과 같은 다른 전자 메일 공급자의 사용자를 포함 하 여 GCC High를 초과 하는 경우 받는 사람은 래퍼 메일을 받습니다. 래퍼 메일은 받는 사람이 메시지를 읽고 회신할 수 있는 OME 포털에 지시 합니다. 그렇지 않고 보낸 사람과 받는 사람이 모두 GCC High 환경에 있고, 같은 조직에 있지 않더라도 Outlook 클라이언트를 사용 하 여 메일을 읽는 받는 사람은 암호화 및 권한으로 보호 되는 메일에 대 한 기본, 최초 클래스 읽기 환경을 수신 합니다. . GCC High의 서로 다른 환경에 대 한 자세한 내용은 [Compare VERSIONS OME](ome-version-comparison.md)을 참조 하십시오.

OME을 사용 하 여 암호화할 수 있는 메시지와 첨부 파일의 크기 제한에 대 한 자세한 내용은 [Exchange Online 제한을](https://technet.microsoft.com/library/exchange-online-limits.aspx)참조 하세요.

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Office 365 고급 메시지 암호화가 OME 최상위에서 작동 하는 방식

Office 365 Advanced Message Encryption을 사용 하면 여러 브랜딩 템플릿을 만들어 받는 사람 메일에 대 한 제어를 세밀 하 게 조정 하 고 다양 한 조직 구조를 지원 하기 위해 사용자 지정 브랜딩 환경을 만들 수 있습니다.

Office 365의 고급 메시지 암호화를 사용 하면 암호화 된 전자 메일에 대 한 외부 받는 사람의 액세스를 보다 유연 하 게 제어 해야 하는 준수 의무를 달성할 수 있습니다. 관리자는 Office 365의 고급 메시지 암호화를 사용 하 여 중요 한 정보 유형을 검색 하는 자동 정책 (예: PII, 재무 또는 건강 Id) 또는 향상 된 키워드를 사용 하 여 조직 외부에서 공유 되는 중요 한 전자 메일을 제어할 수 있습니다. 보안 웹 포털을 통해 암호화 된 전자 메일을 통해 액세스를 만료 시켜 서 보호 합니다. 또한 관리자는 언제 든 지 전자 메일에 대 한 액세스를 취소 하 여 Office 365 웹 포털을 통해 외부에서 액세스 한 암호화 된 전자 메일을 제어할 수 있습니다.

메시지 해지 및 만료는 사용자가 Office 365 조직 외부의 받는 사람에 게 보내는 전자 메일에만 작동 합니다. 또한 받는 사람은 웹 포털을 통해 전자 메일에 액세스 해야 합니다. 받는 사람이 포털을 사용 하 여 전자 메일을 받을 수 있도록 하려면 래퍼를 적용 하는 사용자 지정 브랜딩 서식 파일을 설정 합니다. 그런 다음 메일 흐름 규칙에 브랜딩 서식 파일을 적용 합니다. 고급 메시지 암호화에 대 한 자세한 내용은 [Office 365 고급 메시지 암호화](ome-advanced-message-encryption.md)를 참조 하세요.

## <a name="defining-rules-for-office-365-message-encryption"></a>Office 365 메시지 암호화에 대한 규칙 정의

Office 365 메시지 암호화에 대 한 새로운 기능을 사용 하도록 설정 하는 한 가지 방법은 Exchange Online 및 Exchange Online Protection 관리자가 메일 흐름 규칙을 정의 하는 것입니다. 이러한 규칙은 전자 메일 메시지를 암호화 해야 하는 조건을 결정 합니다. 규칙에 대해 암호화 동작을 설정 하면 규칙 조건과 일치 하는 모든 메시지가 전송 되기 전에 암호화 됩니다.

메일 흐름 규칙은 융통성이 있으므로 단일 규칙에서 특정 보안 요구 사항을 충족할 수 있도록 조건을 조합할 수도 있습니다. 예를 들어 지정 된 키워드를 포함 하 고 외부 받는 사람에 게 보내는 모든 메시지를 암호화 하는 규칙을 만들 수 있습니다. 새로운 Office 365 메시지 암호화 기능을 통해 암호화 된 전자 메일을 받는 사람이 보낸 회신을 암호화할 수도 있습니다.

새 OME 기능을 활용 하기 위해 메일 흐름 규칙을 만드는 방법에 대 한 자세한 내용은 [Define rules For Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)을 참조 하십시오.

## <a name="get-started-with-the-new-ome-capabilities"></a>새로운 OME 기능을 시작 합니다.

조직 내에서 새 OME 기능을 사용할 준비가 되 면 [Set Up Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md)를 참조 하세요.

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>암호화된 전자 메일 메시지 보내기, 보기 및 회신

Office 365 메시지 암호화를 사용 하면 사용자가 Outlook 및 웹용 Outlook에서 암호화 된 전자 메일을 보낼 수 있습니다. 또한 관리자는 키워드 일치 또는 기타 조건에 따라 전자 메일을 자동으로 암호화 하기 위해 Office 365에서 메일 흐름 규칙을 설정할 수 있습니다.

Office 365 조직에 있는 암호화 된 메시지의 받는 사람은 이러한 메시지를 outlook for PC, outlook for Mac, 웹용 outlook, iOS 용 Outlook, Android 용 Outlook 등을 비롯 한 모든 버전에서 원활 하 게 읽을 수 있습니다. 다른 전자 메일 클라이언트에서 암호화 된 메시지를 수신 하는 사용자는 OME 포털에서 메시지를 볼 수 있습니다.

암호화 된 메시지를 보내고 보는 방법에 대 한 자세한 지침은 다음 문서를 참조 하세요.

|||
|:-----|:-----|
|이 문서 읽기 ...|...|
|[Office 365의 보호 된 메시지에 대해 자세히 알아보기](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|암호화 된 메시지의 작동 방식과 사용할 수 있는 옵션에 대해 자세히 알아보려면 최종 사용자를 선택 합니다.|
|[보호 된 메시지를 열려면 어떻게 해야 합니까?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|사용자에 게 전송 되는 보호 된 메시지를 읽으려고 하는 최종 사용자입니다. 이 문서에는 여러 Outlook 버전에서 메시지를 읽는 방법 및 다른 전자 메일 계정 (예: gmail 및 Yahoo! 등의 Office 365 외부에 포함)에 대 한 정보가 포함 되어 있습니다. 거래처.|
|[Outlook에서 암호화 된 메시지 보내기, 확인 및 회신](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)|Outlook에서 암호화 된 메시지를 보내거나 보거나 회신 하려는 최종 사용자입니다. 사용자가 Office 365 조직의 구성원이 아니더라도 Outlook에서 보낸 암호화 된 메시지에 대 한 알림도 계속 받게 됩니다. 이 문서를 사용 하 여 Office 365에서 보낸 암호화 된 메시지를 보고 회신 하는 방법에 대 한 지침을 확인할 수 있습니다.|
|[디지털 서명 되거나 암호화 된 메시지 보내기](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Mac 용 Outlook을 사용 하 여 암호화 된 메시지를 보내거나 보거나 회신 하려는 최종 사용자입니다. 이 문서에서는 S/MIME과 같이 OME 이외의 암호화 방법 사용에 대해서도 설명 합니다.|
|[Android 장치에서 암호화 된 메시지 보기](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Android 장치에서 Office 365 메시지 암호화로 암호화 된 메시지를 받은 최종 사용자는 무료 OME Viewer 앱을 사용 하 여 메시지를 확인 하 고 암호화 된 회신을 보낼 수 있습니다. 이 문서에서는 이러한 방법을 설명 합니다.|
|[IPhone 또는 iPad에서 암호화 된 메시지 보기](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)|IPhone 또는 iPad에서 Office 365 메시지 암호화로 암호화 된 메시지를 받은 최종 사용자는 무료 OME Viewer 앱을 사용 하 여 메시지를 확인 하 고 암호화 된 회신을 보낼 수 있습니다. 이 문서에서는 이러한 방법을 설명 합니다.|
||