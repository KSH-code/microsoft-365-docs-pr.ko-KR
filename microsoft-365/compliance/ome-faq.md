---
title: 메시지 암호화 FAQ
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 새 메시지 보호 기능의 작동 방식에 대한 질문이 있나요? 여기에서 답변을 확인하세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdfcc2e7454b1243016754ba32dcc2622b876672
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927756"
---
# <a name="message-encryption-faq"></a>메시지 암호화 FAQ

새 메시지 보호 기능의 작동 방식에 대한 질문이 있나요? 여기에서 답변을 확인하세요. 또한 Azure Information [Protection의](/information-protection/get-started/faqs-rms) 데이터 보호 서비스인 Azure Rights Management에 대한 질문과 대답은 Azure Information Protection의 데이터 보호에 대한 질문과 대답을 살펴보아야 합니다.

## <a name="what-is-office-365-message-encryption-ome"></a>OME(Office 365 메시지 암호화)란?

OME는 전자 메일 암호화 및 권한 관리 기능을 결합합니다. 권한 관리 기능은 Azure Information Protection을 통해 지원됩니다.

## <a name="who-can-use-ome"></a>OME를 사용할 수 있는 사람

다음과 같은 조건에서 OME에 대한 새 기능을 사용할 수 있습니다.
  
- Office 365에서 Exchange Online에 대해 OME 또는 IRM을 설정한 적이 없는 경우.

- OME 및 IRM을 설정한 경우 Azure Information Protection의 Azure 권한 관리 서비스를 사용하는 경우 다음 단계를 사용할 수 있습니다.

- Ad RMS(Active Directory Rights Management Service)와 함께 Exchange Online을 사용하는 경우 이러한 새 기능을 바로 사용하도록 설정할 수 없습니다. 대신 AD [RMS를 Azure Information Protection으로](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) 먼저 마이그레이션해야 합니다. 마이그레이션이 완료되면 OME를 성공적으로 설정할 수 있습니다.

  Azure Information Protection으로 마이그레이션하는 대신 Exchange Online에서 계속해서 Exchange Online과 함께 사내 AD RMS를 사용하려면 이러한 새 기능을 사용할 수 없습니다.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>새 OME 기능을 사용하려면 어떤 구독을 사용하나요?

새 OME 기능을 사용하려면 다음 계획 중 하나가 필요합니다.
  
- Office 365 메시지 암호화는 Office 365 Enterprise E3 및 E5, Microsoft Enterprise E3 및 E5, Microsoft 365 Business Premium, Office 365 A1, A3 및 A5 및 Office 365 Government G3 및 G5의 일부로 제공됩니다. 고객은 Azure Information Protection을 통해 새로운 보호 기능을 받기 위해 추가 라이선스가 필요하지 않습니다.

- Azure Information Protection 계획 1을 다음 계획에 추가하여 새로운 Office 365 메시지 암호화 기능을 받을 수도 있습니다. Exchange Online 계획 1, Exchange Online 계획 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard 또는 Office 365 Enterprise E1.

- Office 365 메시지 암호화를 통해 혜택을 받을 수 있는 각 사용자는 해당 기능을 적용하도록 라이선스가 부여되어야 합니다.

- 전체 목록은 Office 365 [메시지 암호화에](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 대한 Exchange Online 서비스 설명을 참조하세요.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Azure Information Protection에서 BYOK(Bring Your Own Key)와 함께 Exchange Online을 사용할 수 있나요?

예! OME를 설정하기 전에 BYOK를 설정하는 단계를 완료하는 것이 좋습니다.
  
BYOK에 대한 자세한 내용은 Azure Information Protection 테넌트 키 계획 및 [구현을 참조하세요.](/information-protection/plan-design/plan-implement-tenant-key)
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Azure Information Protection을 사용하여 OME 및 BYOK가 Microsoft의 소속 데이터 요청과 같은 타사 데이터 요청에 대한 접근 방식을 변경하나요?

아니요. OME 및 Azure Information Protection에서 BYOK라는 자체 암호화 키를 제공하고 제어하는 옵션은 사법 기관 소속에 응답하도록 설계되지 않습니다. Azure Information Protection용 BYOK를 사용하여 OME는 규정 준수 중심 고객을 위해 고안된 것입니다. Microsoft는 고객 데이터에 대한 타사 요청을 매우 심각하게 처리합니다. 클라우드 서비스 공급자는 항상 고객 데이터의 개인 정보 보호를 지지합니다. 소계를 받을 경우 당사는 제3자에 대한 정보를 얻기 위해 고객에게 리디렉션을 시도합니다. (Brad Smith의 블로그: 정부 스누프로부터 고객 데이터 [보호)를 읽어 주세요.](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) 당사는 수신하는 요청에 대한 자세한 정보를 주기적으로 게시합니다. 타사 데이터 요청에 대한 자세한 내용은 [](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) Microsoft 보안 센터에서 고객 데이터에 액세스하기 위한 정부 및 사법 기관 요청에 응답을 참조하세요. 또한 온라인 서비스 약관(OST)의 "고객 데이터 [공개"를 참조하세요.](https://www.microsoft.com/Licensing/product-licensing/products.aspx)
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>이 기능은 레거시 Office 365 메시지 암호화(OME) 및 IRM(정보 권한 관리) 기능과 어떻게 관련이 있나요?

Office 365 메시지 암호화의 새로운 기능은 기존 IRM 및 레거시 OME 솔루션의 발전된 기능입니다. 다음 표에서는 자세한 내용을 제공합니다.
  
**레거시 OME, IRM 및 새로운 OME 기능 비교**

| 기능 | 이전 버전의 OME | IRM | 새로운 OME 기능 |
|:-----|:-----|:-----|:-----|
|**암호화된 전자 메일 보내기**|Exchange 메일 흐름 규칙을 통해서만|Windows용 Outlook, Mac용 Outlook 또는 웹용 Outlook에서 시작된 최종 사용자 또는 Exchange 메일 흐름 규칙을 통해|Windows용 Outlook, Mac용 Outlook 또는 웹용 Outlook에서 시작된 최종 사용자 또는 메일 흐름 규칙을 통해|
|**권한 관리**|-|전달하지 않는 옵션 및 사용자 지정 서식 파일|전달하지 않는 옵션, 암호화 전용 옵션, 기본 서식 파일 및 사용자 지정 서식 파일|
|**지원되는 받는 사람 유형**|외부 받는 사람만|내부 받는 사람만|내부 및 외부 받는 사람|
|**받는 사람에 대한 환경**|외부 받는 사람은 브라우저 또는 다운로드한 모바일 앱에서 다운로드하여 열었다는 HTML 메시지를 수신했습니다.|내부 받는 사람은 Windows용 Outlook, Mac용 Outlook 및 웹용 Outlook에서만 암호화된 전자 메일을 수신했습니다.|내부 및 외부 받는 사람은 동일한 조직에 있는지 또는 조직에 있는지에 관계없이 Windows용 Outlook, Mac용 Outlook, 웹용 Outlook, Android용 Outlook 및 iOS용 Outlook 또는 웹 포털을 통해 전자 메일을 받을 수 있습니다. OME 포털은 별도의 다운로드가 필요 없습니다.|
|**키 지원 가져오기**|사용할 수 없음|사용할 수 없음| BYOK 지원|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>조직에서 새 OME 기능을 사용하도록 설정하려면 어떻게 해야 합니까?

새 Office 365 메시지 암호화 기능 [설치를 참조하세요.](set-up-new-message-encryption-capabilities.md)
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>이전 버전의 OME는 더이상 사용되지 않습니다.

여전히 이전 버전의 OME를 사용할 수 있습니다. 현재는 사용되지 않습니다. 그러나 조직에서 새 OME 솔루션과 향상된 OME 솔루션을 사용하는 것이 좋습니다. 아직 OME를 배포하지 않은 고객은 이전 버전의 OME의 새 배포를 설정할 수 없습니다.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>조직에서 Active Directory 권한 관리를 사용하나요? 이 기능을 사용할 수 있나요?

아니요. Ad RMS(Active Directory Rights Management Service)와 함께 Exchange Online을 사용하는 경우 이러한 새 기능을 바로 사용하도록 설정할 수 없습니다. 대신 AD [RMS를 Azure Information Protection으로](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) 먼저 마이그레이션해야 합니다.
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>조직에 Exchange 하이브리드 배포가 있습니다. 이 기능을 사용할 수 있나요?

Exchange Online 메일 흐름 규칙을 사용하여 암호화된 메일을 보낼 수 있습니다. 이렇게하려면 Exchange Online을 통해 전자 메일을 라우팅해야 합니다. 자세한 내용은 2부: 전자 메일 서버에서 [Microsoft 365로](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)흐르도록 메일 구성을 참조하세요.
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>OME 암호화된 메시지를 만들기 위해 어떤 전자 메일 클라이언트를 사용해야 하나요? 보호된 메시지를 보내는 데 지원되는 응용 프로그램은 무엇입니까?

Outlook 2016, Windows 및 Mac용 Outlook 2013 및 웹용 Outlook에서 보호된 메시지를 만들 수 있습니다. 암호화된 메시지를 보내는 데 대한 자세한 내용은 PC용 Outlook에서 암호화된 메시지 보내기, 보기 및 [회신을 참조하세요.](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>보호된 전자 메일을 읽고 회신할 수 있는 전자 메일 클라이언트는 무엇입니까?

Microsoft 365 사용자는 Windows 및 Mac용 Outlook(2013 및 2016), 웹용 Outlook 및 Outlook 모바일(Android 및 iOS)에서 읽고 응답할 수 있습니다. 조직에서 허용하는 경우 iOS 네이티브 메일 클라이언트를 사용할 수도 있습니다. Microsoft 365 사용자가 아닌 경우 웹 브라우저를 통해 웹에서 암호화된 메시지를 읽고 회신할 수 있습니다.

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>암호화 전용 전자 메일을 지원하는 전자 메일 클라이언트는 무엇입니까?

Microsoft 365 사용자는 Outlook for PC 버전 2019 및 Microsoft 365를 사용하여 암호화 전용 정책으로 보호된 메일을 만들 수 있습니다.  즉, 새 암호화 전용 정책이 적용된 메시지는 웹용 Outlook, iOS 및 Android용 Outlook 및 PC용 Outlook 2019 및 Microsoft 365에서 직접 읽을 수 있습니다.

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>OME를 사용하여 보낼 수 있는 메시지의 크기 제한이 있나요?

예. 첨부 파일을 포함하여 OME를 사용하여 보낼 수 있는 최대 메시지 크기는 25MB입니다. 자세한 내용은 메시지 [제한을 참조하세요.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>보호된 전자 메일의 첨부 파일로 지원되는 파일 형식은 무엇입니까? 첨부 파일이 보호된 전자 메일과 연결된 보호 정책을 상속하나요?

모든 파일 형식을 보호된 메일에 첨부할 수 있습니다. 한 가지 예외를 제외하고, 보호 정책은 Azure Information Protection 클라이언트에서 지원하는 파일 형식에 언급된 파일 [형식에만 적용됩니다.](/information-protection/rms-client/client-admin-guide-file-types) OME에서는 Word(.doc), Excel(.xls) 및 PowerPoint(.ppt)의 97-2003 버전을 지원하지 않습니다.

Word, Excel 또는 PowerPoint 파일과 같은 파일 형식이 지원되는 경우 받는 사람이 첨부 파일을 다운로드한 후에도 파일이 항상 보호됩니다. 예를 들어 첨부 파일이 전달 금지로 보호되어 있는 경우를 예로 들 수 있습니다. 원래 받는 사람이 파일을 다운로드하고 새 받는 사람에게 메시지를 만들고 파일을 첨부합니다. 새 받는 사람이 파일을 받으면 받는 사람이 보호된 파일을 열 수 없습니다.
  
## <a name="are-pdf-file-attachments-supported"></a>PDF 첨부 파일이 지원하나요?

그 대답은 예입니다. PDF 암호화를 사용하면 보안 통신 또는 보안 공동 작업을 통해 중요한 PDF 문서를 보호할 수 있습니다. 전자 메일을 보낼 때 Office 365 서비스는 Outlook 클라이언트가 아닌 PDF 첨부 파일을 암호화합니다.

웹용 Outlook, iOS용 Outlook 및 Android용 Outlook의 경우 추가 단계 없이 보내는 PC를 암호화할 수 있습니다. 이러한 클라이언트는 기본적으로 PDF 암호화를 지원합니다.

Outlook 데스크톱은 기본적으로 PDF 첨부 파일의 암호화를 지원하지 않습니다. 대신, 먼저 PDF 첨부 파일에 암호화를 적용하기 위한 Exchange 메일 흐름 규칙 또는 DLP를 설정해야 합니다. PDF 첨부 파일이 있는 Outlook Desktop에서 메일을 보낼 때 클라이언트는 첨부 파일이 있는 메시지를 먼저 서비스에 전송합니다. 서비스가 파일을 받으면 서비스는 Exchange Online에서 DLP(데이터 손실 방지) 정책 또는 메일 흐름 규칙의 OME 보호를 적용합니다. 다음으로 Exchange Online은 보호된 PDF 파일 첨부 파일이 있는 메시지를 전송합니다.

PDF 첨부 파일에 암호화를 사용하도록 설정하려면 [Exchange Online PowerShell에서 다음 명령을 실행합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

PDF 암호화를 사용하면 보안 통신 또는 보안 공동 작업을 통해 중요한 PDF 문서를 보호할 수 있습니다. 모든 Outlook 클라이언트, 메시지 및 보호되지 않은 PDF 첨부 파일은 Exchange Online의 DLP(데이터 손실 방지) 정책 또는 메일 흐름 규칙의 OME 보호를 상속합니다. 또한 웹용 Outlook 사용자가 보호되지 않은 PDF 문서를 첨부하고 메시지에 보호를 적용하는 경우 메시지는 메시지 보호를 상속합니다. 사용자는 보호된 PC를 지원하는 응용 프로그램(예: OME 포털 및 Azure Information Protection 뷰어)에서만 암호화된 첨부 파일을 열 수 있습니다.

> [!IMPORTANT]
> Outlook 데스크톱 클라이언트는 PDF 암호화를 지원하지 않습니다.

## <a name="are-onedrive-for-business-attachments-supported"></a>비즈니스용 OneDrive 첨부 파일이 지원하나요?

Not yet. 비즈니스용 OneDrive 첨부 파일은 지원되지 않습니다. 최종 사용자는 클라우드 비즈니스용 OneDrive 첨부 파일이 포함된 메일을 암호화할 수 없습니다.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>보호된 전자 메일에서 암호화된 첨부 파일 미리 보기를 지원하는 전자 메일 클라이언트는 무엇입니까?

첨부 파일이 보호된 메일로 보호되는 경우 Outlook 클라이언트는 문서를 직접 미리 볼 수 있는 기능을 제공합니다. Outlook에서는 Office 문서(docx, xlsx, pptx, doc, xls, ppt)의 미리 보기가 지원됩니다. 웹에서 Outlook에서는 Office 문서(docx, xlsx, pptx) 및 PDF의 미리 보기가 지원됩니다.  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>보호된 전자 메일의 해지가 지원되는 전자 메일 클라이언트는 무엇입니까?

웹에서 Outlook에서는 보호된 메일의 해지가 지원됩니다.  자세한 내용은 사용자가 보낸 암호화된 메시지를 [해지하는](revoke-ome-encrypted-mail.md#how-to-revoke-an-encrypted-message-that-you-sent) 방법을 참조합니다.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>정책을 설정하여 메시지를 자동으로 암호화할 수 있나요?

예. Exchange Online의 메일 흐름 규칙을 사용하여 특정 조건에 따라 메시지를 자동으로 암호화합니다. 예를 들어 받는 사람 ID, 받는 사람 도메인 또는 메시지 본문 또는 제목의 콘텐츠에 기반한 정책을 만들 수 있습니다. [Office 365에서](define-mail-flow-rules-to-encrypt-email.md)전자 메일 메시지를 암호화하는 메일 흐름 규칙 정의를 참조하세요.
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>받는 메일과 보낸 메일의 암호화를 자동으로 제거할 수 있나요?

관리자는 메일 흐름 규칙을 설정하여 보낸 메일에 대한 암호화를 제거할 수 있습니다. 받는 메일에 대한 암호화를 제거하기 위한 규칙을 설정할 수 없습니다.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>보안 준수 센터를 통해 DLP(데이터 손실 방지)에서 정책을 설정하여 메시지를 자동으로 암호화할 &amp; 수 있나요?

예! Exchange Online에서 또는 보안 준수 센터에서 DLP를 사용하여 메일 흐름 규칙을 설정할 &amp; 수 있습니다.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>회사 브랜징을 사용하여 암호화된 메시지를 사용자 지정할 수 있나요?

예! 전자 메일 메시지 및 OME 포털 사용자 지정에 대한 자세한 내용은 암호화된 메시지에 조직의 브랜드 추가를 참조하세요. 암호화된 메시지에 조직의 [브랜드 추가를 참조합니다.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>암호화된 전자 메일에 대한 보고 기능 또는 인사이트가 있습니까?

보안 및 준수 센터에 암호화 보고서가 있습니다. 보안 및 준수 센터에서 전자 [메일 & 보기를 참조하세요.](../security/office-365-security/view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>eDiscovery와 같은 준수 기능과 함께 메시지 암호화를 사용할 수 있나요?

예. 암호화된 모든 전자 메일 메시지는 Microsoft 365 규정 준수 기능에서 검색할 수 있습니다.

## <a name="can-i-remove-encryption-from-email"></a>전자 메일에서 암호화를 제거할 수 있나요?

관리자는 암호화를 제거하기 위한 메일 흐름 규칙을 설정할 수 있습니다. 암호화 전용 보호를 사용하여 메일을 enrypted하지 않는 한 다른 조직에서 적용한 메일에서 메일 흐름 규칙을 사용하여 암호화를 제거할 수 없습니다.

## <a name="is-delegated-access-supported"></a>위임된 액세스가 지원하나요?

현재는 아니요.

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>공유 사서함으로 보내고 전자 메일을 암호화할 수 있나요?

암호화 메일 흐름 규칙과 일치하는 전자 메일 메시지를 보내는 경우 메시지가 전송되기 전에 암호화됩니다.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>공유 사서함으로 전송된 암호화된 메시지를 열 수 있나요?

예! 암호화된 메시지는 공유 사서함에 대해 지원됩니다.

- 사용자는 공유 사서함이 메일 그룹의 일부로 보호된 메일을 받은 공유 사서함에서 보호된 메일을 열 수 있습니다.

- 사용자는 Windows용 Outlook, Mac용 Outlook 및 웹용 Outlook을 사용할 때 전자 메일로부터 보호를 상속하는 첨부 파일을 볼 수 있습니다.

다음 표에는 공유 사서함에 대해 지원되는 클라이언트가 나열됩니다.

| 플랫폼 | 메일 읽기 | 전자 메일 첨부 파일 보기 |
|----------|-----------|------------------------|
| 웹용 Outlook | 예 | 예                |
| Windows용 Outlook| 예 | 예                |
| Outlook for Mac    | 예 | 예                |
| Android용 Outlook| 예 | 아니요                 |
| iOS용 Outlook    | 예 | 아니요                 |
|

현재 알려진 제한은 두 가지입니다.

- Outlook 모바일을 사용하여 모바일 장치에서 받는 전자 메일에 첨부 파일을 열 수 없습니다.

- 전자 메일 사용이 가능한 보안 그룹을 통한 할당은 지원되지 않습니다. 공유 사서함에 대한 직접 사용자 할당을 통해 제공되는 액세스만 지원하며, Exchange Online에 대해 automapping이 사용하도록 설정됩니다. Automapping은 Exchange Online에서 기본적으로 사용하도록 설정됩니다.

**공유 사서함에 사용자를 할당하기 위해**

1. [원격 PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?v=exchg.150).aspx를 사용하여 Exchange Online에 연결합니다.

2. Automapping Add-MailboxPermission cmdlet을 실행합니다. 이 예에서는 Ayla에게 지원 사서함에 대한 모든 액세스 권한을 부여합니다.

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```

## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>Fullaccess를 사용하여 다른 사용자의 사서함으로 전송된 암호화된 메시지를 열 수 있나요?

사용자가 직접 액세스 권한이 부여되고 자동 응용링이 켜져 있는 한 암호화된 메시지를 열 수 있습니다. 전자 메일 사용이 가능한 보안 그룹을 통해 액세스 권한이 부여된 경우 액세스가 허용되지 않습니다.

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>요청한 후 일회용 통과 코드를 받지 못하면 어떻게 하나요?

먼저 전자 메일 클라이언트에서 정크 또는 스팸 폴더를 확인합니다. 조직의 DKIM 및 DMARC 설정으로 인해 이러한 전자 메일이 스팸으로 필터링될 수 있습니다.

다음으로, 보안 및 준수 센터에서 & 검사합니다. 일회성 통과 코드를 포함하는 메시지( 특히 조직에서 처음 받는 메시지)는 대개 끊어지게 됩니다.