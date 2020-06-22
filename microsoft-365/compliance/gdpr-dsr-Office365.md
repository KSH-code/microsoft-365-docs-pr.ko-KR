---
title: GDPR 및 CCPA에 따른 Office 365 데이터 주체 요청
description: GDPR 및 CCPA에 따른 사용자 권한 및 기업에서 Office 365를 사용하여 DSR에 대한 응답으로 데이터를 찾고 작업하는 방법을 이해합니다.
keywords: Office 365, DSR, Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00ad2290a252ad014e9b364d9aa5ce59f94c6516
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817647"
---
# <a name="office-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 및 CCPA에 대한 Office 365 데이터 주체 요청

## <a name="introduction-to-dsrs"></a>DSR 소개

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR. The controller is obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller. A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.

마찬가지로 캘리포니아 소비자 개인 정보 보호법(CCPA)은 캘리포니아 소비자에게 GDPR의 데이터 주체 권리와 유사한 권리를 포함하여, 소비자의 개인 정보 삭제, 액세스 및 수신(이식성)과 같은 개인 정보 보호 권리 및 의무를 제공합니다. 또한 CCPA는 특정 공개, 실행 권리 행사 시 차별 대우로부터 보호, “판매"로 분류되는 특정 데이터 전송에 대한 "옵트아웃(opt-out)/옵트인(opt-in)" 요구도 허용합니다. 판매는 가치 있는 대가관계를 위하여 데이터 공유를 포함하도록 광범위하게 정의됩니다. CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.

이 가이드에서는 Office 365 제품, 서비스 및 관리 도구를 사용하여 개인 데이터 또는 개인 정보를 찾아 조치를 취함으로써 DSR에 대처하는 데 도움을 주는 방법을 설명합니다. 특히 여기에는 Microsoft 클라우드에 있는 개인 데이터 또는 개인 정보를 찾고, 액세스하고, 조치를 취하는 방법이 포함됩니다. 이 가이드에 설명된 프로세스에 대한 간략한 개요는 다음과 같습니다.

- **검색:** 검색 및 검색 도구를 사용하여 DSR의 대상이 될 수 있는 고객 데이터를 더 쉽게 찾을 수 있습니다. 잠재적으로 반응형 문서가 수집되면 다음 단계에 설명된 DSR 작업을 수행하여 요청에 응답할 수 있습니다. 또는 요청이 DSR에 응답하기 위한 조직의 지침을 충족하지 않는다고 판단할 수 있습니다.
- **액세스:** Microsoft 클라우드에 있는 개인 데이터를 검색하고, 요청될 경우 데이터 주체가 사용할 수 있는 복사본을 만듭니다.
- **수정:** 해당되는 경우 개인 데이터를 변경하거나 요청된 다른 작업을 구현합니다.
- **제한** 다양한 Microsoft 클라우드 서비스에 대한 라이선스를 제거하거나 가능한 경우 원하는 서비스를 꺼서 개인 데이터의 처리를 제한합니다. Microsoft 클라우드에서 데이터를 제거하고 온-프레미스 또는 다른 위치에 보존할 수도 있습니다.
- **삭제:** Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다.
- **내보내기/수신(이식성):** 개인 데이터 또는 개인 정보의 전자 사본(컴퓨터가 읽을 수 있는 형식)을 데이터 주체에게 제공합니다. CCPA 하에서 개인 정보는 식별된 또는 식별 가능한 개인과 관련 있는 모든 정보입니다. 이때 개인의 비공개, 공개 또는 업무 역할이 구분되지 않습니다. 정의된 "개인 정보"라는 용어는 GDPR에 따른 "개인 데이터"와 대략 일치합니다. 그러나 CCPA에는 가족 및 가정 데이터가 포함되어 있습니다. CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.

### <a name="terminology"></a>용어

다음은 이 가이드와 관련된 GDPR 용어의 정의입니다.

- **통제자:** 단독으로 또는 다른 대상과 함께 개인 데이터 처리의 목적 및 방법을 결정하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다. 이러한 처리의 목적 및 방법을 연합국 법률 또는 회원국 법률에 따라 결정하는 경우, 통제자 또는 구체적인 지명 기준을 연합국 법률 또는 회원국 법률에서 제공할 수 있습니다.
- **개인 데이터 및 데이터 주체** 식별되었거나 식별 가능한 자연인(‘데이터 주체’)과 관련된 모든 정보입니다. 식별 가능한 자연인은 직간접적으로, 특히 이름, 식별 번호, 위치 데이터, 온라인 식별자 또는 해당 자연인의 신체적, 생리적, 유전적, 정신적, 경제적, 문화적 또는 사회적 ID와 같은 식별자를 참조하여 식별될 수 있는 사람입니다.
- **프로세서:** 통제자를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다.
- **고객 데이터:** 엔터프라이즈 서비스를 사용하여 고객이 Microsoft에 제공하거나 고객 대신에 Microsoft에 제공된 모든 데이터(모든 텍스트, 소리, 동영상 또는 이미지 파일 포함)입니다. 고객 데이터에는 (1) 최종 사용자의 식별 가능한 정보(예: Azure Active Directory의 사용자 이름 및 연락처 정보) 및 고객이 특정 서비스에 업로드하거나 해당 서비스에서 만드는 고객 콘텐츠(예: Word 또는 Excel 문서의 고객 콘텐츠, 또는 Exchange Online 전자 메일 텍스트의 고객 콘텐츠, SharePoint Online 사이트에 추가되거나 비즈니스용 OneDrive 계정에 저장된 고객 콘텐츠)가 포함되어 있습니다.
- **시스템 생성 로그:** Microsoft에서 생성한 로그 및 관련 데이터이며, 이는 Microsoft에서 엔터프라이즈 서비스를 제공하도록 도와줍니다. 시스템 생성 로그에는 주로 가명 처리된 데이터(예: 일반적으로 시스템에서 생성된 숫자인 고유한 ID)가 있으며, 이 데이터는 개인을 직접 식별할 수 없지만 엔터프라이즈 서비스를 사용자에게 전달하는 데 사용됩니다. 시스템 생성 로그에는 사용자 이름과 같은 최종 사용자에 대한 식별 가능한 정보가 포함될 수도 있습니다.

### <a name="how-to-use-this-guide"></a>이 가이드를 사용하는 방법

사용 사례와 관련된 정보를 찾을 수 있도록 이 가이드는 4부로 구성되어 있습니다.

- **[1부: 고객 데이터의 DSR에 응답](#part-1-responding-to-dsrs-for-customer-data):** *고객 데이터*는 기업을 운영하면서 매일하는 작업으로 Office 365에서 생성되고 저장되는 데이터입니다. 데이터를 작성할 수 있는 가장 일반적으로 사용되는 Office 365 응용 프로그램에는 Word, Excel, PowerPoint, Outlook 및 OneNote가 있습니다. Office 365는 다른 사용자와 더욱 원활하게 공동 작업할 수 있도록 도와주는 SharePoint Online, Teams 및 Forms와 같은 응용 프로그램으로 구성됩니다. 이 가이드의 1부에서는 Office 365 온라인 서비스에서 데이터를 작성하고 저장하는 데 사용한 Office 365 응용 프로그램에서 데이터에 액세스하고 이를 수정, 제한, 삭제 및 내보내기하는 방법을 알아봅니다. 여기에서 Microsoft가 조직에서 데이터 프로세서 역할을 하는 제품 및 서비스를 제공하므로, DSR 기능을 테넌트 관리자가 사용할 수 있도록 만들 수 있습니다.
- **[2부: Office 365에서 생성된 정보와 관련하여 DSR에 응답](#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365):** Office 365는 Delve, MyAnalytics 및 Workplace Analytics와 같은 서비스를 통해 특정 정보를 제공합니다. 이러한 정보를 생성하는 방법과 이와 관련 된 DSR에 응답하는 방법을 이 가이드의 2부에서 알아봅니다.
- **[3부: 시스템 생성 로그에 대해 DSR에 응답](#part-3-responding-to-dsrs-for-system-generated-logs):** Office 365 엔터프라이즈 서비스를 사용하는 경우 Microsoft는 일부 정보(예: 온라인 서비스에서 기능 사용 또는 성능을 기록하는 서비스 로그)를 생성합니다. 대부분의 서비스 생성 데이터에는 Microsoft에서 생성된 가명 처리된 ID가 포함되고 이 범주는 이 문서에서 일반적으로 *시스템 생성 로그*라고 불립니다.  이 데이터를 추가 정보를 사용하지 않고 특정 데이터 주체에 속하는 것으로 할 수 없는 경우에도, 일부 데이터는 GDPR의 “개인 데이터”에 대한 정의에서 개인용으로 간주될 수 있습니다. 이 가이드의 3부에서는 시스템 생성 로그에 액세스하며 이를 삭제하고 내보내는 방법을 설명합니다.
- **[4부: DSR을 지원하는 추가 리소스](#part-4-additional-resources-to-assist-you-with-dsrs):** 이 가이드의 4부에서는 특정 Office 365 제품 및 서비스를 사용할 때 Microsoft가 데이터 통제자인 제한된 시나리오를 나열합니다.

>[!NOTE]
>In most cases, when users in your organization use Microsoft Office 365 products and services, you are the data controller and Microsoft is the processor. As a data controller, you are responsible for responding to the data subject directly. To assist you with this, Parts 1-3 of this guide detail the technical capabilities available to your organization to respond to a DSR request. In some limited scenarios, however, Microsoft will be the data controller when people use certain Office 365 products and services. In these cases, the information in Part 4 provides guidance on how data subjects can submit DSR requests to Microsoft.

### <a name="office-365-national-clouds"></a>Office 365 국가별 클라우드

The Microsoft Office 365 services are also available in the following national cloud environments: [Office 365 Germany](https://docs.microsoft.com/microsoft-365/admin/admin-overview/learn-about-office-365-germany), [Office 365 operated by 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china), and [Office 365 US Government](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans). Most of the guidance for managing data subject requests described in this document applies to these national cloud environments. However, due to the isolated nature of these environments, there are some exceptions. Where notable for a given subsection, these exceptions are called out in a corresponding note.

### <a name="hybrid-deployments"></a>하이브리드 배포

Your organization may consist of Microsoft offerings that are a combination of cloud-based services and on-premises server products. In general, a hybrid deployment is typically the sharing of user accounts (identity management) and resources (such as mailboxes, web sites, and data) that exist in the cloud and on-premises. Common hybrid scenarios include:

- Exchange 하이브리드 배포: 온-프레미스 사서함을 보유하는 사용자도 있고, Exchange Online 사서함을 보유하는 사용자도 있습니다.
- SharePoint 하이브리드 배포: 사이트 및 파일 서버는 온-프레미스에 있고 비즈니스용 OneDrive 계정은 Office 365에 있습니다.
- Azure Activity Directory와 동기화되는 온-프레미스 ID 관리 시스템(Active Directory): Office 365의 기본 디렉터리 서비스입니다.

When responding to a DSR request, you may have to determine if data that's responsive to a DSR request is in the Microsoft cloud or in your on-premise organization, and then take the appropriate steps to respond to that request. The Office 365 Data Subject Request Guide (this guide) provides guidance for responding to cloud-based data. For guidance for data in your on-premises organization, see [GDPR for Office on-premises Servers](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

## <a name="part-1-responding-to-dsrs-for-customer-data"></a>1부: 고객 데이터에 대한 DSR에 응답

고객 데이터에 대한 DSR에 응답하기 위한 지침은 다음 네 개의 섹션으로 구성되어 있습니다.

- [콘텐츠 검색 eDiscovery 도구를 사용하여 DSR에 응답](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)
- [앱 내 기능을 사용하여 DSR에 응답](#using-in-app-functionality-to-respond-to-dsrs)
- [DSR 수정 요청에 응답](#responding-to-dsr-rectification-requests)
- [DSR 제한 요청에 응답](#responding-to-dsr-restriction-requests)

### <a name="how-to-determine-the-office-365-applications-that-may-be-in-scope-for-a-dsr-for-customer-data"></a>데이터에 대한 DSR의 범위 내에 있을 수 있는 Office 365 응용 프로그램을 확인하는 방법

개인 데이터가 검색할 위치 또는 검색할 대상을 결정하는 데 도움이 되도록 조직 사용자가 Office 365에서 데이터를 만들고 저장 하는 데 사용할 수 있는 Office 365 응용 프로그램을 식별 하는 데 도움이 됩니다. 이 기능을 통해 DSR에 대한 범위 내에 있는 Office 365 응용 프로그램을 좁혀서 DSR과 관련된 개인 데이터를 검색하고 액세스하는 방법을 결정하는 데 도움이 됩니다. 구체적으로, 이는 콘텐츠 검색 도구를 사용할 수 있는지 또는 데이터를 만든 응용 프로그램에 대한 인앱 기능을 사용해야 하는지 여부를 나타냅니다.

A quick way to identify the Office 365 applications that people in your organization are using to create Customer Data is to determine which applications are included in your organization's Microsoft 365 for business subscription. To do this, you can access user accounts in the Office 365 admin portal and look at the product licensing information. See [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).

## <a name="using-the-content-search-ediscovery-tool-to-respond-to-dsrs"></a>콘텐츠 검색 eDiscovery 도구를 사용하여 DSR에 응답

When looking for personal data within the larger set of data your organization creates and stores using in Office 365, you may want to first consider which applications people have most likely used to author the data you're looking for. Microsoft estimates that over 90% of an organization's data that is stored in Office 365 is authored in Word, Excel, PowerPoint, OneNote, and Outlook. Documents authored in these Office applications, even if purchased through Microsoft 365 Apps for enterprise or an Office perpetual license, are most likely stored on a SharePoint Online site, in a user's OneDrive for Business account, or in a user's Exchange Online mailbox. That means you can use the Content Search eDiscovery tool to search (and perform other DSR-related actions) across SharePoint Online sites, OneDrive for Business accounts, and Exchange Online mailboxes (including the sites and mailboxes associated with Microsoft 365 Groups, Microsoft Teams, EDU Assignments) to find documents and mailbox items that may be relevant to the DSR you're investigating. You can also use the Content Search tool to discover Customer Data authored in other Office 365 applications.

다음 표에는 고객이 작성한 콘텐츠를 만드는 데 사용하고 콘텐츠 검색을 사용하여 검색할 수 있는 Office 365 응용 프로그램이 나와 있습니다. DSR 가이드의 이 섹션에서는 이러한 Office 365 응용 프로그램으로 만든 데이터를 검색, 액세스, 내보내기 및 삭제하는 방법에 대한 지침을 제공합니다.

***표 1: 콘텐츠 검색을 사용하여 고객 데이터를 찾을 수 있는 응용 프로그램***

| | |
| :---: | :---:|
![일정 아이콘](../media/O365-DSR-Doc-Final_image3.png) <br> 일정 | ![SharePoint 아이콘](../media/o365-sharepoint-64x64.png) <br> SharePoint  |
| ![Excel 아이콘](../media/o365-excel-64x64.png) <br> Excel | ![비즈니스용 Skype 아이콘](../media/o365-skypeforbusiness-64x64.png) <br> 비즈니스용 Skype |
| ![Office Lens 아이콘](../media/o365-lens-64x64.png) <br> Office Lens | ![작업 아이콘](../media/O365-DSR-Doc-Final_image8.png) <br> 작업 |
| ![OneDrive 아이콘](../media/o365-OneDrive-64x64.png) <br> 비즈니스용 OneDrive |![Teams 아이콘](../media/o365-teams-64x64.png) <br> Teams |
| ![OneNote 아이콘](../media/o365-onenote-64x64.png) <br> OneNote| ![할 일 아이콘](../media/o365-todo-64x64.png) <br> To Do |
| ![Outlook 아이콘](../media/o365-outlook-64x64.png) <br> Outlook/Exchange | ![비디오 아이콘](../media/O365-DSR-Doc-Final_image14.png) <br> 비디오 |
| ![사람 아이콘](../media/O365-DSR-Doc-Final_image15.png) <br> 사람 | ![Visio 아이콘](../media/o365-visio-64x64.png) <br> Visio |
| ![PowerPoint 아이콘](../media/o365-powerpoint-64x64.png) <br> PowerPoint | ![Word 아이콘](../media/o365-word-64x64.png) <br> Word
||

>[!NOTE]
>The Content Search eDiscovery tool is not available in [Office 365 operated by 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china). This means you won't able to use this tool to search for and export Customer Data in the Office 365 applications shown in Table 1. However, you can use the In-Place eDiscovery tool in Exchange Online to search for content in user mailboxes. You can also use the eDiscovery Center in SharePoint Online to search for content in SharePoint sites and OneDrive accounts. Alternatively, you can ask a document owner to help you find and make changes or deletions to content or export it if necessary. For more information, see:</br><br> * [원본 위치 eDiscovery 검색 만들기](https://docs.microsoft.com/exchange/create-in-place-ediscovery-search-exchange-2013-help)<br> * [SharePoint Online에서 eDiscovery 센터 설정](https://support.office.com/article/Set-up-an-eDiscovery-Center-in-SharePoint-Online-A18F8975-AA7F-43B4-A7D6-001D14744D8E)

### <a name="using-content-search-to-find-personal-data"></a>콘텐츠 검색을 사용하여 개인 데이터 찾기

DSR에 대응하는 첫 번째 단계는 DSR의 주체인 개인 데이터를 찾는 것입니다. 이는 Office 365 eDiscovery 도구를 사용하여 개인 데이터 (Office 365의 모든 조직 데이터 중에서)를 검색하거나 데이터가 만들어진 기본 응용 프로그램으로 직접 이동하는 것으로 구성됩니다. 첫 번째 단계(문제가 된 개인 데이터 찾기 및 검토)를 통해 데이터 주체 요청의 준수 또는 거부에 필요한 이 조직의 요구 사항을 충족하는지를 판별할 수 있습니다. 예를 들어, 문제가 된 개인 데이터를 찾고 검토한 후, 이 작업이 타인의 권리와 자유에 불리한 영향을 미칠 수 있거나 혹은 사용자의 조직의 정당한 비즈니스 유지의 일환으로 개인 데이터가 비즈니스 기록에 포함되어 있을 수 있으므로 해당 요청이 조직의 요구 사항을 충족하지 않는지를 판별합니다.

As previously stated, Microsoft estimates that over 90% of an organization's data is created with Office applications, such as Word and Excel. This means that you can use the Content Search in the Security & Compliance Center to search for most DSR-related data.

This guide assumes that you or the person searching for personal data that may be responsive to a DSR request is familiar with or has experience using the Content Search tool in the Security & Compliance Center. For general guidance on using Content Search, see [Content Search in Office 365](https://docs.microsoft.com/microsoft-365/compliance/content-search). Be sure that the person running the searches has been assigned the necessary permissions in the Security & Compliance Center. This person should be added as a member of the eDiscovery Manager role group in the Security & Compliance Center; see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions). Consider adding other people in your organization who are involved in investigating DSRs to the eDiscovery Manager role group, so they can perform the necessary actions in the Content Search tool such as previewing and exporting search results. However, unless you set up compliance boundaries (as described [here](#set-up-compliance-boundaries-to-limit-the-scope-of-content-searches)) be aware that an eDiscovery Manager can search all content locations in your organization, including ones that may not be related to a DSR investigation.

데이터를 찾은 후에 데이터 주체의 요청을 충족하기 위한 특정 작업을 수행할 수 있습니다.

>[!NOTE]
>Office 365 Germany에서 보안 및 준수 센터는 https://protection.office.de에 있습니다.

#### <a name="searching-content-locations"></a>콘텐츠 위치 검색

콘텐츠 검색 도구를 사용하여 검색할 수 있는 콘텐츠 유형은 다음과 같습니다.

- Exchange Online 사서함 여기에는 Microsoft 365 그룹 및 Microsoft Teams와 연결된 사서함이 포함됩니다.
- Exchange Online 공용 폴더
- SharePoint Online 사이트 여기에는 Microsoft 365 그룹 및 Microsoft Teams와 연결된 사이트가 포함됩니다.
- 비즈니스용 OneDrive 계정

>[!NOTE]
>This guide assumes that all data that might be relevant to a DSR investigation is stored in Office 365; in other words, stored in the Microsoft cloud. Data stored on a user's local computer or on-premises on your organization's file servers is outside the scope of a DSR investigation for data stored in Office 365. For guidance about responding to DSR requests for data in on-premises organizations, see [GDPR for Office on-premises Servers](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

#### <a name="tips-for-searching-content-locations"></a>콘텐츠 위치 검색을 위한 팁

- 조직에서 모든 콘텐츠 위치를 검색(단일 검색으로 검색 가능한)하여 검색 쿼리와 일치하는 항목이 포함된 콘텐츠 위치를 빠르게 확인할 수 있습니다. 그런 다음 검색을 다시 실행하여 관련 항목이 포함된 특정 위치로 검색 범위를 좁힐 수 있습니다.
- Use search statistics to identify the top locations that contain items that match your search query. See [View keyword statistics for Content Search results](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).
- 감사 로그에서 DSR의 주체인 사용자가 수행한 최근 파일 및 폴더 작업을 검색 합니다. 감사 로그를 검색하면 사용자가 최근에 상호 작용한 리소스의 이름과 위치가 포함 된 감사 레코드 목록이 반환됩니다. 이 정보를 사용하여 콘텐츠 검색 쿼리를 작성할 수 있습니다. [보안 및 준수 센터에서 감사 로그 검색하기](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)를 참조하세요.

#### <a name="building-search-queries-to-find-personal-data"></a>검색 쿼리를 작성하여 개인 데이터 찾기

조사 중인 DSR에는 개인 데이터를 검색하기 위해 키워드 검색 쿼리에 사용할 수있는 식별자가 포함되어 있을 가능성이 큽니다. 다음은 검색 쿼리에서 개인 데이터를 찾는 데 사용할 수 있는 몇 가지 일반적인 식별자입니다.

- 전자 메일 주소 또는 별칭
- 전화 번호
- 우편 주소
- 직원 ID 번호
- 국가 ID 번호 또는 EU 회원국 버전의 사회 보장 번호

조사 중인 DSR에는 검색 쿼리에서 사용할 수 있는 요청의 주체인 개인 데이터에 대한 식별자 및 기타 세부 정보가 포함될 가능성이 높습니다.

전자 메일 주소 또는 직원 ID만 검색해도 많은 결과가 반환될 수 있습니다. 검색 범위를 좁혀 DSR과 가장 관련이 있는 콘텐츠를 반환하도록 검색 쿼리에 조건을 추가할 수 있습니다. 조건을 추가할 때 키워드와 검색 조건은 **and** 부울 연산자로 논리적으로 연결됩니다. 즉, 키워드와 조건 *모두*와 일치하는 항목만 검색 결과에 반환됩니다.

The following table lists some conditions you can use to narrow the scope of a search. The table also lists the values that you can use for each condition to search for specific document types and mailbox items.

***표 2: 조건을 사용하여 검색 범위 좁히기***

||||
| :--- | :--- |:--- |
|**조건**|**설명** |**조건 값의 예**|
| 파일 형식 | 문서 또는 파일의 확장명입니다. 이 조건을 사용하여 Office 365 응용 프로그램에서 만든 Office 문서와 파일을 검색합니다. SharePoint Online 사이트 및 비즈니스용 OneDrive 계정에서 문서를 검색하려면이 조건을 사용하세요.<br/>해당 문서 속성은 filetype입니다. <br/>검색할 수 있는 파일 확장명의 전체 목록은 SharePoint에서 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식https://technet.microsoft.com/library/jj219530.aspx)을 참조하세요.|&nbsp;&bull;&nbsp;&nbsp;csv – CSV(쉼표로 구분된 값) 파일 검색. Excel 파일을 CSV 형식으로 저장할 수 있으며 CSV 파일을 Excel로 쉽게 가져올 수 있습니다.<br><br>&bull;&nbsp;&nbsp;docx - Word 파일 검색 <br><br>&bull;&nbsp;&nbsp;mpp – Project 파일 검색<br/><br>&bull;&nbsp;&nbsp;one – OneNote 파일 검색 <br><br>&bull;&nbsp;&nbsp;pdf - PDF 형식으로 저장된 파일 검색 <br><br>&bull;&nbsp;&nbsp;pptx – PowerPoint 파일 검색 <br><br>&bull;&nbsp;&nbsp;xlxs – Excel 파일 검색 <br><br>&bull;&nbsp;&nbsp;vsd – Visio 파일 검색 <br><br>&bull;&nbsp;&nbsp;wmv – Windows Media 동영상 파일 검색 <br>|
| 메시지 유형 | 검색할 전자 메일 메시지의 유형입니다. 연락처(사람), 회의(일정) 작업 또는 비즈니스용 Skype 대화에 대해 사서함을 검색하려면 이 조건을 사용하세요. 해당 전자 메일 속성은 *유형*입니다.|&bull;&nbsp;&nbsp;*연락처 — 사서함의 내 연락처 목록(사용자) 검색 <br><br>&bull;&nbsp;&nbsp;* 전자 메일 — 전자 메일 메시지 검색 <br><br>&bull;&nbsp;&nbsp;*im — 비즈니스용 Skype 대화 검색<br><br>&bull;&nbsp;&nbsp;* 모임 — 약속 및 모임 요청(일정) 검색 <br><br>&bull;&nbsp;&nbsp;*작업 – 내 작업 목록(작업) 검색. 이 값을 사용하면 Microsoft To Do에서 만든 작업도 반환됩니다.<br>|
| 준수 태그 |The label assigned to an email message or a document. Labels are used to classify email and documents for data governance and enforce retention rules based on the classification defined by the label. Use this condition to search for items that have been automatically or manually assigned a label.<br/>This is a useful condition for DSR investigations because your organization may be using labels to classify content related to data privacy or that contains personal data or sensitive information. See the "Using Content Search to find all content with a specific label applied to it" section in [Overview of labels in Office 365.](https://docs.microsoft.com/microsoft-365/compliance/labels)|compliancetag="개인 데이터"|
||||

There are many more email and document properties and search conditions that you can use to build more complex search queries. See the following sections in the [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions) help topic for more information.

- [검색 가능한 전자 메일 속성](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [검색 가능한 사이트(문서) 속성](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [검색 조건](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)

#### <a name="searching-for-personal-data-in-sharepoint-lists-discussions-and-forms"></a>SharePoint 목록, 토론 및 양식에서 개인 데이터 검색

In addition to searching for personal data in documents, you can also use Content Search to search for other types of data that's created by using native SharePoint Online apps. This includes data created by using SharePoint lists, discussions, and forms. When you run a Content Search and search SharePoint Online sites (or OneDrive for Business accounts) data from lists, discussions, and forms that match the search criteria will be returned in the search results.

##### <a name="examples-of-search-queries"></a>검색 쿼리의 예

다음은 키워드와 조건을 사용하여 DSR에 대한 응답으로 개인 데이터를 검색하는 검색 쿼리의 몇 가지 예입니다. 예제는 두 가지 버전의 쿼리를 보여줍니다. 하나는 키워드 구문 (키워드 상자에 조건이 포함되어 있음)을 나타내고 다른 하나는 조건이있는 쿼리의 GUI 기반 버전을 보여줍니다.

##### <a name="example-1"></a>예 1

이 예에서는 SharePoint Online 사이트의 Excel 파일과 지정된 전자 메일 주소가 포함된 비즈니스용 OneDrive 계정을 반환합니다. 파일 메타 데이터에 전자 메일 주소가 나타나면 파일이 반환될 수 있습니다.

***키워드 구문***

```Query
pilar@contoso.com AND filetype="xlxs"
```

***GUI***

![키워드 대화 상자](../media/O365-DSR-Doc_image18.png)

##### <a name="example-2"></a>예 2

이 예에서는 SharePoint Online 사이트 및 비즈니스용 OneDrive 계정에 있는 Excel 또는 Word 파일 중 지정된 직원 ID 또는 생일이 포함된 Excel 또는 Word 파일을 반환합니다.

(98765 OR "01-20-1990") AND (filetype="xlxs" OR filetype="docx")

***GUI***

![키워드 대화 상자](../media/O365-DSR-Doc_image19.png)

##### <a name="example-3"></a>예 3

이 예에서는 지정된 ID 번호, 즉 프랑스 사회 보장 번호(INSEE)가 포함된 전자 메일 메시지를 반환합니다.

```Query
"1600330345678 97" AND kind="email"
```

***GUI***

![키워드 대화 상자](../media/O365-DSR-Doc_image20.png)

#### <a name="working-with-partially-indexed-items-in-content-search"></a>콘텐츠 검색에서 부분적으로 인덱싱된 항목 사용

부분적으로 인덱싱된 항목 (*인덱싱되지 않은 항목*이라고도 함)은 Exchange Online 사서함 항목 및 SharePoint Online 및 OneDrive for Business 사이트의 문서로, 검색을 위해 인덱싱되지 않았기 때문에 콘텐츠 검색을 사용하여 검색할 수 없습니다. 대부분의 전자 메일 메시지 및 사이트 문서는 [Office 365의 인덱싱 제한](https://docs.microsoft.com/microsoft-365/compliance/limits-for-content-search) 범위에 속하기 때문에 성공적으로 인덱싱됩니다. 전자 메일 메시지 또는 파일의 검색이 인덱싱되지 않은 이유는 다음과 같습니다.

- 파일 형식을 [인식할 수 없거나 인덱싱이 지원되지 않습니다](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search). 파일 형식 인덱싱은 지원되지만 특정 파일에 대해 인덱싱 오류가 발생했습니다.
- 전자 메일 메시지에 이미지 파일(부분적으로 인덱싱된 전자 메일 항목의 가장 일반적인 사유)과 같은 유효한 처리기가 없는 첨부 파일이 있습니다.
- 전자 메일 메시지에 첨부된 파일이 너무 크거나 첨부 파일이 너무 많습니다.

We recommend that you learn more about partially indexed items so that you can work with them when responding to DSR requests. For more information, see:

- [Office 365의 콘텐츠 검색에서 부분적으로 인덱싱된 항목](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search)
- [Office 365 eDiscovery에서 부분적으로 인덱싱된 항목 조사](https://docs.microsoft.com/microsoft-365/compliance/investigating-partially-indexed-items-in-ediscovery)
- [인덱싱되지 않은 항목 내보내기](export-search-results.md)

#### <a name="tips-for-working-with-partially-indexed-items"></a>부분적으로 인덱싱된 항목 사용을 위한 팁

It's possible that data responsive to a DSR investigation may be in a partially indexed item. Here's some suggestions for working with partially indexed items:

- 검색을 실행한 후에는 예상되는 부분적 항목 수가 검색 통계에 표시 됩니다. 이 추정값에는 SharePoint Online 및 비즈니스용 OneDrive의 부분적 색인 항목이 포함되어 있지 않습니다. 콘텐츠 검색에 대한 보고서를 내보내서 부분적으로 인덱싱된 항목에 대한 정보를 얻습니다. **Unindexed Items.csv** 보고서에는 항목 위치, 항목이 SharePoint Online 또는 비즈니스용 OneDrive의 경우 URL, 제목 줄 (메시지의 경우) 또는 문서 이름을 포함하여 인덱스되지 않은 항목에 대한 정보가 포함됩니다. 자세한 내용은 [콘텐츠 검색 보고서 내보내기](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report)를 참조하세요.

- 콘텐츠 검색 결과와 함께 반환되는 통계 및 부분적으로 인덱싱된 항목 목록은 모두 검색된 콘텐츠 위치의 부분적으로 인덱싱된 항목입니다.

- 잠재적으로 DSR 조사에 응답하는 부분적으로 인덱싱된 항목을 검색하려면 다음 중 하나를 수행하면 됩니다.

##### <a name="export-all-partially-indexed-items"></a>모든 부분적으로 인덱싱된 항목 내보내기

콘텐츠 검색 결과와 부분적으로 인덱싱 된 항목을 모두 검색된 콘텐츠 위치에서 내보냅니다. 부분적으로 인덱싱된 항목만 내보낼 수도 있습니다. 그런 다음 기본 응용 프로그램에서 열어 내용을 검토할 수 있습니다. SharePoint Online 및 비즈니스용 OneDrive의 항목을 내보내려면 이 옵션을 사용 해야 합니다. [보안 및 준수 센터에서 콘텐츠 검색 결과 내보내기](export-search-results.md)를 참조하세요.

##### <a name="export-a-specific-set-of-partially-indexed-items-from-mailboxes"></a>사서함에서 부분적으로 인덱싱된 항목의 특정 집합 내보내기

부분적으로 인덱싱 된 사서함 항목을 검색에서 내보내는 대신 내용 검색을 다시 실행하여 부분적으로 인덱싱 된 항목의 특정 목록을 검색한 다음 내보낼 수 있습니다. 사서함 항목에 대해서만 이 작업을 수행할 수 있습니다. [Office 365에서 대상 지정된 콘텐츠 검색에 대한 CSV 파일 준비](https://docs.microsoft.com/microsoft-365/compliance/csv-file-for-an-id-list-content-search)를 참조하세요.

### <a name="next-steps"></a>다음 단계

DSR과 관련된 개인 데이터를 찾은 후에는 데이터를 찾는 데 사용한 특정 콘텐츠 검색을 유지해야 합니다. 이 검색을 재사용하여 DSR 응답 프로세스의 다른 단계 (예 : [복사본 얻기](#providing-a-copy-of-personal-data), [내보내기](#exporting-personal-data) 또는 [영구 삭제](#deleting-personal-data))를 완료할 수 있습니다.

### <a name="additional-considerations-for-selected-applications"></a>선택한 응용 프로그램에 대한 추가 고려 사항

다음 섹션에서는 아래의 Office 365 응용 프로그램에서 데이터를 검색할 때 염두에 두어야 하는 사항을 설명합니다.

- [Office Lens](#office-lens)
- [비즈니스용 OneDrive 및 SharePoint 환경 설정](#onedrive-for-business-and-sharepoint-online-experience-settings)
- [교육용 Microsoft Teams](#microsoft-teams-for-education)
- [Microsoft To Do](#microsoft-to-do)
- [비즈니스용 Skype](#skype-for-business)

#### <a name="office-lens"></a>Office Lens

Office Lens (iOS, Android 및 Windows를 실행하는 장치에서 지원되는 카메라 앱)를 사용하는 사용자는 화이트 보드, 하드 카피 문서, 명함 및 많은 텍스트가 포함된 기타 항목의 사진을 찍을 수 있습니다. Office Lens는 이미지의 텍스트를 추출하여 Word, PowerPoint, OneNote 또는 PDF 파일과 같은 Office 문서에 저장하는 광학 문자 인식 기술을 사용합니다. 그런 다음 사용자는 이미지의 텍스트가 포함 된 파일을 Office 365의 비즈니스용 OneDrive 계정에 업로드 할 수 있습니다. 즉, 콘텐츠 검색 도구를 사용하여 Office Lens 이미지에서 생성 된 파일의 데이터를 검색, 액세스, 삭제 및 내보낼 수 있습니다. Office Lens에 대한 자세한 내용은 다음을 참조하세요.

- [iOS용 Office Lens](https://support.microsoft.com/ko-KR/office/microsoft-office-lens-for-ios-fbdca5f4-1b1b-4391-a931-dc1c2582397b)
- [Android용 Office Lens](https://support.office.com/article/Office-Lens-for-Android-ec124207-0049-4201-afaf-b5874a8e6f2b)
- [Windows용 Office Lens](https://support.microsoft.com/ko-KR/office/office-lens-for-windows-577ec09d-8da2-4029-8bb7-12f8114f472a)

#### <a name="onedrive-for-business-and-sharepoint-online-experience-settings"></a>비즈니스용 OneDrive 및 SharePoint Online 환경 설정

In addition to user-created files stored in OneDrive for Business accounts and SharePoint Online sites, these services store information about the user that is used to enable various experiences. Users still in your organization can access much of this information by using in-product functionality. The following information provides guidance on how to access, view, and export OneDrive for Business and SharePoint Online application data.

##### <a name="sharepoint-user-profiles"></a>SharePoint 사용자 프로필

사용자는 자신의 Delve 프로필을 통해 생일, 휴대폰 번호(및 기타 연락처 정보), 자기 소개, 프로젝트, 기술 및 전문 지식, 학력, 관심사, 취미 등 SharePoint Online 사용자 프로필에 저장된 속성을 유지 관리할 수 있습니다.

###### <a name="end-users"></a>최종 사용자

End users can discover, access, and rectify SharePoint Online user profile data using the Delve profile experience. See [View and update your profile in Office Delve](https://support.office.com/article/view-and-update-your-profile-in-office-delve-4e84343b-eedf-45a1-aeb9-8627ccca14ba) for more details.

사용자가 자신의 SharePoint 프로필 데이터에 액세스하는 또 다른 방법은 비즈니스용 OneDrive 계정에서 **프로필 편집 페이지**로 이동하는 것입니다. 이 페이지에 액세스하려면 비즈니스용 OneDrive 계정 URL 아래의 **EditProfile.aspx** 경로로 이동하면 됩니다. 예를 들어 <strong>user1@contoso.com</strong>사용자의 경우 비즈니스용 OneDrive 계정은 다음 위치에 있습니다.

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/OneDrive.aspx`
```

프로필 편집 페이지의 URL은 다음과 같습니다.

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/EditProfile.aspx`
```

Azure Active Directory에서 제공되는 속성은 SharePoint Online에서 변경할 수 없습니다. 그러나 사용자는 Office 365 머리글에서 **사진**을 선택한 다음 **내 계정**을 선택하여 **계정** 페이지로 이동할 수 있습니다. 여기서 속성을 변경하려면 사용자가 관리자와 협력하여 사용자 프로필 속성을 검색, 액세스 또는 수정해야 할 수 있습니다.

###### <a name="admins"></a>관리자

관리자는 SharePoint 관리 센터에서 프로필 속성에 액세스하고 수정할 수 있습니다. **SharePoint 관리 센터**에서 **사용자 프로필** 탭을 클릭합니다. **사용자 프로필 관리**를 클릭하고 사용자 이름을 입력 한 다음 **찾기**를 클릭합니다. 관리자는 모든 사용자를 마우스 오른쪽 단추로 클릭하고 **내 프로필 편집**을 선택할 수 있습니다. Azure Active Directory에서 제공되는 속성은 SharePoint Online에서 변경할 수 없습니다.

An admin can export all User Profile properties for a user by using the **Export-SPOUserProfile** cmdlet in SharePoint Online PowerShell. See  [Export-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserprofile?view=sharepoint-ps).

사용자 프로필에 대한 자세한 내용은 [SharePoint 관리 센터에서 사용자 프로필 관리](https://docs.microsoft.com/sharepoint/manage-user-profiles)를 참조하세요.

##### <a name="user-information-list-on-sharepoint-online-sites"></a>SharePoint Online 사이트의 사용자 정보 목록

사용자의 SharePoint 사용자 프로필의 하위 집합은 방문하거나 액세스 권한이있는 모든 사이트의 사용자 정보 목록과 동기화됩니다. 이 기능은 문서 라이브러리의 사용자 열과 같은 SharePoint Online 환경에서 문서 작성자의 이름과 같은 사용자에 대한 기본 정보를 표시하는 데 사용됩니다. 사용자 정보 목록의 데이터는 SharePoint 사용자 프로필에 저장된 정보와 일치하며 원본이 변경되면 자동으로 수정됩니다. 삭제된 사용자의 경우 이 데이터는 SharePoint 열 필드의 참조 무결성을 위해 해당 사이트와 상호 작용하는 사이트에 남아 있습니다. 

Admins can control which properties are replicable inside the SharePoint admin center. To do this:

1. **SharePoint 관리 센터**로 이동하여 **사용자 프로필** 탭을 클릭합니다.
2. **사용자 속성 관리**를 클릭하여 속성 목록을 표시합니다.
3. 속성을 마우스 오른쪽 단추로 클릭하고 **편집**을 선택하여 다양한 설정을 조정합니다.
4. **정책 설정** 아래의 복제 가능 속성은 속성이 사용자 정보 목록에 표시되는지 여부를 제어합니다. 일부 속성은 이를 조정 하는 것을 지원하지 않습니다.

An admin can export all User information properties for a user on a given site by using the **Export-SPOUserInfo** cmdlet in SharePoint Online PowerShell. See [Export-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserinfo?view=sharepoint-ps).

##### <a name="onedrive-for-business-experience-settings"></a>비즈니스용 OneDrive 환경 설정

A user's OneDrive for Business experience stores information to help the user find and navigate content of interest to them. Most of this information can be accessed by end users using in-product features. An admin can export the information using a [PowerShell Script](https://docs.microsoft.com/powershell/scripting/overview) and [SharePoint Client-Side Object Model (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) commands.

설정, 설정이 저장되는 방식 및 내보내는 방법에 대한 자세한 내용은 [비즈니스용 OneDrive 환경 설정 내보내기](https://docs.microsoft.com/sharepoint/export-odfb-lists)를 참조하세요.

##### <a name="onedrive-for-business-and-sharepoint-online-search"></a>비즈니스용 OneDrive 및 SharePoint Online 검색

The in-app search experience in OneDrive for Business and SharePoint Online stores a user's search queries for 30 days to increase relevance of search results. An admin can export search queries for a user by using the **Export-SPOQueryLogs** cmdlet in SharePoint Online PowerShell. See [Export-SPOQueryLogs](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spoquerylogs?view=sharepoint-ps).

#### <a name="microsoft-teams-for-education"></a>교육용 Microsoft Teams

Microsoft Teams for Education offers two additional collaboration features that teachers and students can use that creates and stores personal data: Assignments and OneNote Class Notebook. You can use Content Search to discover data in both.

##### <a name="assignments"></a>Assignments

Students files associated with an Assignment are stored in a document library in the corresponding Teams SharePoint Online site. IT admins can use the Content Search tool to search for student files that are related to assignments. For example, an admin could search all SharePoint Online sites in the organization and use the student's name and class or assignment name in the search query to find data relevant to a DSR.

There's other data related to Assignments that isn't stored in the class team SharePoint Online site, which means it's not discoverable with Content Search. This includes:

- 교사가 과제의 일환으로 학생에게 할당하는 파일
- 학생의 성적과 교사의 피드백
- 각 학생이 과제에 대해 제출한 문서 목록
- 과제 메타데이터

이 데이터 유형의 경우 IT 관리자 또는 데이터 소유자(예: 교사)는 DSR과 관련된 데이터를 찾기 위해 수업 팀의 과제로 이동해야 할 수도 있습니다.

##### <a name="onenote-class-notebook"></a>OneNote 수업용 전자 필기장

The OneNote Class Notebook is stored in the class team SharePoint Online site. Every student in a class has a private notebook that's shared with the teacher. There's also a content library where a teacher can share documents with students, and a collaboration space for all students in the class. Data related to these capabilities is discoverable with Content Search.

수업용 전자 필기장을 검색하기 위한 특정 지침은 다음과 같습니다.

1. 다음 검색 조건을 사용하여 콘텐츠 검색을 실행합니다.

   - 모든 SharePoint Online 사이트 검색

   - 수업 팀의 이름(예: “9C Biology”)을 검색 키워드로 포함합니다.

2. 검색 결과를 미리 보고 수업용 전자 필기장에 해당하는 항목을 찾습니다.
3. Select that item, and then copy the folder path that's displayed in the details pane. This is the root folder for the Class Notebook.
4. Edit the search that you created in step 1 and replace the class name in the keyword query with the folder path of the Class Notebook and precede the folder path with the **path** site property; for example, **path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/"**. Be sure to include the quotation marks and the trailing forward slash.
5. 검색 조건을 추가하고 파일 형식 조건을 선택하고 파일 형식의 값으로 조건을 사용합니다. 그러면 모든 OneNote 파일이 검색 결과에 반환됩니다. 결과로 생성되는 키워드 구문은 다음과 같습니다.[](#building-search-queries-to-find-personal-data)

    ```Query
   path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/" AND filetype="one"
   ```

6.  콘텐츠 검색을 다시 실행합니다. 검색 결과에 수업 팀의 수업용 전자 필기장에 대한 모든 OneNote 파일이 포함되어야 합니다.

#### <a name="microsoft-to-do"></a>Microsoft To Do

Microsoft To Do의 작업(*to-do 목록*에 저장되는 *to-dos*)은 사용자의 Exchange Online 사서함에 작업으로 저장됩니다. 즉, 콘텐츠 검색 도구를 사용하여 할 일을 검색, 액세스, 삭제 및 내보낼 수 있습니다. 자세한 내용은 [Microsoft To Do 설정](https://support.microsoft.com/ko-KR/office/set-up-microsoft-to-do-490c1a8c-2333-4952-8125-841afadb9620)을 참조하세요.

#### <a name="skype-for-business"></a>비즈니스용 Skype

비즈니스용 Skype에서 개인 데이터를 액세스하고, 보고, 내보내는 방법에 대한 몇 가지 추가 정보는 다음과 같습니다.

- Files attached to a meeting are retained in the actual meeting for 180 days and then become inaccessible. These files can be accessed by meeting participants by joining the meeting from the meeting request and then viewing or downloading the attached file. See the "Use the attachments in the meeting" section in [Preload attachments for a Skype for Business meeting](https://support.microsoft.com/ko-KR/office/preload-attachments-for-a-skype-for-business-meeting-fd3d9f9d-b448-4754-b813-02e49393f251).
- Conversations in Skype for Business are retained in the Conversation History folder in user mailboxes. You can use Content Search to search mailboxes for data in Skype conversations.
- A data subject can export their contacts in Skype for Business. To do this, they would right-click a contact group in Skype for Business and click **Copy**. Then they can paste the list of email addresses into a text or Word document.
- If the Exchange Online mailbox of a meeting participant is placed on Litigation Hold or assigned to an Office 365 retention policy, files attached to a meeting are retained in the participants mailbox. You can use Content Search to search for those files in the participant's mailbox if the retention period for the file has not expired. For more information about retaining files, see [Retaining large files attached to a Skype for Business meeting](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/retaining-large-files-attached-to-a-meeting).

## <a name="providing-a-copy-of-personal-data"></a>개인 데이터의 복사본 제공

After you've found personal data that is potentially responsive to a DSR, it's up to you and your organization to decide which data to provide the data subject. For example, you can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions that you've deemed appropriate to share. For each of these responses to an access request, you'll have to retrieve a copy of the document or other item that contains the responsive data.

데이터 주체에 사본을 제공할 때는 다른 데이터 주체에 대한 개인 정보와 모든 기밀 정보를 제거하거나 편집해야 할 수 있습니다.

### <a name="using-content-search-to-get-a-copy-of-personal-data"></a>콘텐츠 검색을 사용하여 개인 데이터의 복사본 가져오기

콘텐츠 검색을 사용하여 검색을 실행한 후 찾은 문서 또는 사서함 항목의 복사본을 가져오는 두 가지 방법이 있습니다.

- Preview the search results and then download a copy of the document or item. This is a good way to download a few items or files.
- 검색 결과를 내보낸 다음 검색 결과로 반환된 모든 항목의 복사본을 다운로드 합니다. 이 방법은 더 복잡하지만 DSR에 응답하는 많은 항목을 다운로드하는 좋은 방법입니다. 검색 결과를 내보내는 데 유용한 보고서도 포함되어 있습니다. 이러한 보고서를 사용하여 각 항목에 대한 추가 정보를 얻을 수 있습니다. **Results.csv** 보고서에는 항목의 정확한 위치 (예 : 전자 메일 메시지의 사서함 또는 SharePoint Online 및 비즈니스용 OneDrive 사이트의 문서 또는 목록 URL)와 같이 내보낸 항목에 대한 많은 정보가 포함되어있어 유용합니다. 이 정보는 DSR 조사 과정에서 연락해야 할 경우에 대비하여 항목 소유자를 식별하는 데 도움이 됩니다. 검색 결과를 내보낼 때 포함되는 보고서에 대한 자세한 내용은 [콘텐츠 검색 보고서 내보내기](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report)를 참조하세요.

#### <a name="preview-and-download-items"></a>항목 미리 보기 및 다운로드

새 검색을 실행하거나 기존 검색을 열면 검색 쿼리와 일치하는 각 항목을 미리 보고, 조사 중인 DSR과 관련이 있는지 확인할 수 있습니다. 여기에는 검색 결과에 반환되는 SharePoint 목록 및 웹 페이지도 포함됩니다. 원본 파일을 데이터 주체에 제공해야하는 경우 원본 파일을 다운로드 할 수도 있습니다. 두 경우 모두 데이터 주체의 요청을 충족시키기 위해 스크린샷을 찍어 정보를 얻을 수 있습니다.

일부 유형의 항목은 미리 볼 수 없습니다. 항목 또는 파일 형식의 미리 보기가 지원되지 않는 경우 로컬 컴퓨터나 매핑된 네트워크 드라이브 또는 다른 네트워크 위치에 개별 항목을 다운로드할 수 있습니다. [지원되는 파일 형식](https://docs.microsoft.com/microsoft-365/compliance/content-search)만 미리 볼 수 있습니다.

항목을 미리 보고 다운로드하려면

1. 보안 및 준수 센터에서 콘텐츠 검색을 엽니다.
2. 결과가 표시되지 않으면 **결과 미리 보기**를 클릭합니다.
3. 항목을 클릭하여 확인합니다.
4. Click **Download original file** to download the item to your local computer. You'll also have to download items that can't be previewed.

검색 결과 미리 보기에 대한 자세한 내용은 [검색 결과 미리 보기](https://docs.microsoft.com/microsoft-365/compliance/content-search)를 참조하세요.

#### <a name="export-and-download-items"></a>항목 내보내기 및 다운로드

You can also export the results of a content search to get a copy of email messages, documents, lists, and web pages containing the personal data, though this method is more involved than previewing items. See the next section for details about [exporting the results of a Content Search](#export-and-download-content-using-content-search).

## <a name="exporting-personal-data"></a>개인 데이터 내보내기

The "right of data portability" allows a data subject to request an electronic copy of personal data that's in a "structured, commonly used, machine-readable format", and to request that your organization transmit these electronic files to another data controller. Microsoft supports this right in two ways:

- 네이티브의 기계가 읽을 수 있고 일반적으로 사용되는 전자 형식으로 데이터를 저장하는 Office 365 애플리케이션을 제공합니다. Office 파일 형식에 대한 자세한 내용은 [Office 파일 형식-기술 문서](https://msdn.microsoft.com/library/office/cc313105(v=office.12).aspx)를 참조 하세요.
- 조직에서 기본 파일 형식 또는 다른 응용 프로그램으로 쉽게 가져올 수 있는 형식(예: CSV, TXT 및 JSON)으로 데이터를 내보내도록 지원합니다.

DSR 내보내기 요청을 충족하기 위해 Office 문서를 해당 기본 파일 형식으로 내보내고, 다른 Office 365 응용 프로그램에서 데이터를 내보낼 수 있습니다.

### <a name="export-and-download-content-using-content-search"></a>콘텐츠 검색을 사용하여 콘텐츠 내보내기 및 다운로드

When you export the results of a Content Search, email items can be downloaded as PST files or as individual messages (.msg files). When you export documents and lists from SharePoint Online and OneDrive for Business sites, copies in the native file formats are exported. For example, SharePoint lists are exported as CSV files and Web pages are exported as .aspx or html files.

>[!NOTE]
>콘텐츠 검색을 사용하여 사용자의 사서함에서 사서함 항목을 내보려면 사용자(항목을 내보내는 사서함의 소유자)에게 Exchange Online 요금제 2 라이선스가 할당되어 있어야 합니다. 

항목을 내보내고 다운로드하려면

1. 보안 및 준수 센터에서 콘텐츠 검색을 엽니다.
2. 검색 플라이아웃 페이지에서 ![다운로드 아이콘](../media/o365-dsr_image21.png) **자세히**를 클릭한 다음 **결과 내보내기**를 클릭합니다. 보고서를 내보낼 수도 있습니다.
3. Complete the sections on the **Export results** fly out page. Be sure to use the scroll bar to view all export options.
4. 보안 및 준수 센터의 콘텐츠 검색 페이지로 돌아가 **내보내기** 탭을 클릭합니다.
5. **새로 고침**을 클릭하여 페이지를 업데이트합니다.
6. **이름** 열에서 작성한 내보내기 작업을 클릭합니다. 내보내기 작업의 이름은 **\_내보내기**와 함께 추가된 콘텐츠 검색의 이름입니다.
7. 내보내기 플라이 아웃 페이지의 **키 내보내기**에서 **클립 보드로 복사를 클릭**합니다. 10단계에서 이 키를 사용하여 검색 결과를 다운로드하게 됩니다.
8. 플라이아웃 페이지 위쪽에서 ![다운로드 아이콘](../media/o365-dsr_image21.png) **결과 다운로드**를 클릭합니다.
9. **Microsoft Office 365 eDiscovery 내보내기 도구**를 설치하라는 메시지가 표시되면 **설치**를 클릭합니다.
10. **eDiscovery 내보내기 도구**에서 7단계에서 복사한 내보내기 키를 해당 상자에 붙여 넣습니다.
11. **찾아보기**를 클릭하여 검색 결과 파일을 다운로드하려는 위치를 지정합니다.
12. **시작**을 클릭하여 컴퓨터에 검색 결과를 다운로드합니다.

When the export process is complete, you can access the files in the location on your local computer where they were downloaded. Results of a content search are downloaded to a folder named after the Content Search. Documents from sites are copied to a subfolder named **SharePoint**. Mailbox items are copied to subfolder named **Exchange**.

자세한 단계별 지침은 [보안 및 준수 센터에서 콘텐츠 검색 결과 내보내기](export-search-results.md)를 참조하세요.

### <a name="downloading-documents-and-lists-from-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 및 비즈니스용 OneDrive에서 문서 및 목록 다운로드

Another way to export data from SharePoint Online and OneDrive for Business is to download documents and lists directly from a SharePoint Online site or a OneDrive for Business account. You would have to get assigned the permissions to access a site, and then go to the site and download the contents. See:

- [OneDrive 또는 SharePoint에서 파일 및 폴더 다운로드](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)
- [SharePoint 목록을 Excel로 내보내기](https://support.office.com/article/export-to-excel-from-sharepoint-bfb2ea48-6118-4fa9-abb6-cced9424e5d9)

For some DSR export requests, you may want to allow the data subject to download content themselves. This enables the data subject to go to a SharePoint Online site or shared folder and click **Sync** to sync all contents in the document library or selected folders. See:

- [사용자가 새 OneDrive 동기화 클라이언트를 사용하여 SharePoint 파일을 동기화하도록 지원](https://docs.microsoft.com/sharepoint/let-users-use-new-onedrive-sync-client)
- [새 OneDrive 동기화 클라이언트를 사용하여 SharePoint 파일 동기화](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-client-6de9ede8-5b6e-4503-80b2-6190f3354a88)

## <a name="deleting-personal-data"></a>개인 데이터 삭제

조직의 고객 데이터에서 개인 데이터를 제거할 수 있는 "삭제권"은 GDPR의 주요 보호 기능입니다. 개인 데이터 제거에는 전체 문서 또는 파일 삭제, 문서 또는 파일 내의 특정 데이터 삭제(이 가이드의 수정 섹션에 설명된 것과 같은 작업 및 프로세스) 등이 포함됩니다.

DSR에 응답하여 개인 데이터를 조사하거나 삭제할 준비를 할 때 Office 365에서 데이터 삭제(및 보존)가 작동하는 방식에 대해 이해해야 할 몇 가지 사항은 다음과 같습니다.

- **일시 삭제 및 영구 삭제:** Exchange Online, SharePoint Online 및 비즈니스용 OneDrive와 같은 Office 365 서비스에는 삭제한 항목을 복구 기회 없이 Microsoft 클라우드에서 영구히 제거하기 전에 복구할 수 있는지(일반적으로 제한된 기간 동안)와 관련된 *일시 삭제* 및 *영구 삭제* 개념이 있습니다. 이 컨텍스트에서 일시 삭제한 항목은 영구 삭제하기 전에 제한된 기간 동안 사용자 및/또는 관리자가 복구할 수 있습니다. 항목이 영구 삭제되면 영구 제거 상태로 표시되며, 해당 Office 365 서비스에 의해 처리될 때 제거됩니다. 일시 삭제 및 영구 삭제가 사서함 및 사이트의 항목에 작동하는 방식은 다음과 같습니다(항목을 삭제한 사람이 데이터 소유자인지 또는 관리자인지는 관계없음).

    - **사서함:** 항목은 지운 편지함 폴더에서 삭제되거나 사용자가 **Shift+Delete**를 눌러 삭제할 때까지 일시 삭제됩니다. 항목을 일시 삭제하면 사서함의 복구 가능한 항목 폴더로 이동됩니다. 이때 항목은 삭제한 항목 보존 기간이 만료될 때까지 사용자가 복구할 수 있습니다(Office 365에서 삭제한 항목 보존 기간은 14일이지만 관리자가 30일까지 늘릴 수 있음). 보존 기간이 만료되면 항목은 영구 삭제된 후 숨겨진 폴더(*제거* 폴더)로 이동됩니다. 항목은 다음 번에 사서함을 처리할 때 Office 365에서 영구적으로 제거됩니다(사서함은 7일마다 1번 처리됨).

    - **SharePoint Online 및 비즈니스용 OneDrive 사이트**: 파일 또는 문서가 삭제되면 사이트의 휴지통(라고도 *1단계 휴지통*(Windows의 휴지통과 유사함)으로 이동됩니다. 항목은 93일(Office 365 사이트에 대한 삭제한 항목 보존 기간) 동안 휴지통에 유지됩니다. 이 기간 후에 항목은 사이트 모음용 휴지통(*2단계 휴지통*)으로 자동으로 이동됩니다. (해당 권한이 있는 사용자 또는 관리자는 1단계 휴지통에서 항목을 삭제할 수도 있음) 이때 항목은 일시 삭제되며, SharePoint Online의 사이트 모음 관리자가 또는 비즈니스용 OneDrive의 사용자 또는 관리자가 복구할 수 있습니다. 항목이 2단계 휴지통에서 삭제되면(수동으로 또는 자동으로) 영구 삭제되며, 사용자 또는 관리자가 액세스할 수 없게 됩니다. 보존 기간은 1단계 및 2단계 휴지통 모두 93일입니다. 즉, 2단계 휴지통 보존은 항목이 처음 삭제될 때 시작됩니다. 따라서 총 최대 보존 기간은 두 휴지통 모두 93일입니다.

>[!NOTE]
>항목이 일시 삭제되거나 영구 삭제되는 작업을 이해하면 삭제 요청에 응답할 때 GDPR 요구 사항을 충족하는 방식으로 데이터를 삭제하는 방법을 결정하는 데 도움이 됩니다.

- **법적 보류 및 보존 정책:** Office 365에서는 사서함과 사이트에 "보류"가 적용될 수 있습니다. 간단히 말해서, 이는 사서함이나 사이트가 보류 중일 때, 항목의 보존 기간이 만료되거나 보류가 제거될 때까지 영구적으로 제거 (하드 삭제)되지 않는 것을 의미합니다. 이는 DSR에 대한 응답으로 고객 콘텐츠를 삭제하는 맥락에서 중요합니다. 보류중인 콘텐츠 위치에서 항목을 하드 삭제하면 해당 항목이 Office 365에서 영구적으로 제거되지 않습니다. 이는 IT 관리자가 복구할 수 있음을 의미합니다. 조직에서 DSR에 대한 응답으로 Office 365에서 데이터를 영구히 삭제하고 복구할 수 없는 요구 사항이나 정책이있는 경우 Office 365에서 데이터를 영구적으로 삭제하려면 보류를 사서함이나 사이트에서 제거해야합니다. DSR에 응답하기 위한 조직의 지침에는 특정 DSR 삭제 요청 또는 법적 보류가 우선하는지 여부를 결정하는 프로세스가 있습니다. 항목을 삭제하기 위해 보류가 제거되면 항목을 삭제한 후에 보류를 다시 구현할 수 있습니다.

### <a name="deleting-documents-in-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 및 비즈니스용 OneDrive에서 문서 삭제

SharePoint Online 사이트 또는 비즈니스용 OneDrive 계정에서 삭제해야 하는 문서를 찾은 후(이 가이드의 검색 섹션에 설명된 지침 참조) 데이터 개인 정보 관리자 또는 IT 관리자는 필요한 권한을 할당 받아야 사이트에 액세스하고 문서를 삭제할 수 있습니다. 해당되는 경우 문서 소유자에게 문서를 삭제하도록 지시할 수도 있습니다.

사이트에서 문서를 삭제하기 위한 대략적인 프로세스는 다음과 같습니다.

1. 사이트로 이동하여 문서를 찾습니다.
2. Delete the document. When you delete a document from a site, it's sent to the first-stage Recycle Bin.
3. Go to the first-stage Recycle Bin (the site Recycle Bin) and delete the same document you deleted in the previous step. The document is sent to the second-stage Recycle Bin. **At this point, the document is soft-deleted**.
4. Go to the second-stage Recycle Bin (which is the site collection Recycle Bin) and delete the same document that you deleted from the first-stage Recycle Bin. **At this point, the document is hard-deleted.**

>[!IMPORTANT]
>You can't delete a document that is located on a site that is on hold (with one of the retention or legal hold features in Office 365). In the case where a DSR delete request takes precedence over a legal hold, the hold would have to be removed from the site before a document could be permanently deleted.

자세한 절차는 다음 항목을 참조하세요.

- [SharePoint 문서 라이브러리에서 파일, 폴더 또는 링크 삭제](https://support.microsoft.com/ko-KR/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52)
- [SharePoint 사이트의 휴지통 항목 삭제 또는 비우기](https://support.microsoft.com/ko-KR/office/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site-2e713599-d13e-40d6-96dc-66f0a366f74e)
- [사이트 모음 휴지통에서 항목 삭제](https://support.microsoft.com/ko-KR/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653)
- [이전 사용자의 데이터에 대한 액세스 권한 얻기 및 백업](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)의 "이전 직원의 비즈니스용 OneDrive 문서에 대한 액세스 권한 얻기" 섹션
- [비즈니스용 OneDrive에서 파일 또는 폴더 삭제](https://support.office.com/article/Delete-files-or-folders-in-OneDrive-21fe345a-e488-4fa7-932b-f053c1bebe8a)
- [SharePoint에서 목록 삭제](https://support.microsoft.com/ko-KR/office/delete-a-list-in-sharepoint-2a7bca5b-b8fd-4e5b-8f4b-2ac034f3070d)
- [SharePoint Online에서 목록 항목 삭제](https://support.office.com/article/delete-list-items-in-sharepoint-online-db722233-4a38-4889-a6cf-4b33fe5c60c0)

### <a name="deleting-a-sharepoint-site"></a>SharePoint 사이트 삭제

You may determine that the best way to respond to a DSR delete request is to delete an entire SharePoint site, which will delete all that data located in the site. You can do this by running cmdlets in SharePoint Online PowerShell.

- 사이트를 삭제하여 SharePoint Online 휴지통으로 이동하려면 [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) cmdlet을 사용합니다(일시 삭제).
- 사이트를 영구적으로 삭제하려면 [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) cmdlet을 사용합니다(영구 삭제).

eDiscovery 보류 상태에 있거나 보존 정책에 지정된 사이트는 삭제할 수 없습니다. 사이트를 삭제 하려면 먼저 eDiscovery 보류 또는 보존 정책에서 제거해야 합니다.

### <a name="deleting-a-onedrive-for-business-site"></a>비즈니스용 OneDrive 사이트 삭제

Similarly, you may determine to delete a user's OneDrive for Business site in response to a DSR deletion request. If you delete the user's Office 365 account, their OneDrive for Business site is retained (and restorable) for 30 days. After 30 days, it's moved to the SharePoint Online Recycle Bin (soft-deleted), and then after 93 days, it's permanently deleted (hard-deleted). To accelerate this process, you can use the [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) cmdlet to move the OneDrive for Business site to the Recycle Bin and then use the [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) cmdlet to permanently delete it. As with sites in SharePoint Online, you can't delete a user's OneDrive for Business site if it was assigned to an eDiscovery hold or a retention policy before the user's account was deleted.

### <a name="deleting-onedrive-for-business-and-sharepoint-online-experience-settings"></a>비즈니스용 OneDrive 및 SharePoint Online 환경 설정 삭제

이 서비스는 비즈니스용 OneDrive 및 SharePoint Online에 저장된 사용자가 만든 파일 뿐만 아니라 다양한 환경을 활용하기 위해 사용하는 사용자에 관한 정보를 저장합니다. 이 내용은 이전에 이 문서에 기재되었습니다. 비즈니스용 OneDrive 및 SharePoint Online 응용 프로그램 데이터에 액세스하고, 보고, 내보내는 방법에 대한 정보는 [콘텐츠 검색 eDiscovery 도구를 사용하여 DSR에 응답](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)의 [선택한 응용 프로그램에 관한 추가 고려 사항](#additional-considerations-for-selected-applications) 섹션을 참조하세요.

#### <a name="deleting-a-sharepoint-user-profile"></a>SharePoint 사용자 프로필 삭제

The SharePoint user profile will be permanently deleted 30 days after the user account is deleted in Azure Active Directory. However, you can hard-delete the user account, which will remove the SharePoint user profile. For more information, see the [Deleting a user section in this guide](#deleting-a-user).

An admin can expedite the deletion of the User Profile for a user by using the **Remove-SPOUserProfile** cmdlet in SharePoint Online PowerShell. See [Remove-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserprofile?view=sharepoint-ps). This requires the user to be at least soft-deleted in Azure Active Directory.

#### <a name="deleting-user-information-lists-on-sharepoint-online-sites"></a>SharePoint Online 사이트에서 사용자 정보 목록 삭제

For users that have left the organization, this data remains in the sites they interacted with for referential integrity of SharePoint column fields. An admin can delete all User information properties for a user on a given site by using the **Remove-SPOUserInfo** command in SharePoint Online PowerShell. See [Remove-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserinfo?view=sharepoint-ps) for information about running this PowerShell cmdlet.

기본적으로 이 명령은 사용자의 표시 이름을 유지하고 전화 번호, 전자 메일 주소, 기술 및 전문 지식 또는 SharePoint Online 사용자 프로필에서 복사된 기타 속성과 같은 속성을 삭제합니다. 관리자는 **RedactUser** 매개 변수를 사용하여 사용자 정보 목록에서 사용자의 대체 표시 이름을 지정할 수 있습니다. 이는 사용자 경험의 여러 부분에 영향을 미치며 사이트의 파일 기록에서 정보가 손실됩니다.

Finally, the redaction capability will not remove all metadata or content referencing a user from documents. The way to achieve redaction of file content and metadata is described in the [Making changes to content in OneDrive for Business and SharePoint Online](#making-changes-to-content-in-onedrive-for-business-and-sharepoint-online) section in this guide. This method consists of downloading, deleting, and then uploading a redacted copy of the file.

#### <a name="deleting-onedrive-for-business-experience-settings"></a>비즈니스용 OneDrive 환경 설정 삭제

The recommended way to delete all OneDrive for Business experience settings and information is to remove the user's OneDrive for Business site, after reassigning any retained files to other users. An admin can delete these lists using [PowerShell Script](https://docs.microsoft.com/powershell/scripting/overview) and [SharePoint Client-Side Object Model (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) commands. See [Deleting OneDrive for Business experience settings](https://docs.microsoft.com/sharepoint/delete-odfb-lists) for more information about the settings, how they are stored, and how to delete them.

#### <a name="onedrive-for-business-and-sharepoint-online-search-queries"></a>비즈니스용 OneDrive 및 SharePoint Online 검색 쿼리

비즈니스용 OneDrive 및 SharePoint Online 검색 환경에서 만든 사용자의 검색 쿼리는 사용자가 쿼리를 만든 후 30일이 지나면 자동으로 삭제됩니다.

### <a name="deleting-items-in-exchange-online-mailboxes"></a>Exchange Online 사서함에서 항목 삭제

DSR 삭제 요청을 충족하기 위해 Exchange Online 사서함의 항목을 삭제해야 할 수 있습니다. IT 관리자가 대상 항목을 일시 삭제할지 또는 영구 삭제할지에 따라 사서함의 항목을 삭제할 수 있는 두 가지 방법이 있습니다. SharePoint Online 또는 비즈니스용 OneDrive 사이트의 문서와 마찬가지로 보류 중인 사서함의 항목은 Office 365에서 영구적으로 삭제할 수 없습니다. 항목을 삭제하려면 먼저 보류를 제거해야 합니다. 다시 말하자면 사서함의 보류 또는 DSR 삭제 요청이 우선적인지 여부를 결정해야합니다.

#### <a name="soft-delete-mailbox-items"></a>사서함 항목 일시 삭제

콘텐츠 검색 작업 기능을 사용하여 콘텐츠 검색에서 반환 되는 항목을 일시 삭제할 수 있습니다. 앞에서 설명한 것처럼 일시 삭제된 항목은 사서함의 복구할 수 있는 항목 폴더로 이동됩니다.

다음은 이 프로세스에 대한 간략한 개요입니다.

1. 콘텐츠 검색을 만들고 실행하여 사용자 사서함에서 삭제하려는 항목을 찾습니다. 검색 결과를 좁히려면 삭제하려는 항목만 검색 결과에 반환되도록 검색을 다시 실행해야 할 수 있습니다.
2. Office 365 PowerShell에서 **New-ComplianceSearchAction** **-Purge** 명령을 사용하여 이전 단계에서 만든 콘텐츠 검색에서 반환되는 항목을 일시 삭제합니다.

자세한 지침은 [조직에서 전자 메일 메시지 검색 및 삭제하기](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)를 참조하세요.

#### <a name="hard-delete-mailbox-items"></a>사서함 항목 영구 삭제

If you have to hard-delete mailbox items in response to the DSR deletion request, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell. If you use this method, consider using Content Search to develop and refine a search query so that only the items that are to be deleted are returned in the search. Then you can use that query syntax when you run the **Search-Mailbox -DeleteContent** command.

자세한 지침은 [메시지 검색 및 삭제](https://technet.microsoft.com/library/ff459253(v=exchg.150).aspx)를 참조하세요.

#### <a name="hard-delete-items-in-a-mailbox-on-hold"></a>보존 중인 사서함의 항목 영구 삭제

As previously explained, if you hard-delete items in a mailbox on hold, items are not removed from the mailbox. They are moved to a hidden folder in the Recoverable Items folder (the **Purges** folder) and will remain there until the hold duration for the item expires or until the hold is removed from the mailbox. If either of those things happen, the items will be purged from Office 365 the next time that the mailbox is processed.

Your organization might determine that items being permanently deleted when the hold duration expires meets the requirements for a DSR deletion request. However, if you determine that mailbox items must be immediately purged from Office 365, you would have to remove the hold from the mailbox and then hard-deleted the items from the mailbox. For detailed instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](https://docs.microsoft.com/microsoft-365/compliance/delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold).

>[!NOTE]
>이전 항목의 절차에 따라 DSR 삭제 요청을 충족하기 위해 사서함 항목을 영구 삭제하려면 사서함이 여전히 보존 중인 동안 해당 항목을 일시 삭제하여 복구 가능한 항목 폴더로 이동하도록 해야 할 수 있습니다.

## <a name="deleting-a-user"></a>사용자 삭제

In addition to deleting personal data in response to a DSR deletion request, a data subject's "right to be forgotten" may also be fulfilled by deleting their user account. Here are some reasons that you might want to delete a user:

- 데이터 주체가 조직을 떠났거나 떠나는 중입니다.
- The data subject has requested that you delete system-generated logs that have been collected about them. Examples of data in system-generated logs include Office 365 app and service usage data, information about search requests performed by the data subject, and data generated by product and services as a product of system functionality and interaction by users or other systems. For more information, see [Part 3: Responding to DSRs for system-generated Logs](#part-3-responding-to-dsrs-for-system-generated-logs) in this guide.
- 데이터 주체가 Office 365에서 데이터에 액세스하거나 처리하는 것을 영구적으로 방지합니다([DSR 제한 요청에 응답](#responding-to-dsr-restriction-requests) 섹션에 설명된 방법을 통한 일시적인 액세스 제한과 반대).

사용자 계정을 삭제한 후

- 사용자가 더 이상 Office 365에 로그인할 수 없거나 조직의 Microsoft 리소스(예: 비즈니스용 OneDrive 계정, SharePoint Online 사이트 또는 Exchange Online 사서함)에 액세스할 수 없습니다.
- 사용자 계정과 연결된 개인 데이터(예: 전자 메일 주소, 별칭, 전화 번호, 우편 주소)가 삭제됩니다.
- 일부 Office 365 응용 프로그램은 사용자에 대한 정보를 제거합니다. 예를 들어, Microsoft Flow에서 삭제된 사용자는 공유된 흐름의 소유자 목록에서 제거됩니다.
- 서비스의 보안 혹은 안정성을 손상시킬 수 있는 데이터를 제외하고 데이터 주체에 대한 시스템 생성 로그는 사용자 계정을 삭제한 후 30일 후에 삭제됩니다. 자세한 내용은 [시스템 생성 로그 삭제 섹션](#deleting-system-generated-logs)을 참조하세요.

>[!IMPORTANT]
>After you delete a user account, that person will lose the ability to sign in to Office 365 and the ability to sign in to any products or services for which he or she formerly relied upon for a work or school account. That person would also be unable to initiate any DSR requests through Microsoft directly in instances where Microsoft is the data controller. For more information, see the [Product and services authenticated with an Org ID for which Microsoft is a data controller](#product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller) section in Part 4 of this guide.

>[!NOTE]
>In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If, during the migration, you would like the Microsoft FastTrack team to also delete the data copy, you can [submit a request](https://go.microsoft.com/fwlink/?linkid=874544). In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.

개인 데이터 삭제에 대한 이전 섹션에서 설명된 데이터의 일시 삭제 및 영구 삭제와 마찬가지로 사용자 계정을 삭제할 때도 일시 삭제 및 영구 삭제 상태가 있습니다.

- 관리 센터 또는 Azure Portal에서 사용자를 삭제하여 초기에 사용자 계정을 삭제한 경우 해당 사용자 계정은 일시 삭제되며 Azure의 휴지통으로 이동하여 최대 30일 동안 보존됩니다. 이때는 사용자 계정을 복원할 수 있습니다.
- If you permanently deleted the user account, the user account is hard-deleted and removed from the Recycle Bin in Azure. At this point, the user account can't be restored, and any data associated with the user account will be permanently removed from the Microsoft cloud. Hard-deleting an account deletes system-generated logs about the data subject, except for data that may compromise the security or stability of the service.

조직에서 사용자를 삭제하는 대략적인 프로세스는 다음과 같습니다.

1. 관리 센터 또는 Azure Portal로 이동하여 사용자를 찾습니다.

2. Delete the user. When you initially delete the user, the user's account is sent to the Recycle Bin. At this point, the user is soft-deleted. The account is retained in the soft-deleted for 30 days, which allows you to restore the account. After 30 days, the account is automatically hard-deleted. For specific instructions, see [Delete users from Azure AD](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory).<br><br> 관리 센터에서 사용자 계정을 일시 삭제할 수도 있습니다. [조직에서 사용자 삭제](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)를 참조합니다.

3. 사용자 계정이 영구 삭제되도록 30 일 동안 기다리지 않으려는 경우 수동으로 영구 삭제할 수 있습니다. Azure 포털에서 이 작업을 수행하려면 최근에 삭제된 사용자 목록으로 이동하여 사용자를 영구적으로 삭제합니다. 이 시점에서 사용자가 영구 삭제 되었습니다. 자세한 내용은 [최근에 삭제된 사용자를 영구 삭제하는 방법](https://docs.microsoft.com/azure/active-directory/active-directory-users-restore)을 참조하세요.

Office 365 관리 포털에서 사용자를 영구 삭제할 수 없습니다.

>[!NOTE]
>In Office 365 operated by 21Vianet (China), you can't permanently delete a user as previously described. To permanently delete a user, you can submit a request via the Office 365 admin portal at this [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage). Go to **Commerce** and then select **Subscription** -> **Privacy** ->  **GDPR** and enter the required information.

### <a name="removing-exchange-online-data"></a>Exchange Online 데이터 제거

사용자를 삭제할 때 사용자의 Exchange Online 사서함이 어떻게 되는지 이해해야합니다. 사용자 계정을 영구 삭제하면 (이전 프로세스의 3 단계에서) 삭제된 사용자의 사서함은 Office 365에서 자동으로 제거되지 않습니다. Office 365에서 영구적으로 제거하려면 사용자 계정을 영구 삭제한 후 최대 60 일이 소요됩니다. 사용자 계정을 삭제한 후의 사서함 수명 주기 및 해당 시간 동안의 사서함 데이터 상태에 대한 설명은 다음과 같습니다.

- **1~30일** - 일시 삭제된 사용자 계정을 복원하여 사서함을 완전히 복원할 수 있습니다.
- **31~60일** - 사용자 계정이 영구 삭제된 후 30일 동안 조직의 관리자는 사서함의 데이터를 복구하여 다른 사서함으로 가져올 수 있습니다. 이에 따라 필요한 경우 조직에 사서함 데이터를 복원할 수 있는 기능이 제공됩니다.
- **61~90일** - 관리자는 사서함의 데이터를 더 이상 복구할 수 없습니다 사서함 데이터는 영구적으로 제거된 것으로 표시되며, 최대 30일 후 Office 365에서 제거됩니다.

이 사서함 수명 주기가 DSR 삭제 요청에 응답하기 위한 조직의 요구 사항을 충족하지 않는 경우 사용자 계정을 영구 삭제한 *후* [Microsoft 지원에 문의](https://support.microsoft.com/)하여 Microsoft에 프로세스를 수동으로 초기화하여 사서함 데이터를 영구적으로 제거하도록 요청할 수 있습니다. 사서함 데이터를 영구적으로 제거하는 이 프로세스는 수명 주기에서 61일 후에 자동으로 시작되므로 수명 주기에서 이 시점 후에는 Microsoft에 문의할 이유가 없습니다.

## <a name="using-in-app-functionality-to-respond-to-dsrs"></a>앱 내 기능을 사용하여 DSR에 응답

While most Customer Data is authored and produced using the applications described in the previous section, Office 365 also offers many other applications that customers can use to produce and store Customer Data. However, Content Search doesn't currently have the ability to find data authored in these other Office 365 applications. To find data generated by these applications, you or the data owner must use in-product functionality or features to find data that may be relevant to a DSR. The following table lists these Office 365 applications. Click the application icon to go the section in this guide that describes how to respond to DSR requests for data authored in the application.

***표 3: 앱 내 기능을 사용하여 고객 데이터를 찾을 수 있는 응용 프로그램***

||||
|:-----:|:-----:|:-----:|:-----:|
| ![Access 아이콘](../media/o365-access-64x64.png) <br> [Access](#access) | ![Office 아이콘](../media/O365-DSR-Doc_image22.png) <br> [Office 365용 <br>비즈니스 앱](#business-apps-for-office-365) | ![Office 아이콘](../media/O365-DSR-Doc_image22.png) <br> [Education](#education)|
| ![Flow 아이콘](../media/o365-flow-64x64.png) <br> [Flow](#flow) | ![Forms 아이콘](../media/o365-forms-64x64.png) <br> [Forms​​](#forms) |![Kaizala 아이콘](../media/o365-kaizala-64x64.png) <br> [Kaizala](#kaizala) |
| ![Planner 아이콘](../media/o365-planner-64x64.png) <br> [Planner](#planner) |![PowerApps 아이콘](../media/o365-powerapps-64x64.png) <br> [Power Apps](#powerapps) |![Power BI 아이콘](../media/o365-powerbi-64x64.png) <br> [Power BI](#power-bi) |
|![Project 아이콘](../media/o365-project-64x64.png) <br> [Project](#project-online) |![Publisher 아이콘](../media/o365-publisher-64x64.png) <br> [Publisher](#publisher) |![Stream 아이콘](../media/o365-stream-64x64.png) <br> [Stream](#stream) |![Sway 아이콘](../media/o365-sway-64x64.png) <br> [Sway](#sway) | ![Whiteboard 아이콘](../media/O365-DSR-Doc_image36.png) <br> [Whiteboard](#whiteboard) |
|![Yammer 아이콘](../media/o365-yammer-64x64.png) <br> [Yammer](#yammer) |
|||

### <a name="access"></a>Access

다음 섹션에서는 Microsoft Access의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

##### <a name="discover"></a>검색

There are several ways that you can search for records in an Access database that might be responsive to a DSR request. For a DSR investigation, you can search for records that related to the data subject or search for records that contain specific data. For example, you could either search or go to a record that corresponds to the data subject. Or you can search for records that contain specific data, such as personal data about the data subject. For more information, see:

- [Access 데이터베이스에서 레코드 찾기](https://support.microsoft.com/ko-KR/office/find-records-in-an-access-database-705220b7-0255-4ef9-9349-6bd7442d1b7e) 
- [단순 선택 쿼리 만들기](https://support.office.com/article/create-a-simple-select-query-de8b1c8d-14e9-4b25-8e22-70888d54de59)

##### <a name="access"></a>Access

After you find the records or fields that are relevant to the DSR request, you can take a screenshot of the data or export it to an Excel file, Word file, or a text file. You can also create and print a report based on a record source, or a select query that you created to find the data. See:

- [Access 보고서 소개](https://support.office.com/article/introduction-to-reports-in-access-e0869f59-7536-4d19-8e05-7158dcd3681c)
- [Excel로 데이터 내보내기](https://support.office.com/article/export-data-to-excel-64e974e6-ae43-4301-a53e-20463655b1a9)
- [Word 문서에 데이터 내보내기](https://support.microsoft.com/ko-KR/office/export-access-data-to-a-word-document-6e954c8e-2243-4cb9-8544-607e5b7bfc12)
- [텍스트 파일로 데이터 내보내기](https://support.microsoft.com/ko-KR/office/export-data-to-a-text-file-f72dfc38-a8a0-4c5b-8c2c-bf2950814140)

##### <a name="export"></a>내보내기

앞에서 설명한 것처럼 Access 데이터베이스에서 다른 파일 형식으로 데이터를 내보낼 수 있습니다. 선택한 내보내기 파일 형식은 데이터 주체의 특정 DSR 내보내기 요청에 의해 결정될 수 있습니다. 다른 파일 형식으로 Access 데이터를 내보내는 방법을 설명하는 항목 목록은 [가져오기 및 내보내기](https://support.microsoft.com/ko-KR/office/import-and-export-c060505b-d8ac-4499-8879-733e56c6106f)를 참조하세요.

##### <a name="delete"></a>삭제

Access 데이터베이스에서 전체 레코드 또는 필드만 삭제할 수 있습니다. Access 데이터베이스에서 레코드를 삭제하는 가장 빠른 방법은 데이터 시트 보기에서 테이블을 열고 레코드 (행) 또는 삭제할 필드의 데이터만 선택한 다음 Delete 키를 누르는 것입니다. 또한 만든 선택 쿼리를 사용하여 데이터를 찾은 다음 삭제 쿼리로 변환할 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [데이터베이스에서 하나 이상의 레코드 삭제](https://support.office.com/article/ways-to-add-edit-and-delete-records-5e90a80c-106d-4c55-996e-07d7200980ce)
- [삭제 쿼리 만들기 및 실행](https://support.office.com/article/create-and-run-a-delete-query-6da65fe1-0fc7-4a64-8ef0-c052cd4c3ec5)

### <a name="business-apps-for-office-365"></a>Office 365용 비즈니스 앱

이 섹션에서는 다음의 각 Office 365용 비즈니스 앱에 포함되어 있는 앱 내 기능을 사용하여 DSR 요청에 응답하는 방법을 설명합니다.

- [Bookings](#bookings)
- [Listings](#listings)
- [Connections](#connections)
- [Outlook Customer Manager](#outlook-customer-manager)
- [Invoicing](#invoicing)

#### <a name="bookings"></a>Bookings

다음 섹션에서는 Microsoft Bookings의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다. 이는 비즈니스 센터를 통해 액세스할 때 독립 실행형 Bookings 앱과 Bookings에 모두 적용 됩니다.

Microsoft Bookings allows administrators and users or staff, with a Bookings license in their organization, to set up booking pages so customers can schedule and make changes to appointments, receive confirmation emails, updates, cancellation, and reminders email. Business owners and their staff can also book events on behalf of their customers with Bookings. 

고객, 관리자 또는 직원은 다음과 같은 유형의 데이터를 만듭니다.

- **고객, 파트너 및 친구의 연락처 정보** - 이 데이터에는 이름, 전화번호, 전자 메일 주소, 주소, 메모가 포함됩니다.

    - 모든 사용자에 대한 연락처는 Bookings Web, iOS 및 Android 클라이언트를 사용하여 수동으로 만들 수 있습니다.
    
    - Bookings iOS와 Android 클라이언트를 사용하여 모든 사용자에 대한 연락처를 C1의 모바일 장치에서 Bookings로 가져올 수 있습니다.
    
    - 고객을 대신해서 사용자가 예약을 만들었거나 소유자의 예약 페이지를 사용하여 고객이 연락처를 만든 경우를 비롯하여 예약 워크플로를 통해 예약을 만들 때 연락처도 자동으로 생성됩니다.

- **예약 이벤트** - 비즈니스 소유자 또는 지정된 해당 담당자 및 고객 간 진행되는 모임입니다. 이 모임은 비즈니스 소유자의 공개 예약 페이지를 통해 비즈니스 소유자 또는 고객이 만든 모임입니다. 이 데이터에는 이름, 주소, 전자 메일 주소, 전화번호 및 비즈니스 소유자가 예약 시 고객으로부터 수집하는 기타 모든 정보를 포함합니다.

- **확인/취소/업데이트 전자 메일** - 특정 예약 이벤트와 관련하여 시스템이 생성하고 전송하는 전자 메일 메시지입니다.  여기에는 관련 서비스를 전달하도록 예약된 직원에 대한 개인 데이터가 포함되며, 비즈니스 소유자 또는 고객이 예약 시에 입력한 고객의 개인 데이터도 포함됩니다.

모든 고객 콘텐츠는 조직의 Bookings를 호스트하는 Exchange Online 사서함에 저장됩니다. 이 콘텐츠는 비즈니스 소유자와 사용자가 데이터를 삭제하도록 명시적으로 요청 하거나 서비스를 종료하는 경우를 제외하고 서비스에서 활성화 된 경우 계속 유지됩니다. 이 콘텐츠는 제품 내 UI, cmdlet 또는 관련 예약 사서함을 삭제하여 제거할 수 있습니다. 삭제 된 작업이 시작되면 비즈니스 소유자가 설정한 기간 내에 데이터가 삭제됩니다. 

고객이 서비스를 종료하기로 결정하면 고객의 콘텐츠는 90일 후에 삭제됩니다. 사용자 계정을 삭제한 후에 사서함 콘텐츠를 삭제하는 경우에 대한 자세한 내용은 [Exchange Online 데이터 제거](#removing-exchange-online-data)를 참조하세요.

#### <a name="end-user-identifiable-information"></a>최종 사용자 식별 가능 정보

End user Identifiable Information (EUII) includes personal and contact information about the staff that gets scheduled in Bookings. It's added to the Staff details pages when the business owner sets up Bookings and makes updates after the setup. It contains staff member's name, initials, email address, and phone number. This data is stored in the Exchange Online mailbox that hosts Bookings.

This data is retained for as long as the staff member is active in the service unless it's explicitly deleted the business owner or an admin using the in-app UI or by deleting the relevant booking mailbox. When the admin initiates the deletion of staff's details, or if the staff member leaves the service, their details are deleted in accordance with the Exchange Online mailbox's content retention policies set by the business owner or admin.

##### <a name="discoveraccess"></a>검색/액세스

Bookings에서는 다음과 같은 유형의 데이터를 수집하고 저장합니다.

- **비즈니스 프로필 정보:** Bookings를 사용하는 비즈니스에 대한 고객 콘텐츠는 Bookings의 비즈니스 정보 양식을 통해 수집되고, 고객이 비즈니스 센터와 함께 Bookings를 사용하는 경우에는 비즈니스 센터 비즈니스 프로필과 동기화됩니다. 이 데이터와 연결된 유일한 EUII는 C1의 전자 메일 주소입니다. 새 예약 알림과 업데이트 전자 메일이 이 주소로 전송됩니다.
- **고객 연락처:** Bookings 웹, iOS 및 Android 클라이언트에서 연락처를 수동으로 만들거나, 모바일 디바이스에서 연락처를 가져올 수 있습니다. 셀프 서비스 예약 페이지를 사용하는 동안 연락처를 자동으로 만들 수도 있습니다. 연락처에는 EUII가 포함되며 해당 연락처는 Bookings 사서함에 저장됩니다.
- **직원 세부 정보:** 고객 콘텐츠에는 Bookings Web, iOS 또는 Android 클라이언트에서 만든 서비스를 제공할 수 있는 자격이 있는 직원에 대한 데이터가 포함됩니다. 직원 세부 정보에는 이름, 전자 메일 주소 및 전화번호가 포함될 수 있습니다.
- **예약 이벤트:** 웹 클라이언트 또는 Android/iOS 앱을 사용하여 기업에서 만들었거나 고객이 공개 예약 페이지(또는 Facebook 페이지)를 사용하여 만든 고객 모임 및 관련 고객 콘텐츠입니다. 이 이벤트에는 이름, 주소, 전자 메일 주소, 전화번호 및 약속 세부 정보가 포함될 수 있습니다.
- **모임 요청, 확인/취소/업데이트 전자 메일, 전자 메일 미리 알림:** Bookings에 연결된 시스템에서 전송하는 전자 메일 메시지입니다. 직원 데이터와 예약 시 입력된 고객 데이터가 포함됩니다.

##### <a name="export"></a>내보내기

To export data corresponding to the business owner, staff and customers, you can use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>삭제

DSR 삭제 요청에 대한 응답으로 다음과 같은 유형의 Bookings 데이터를 삭제할 수 있습니다.

- **비즈니스 프로필 정보 및 연락처:** 관리 센터에서 Bookings 사서함을 삭제할 수 있습니다. 사서함을 삭제한 후 30일 이내에 복원할 수 있습니다. 30일이 지나면 이 계정과 해당 사서함이 영구적으로 삭제됩니다. 사용자 계정 삭제에 관한 자세한 내용은 [사용자 삭제](#deleting-a-user) 섹션을 참조하세요.
- **직원 세부 정보:** Bookings 대시보드에서 직원을 삭제할 수 있습니다. 직원을 영구적으로 삭제하려면 직원의 Office 365 계정을 삭제하세요.
- **Bookings 이벤트:** Bookings 일정에서 예약 이벤트를 삭제할 수 있으며 이벤트를 삭제하면 고객의 정보가 제거됩니다.
- **모임 요청, 전자 메일 확인/취소/업데이트 및 전자 메일 미리 알림:** Bookings 일정에서 이러한 항목을 삭제하여 고객 정보를 제거할 수 있습니다.

Business owners and admins can also delete their customer's data by using the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

Additionally, you can delete business owner and staff data, you can delete the corresponding user account. See the section  [Deleting a user](#deleting-a-user).

#### <a name="listings"></a>Listings

다음 섹션에서는 Microsoft Listings의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

##### <a name="discover"></a>검색

Listings 소유자는 비즈니스를 Google, Bing, Yelp 및 Facebook에 연결하여 집계된 평점 및 리뷰를 볼 수 있습니다. Listings는 다음과 같은 유형의 데이터를 수집하고 저장합니다.

- Google 리뷰 및 평점
- Bing 리뷰 및 평점
- Yelp 리뷰 및 평점
- Facebook 리뷰 및 평점

##### <a name="access"></a>액세스
Listings 소유자는 Listings 대시보드에 로그인하여 해당 리뷰와 평점을 볼 수 있습니다.

##### <a name="export"></a>내보내기

To export business owner, staff and customer data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>삭제

If a Listings owner would like to delete their Listings information, they can disconnect from the provider on the Listings page. After they disconnect, their Listings information will be deleted.

#### <a name="connections"></a>Connections

다음 섹션에서는 Microsoft Connections의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

##### <a name="discover"></a>검색

Connections에서는 다음과 같은 유형의 데이터를 수집하고 저장합니다. 

- 고객 / 연락처는 웹 클라이언트 또는 모바일 앱 (iOS, Android)을 사용하는 비즈니스에서 생성되거나 비즈니스 담당자에게 이메일 마케팅 캠페인이 전송 될 때 앱을 사용하여 생성됩니다. 고객 데이터에는 이름, 주소, 전자 메일 주소, 세금 ID 번호가 포함될 수 있습니다. 연락처는 모든 비즈니스 센터 앱에서 공유됩니다.
- 고객은 Connections 등록 페이지에서 등록하고 개인 정보를 저장할 수 있습니다.
- 전자 메일 캠페인의 링크

##### <a name="access"></a>Access

Connections 소유자는 Connections 대시보드에 로그인하고 전송한 전자 메일 캠페인을 볼 수 있습니다.

##### <a name="export"></a>내보내기

To export business owner, staff and customer data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>삭제

After a Connections owner sends an email campaign, they can't delete the campaign. If there are any draft campaigns they want to delete, they can sign in to the Connections dashboard and delete the draft campaigns.

#### <a name="outlook-customer-manager"></a>Outlook Customer Manager

다음 섹션에서는 Outlook Customer Manager의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

##### <a name="discover"></a>검색

Outlook Customer Manager는 Outlook Customer Manager 소유자 및 해당 고객에 대한 사용자 정보와 비즈니스 연락처를 수집하고 저장합니다.

- Owner data. This includes name, address, and email address. Documents and files that an owner shares with a customer are stored in OneDrive for Business, SharePoint Online, and as tasks in Outlook.
- Customer and business contact data. Customer data can include name, address, and email address. Customer and contact data is created by the business in Outlook or Outlook web app. Contacts are shared across Business center. Documents and files that a customer shares with a business are stored in OneDrive for Business, SharePoint Online, and as tasks in Outlook.

또한 Outlook Customer Manager는 고객에 대한 활동 및 정보를 Exchange에 저장합니다.

##### <a name="access"></a>Access

Outlook Customer Manager 소유자는 Outlook 또는 Outlook Web App에 로그인한 후 Outlook Customer Manager 대시보드로 가서 고객과 수행한 상호 작용을 확인할 수 있습니다.

##### <a name="export"></a>내보내기

To export business owner and customer data, use the Outlook Customer Manager privacy portal. For details. See [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>삭제

To delete customer data, use the Outlook Customer Manager privacy portal. See [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

#### <a name="invoicing"></a>Invoicing

다음 섹션에서는 Microsoft Invoicing의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

##### <a name="discover"></a>검색

Invoicing에서는 다음과 같은 유형의 데이터를 수집하고 저장합니다.

- **연락처:** 고객/비즈니스 연락처의 송장 또는 예상 비용이 생성되면 만들어집니다. 연락처는 비즈니스 센터에서 공유됩니다. 고객 데이터에는 이름, 주소, 전자 메일 주소, 세금 ID 번호가 포함됩니다.
- **송장:** 생성된 후 고객에게 전송되며, 부채 및 과세 의무를 모두 나타냅니다.
- **예상 비용:** 비즈니스가 고객에게 예상 비용을 보낼 수도 있습니다. 고객이 예상 비용을 수락하는 경우 해당 비용이 송장으로 변환됩니다. 고객이 예상 비용을 수락하면 해당 비용이 송장으로 변환됩니다. 예상 비용이 송장으로 변환되면 예상 비용 기록이 삭제됩니다.

##### <a name="access"></a>Access

사용자는 비즈니스 센터의 Invoicing 대시보드도 이동하여 만든 송장 초안과 고객에게 전송된 송장을 확인할 수 있습니다.

##### <a name="export"></a>내보내기

To export customer invoicing data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>삭제

After an invoice is created and sent, it can't be deleted due to accounting laws. The Invoicing owner can request that Microsoft delete some or all their information from Office 365.

Alternatively, you can delete the invoicing owner's user account in Office 365. See the section [Deleting a user](#deleting-a-user).

### <a name="education"></a>Education

이 섹션에서는 다음 Microsoft Education 앱의 앱 내 기능을 사용하여 DSR 요청에 응답하는 방법을 설명합니다.

- Assignments
- Class Notebook

#### <a name="assignments"></a>Assignments

다음 섹션에서는 Assignments의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

##### <a name="discoveraccess"></a>검색/액세스

Assignments stores information that is generated both by teachers and students. Some of this information is store in SharePoint and some is stored in a non-SharePoint location.

##### <a name="finding-assignments-data-stored-in-sharepoint"></a>SharePoint에 저장된 Assignments 데이터 찾기

Students files associated with a Submission for Assignment are stored in a document library (named **Student Work**) and files associated with Assignments that are created by teachers and (accessible by students) are stored in a different document library (named **Class Files**). Both document libraries are in the corresponding Class Team SharePoint site.

관리자는 보안 및 준수 센터의 콘텐츠 검색 도구를 사용하여 과제 및 과제와 관련된 파일에 관련된 제출물과 관련된 학생 파일(학생 작업 및 수업 파일 라이브러리에서)을 검색할 수 있습니다. 예를 들어 관리자는 조직의 모든 SharePoint 사이트를 검색하고 검색 쿼리에서 학생의 이름과 수업 또는 과제 이름을 사용하여 DSR 요청과 관련된 데이터를 찾을 수 있습니다.

마찬가지로 관리자는 교사가 학생에게 배포한 파일 과제와 관련된 교사 파일을 검색할 수 있습니다. 예를 들어 관리자는 조직의 모든 SharePoint 사이트를 검색하고 검색 쿼리에서 교사의 이름과 수업 또는 과제 이름을 사용하여 DSR 요청과 관련된 데이터를 찾을 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [과제 관리자 설명서](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-admin-documentation)
- [콘텐츠 검색 eDiscovery 도구를 사용하여 DSR에 응답](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)(이 가이드에 포함)

##### <a name="finding-assignments-data-not-stored-in-sharepoint"></a>SharePoint에 저장되지 않은 Assignments 데이터 찾기

다음과 같은 유형의 과제 데이터는 수업 팀 SharePoint 사이트에 저장되지 않으므로 콘텐츠 검색을 사용하여 검색할 수 없습니다. 이러한 데이터에는 다음이 포함됩니다.

- 학생의 성적과 교사의 피드백
- 각 학생이 과제에 대해 제출한 문서 목록
- 과제 세부 정보(예: 과제 기한)

To find data, an admin or a teacher would have to go into the Assignment in the Class Team site to find data that may be relevant to a DSR request. An admin can add themselves as an owner to the class and view all the assignments for that class team.

학생이 더 이상 수업에 참여하지 않더라도 해당 데이터는 수업에 계속 남아있을 수 있으며 "더 이상 등록되지 않음"으로 표시될 수 있습니다. 이 경우에는 DSR 요청을 제출하는 학생이 관리자에게 공식적으로 등록한 수업 목록을 제공해야 합니다.

##### <a name="export"></a>내보내기

PowerShell 스크립트를 사용하여 학생의 수업 목록을 가져온 다음 PowerShell 스크립트를 사용하여 데이터를 내보내면, 특정 학생이 등록된 모든 수업에서 해당 학생에 대한 Assignments 데이터를 내보낼 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [Teams에 대한 Assignments 구성](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [특정 학생에 대한 수업 목록 가져오기](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [Assignments에서 학생 및 교사 데이터 내보내기](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-export)

If the student has been removed from the Team Class site, the admin can add the student back to the site before running the export script. Or the admin can use the input file for the script to identify every class that the student was ever enrolled in. You can also use the Assignment export script to export submissions data for all assignments that a teacher has access to.

##### <a name="delete"></a>삭제

PowerShell 스크립트를 사용하여 학생의 수업 목록을 가져온 다음 PowerShell 스크립트를 사용하여 데이터를 삭제하면, 특정 학생이 등록된 모든 수업에서 해당 학생에 대한 Assignments 데이터를 삭제할 수 있습니다. 수업에서 학생을 제거하기 전에 먼저 이 작업을 수행해야 합니다. 자세한 내용은 다음을 참조하세요.

- [Teams에 대한 Assignments 구성](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [특정 학생에 대한 수업 목록 가져오기](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [Assignments에서 학생 데이터 삭제](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-delete)

If the student has been removed from the Team Class site, the admin can add the student back to the site before running the export script. Or the admin can use the input file for the script to identify every class that the student was ever enrolled in. You can't use the Assignments deletion script to delete teacher data because all Assignments are shared across the Class Team site. As an alternative, an admin would have to add themselves to the Class Team site and then delete a specific Assignment.

#### <a name="class-notebook"></a>수업용 전자 필기장

수업용 전자 필기장에서 콘텐츠를 검색하는 방법은 이 가이드의 앞에서 설명되어 있습니다. [OneNote 수업용 전자 필기장](#onenote-class-notebook) 섹션을 참조하세요. 콘텐츠 검색 도구를 사용하여 수업용 전자 필기장에서 데이터를 내보낼 수도 있습니다. 또는 관리자 또는 데이터 주체가 수업용 전자 필기장에서 데이터를 내보낼 수 있습니다. 수업용 [전자 필기장의 복사본 저장](https://support.office.com/article/44733e18-0ef1-4d4b-be51-fc2ac5bfe9ec)을 참조 하세요.

### <a name="flow"></a>Flow

다음 섹션에서는 Microsoft Flow의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover"></a>검색

People can use Flow to perform data-related tasks such as synchronizing files between applications, copying files from one Office 365 service to another, and collecting data from one Office 365 app and storing it in another. For example, a user could set up a Flow to save Outlook email attachments to their OneDrive for Business account. In this example, you could use the Content Search tool to search the user's mailbox for the email message that contained the attachment or search their OneDrive for Business account for the file. This is an example where data handled by Flow might be discoverable in the Office 365 services connected by a Flow workflow.

Additionally, people can use Flow to copy or upload files from Office 365 to an external service, such as Dropbox. In these cases, a DSR request concerning the data in an external service would have to be submitted to the external service, who is processing the data in this type of scenario.

관리자가 DSR 요청을 받으면 자신을 사용자 흐름의 소유자로 추가할 수 있습니다. 이를 통해 관리자는 흐름 정의 내보내기, 실행 기록 및 흐름 권한 재할당 수행과 같은 기능을 수행할 수 있습니다. [관리 센터에서 흐름 관리](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/)를 참조하십시오.

관리자가 자신을 흐름의 소유자로 추가하려면 다음 권한이 있는 계정이 필요합니다.

- Flow/PowerApps 요금제 2 라이선스(유료 또는 평가판)

- [전역 관리자\](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

    또는

- [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

이러한 권한이 있으면 Flow 관리 센터를 사용하여 조직의 모든 흐름에 액세스할 수 있습니다.

자신을 흐름의 소유자로 추가하려면

1. <https://admin.flow.microsoft.com>으로 이동합니다.
2. Office 365 자격 증명으로 로그인합니다.
3. **환경** 페이지에서 액세스하려는 흐름의 환경을 클릭하십시오. 조직에는 기본 환경이 있습니다.
4. On the page for the environment that you selected, click **Resources**, and then click **Flows.** A list of all flows in the environment is displayed.
5. 자신을 구성원으로 추가하려는 흐름에 대해 **세부 정보 보기**를 클릭합니다.
6. **소유자** 아래에서 **공유 관리**를 클릭합니다.
7. **공유** 플라이아웃에서 자신을 구성원으로 추가하고 변경 내용을 저장합니다.

자신을 소유주로 만든 후에는 **흐름** \> **내 흐름** \>**팀 흐름**으로 이동하여 흐름에 액세스합니다. 여기서 실행 기록을 다운로드 하거나 흐름을 내보낼 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [흐름 실행 기록 다운로드](https://flow.microsoft.com/blog/download-history-recurrence/)
- [패키징을 사용하여 환경 간에 흐름 내보내기 및 가져오기](https://flow.microsoft.com/blog/import-export-bap-packages/)

#### <a name="access"></a>액세스

사용자는 자신의 흐름에 대한 정의 및 실행 기록에 액세스할 수 있습니다.

- **흐름 정의:** 흐름 정의를 내보낼 수 있습니다(zip 파일 JSON 형식의 Flow 패키지로 내보냄). [패키징을 사용하여 환경 간에 흐름 내보내기 및 가져오기](https://flow.microsoft.com/blog/import-export-bap-packages/)를 참조하세요.
- **흐름 실행 기록:** 각 흐름의 실행 기록을 다운로드할 수 있습니다. 흐름 실행 기록은 CSV 파일로 다운로드되고, Excel에서 열어 필터링하거나 검색할 수 있습니다. 여러 흐름에 대한 실행 기록을 다운로드할 수도 있습니다. [흐름 실행 기록 다운로드](https://flow.microsoft.com/blog/download-history-recurrence/)를 참조하세요.

#### <a name="delete"></a>삭제

관리자는 흐름 관리 센터에서 사용자 흐름의 소유자로 자신을 추가할 수 있습니다. 사용자가 조직을 떠나고 해당 Office 365 계정이 삭제되는 경우, 해당 사용자가 단독으로 소유했던 흐름은 보존됩니다. 이 기능으로 조직에서 새 소유자에게 해당 흐름을 전달하고, 공유하는 비즈니스 프로세스에 사용되는 흐름에 비즈니스 중단을 방지할 수 있습니다. 그런 다음 관리자는 해당 사용자가 소유했던 흐름을 삭제할지 또는 새 소유자에게 다시 할당할지를 결정하고 해당 작업을 수행해야 합니다.

공유 흐름의 경우 사용자가 조직에서 삭제되면 해당 사용자의 이름이 소유자 목록에서 제거됩니다.

#### <a name="export"></a>내보내기

An admin can export the definition and run history of a user's flows. To do this, an admin must add themselves as an owner of the user's flow in the Flow admin center

- **흐름 정의:** 관리자가 자신을 흐름의 소유자로 추가한 후, **흐름** \> **내 흐름** \> **팀 흐름**으로 이동하여 흐름 정의를 내보낼 수 있습니다(zip 파일 JSON 형식의 Flow 패키지로 내보냄).  [패키징을 사용하여 환경 간에 흐름 내보내기 및 가져오기](https://flow.microsoft.com/blog/import-export-bap-packages/)를 참조하세요.

- **흐름 실행 기록:** 마찬가지로 관리자가 흐름 실행 기록을 내보내려면 흐름 소유자로 자신을 추가 해야 합니다. 흐름 실행 기록은 CSV 파일로 다운로드되므로, Excel을 사용하여 필터링하거나 검색할 수 있습니다. 소유권이 있는 한, 여러 흐름의 실행 기록을 다운로드할 수도 있습니다. [흐름 실행 기록 다운로드](https://flow.microsoft.com/blog/download-history-recurrence/)를 참조하세요.

#### <a name="connections-and-custom-connectors-in-flow"></a>Flow의 연결 및 사용자 지정 커넥터

연결을 위해서는 사용자가 API, SaaS 응용 프로그램 및 사용자 정의 개발 시스템에 연결할 수 있는 자격 증명을 제공해야합니다. 이러한 연결은 연결을 설정한 사용자가 소유하며, 제품 내에서 [관리](https://docs.microsoft.com/flow/add-manage-connections)될 수 있습니다. 흐름이 다시 할당된 후에는 관리자가 PowerShell cmdlet을 사용하여 사용자 데이터 삭제의 일부로 이러한 연결을 나열하고 삭제할 수 있습니다.

사용자 정의 커넥터를 사용하면 즉시 사용 가능한 커넥터를 사용할 수 없는 시스템에 연결하여 조직의 흐름 기능을 확장 할 수 있습니다. 사용자 지정 커넥터 작성자는 커넥터를 조직의 다른 사용자와 [공유](https://docs.microsoft.com/flow/register-custom-api)할 수 있습니다. DSR 삭제 요청을 받은 관리자는 비즈니스 중단을 방지하기 위해 이러한 커넥터의 소유권을 다시 할당하는 것을 고려해야 합니다. 이 프로세스를 신속히 처리하기 위해 관리자는 PowerShell cmdlet을 사용하여 사용자 지정 커넥터를 나열, 다시 할당 또는 삭제할 수 있습니다.

### <a name="forms"></a>Forms

다음 섹션에서는 Microsoft Forms의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover"></a>검색

Forms users can go to <https://forms.office.com> and select **My forms** to see the Forms they've created. They can also select **Shared with me** to view Forms others have shared via a link. If there are many Forms to sort through, users can use the in-product search bar to search for Forms by title or author. To determine whether Microsoft Forms is a place where personal data responsive to your DSR is likely to reside, you can ask the Data Subject to search his or her **Shared with me** list to determine which users ("Forms owners") have sent Forms to the Data Subject. You can then ask the forms owners to select **Share** in the top navigation bar and send you a link to a specific form so you can view it and further determine whether it is material to your DSR.

#### <a name="access"></a>Access

관련 Forms가 발견되면 **응답** 탭을 클릭하여 Forms에 대한 응답에 액세스할 수 있습니다. [퀴즈 결과](https://support.microsoft.com/ko-KR/office/check-and-share-your-quiz-results-c4a9b45c-d62f-4eb7-b5db-ad81892c7c07)를 확인하거나 [form 결과](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)를 확인하는 방법에 대해 자세히 알아보십시오. Excel에서 응답 결과를 검토하려면 **응답** 탭을 선택한 다음 **Excel에서 열기**를 클릭합니다. 데이터 주체에 Form 사본을 보내려는 경우 응용 프로그램에 표시된 관련 질문 및 답변의 스크린 샷을 서식있는 텍스트 형식으로 가져 오거나 데이터 주체에 결과의 Excel 복사본을 보낼 수 있습니다. Excel을 사용하면서 설문 결과의 데이터 주체 부분만 공유하려는 경우 결과를 공유하기 전에 특정 행이나 열을 삭제하거나 나머지 섹션을 삭제합니다. 또는 **공유\>복제본에 대한 링크를 가져오기**(서식 파일로 공유 아래)로 이동하여 전체 Form의 복제본을 데이터 주체에게 제공할 수 있습니다.

#### <a name="delete"></a>삭제

Any survey, quiz, questionnaire, or poll can be permanently deleted by its owner. If you would like to honor a DSR "forget me" and delete a form in its entirety, find the Form in the list of forms, select the series of dots (ellipsis) in the upper right corner of the form preview window, and then click **Delete**. Once a Form is deleted, it can't be retrieved. For information, see [Delete a Form](https://support.microsoft.com/ko-KR/office/delete-a-form-2207e468-ce1b-4c4a-a256-caf631d87af0).

#### <a name="export"></a>내보내기

양식 질문과 대답을 Excel 파일로 내보내려면 양식을 열고 **응답** 탭을 선택한 다음 **Excel에서 열기**를 선택합니다.

### <a name="kaizala"></a>Kaizala

다음 섹션에서는 Microsoft Kaizala의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover"></a>검색

A user's organizational data, which is data that is shared in organizational groups, can be accessed by an admin from the Kaizala management portal. Organizational data is retained for a duration of time determined by your organization's retention policies. In addition to user data, Kaizala servers also store the following types of organizational data:

- 조직 그룹에 속한 구성원 목록
- 조직 그룹에서 공유되는 메시지 및 응답을 나타내는 조직 그룹 메시지 데이터
- 조직의 사용자 목록
- 조직의 모든 사용자에 대해 캡처된 제품 및 서비스 사용 현황 데이터
- 조직에서 만든 Kaizala 작업
- Kaizala 커넥터 데이터

A user's consumer data can be accessed by the data subject using the Kaizala mobile app for consumer data. Consumer data includes the following types of data:

- Kaizala의 비공개 그룹에 속하는 데이터(90일 동안 Kaizala 서버에 저장)
- 사용자의 프로필 정보 및 사용자의 연락처
- 사용자와 같은 그룹에 속하는 구성원 목록
- 그룹 간에 공유되는 그룹 메시지 및 응답
- 사용자의 연락처 목록(Kaizala 서비스에 저장)
- Kaizala에서 사용자가 수행한 거래(인도의 Kaizala 사용자에게만 해당)
- 사용자의 제품 및 서비스 사용 현황 데이터

#### <a name="access"></a>Access

Kaizala users can go to their mobile device to see Kaizala content they've created on their device. To determine whether Kaizala mobile apps is a place where personal data responsive to a DSR is likely to reside, you can ask the data subject to search their Kaizala app for the requested information.

#### <a name="export"></a>내보내기

When users in your organization use Kaizala, consumer data is generated, and organizational data may be generated if the user participates in an organization group. Admins can export a user's organizational data from the Kaizala management portal. Kaizala consumer users can export their private data from the Kaizala mobile app. In both cases, note that product and service usage data is also export when an admin or user exports Kaizala data. For details, see:

- [Kaizala에서 사용자의 조직 데이터 내보내기 또는 삭제](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [Kaizala 모바일 앱에서 데이터 내보내기 또는 삭제](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

#### <a name="delete"></a>삭제

A Kaizala admin can remove a Kaizala user's account in the Kaizala management portal. After a user account is deleted, the user is removed from all groups that belong to your organization and organizational data is deleted from their device. 

To remove all private data from the user's mobile device, the Kaizala user can delete their Kaizala account. After the account is deleted, all related Kaizala content including, chats, photos, and other data will be deleted from the device.

자세한 내용은 다음을 참조하세요.

- [Kaizala에서 사용자의 조직 데이터 내보내기 또는 삭제](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [Kaizala 모바일 앱에서 데이터 내보내기 또는 삭제](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

### <a name="planner"></a>Planner

다음 섹션에서는 Microsoft Planner의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover"></a>검색

Planner 계획은 Microsoft 365 그룹과 연결되고, Microsoft 365 그룹의 파일은 해당 그룹의 연결된 SharePoint Online 사이트에 저장됩니다. 즉, Microsoft 365 그룹 사이트를 검색하여 콘텐츠 검색을 사용하면 Planner 파일을 찾을 수 있습니다. 이렇게 하려면 Microsoft 365 그룹에 대한 URL이 있어야 합니다. "Office 365의 콘텐츠 검색" 도움말 항목에서 [Microsoft Teams 및 Microsoft 365 그룹 검색](https://docs.microsoft.com/microsoft-365/compliance/content-search)을 참조하여 해당 SharePoint Online 사이트에서 Planner 파일을 검색하는 데 도움이 되는 Microsoft 365 그룹에 대한 정보를 얻는 방법에 대한 팁을 참조하세요.

#### <a name="access"></a>Access

이전에 설명한 바와 같이 플랜에 연결된 기본 SharePoint Online 사이트와 사서함을 검색할 수 있습니다. 그런 다음 관련 검색 결과를 미리 보거나 다운로드하여 데이터를 이용할 수 있습니다.

#### <a name="delete"></a>삭제

You can manually delete a user's personally information by either giving yourself permissions to access the plans the user is part of or signing in as the user to make the changes. See [Delete user data in Microsoft Planner](https://support.office.com/article/delete-user-data-in-microsoft-planner-4349ded2-1891-4896-8e27-05fd40f3929f).

#### <a name="export"></a>내보내기

You can use a PowerShell script to export a user's data from Planner. When you export the data, a separate JSON file is export for each plan that the user is a part of. See [Export user data from Microsoft Planner](https://support.office.com/article/export-user-data-from-microsoft-planner-91258c96-b353-4da1-b6d9-d78e4809cf08).

### <a name="power-bi"></a>Power BI

다음 섹션에서는 Microsoft Power BI의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover"></a>검색
You can search for content in the different workspaces in Power BI, including dashboards, reports, workbooks, and datasets. Each type of workspace contains a search field that you can use to search that workspace. See [Searching, finding, and sorting content in Power BI service](https://docs.microsoft.com/power-bi/service-navigation-search-filter-sort).

#### <a name="access"></a>Access

Power BI의 보고서에서 대시보드, 보고서 및 시각적 개체를 인쇄하여 실제 복사본을 만들 수 있습니다. 전체 보고서를 인쇄할 수는 없습니다. 한번에 한 페이지만 인쇄할 수 있습니다. 이렇게하려면 보고서로 이동하고 검색 필드를 사용하여 특정 데이터를 찾은 다음 해당 페이지를 인쇄합니다. [Power BI 서비스에서 인쇄](https://docs.microsoft.com/power-bi/service-print)를 참조하세요.

#### <a name="delete"></a>삭제

대시보드, 보고서 및 통합 문서를 삭제하려면 [Power BI 서비스에서 거의 모든 항목 삭제](https://docs.microsoft.com/power-bi/service-delete)를 참조하세요.

Deleting a dashboard, report, or workbook doesn't delete the underlying dataset. Because Power BI relies on a live connection to the underlying source data to be complete and accurate, deleting personal data must be done there. (For example, if you created a Power BI report that is connected to Dynamics 365 for Sales as the live data source, you would have to make any corrections to the data in Dynamics 365 for Sales.)

데이터가 삭제된 후 Power BI의 [예약된 데이터 새로 고침](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) 기능을 사용하여 Power BI에 저장된 데이터 집합을 업데이트할 수 있습니다. 이후에는 해당 데이터를 활용한 모든 Power BI 보고서 또는 대시보드에서 삭제된 데이터가 더 이상 반영되지 않습니다.  GDPR 요구 사항을 준수하려면 적절한 주기로 데이터를 새로 고치는 정책이 있어야 합니다.

#### <a name="export"></a>내보내기

데이터 이동성 요청을 용이하게 하기 위해 Power BI에서 대시보드와 보고서를 내보낼 수 있습니다.

- You can export the underlying data for dashboards and reports to a static Excel file. See the video in [Printing from Power BI service](https://docs.microsoft.com/power-bi/service-print). Using Excel, you can then edit the personal data to be included in the portability request, and save it in a commonly used, machine-readable format such as .csv or .xml.
- You can export (download) a report from the Power BI service in Office 365 to a .pbix file if it was originally published using Power BI Desktop. You can then import this file to Power BI Desktop and publish (export) it to the Power BI service of another organization. See [Export a report from Power BI service to Desktop](https://docs.microsoft.com/power-bi/service-export-to-pbix).

### <a name="powerapps"></a>PowerApps

다음 섹션에서는 Microsoft Power Apps의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다. 다음 단계는 관리자가 앱 및 해당 종속 리소스를 새 소유자로 전환하여 비즈니스 중단을 제한하는 방법을 설명합니다.

#### <a name="discover"></a>검색

PowerApps는 조직 내에서 공유 및 사용할 수 있는 응용 프로그램을 작성하는 서비스입니다. 앱을 빌드하거나 실행하는 프로세스의 일부로 사용자는 앱, 환경, 연결, 사용자 지정 커넥터, 사용 권한 등 여러 유형의 리소스와 데이터를 PowerApps 서비스에 저장하게 됩니다.

PowerApps와 관련된 DSR 요청을 용이하게 하기 위해 [PowerApps 관리 센터](https://admin.powerapps.com/) 및 [PowerApps 관리 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)에 노출된 관리 작업을 활용할 수 있습니다. 이러한 도구에 액세스하려면 다음 권한이 있는 계정이 필요합니다.

- 유료 PowerApps Plan 2 라이선스 또는 PowerApps Plan 2 평가판 라이선스. [여기](https://web.powerapps.com/trial)에서 30일 평가판 라이선스에 등록할 수 있습니다.
- [전역 관리자](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) 또는
- [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

개인 데이터를 찾는 방법에 대한 자세한 내용은 [PowerApps 개인 데이터 검색](https://go.microsoft.com/fwlink/?linkid=871880)을 참조하세요.

PowerApps 서비스에는 사용자가 Common Data Service 데이터베이스 내에 표준 및 사용자 지정 엔터티에 데이터를 저장할 수 있도록 하는 응용 프로그램에 대한 Common Data Service도 포함 되어 있습니다. [PowerApps Maker 포털](https://web.powerapps.com)에서 이러한 엔터티에 저장된 데이터를 확인하고, [고급 검색](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)의 제품내 검색 기능을 사용하여 엔터티에서 특정 데이터를 검색할 수 있습니다. Common Data Service에서 개인 데이터를 검색하는 방법에 대한 자세한 내용은 [Common Data Service 개인 데이터 검색](https://go.microsoft.com/fwlink/?linkid=871881)을 참조 하세요.

#### <a name="access"></a>Access

관리자는 [PowerApps 관리 센터](https://admin.powerapps.com/) 또는 [PowerApps 관리 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)을 사용하여 앱 및 연결된 리소스(흐름, 연결, 사용자 지정 커넥터 포함)를 액세스하고 실행할 수 있는 권한을 자신에게 할당할 수 있습니다.

After you have access to the user's app, you can use a web browser to open the app. After you open an app, you can take a screenshot of the data. See [Use PowerApps in a web browser](https://docs.microsoft.com/powerapps/run-app-browser).

#### <a name="delete"></a>삭제

PowerApp는 사용자가 조직의 일상적인 작업에서 중요한 역할을 할 수 있는 기간 업무 (LOB) 응용 프로그램을 만들 수 있도록 하기 때문에 사용자가 조직을 떠나 자신의 Office 365 계정이 삭제될 때 관리자는 사용자가 소유한 앱을 삭제할지 또는 새 소유자에게 재할당할 지 여부를 결정해야 합니다. 이 기능으로 조직에서 새 소유자에게 해당 앱을 이전하고, 공유된 비즈니스 프로세스에 사용되는 앱에 대한 비즈니스 중단을 방지할 수 있습니다.

앱과 같은 공유 데이터의 경우 관리자는 해당 사용자의 공유 데이터를 영구적으로 삭제할지 또는 조직 내에서 자신이나 다른 누군가에게 데이터를 재할당하여 유지할지 결정해야 합니다. [PowerApps 개인 데이터 삭제](https://go.microsoft.com/fwlink/?linkid=871883)를 참조하세요.

Any data that was stored by a user in an entity in a Common Data Service For Apps database will also need to be reviewed and (if desired) deleted by an admin using the in-product capabilities. See [Delete Common Data Service user personal data](https://go.microsoft.com/fwlink/?linkid=871886).

#### <a name="export"></a>내보내기

Admins have the ability to export personal data stored for a user within the PowerApps service using the [PowerApps Admin Center](https://admin.powerapps.com/) and [PowerApps Admin PowerShell cmdlets](https://go.microsoft.com/fwlink/?linkid=871804). See [Export PowerApps personal data](https://go.microsoft.com/fwlink/?linkid=871883).

You can also use the in-product search capabilities of [Advanced Find](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) to search for a user's personal data in any entity. For details about exporting personal data in the Common Data Service, see [Export Common Data Service personal data](https://go.microsoft.com/fwlink/?linkid=871889).

#### <a name="connections-and-custom-connectors-in-powerapps"></a>PowerApps의 연결 및 사용자 지정 커넥터

연결을 위해서는 사용자가 API, SaaS 응용 프로그램 및 사용자 정의 개발 시스템에 연결할 수 있는 자격 증명을 제공해야합니다. 이러한 연결은 연결을 설정한 사용자가 소유하며, 제품 내에서 [관리](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection)될 수 있습니다. PowerApps가 다시 할당된 후에는 관리자가 PowerShell cmdlet을 사용하여 사용자 데이터 삭제의 일부로 이러한 연결을 나열하고 삭제할 수 있습니다.

사용자 정의 커넥터를 사용하면 즉시 사용 가능한 커넥터를 사용할 수 없는 시스템에 연결하여 조직의 PowerApps 기능을 확장 할 수 있습니다. 사용자 지정 커넥터 작성자는 커넥터를 조직의 다른 사용자와 [공유](https://docs.microsoft.com/connectors/custom-connectors/use-custom-connector-powerapps)할 수 있습니다. DSR 삭제 요청을 받은 관리자는 비즈니스 중단을 방지하기 위해 이러한 커넥터의 소유권을 다시 할당하는 것을 고려해야 합니다. 이 프로세스를 신속히 처리하기 위해 관리자는 PowerShell cmdlet을 사용하여 사용자 지정 커넥터를 나열, 다시 할당 또는 삭제할 수 있습니다.

### <a name="project-online"></a>Project Online

다음 섹션에서는 Microsoft Project Online의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover-and-access"></a>검색 및 액세스

콘텐츠 검색을 사용하여 프로젝트와 연결된 SharePoint Online 사이트를 검색할 수 있습니다. (프로젝트가 처음 생성되면 연결된 SharePoint Online 사이트를 만들 수 있는 옵션이 표시됩니다.) 콘텐츠 검색을 통해 Project Online에서 실제 프로젝트의 데이터를 검색하지 않고, 연결된 사이트의 데이터만 검색합니다. 콘텐츠 검색에서 제목에 언급된 사용자와 같은 프로젝트에 대한 메타 데이터를 검색하지만,이를 통해 DSR과 관련된 데이터를 포함하는 프로젝트를 찾는 데 (또한 액세스 하는 데) 도움이 될 수 있습니다.

>[!TIP]
>The URL for the site collection in your organization where sites associated with Projects is **https://\<your org\>.sharepoint.com/sites/pwa**; for example, **https://contoso.sharepoint.com/pwa**. You can use this specific site collection as the location of your content search and then the name of the Project in the search query. Additionally, an IT admin can use the Site Collections page in the SharePoint admin center to get a list of PWA site collections in the organization.

#### <a name="delete"></a>삭제

You can delete information about a user from your Project Online environment. See [Delete user data from Project Online](https://support.office.com/article/delete-user-data-from-project-online-252fa593-9c25-47ed-b861-643fe8bf1cb7).

#### <a name="export"></a>내보내기

You can a specific user's content from your Project Online environment. This data is exported to multiple files in the JSON format. For step-by instructions see, [Export user data from Project Online](https://support.office.com/article/export-user-data-from-project-online-27f3838d-3dbe-4b98-80dc-df55f851154d). For detailed information about the files that are exported, see [Project Online export json object definitions](https://support.office.com/article/project-online-export-json-object-definitions-ce5faeae-9af4-4696-b847-a1f4f20327c7).

### <a name="publisher"></a>Publisher

다음 섹션에서는 Microsoft Publisher의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover"></a>검색

대부분의 Office 응용 프로그램에서 사용하는 방법과 마찬가지로 앱 내 검색 기능을 사용하여 Publisher 파일에서 텍스트를 찾을 수 있습니다. [텍스트 찾기 및 바꾸기](https://support.office.com/article/find-and-replace-text-bfe54275-b7c7-4d0f-904d-a2f38d322268)를 참조하세요.

#### <a name="access"></a>액세스

데이터를 찾은 후 해당 데이터의 스크린샷을 찍거나 Word 또는 텍스트 파일에 복사하여 붙여넣고 데이터 주체에 제공할 수 있습니다. 발행물을 Word, PDF 또는 XPS 파일로 저장할 수도 있습니다. 자세한 내용은 다음을 참조하세요.

  - [발행물을 Word 문서로 저장](https://support.microsoft.com/ko-KR/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [다른 이름으로 저장 또는 Publisher를 사용하여 발행물을 .pdf 또는.xps로 변환](https://support.microsoft.com/ko-KR/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="export"></a>내보내기

데이터 주체에 실제 Publisher 파일을 제공하거나 이전에 설명한 바와 같이 발행물을 Word, PDF 또는 XPS 파일로 저장할 수 있습니다. 자세한 내용은 다음을 참조하세요.

  - [발행물을 Word 문서로 저장](https://support.microsoft.com/ko-KR/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [다른 이름으로 저장 또는 Publisher를 사용하여 발행물을 .pdf 또는.xps로 변환](https://support.microsoft.com/ko-KR/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="delete"></a>삭제

발행물에서 콘텐츠를 삭제하고, 전체 페이지를 삭제하거나, 전체 Publisher 파일을 삭제할 수 있습니다. [페이지 추가 또는 삭제](https://support.office.com/article/add-or-delete-pages-daf71e39-86e0-4bbc-a186-d5ec70450b08)를 참조하세요.

### <a name="stream"></a>Stream

다음 섹션에서는 Microsoft Stream의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover"></a>검색

데이터 주체 요청과 관련이 있을 수 있는 Stream에 생성되거나 업로드 된 콘텐츠를 검색하기 위해 Stream 관리자는 사용자 보고서를 실행하여 Stream 사용자가 어떤 동영상, 동영상 설명, 그룹, 채널 또는 댓글에 업로드하거나 생성하거나 또는 포스팅했는지 확인할 수 있습니다. 보고서를 생성하는 방법에 대한 지침은 [Microsoft Stream에서 사용자 데이터 관리](https://docs.microsoft.com/stream/managing-user-data)를 참조하세요. 보고서 출력은 HTML 형식이며 잠재적 관심사를 포함하는 비디오로 이동하는 데 사용할 수 있는 하이퍼링크를 포함합니다. 사용자 지정 권한 집합이 있는 비디오를 보고 싶고 해당 비디오가 원래 의도했던 사용자의 일부가 아닌 경우 관리자 모드로 볼 수 있습니다. 자세한 내용은 [Microsoft Stream의 관리 기능](https://docs.microsoft.com/stream/manage-content-permissions)을 참조하세요.  

#### <a name="access"></a>Access

Depending on the nature of the data subject request, a copy of the report described above can be used help satisfy a data subject request. The user report includes the Stream user's name and unique ID, a list of videos the user uploaded, a list of videos the user has access to, a list of channels the user created, a list of all the groups the user is a member of, and a list of all comments the user left on videos. The report further shows whether the user viewed each video listed in the user report. If you would like to provide the data subject with access to a video to satisfy a DSR request, you can share the video.

#### <a name="export"></a>내보내기

Stream에 대한 액세스 섹션을 참조하세요. 

#### <a name="delete"></a>삭제

To delete or edit videos or any other Stream content, a Stream admin can select view in admin mode to perform the necessary function. See [Admin capabilities in Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions). If a user has left the organization and would like to have their name removed from appearing next to videos that they uploaded, you can remove their name or replace it with another. See [Managing deleted users in Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users).

### <a name="sway"></a>Sway

다음 섹션에서는 Microsoft Sway의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover"></a>검색

Sway ([www.sway.com](https://sway.office.com/)에서 찾음)를 사용하여 만든 콘텐츠는 소유자와 작성자가 Sway를 볼 수 있도록 허용한 사람만 볼 수 있습니다. [Sway의 개인 정보 설정](https://support.microsoft.com/ko-KR/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217)을 참조하세요. Sway가 사용자의 DSR에 대응하는 개인 데이터가 있는 장소인지 여부를 확인하려면 데이터 주체 및 데이터 주체에 대한 컨텐츠를 생성할 가능성이 있는 조직 사용자에게 Sways를 검색하고 데이터 주체의 요청에 응답하는 개인 데이터를 포함할 가능성이 있는 Sways를 공유하도록 요청할 수 있습니다. Sway를 공유하는 방법에 대한 자세한 내용은 이 [Sway 공유](https://support.microsoft.com/ko-KR/office/share-your-sway-1cf853b8-ef7e-46b0-b704-003e58d28998) 문서에서 "조직 계정에서 Sway를 공유하세요"를 참조하세요.

#### <a name="access"></a>Access

Sway에서 데이터 주체와 공유하려는 개인 데이터가 있는 경우 데이터에 대한 액세스 권한을 여러 가지 방법 중 하나로 제공할 수 있습니다. 데이터 주체에 Sway의 온라인 버전 사본을 제공할 수 있습니다 (위 설명 참조). 사용자는 공유하고 싶은 Sway의 관련 부분에 대한 스크린 샷을 찍을 수 있습니다. 또는 Sway를 인쇄하거나 Word로 다운로드하거나 PDF로 변환할 수 있습니다. Sway를 다운로드하는 방법에 대한 자세한 내용은 아래의 "내보내기" 섹션을 참조하세요.

#### <a name="delete"></a>삭제

To learn how to delete a Sway, go to the "How do I delete my Sway?" section in [Privacy settings in Sway](https://support.microsoft.com/ko-KR/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217).

#### <a name="export"></a>내보내기

Sway를 내보내려면 다운로드할 Sway를 열고 오른쪽 위에서 일련의 점(줄임표)을 선택한 후 **내보내기**를 선택하고 **Word** 또는 **PDF**를 선택합니다.

### <a name="whiteboard"></a>Whiteboard

다음 섹션에서는 Microsoft Whiteboard의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

- [Surface Hub의 Whiteboard 2016](#whiteboard-2016-on-surface-hub)
- [다른 모든 플랫폼의 Whiteboard](#whiteboard-for-pc-surface-hub-and-other-platforms)

#### <a name="whiteboard-2016-on-surface-hub"></a>Surface Hub의 Whiteboard 2016

이 섹션에서는 Surface Hub에서 기본 제공 Whiteboard 2016 앱을 사용하여 만든 데이터에 대한 DSR 요청에 응답하는 방법을 설명합니다.

##### <a name="discover"></a>검색

Whiteboard files (.wbx files) are stored in users' OneDrive for Business account. You can ask the data subject or other users if whiteboards they created may contain personal data responsive to a DSR request. They can share a whiteboard with you, or you can get a copy of it to give to the data subject.

화이트보드를 액세스 및 전송하려면 

1. Give yourself access to the user's OneDrive for Business account. See the "Get access to the former employee's OneDrive for Business documents" section in [Get access to and back up a former user's data](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data).
2. 사용자의 비즈니스용 OneDrive 계정에서 화이트보드 앱 데이터 폴더로 이동한 후 전송하려는 화이트보드의 .wbx 파일을 복사합니다.
3. 자기 자신에게 데이터 주체의 비즈니스용 OneDrive 계정에 대한 액세스 권한을 부여한 후 화이트보드 앱 데이터 폴더로 이동합니다.
4. 이전 단계에서 복사한 .wbx 파일을 붙여넣습니다.

##### <a name="access"></a>Access

화이트보드에서 DSR 액세스 요청에 해당하는 개인 데이터를 찾으면 다음과 같은 여러 가지 방법으로 데이터 주체에게 화이트보드에 대한 액세스 권한을 제공할 수 있습니다.

- 화이트보드의 관련 부분에 대한 스크린샷을 만듭니다.
- Upload a copy of the .wbx file to the data subject's OneDrive for Business account. See the previous section for steps on accessing and transferring .wbx files.
- 화이트보드 복사본을 .png 파일로 내보냅니다.

##### <a name="export"></a>내보내기

화이트보드의 복사본을 가져온 경우 내보낼 수 있습니다. 

1. Surface Hub에서 Whiteboard를 시작합니다.
2. Tap the Share button and then select Export a copy.
You can export a whiteboard to a OneNote (.one) file or to an image (.png) file.

##### <a name="delete"></a>삭제

자기 자신에게 사용자의 비즈니스용 OneDrive 계정에 대한 액세스 권한을 부여한 후 화이트보드를 삭제할 수 있습니다.

1. Give yourself access to the data subject's OneDrive for Business account. See the "Get access to the former employee's OneDrive for Business documents" section in [Get access to and back up a former user's data](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)
2. 화이트보드 앱 데이터 폴더로 이동한 후 이 폴더의 내용을 삭제합니다.

#### <a name="whiteboard-for-pc-surface-hub-and-other-platforms"></a>PC, Surface Hub 및 기타 플랫폼용 Whiteboard

If an admin receives a DSR request for data in the new Whiteboard app, they can use Whiteboard PowerShell to add themselves (or other users) as an owner of a user's whiteboards. This enables an admin to perform actions including accessing, exporting, and deleting whiteboards. Use either the **Set-WhiteboardOwner** cmdlet to add yourself or another user as the owner of a whiteboard or use the **Invoke-TransferAllWhiteboards** cmdlet to transfer the ownership of all whiteboards for a specific user to a new owner. For information about using these cmdlets and installing the Whiteboard PowerShell module, see Microsoft Whiteboard cmdlet reference.
After you or another person has ownership of a whiteboard, see [Microsoft Whiteboard cmdlet reference](https://docs.microsoft.com/powershell/module/whiteboard/?view=whiteboard-ps).

화이트보드에 대한 소유권을 얻은 후에는 [화이트보드 지원 문서](https://go.microsoft.com/fwlink/?linkid=872780)에서 화이트보드 액세스, 내보내기 및 삭제 방법에 대한 자세한 지침을 참조하세요.

### <a name="yammer"></a>Yammer

다음 섹션에서는 Microsoft Yammer의 앱 내 기능을 사용하여 개인 데이터를 찾고, 액세스하고, 내보내고, 삭제하는 방법을 설명합니다.

#### <a name="discover"></a>검색

Yammer 관리 센터에서 Yammer 확인된 관리자 (전역 관리자 또는 Yammer에 설정된 관리자)는 지정된 사용자에 관련된 데이터를 내보낼 수 있습니다. 내보내기에는 사용자가 게시하고 수정한 메시지와 파일 및 사용자가 만든 주제 및 그룹에 대한 정보가 포함됩니다. 사용자별 데이터 내보내기가 실행되면 관리자는 선택한 경우 사용자에게 제공할 수 있는 사용자의 계정 활동 데이터가 포함된 받은 편지함 메시지를 받습니다. 자세한 지침은 [Yammer Enterprise: 개인 정보](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)를 참조하세요.

사용자별 내보내기는 단일 네트워크에 적용되므로 사용자가 외부 Yammer 네트워크에 있는 경우 관리자는 홈 네트워크뿐와 해당 외부 네트워크에 데이터를 내보내야 합니다.

데이터 내보내기에 포함되지 않은 데이터에 액세스하려면 사용자의 프로필, 설정, 그룹 구성원 자격, 책갈피에 지정된 메시지, 팔로우한 사용자 및 팔로우한 항목에 대한 스크린샷을 만들 수 있습니다. 사용자 또는 관리자는 이 정보를 수집할 수 있습니다.  자세한 내용은 [Yammer Enterprise: 개인 정보](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)를 참조하세요.

#### <a name="access"></a>Access

You can view data in the exported files, including the full text of messages and the contents of files. You can also click links in the exported files to go directly to the posted messages and files in Yammer, and to groups, and topics the user created, messages the user liked, messages where the user is @mentioned, polls the user has voted on, and links the user has added.

다음은 사용자 단위 데이터 내보내기에 포함되지 않습니다.

- 사용자의 프로필:
    - If the user has a Yammer identity, the user has full control of their profile. For information on how to view and modify the profile, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    
    - If the user has an Office 365 identity, the Yammer user profile is pulled automatically from Office 365, which gets the profile information from Azure Active Directory (AAD). Yammer users can temporarily change their profiles in Yammer, but these changes are overwritten when there is a change in AAD, so you must view and change directory data in AAD. See [Manage Yammer users across their lifecycle from Office 365](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle) and [Add or change profile information for a user in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

-   사용자의 설정:

- The user can view and change their own settings. For information on how to view and modify user settings, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851). An admin can view this information and take screenshots, but can't change it. Go to Yammer settings \> **People**, and then click the name of the user.<br/>
    - 사용자의 그룹 구성원 자격, 책갈피로 지정된 메시지, 팔로우한 사용자 및 팔로우한 항목.
    
    - The user can view this information. For information on how, see [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380). An admin can view this information and take screenshots, but can't change it. Go to Yammer settings \> **People**, and then click the name of the user.

#### <a name="export"></a>내보내기

For instructions for how to export data, see [Manage GDPR data subject requests in Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise). You must run a per-user export for each Yammer network the user is a member of.

Yammer에는 사용자가 메시지나 파일을 삭제할 때 데이터가 일시 삭제되거나 영구 삭제되는 데이터 보존 설정이 있습니다. 이를 일시 삭제로 설정하면 사용자가 삭제한 데이터가 내보내기에 포함됩니다. Yammer 데이터 보존 설정을 영구 삭제로 설정한 경우 삭제된 정보는 Yammer에 더 이상 저장되지 않으므로 내보내기에 포함되지 않습니다.

#### <a name="delete"></a>삭제

Yammer allows verified admins to execute a GDPR-compliant delete via the Yammer admin center if they receive a DSR. This option is called Erase User, and it suspends the user for 14 days and then removes all their personal data, excluding files and messages. If the user is a guest user, this must be done for each external network the guest user is a member of.

>[!NOTE]
>If an admin wants to remove the files and messages of a user during the 14-day window, they will have to perform a user level export to identify the files and messages, and then decide which ones to delete either by in-product deletion or by using a PowerShell script. After the 14-day window, the admin can no longer associate the user with their files or messages.

When a user is deleted with the Erase User option, notification is sent to the Yammer Inbox of all network admins and verified admins. The Erase User option deletes the user's Yammer profile, but does not delete their Office 365 or Azure Active Directory profile.

사용자를 제거하기 위한 세부 단계는 [Yammer Enterprise에서 GDPR 데이터 주체 요청 관리](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)를 참조하세요.

## <a name="responding-to-dsr-rectification-requests"></a>DSR 수정 요청에 응답

데이터 주체가 Office 365에 저장된 조직의 데이터에 있는 개인 데이터를 수정하도록 요청한 경우 사용자와 조직은 요청을 준수하는 것이 적절한지 여부를 결정해야 합니다. 요청을 존중하기로 선택한 경우 데이터의 수정은 문서 또는 다른 유형이나 항목에서 개인 데이터를 편집, 삭제 또는 제거하는 등의 조치를 취하는 것을 포함합니다. 이 작업을 수행 하는 가장 쉬운 방법은 데이터/문서 소유자에게 해당 Office 365 응용 프로그램을 사용하여 요청한 변경을 수행하도록 요청하는 것입니다. 다른 방법은 조직에서 IT 관리자가 변경을 수행하는 것입니다. 이 경우 IT 관리자 (또는 SharePoint Online 사이트 모음 관리자와 같은 적절한 권한이 있는 조직에 있는 다른 사용자)에게 그 자신 또는 다른 사용자에게 DSR 관련한 작업을 하는데 필요한 사용 권한을 부여 해야 합니다. 이는 문서에 대한 액세스 또는 문서가 있는 콘텐츠 위치에 대한 액세스에 대한 권한을 주어 문서를 직접 변경할 수 있습니다.

### <a name="requesting-that-the-data-owner-to-make-the-approved-change"></a>데이터 소유자에게 승인된 변경 작업을 수행하도록 요청

The most direct way to rectify personal data is to ask the data owner to make the change. After you locate the data that is the subject of the DSR, you can provide the following information so that they can make the change.

- 변경 해야 하는 항목의 위치 및 파일 이름 (문서 및 기타 파일). 해당 데이터 찾기는 앞서 설명한 검색 프로세스 [검색 프로세스](#using-content-search-to-find-personal-data) 의 일부입니다.
- 데이터 소유자가 적용해야 하는 승인된 변경 내용

여러분 또는 DSR 조사에 참여한 다른 사람이 요청된 변경 내용이 적용되었는지 확인하는 확인 프로세스를 구현할 수 있습니다.

### <a name="gaining-access-to-a-sharepoint-online-site-or-onedrive-for-business-account-to-make-changes"></a>변경 작업을 수행하기 위해 SharePoint Online 사이트 또는 비즈니스용 OneDrive 계정에 대한 액세스 권한 얻기

If it's not feasible for the data owner to implement the data subject's request for rectification, an IT admin or SharePoint admin in your organization can get access to the content location and make the required changes. Or, an admin can assign you or another data privacy officer the necessary permissions.

#### <a name="sharepoint-online"></a>SharePoint Online

여러분이나 다른 사용자가 해당 문서에 액세스하여 편집할 수 있도록 관리자 또는 소유자를 SharePoint Online 사이트에 할당하려면 다음을 참조하세요.

- [사이트 모음 관리자 관리](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators)

- [SharePoint 목록 또는 라이브러리에 대한 사용 권한 편집 및 관리](https://support.office.com/article/Edit-and-manage-permissions-for-a-SharePoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)

#### <a name="onedrive-for-business"></a>비즈니스용 OneDrive

전역 관리자는 자격 증명을 사용하여 사용자의 비즈니스용 OneDrive 계정에 액세스할 수 있습니다.

1. 전역 관리자 자격 증명으로 Office 365에 로그인합니다.
2. 관리 센터로 이동합니다.
3. **활성 사용자**로 이동하여 사용자를 선택합니다.
4. 세부 정보 창에서 **비즈니스용 OneDrive 설정**을 확장하고 **파일 액세스**를 클릭합니다.
5. URL을 클릭하여 사용자의 비즈니스용 OneDrive 계정으로 이동합니다.

### <a name="gaining-access-to-an-exchange-online-mailbox-to-make-changes-to-data"></a>데이터를 변경하기 위해 Exchange Online 사서함에 대한 액세스 권한 얻기

A global admin can assign themselves the permissions necessary to open and edit (or delete) items in another user's mailbox, as if they were the mailbox owner. A global admin can also assign these permissions to another user. Specifically, the global admin needs to add the **Read and manage** permission, which is the Full Access permission in Exchange Online. For details, see:

- [Office 365에서 다른 사용자에게 사서함 권한 제공](https://docs.microsoft.com/microsoft-365/admin/add-users/give-mailbox-permissions-to-another-user)
- [다른 사용자의 사서함 액세스](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081)

사용자 사서함이 법적인 보류 상태이거나 보존 정책에 할당된 경우 보존 기간이 만료되거나 보류가 사서함에서 제거될 때까지 모든 버전의 사서함이 유지됩니다. 즉, DSR 수정 요청에 대한 응답으로 사서함 항목이 변경되면 원본 항목의 복사본(변경 전)이 유지되고 사용자 사서함의 복구 가능한 항목 폴더에 있는 숨겨진 폴더에 저장됩니다.

### <a name="making-changes-to-content-in-onedrive-for-business-and-sharepoint-online"></a>비즈니스용 OneDrive 및 SharePoint Online의 콘텐츠 변경

Admins or data owners can make changes to SharePoint Online documents, lists, and pages. Keep the following things in mind when making changes to SharePoint content:

- 문서를 업데이트하면 개정판이 포함된 새 버전의 문서가 저장됩니다. 이전 버전의 문서는 업데이트 되지 않습니다. 즉, DSR 수정 요청의 주체인 데이터가 이전 버전의 항목에서 유지될 수 있음을 의미합니다. 이전 버전의 항목을 삭제한 다음 Office 365에서 영구적으로 제거할 수 있습니다. 이 가이드의 [SharePoint Online 및 비즈니스용 OneDrive에서 문서 삭제 섹션](#deleting-documents-in-sharepoint-online-and-onedrive-for-business)을 참조하세요.
- 파일의 모든 버전 및 데이터 주체가 수행한 기록된 모든 활동을 포함하여 데이터 주체의 모든 추적을 파일에서 제거하는 방식으로 SharePoint 파일을 편집하려면 다음 단계를 수행해야 합니다.

    1. 파일의 복사본을 로컬 컴퓨터에 다운로드합니다.
    2. Permanently delete the file from SharePoint Online, by deleting the file, and then deleting if from the first-stage and second-stage Recycle Bin. See the [Deleting documents in SharePoint Online and OneDrive for Business](#deleting-documents-in-sharepoint-online-and-onedrive-for-business) section in this guide.
    3. 로컬 컴퓨터에서 문서의 복사본을 수정합니다.
    4. 수정된 파일을 원래 SharePoint Online 위치에 업로드합니다.

- Data in SharePoint lists can be edited. See [Add, edit, or delete list items](https://support.microsoft.com/ko-KR/office/add-edit-or-delete-list-items-a4b31f53-f044-470e-9823-4526594bacde).

또한 IT 관리자는 문서와 연관된 특정 개인 속성이 수정할 수 있습니다.

User information from the SharePoint User Profile or Office 365 is often associated with OneDrive for Business and SharePoint Online documents to represent that person. For example, a user's name in a Created By or Modified By People column for a document or list item. This user information can be rectified in several ways, depending on the source:

- 그들 자신의 온-프레미스 Active Directory에서 사용자 속성을 수정합니다. 사용자가 온-프레미스 AD에서 사용자 속성 (예: 사용자 표시 이름, 이름 등)을 동기화하는 고객의 경우 해당 속성을 수정해야 합니다. 적절하게 매핑된 속성은 Office 365로 이동하고 비즈니스용 OneDrive 및 SharePoint Online에 전달됩니다.
- 관리 센터에서 사용자 속성을 수정합니다. 계정 정보에 대한 변경 내용이 비즈니스용 OneDrive 및 SharePoint Online 환경에 자동으로 반영 됩니다. 자세한 내용은 [Azure Active Directory에서 사용자에 대한 프로필 정보 추가 또는 변경](https://go.microsoft.com/fwlink/?linkid=864809)을 참조하세요. Office 365에서 제공되는 속성의 경우 SharePoint 측에서 변경할 수 없습니다.
- Rectify user properties in the SharePoint user profile experience of the SharePoint admin center. In the user profiles tab of the SharePoint admin center, admins can click **Manage user profiles**, and look up any user's properties. Then they can choose to Edit the user's properties.
- Rectify user properties in a custom source. Custom SharePoint profile properties may be syncing from a custom source via Microsoft Identity Manager (MIM) or another method.

이것은 이전 정보를 보유할 수있는 모든 환경에는 영향을 미치지 않습니다. 예를 들어, 문서의 텍스트로 표시된 사용자의 이름입니다.

### <a name="making-changes-to-content-in-power-bi"></a>Power BI의 콘텐츠 변경

Power BI relies on the underlying source data used in its dashboards and reports to be complete and accurate, so correcting inaccurate or incomplete source data must be done there. For example, if you created a Power BI report that is connected to Dynamics 365 for Sales as the live data source, you would have to make any corrections to the data in Dynamics 365 for Sales.

After those changes are made, you can take advantage of the [scheduled data refresh](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) capabilities to update the dataset that is stored in Power BI so that the revised data is reflected in the dependent Power BI assets. To help comply with GDPR requirements, you should have policies in place to ensure that you are refreshing your data at an appropriate cadence.

### <a name="making-changes-to-content-in-yammer"></a>Yammer의 콘텐츠 변경

For messages, a user can edit a given message to rectify any inaccuracies. They can request a list of all their messages from a Yammer verified admin, and then click a link in the file to review each message.

For files, a user can edit a given file to rectify any inaccuracies. They can request a list of all the files they posted from a Yammer verified admin, and then access the files in Yammer. Files that are exported into the Files folder can be viewed by searching for the file by number. For example, for a file named 12345678.ppx in the export, use the Search box in Yammer to search for 1235678.ppx. Or, go to <strong>https://www.yammer.com/\<network\_name\>/\#/files/\<file\_number\></strong>; for example, <strong>https://www.yammer.com/contosomkt.onmicrosoft.com/\#/files/12345678</strong>.

사용자가 자신의 프로필 및 설정을 통해 액세스할 수 있는 데이터의 경우 사용자는 필요한 모든 항목을 변경할 수 있습니다.

- 사용자의 프로필:

    - If the user has a Yammer identity, the user has full control of their profile. For information on how to view and modify the profile, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - 사용자에게 Office 365 ID가 있는 경우 Office 365에서 Yammer 사용자 프로필을 자동으로 가져오게 되므로 AAD (Azure Active Directory)에서 프로필 정보를 가져옵니다. Yammer 사용자는 Yammer에서 프로필을 일시적으로 변경할 수 있지만 AAD에 변경 사항이 있을 경우 이러한 변경 내용을 덮어쓰게 되므로 디렉터리 데이터를 보고 변경하는 가장 좋은 위치는 AAD입니다. 사용자가 AAD를 업데이트 하도록 요청해야 합니다. [Office 365의 수명 주기 동안 Yammer 사용자 관리](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle)와 [Azure Active Directory에서 사용자의 프로필 정보를 추가하거나 변경](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal)을 참조합니다.

- 사용자의 설정:

    - The user can change their own settings. For information on how to view and modify user settings, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - The user's group membership, bookmarked messages, followed users, and followed topics. The user can change this information; see [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380).

## <a name="responding-to-dsr-restriction-requests"></a>DSR 제한 요청에 응답

다음은 Office 365에서 데이터 처리를 제한하는 방법입니다.

- Office 365 응용 프로그램 라이선스를 제거하여 사용자가 응용 프로그램을 통해 데이터에 액세스하지 못하도록 합니다.
- 사용자가 비즈니스용 OneDrive 계정에 액세스하지 못하도록 합니다.
- 데이터 처리에서 Office 365 서비스를 해제합니다.
- SharePoint Online 및 비즈니스용 OneDrive에서 일시적으로 데이터를 제거하고 온-프레미스에서 유지합니다.
- SharePoint Online 사이트에 대한 모든 액세스를 일시적으로 제한합니다.
- 사용자가 Office 365에 로그인하지 못하도록 합니다.

나중에 조직에서 제한을 더 이상 적용하지 않기로 결정한 경우 라이선스를 다시 할당하거나, 서비스를 다시 설정하거나, 사용자가 Office 365에 로그인하도록 허용하는 등 제한하기 위해 수행한 단계를 역순으로 수행하여 제한을 종료할 수 있습니다.

### <a name="removing-the-license-for-an-office-365-application"></a>Office 365 응용 프로그램에 대한 라이선스 제거

앞서 설명한 것처럼 조직의 비즈니스용 Microsoft 365 구독에 포함된 모든 Office 365 응용 프로그램에 대한 라이선스는 기본적으로 모든 사용자에게 할당됩니다. IT 관리자는 DSR이 적용되는 데이터에 대한 액세스를 제한해야 할 필요가 있는 경우 Office 365 관리 포털을 사용하여 응용 프로그램에 대한 사용자 라이선스를 일시적으로 해제할 수 있습니다. 사용자가 해당 응용 프로그램을 사용하려고 하면 사용 허가되지 않은 제품 알림이나 해당 사용자에게 더 이상 액세스 권한이 없다는 메시지가 나타납니다. 자세한 내용은 [비즈니스용 Office 365 사용자로부터 라이선스 제거](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)를 참조하세요.

**참고:**

- 사용자가 Yammer에 액세스하는 것을 제한하려면 먼저 [Yammer 사용자에 대해 Office 365 ID를 적용](https://docs.microsoft.com/yammer/configure-your-yammer-network/enforce-office-365-identity)한 다음 사용자의 Yammer 라이선스를 제거해야 합니다.

- Power BI Embedded를 활용하는 시나리오의 경우 콘텐츠가 포함된 ISV(Independent Software Vendor) 응용 프로그램에 대한 액세스를 제한할 수 있습니다.

### <a name="preventing-users-from-accessing-their-onedrive-for-business-account"></a>사용자가 비즈니스용 OneDrive 계정에 액세스하지 못하도록 방지

사용자의 SharePoint Online 라이선스를 제거해도 해당 사용자의 비즈니스용 OneDrive 계정이 존재하면 이에 액세스할 수 있습니다. 비즈니스용 OneDrive 계정에 대한 사용자 권한을 제거해야 합니다. 비즈니스용 OneDrive 계정의 사이트 모음 소유자로 사용자를 제거하여 이 작업을 수행할 수 있습니다. 특히 사용자 프로필의 기본 사이트 모음 관리자 및 사이트 모음 관리자 그룹에서 사용자를 제거해야 합니다. [SharePoint 관리 센터의 사용자 프로필 관리](https://docs.microsoft.com/sharepoint/manage-user-profiles)에서 "비즈니스용 OneDrive 계정에서 관리자 추가 및 제거" 섹션을 참조하세요.

### <a name="turning-off-an-office-365-service"></a>Office 365 서비스 해제

데이터 처리를 제한하는 DSR 요청을 처리하는 또 다른 방법은 Office 365 서비스를 해제하는 것입니다. 이는 조직 전체의 모든 사용자에게 영향을 미치며 모든 사람이 서비스를 사용하거나 서비스의 데이터에 액세스하지 못하게 합니다.

The most expedient way to turn off a service is to use Office 365 PowerShell and remove the corresponding user license from all users in the organization. This will in effect restrict anyone from access data in that service. For detailed instructions, see [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and follow the procedures to disable Office 365 services for users from a single licensing plan.

>[!NOTE]
>For Yammer, in additional to removing the Yammer license from user accounts, you also must disable users' ability to sign in to Yammer with Yammer credentials (by enforcing the use of their Office 365 credentials when signing in). For detailed instructions, see [Turn off Yammer access for Microsoft 365 users](https://support.office.com/article/Turn-off-Yammer-access-for-Office-365-users-1f79bfad-f713-4143-aa5d-5584985ce53a).

### <a name="temporarily-removing-data-from-sharepoint-online-or-onedrive-for-business-sites"></a>SharePoint Online 또는 비즈니스용 OneDrive 사이트에서 일시적으로 데이터 제거

Another way to restrict the processing of personal data is to temporarily remove it from Office 365 in response to a DSR. When your organization determines that the restriction no longer applies, you can import the data back into Office 365.

대부분의 Office 문서는 SharePoint Online 또는 비즈니스용 OneDrive 사이트에 있는 때문에 사이트에서 문서를 제거한 다음, 다시 가져오는 개략적인 프로세스는 다음과 같습니다.

1. Get a copy of the document that is the subject of the restriction request. You may have to request either access to the site or ask a global admin or a site collection administrator to provide you with a copy of the document.
2. 온-프레미스 위치(예: 파일 서버 또는 파일 공유) 또는 Microsoft 클라우드의 Office 365 테넌트가 아닌 다른 위치에 문서를 저장합니다.
3. Permanently delete (purge) the original document from Office 365. This is a 3-step process:

    a.  Delete the original copy of the document. When you delete a document from a site, it's sent to the site Recycle Bin (also called the *first-stage Recycle Bin*).

    b.  Go to the site Recycle Bin and delete that copy of the document. When you delete a document from the site Recycle Bin, it's sent to the site collection Recycle Bin (also called the *second-stage Recycle Bin*). See [Delete a file, folder, or link from a SharePoint document library](https://support.microsoft.com/ko-KR/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52).

    c.  Go to the site collection Recycle Bin and delete that copy of the document, which permanently removes it from Office 365. See [Delete items from the site collection recycle bin](https://support.microsoft.com/ko-KR/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653).

4. 제한이 더 이상 적용되지 않는 경우 온-프레미스에 저장된 문서의 복사본을 Office 365의 사이트에 다시 업로드할 수 있습니다.

>[!IMPORTANT]
>The preceding procedure won't work if the document is located on a site that is on hold (with one of the retention or legal hold features in Office 365). In the case where a restriction request for a DSR takes precedence over a legal hold, the hold would have to be removed from the site before a document could be permanently deleted. Additionally, the document history for deleted documents is permanently removed.

### <a name="temporarily-restricting-access-to-sharepoint-online-sites"></a>일시적으로 SharePoint Online 사이트에 대한 액세스 제한

SharePoint Online 관리자는 일시적으로 SharePoint Online PowerShell의 **Set-SPOSite -LockState** 명령을 사용하여 사이트 모음을 잠가서 모든 사용자가 SharePoint Online 사이트 모음에 액세스하지 못하게 할 수 있습니다. 이렇게 하면 사용자가 사이트 모음 및 사이트에 있는 콘텐츠나 데이터에 액세스할 수 없습니다. 그런 다음 사용자가 사이트에 액세스할 수 있어야 한다고 결정하면 관리자는 사이트의 잠금을 해제할 수 있습니다. 이 PowerShell cmdlet 실행에 대한 자세한 내용은 [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite)를 참조하세요.

### <a name="preventing-a-user-from-signing-in-to-office-365"></a>사용자가 Office 365에 로그인하지 못하도록 방지

An IT admin can also prevent a user from signing into Office 365, which would prevent the user from accessing any Office 365 online service or processing any data stored in Office 365. See [Block a former employee's access to Office 365 data](https://docs.microsoft.com/microsoft-365/admin/add-users/remove-former-employee).

## <a name="part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365"></a>2부: Office 365에서 생성된 정보에 관한 DSR에 응답

Microsoft의 Office 365 서비스 제품군에는 사용자와 조직에 정보를 제공하는 온라인 서비스가 포함되어 있습니다.

- Delve 및 MyAnalytics는 개별 사용자에게 정보 제공
- Workplace Analytics는 조직에 정보 제공

다음 섹션에서는 이러한 서비스에 대해 설명합니다.

### <a name="delve"></a>Delve

Delve에서는 사용자가 Office 365 프로필을 관리하고 관련된 사람과 문서를 검색할 수 있습니다. 사용자는 액세스 권한이 있는 문서만 볼 수 있습니다. Delve에 대한 유용한 문서의 시리즈에 대한 자세한 내용은 [Office Delve](https://support.office.com/article/What-is-Office-Delve-1315665a-c6af-4409-a28d-49f8916878ca)를 참조하세요.

#### <a name="access-and-export"></a>액세스 및 내보내기

Admins can't access or export a users' Delve data. This means that users have to access and export Delve data themselves. Most of the data types can be accessed and exported directly from Delve, but some data types are only available through other services.

##### <a name="data-available-in-the-delve-user-interface"></a>Delve 사용자 인터페이스에서 사용할 수 있는 데이터

- **프로필 데이터:** 사용자가 자신에 대해 추가하도록 선택한 정보(선택 사항)와 Azure Active Directory에 있는 조직의 전체 주소 목록의 프로필 정보입니다. Delve에서 프로필 데이터에 액세스하거나 데이터를 내보내려면 **나** \> **프로필 업데이트**를 클릭합니다. 페이지에서 직접 콘텐츠를 복사하거나 
- **블로그 데이터:** 사용자가 게시한 블로그 게시물입니다. 사용자는 **나** \> **모든 게시물**을 클릭하여 블로그 데이터에 액세스하거나 데이터를 내보낼 수 있습니다. 페이지에서 직접 콘텐츠를 복사하거나 스크린샷을 찍을 수 있습니다.
- **최근 사용자 데이터:** 일정 시기에 가장 관련이 높은 조직 내 사용자를 Delve가 유추한 정보입니다. 사용자가 “사용자를 클릭하여 각자 진행 중인 작업 보기” 창에서 **나** \> **모두 보기**를 클릭하면 일정 시기에 가장 관련이 높은 사용자가 Delve에 표시됩니다.

##### <a name="data-available-through-an-export-link-in-delve"></a>Delve에서 내보내기 링크를 통해 사용할 수 있는 데이터

- **사용자 목록 데이터:** 사용자가 Delve에서 확인한 사람들입니다. **사용자** 목록은 홈페이지의 왼쪽 창에 표시됩니다. Delve에서 최근에 조회한 사용자 목록을 내보낼 수 있습니다.
- **즐겨찾기 데이터:** 사용자가 즐겨찾기로 표시한 보드 및 문서입니다. **즐겨찾기** 페이지에는 사용자가 즐겨찾기에 추가한 보드와 문서가 표시됩니다. 사용자는 현재 즐겨찾기 보드와 문서 목록을 내보낼 수 있습니다.
- **기능 설정 데이터:** 사용자가 Delve를 사용한 결과로 발생하는 Delve 구성 또는 작업입니다. 사용자는 이 설정의 전체 목록을 내보낼 수 있습니다.

To access or export the above data, the user can click the gear icon in the upper-right corner in Delve, and then click **Feature settings** > **Export data**. Information is exported in JSON format.

##### <a name="data-thats-available-through-other-services"></a>다른 서비스를 통해 사용할 수 있는 데이터

- **인기 문서 데이터:** 사용자와 연관이 있을 수 있는 문서와 전자 메일 첨부 파일입니다. Delve는 사용자의 활동과 Office 365에서 함께 작업하는 사람들을 기준으로 이 문서와 전자 메일 메시지를 자동으로 정리합니다. 사용자가 Delve를 열거나 **홈**을 클릭하면 일정 시간에 사용자에게 가장 관련이 있는 문서 또는 첨부 파일이 Delve에 표시됩니다. 사용자는 실제 문서 및 첨부 파일에 액세스하거나 내보내기 위해 문서 또는 첨부 파일을 사용할 수 있는 플랫폼(예: Office.com, SharePoint Online, 비즈니스용 OneDrive 또는 Exchange Online)을 통해 Office 365 서비스로 이동할 수 있습니다.
- **최근 문서 및 전자 메일 첨부 파일 데이터:** 사용자가 수정한 최근 문서 및 전자 메일 첨부 파일입니다. “최근 문서 및 전자 메일 첨부 파일로 돌아가기” 창에서 사용자가 **나** \> **모두 보기**를 클릭하면 일정 시기에 사용자가 수정한 최근 문서와 전자 메일 첨부 파일이 Delve에 표시됩니다. 사용자는 실제 문서 및 첨부 파일에 액세스하거나 내보내기 위해 문서 또는 첨부 파일을 사용할 수 있는 플랫폼(예: Office.com, SharePoint Online, 비즈니스용 OneDrive 또는 Exchange Online)을 통해 Office 365 서비스로 이동할 수 있습니다.
- **주변 사용자의 문서 데이터:** Delve가 일정 시기에 사용자와 가장 관련이 높은 것으로 추정한 문서입니다. 사용자가 “주변 사용자의 문서 검색” 창에서 **나** \> **모두 보기**를 클릭하면 일정 시기에 사용자와 가장 관련이 높은 문서가 Delve에 표시됩니다. 사용자는 실제 문서에 액세스하거나 내보내기 위해 문서 또는 첨부 파일을 사용할 수 있는 플랫폼(예: Office.com, SharePoint Online, 비즈니스용 OneDrive 또는 Exchange Online)을 통해 Office 365 서비스로 이동할 수 있습니다.

#### <a name="rectify"></a>수정

사용자는 Delve에서 다음 정보를 수정할 수 있습니다.

- **프로필 정보:** 사용자는 **나** \> **프로필 업데이트**를 클릭하여 자신의 정보를 업데이트할 수 있습니다. 전체 주소 목록에서 조직의 설정에 따라 사용자는 이름 또는 직함과 같은 일부 프로필 정보를 수정하지 못할 수도 있습니다.
- **기능 설정:** 사용자는 Delve의 오른쪽 위에 있는 기어 아이콘을 클릭한 다음 **기능 설정** \>을 클릭하여 원하는 설정을 변경할 수 있습니다.

#### <a name="restrict"></a>제한

To restrict processing in Delve for your organization, you can turn off the Office Graph. Learn more [here](https://docs.microsoft.com/sharepoint/delve-for-office-365-admins).

#### <a name="delete"></a>삭제

사용자는 Delve에서 다음 정보를 삭제할 수 있습니다.

- **프로필 정보:** 사용자는 **나** \> **프로필 업데이트**를 클릭하여 프로필 정보를 삭제하고 자유 형식 텍스트를 삭제할 수 있습니다. 전체 주소 목록에서 조직의 설정에 따라 사용자는 이름 또는 직함과 같은 일부 프로필 정보를 삭제하지 못할 수도 있습니다.
- **문서 및 전자 메일 첨부 파일:** 문서 또는 첨부 파일을 삭제하려면 사용자는 해당 문서 또는 첨부 파일이 저장된 서비스(예: SharePoint Online, 비즈니스용 OneDrive 또는 Exchange Online)로 이동하여 문서를 삭제해야 합니다.

### <a name="myanalytics"></a>MyAnalytics

MyAnalytics provides statistics to users to help them understand how they spend their time at work. To help your users better understand the data that is presented to them in their personal dashboard and how that data is calculated, direct your users to the [MyAnalytics personal dashboard](https://docs.microsoft.com/workplace-analytics/myanalytics/use/dashboard-2) help topic.

#### <a name="access-and-export"></a>액세스 및 내보내기

조직에서 MyAnalytics를 사용하는 경우 Microsoft는 모든 사용자에 대한 인사이트를 제공합니다. 모든 MyAnalytics 인사이트는 사용자 사서함의 전자 메일 및 모임 머리글에서 가져옵니다. 사용자는 자신의 Office 365 계정에 로그인 한 상태에서 [MyAnalytics 대시 보드](https://delve.office.com)로 이동하여 직장에서 시간을 보내는 방법에 대한 인사이트를 볼 수 있습니다. 사용자가 자신의 정보에 대한 영구적인 복사본을 갖고 싶어하는 경우 MyAnalytics 인사이트를 스크린샷할 수 있습니다.

#### <a name="rectify"></a>수정

All insights generated by MyAnalytics are derived from the user's mail and calendar items. Therefore, there is nothing to rectify other than the source email or calendar items.

#### <a name="restrict"></a>제한

To restrict processing for a specific user, you can opt them out of MyAnalytics. To see how, see [Configure MyAnalytics user settings](https://docs.microsoft.com/workplace-analytics/myanalytics/setup/configure-myanalytics).

#### <a name="delete"></a>삭제

All mailbox content, including MyAnalytics data, is purged when a user account is "hard-deleted" from Active Directory. For more information, see the [Deleting a user](#deleting-a-user) section in this guide.

### <a name="workplace-analytics"></a>Workplace Analytics

Workplace Analytics allows organizations to augment Office 365 data with their own business data to gain insights about organizational productivity, collaboration patterns, and employee engagement. [This article](https://docs.microsoft.com/workplace-analytics/index-orig) explains the control that your organization has over the data that Workplace Analytics processes and who has access to that data.

Workplace Analytics에서 DSR을 지원하려면 

1. Determine whether your organization is using Workplace Analytics. For more information, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md). If your organization is not using Workplace Analytics, there is no further action.

2. 조직에서 Workplace Analytics를 사용하는 경우 조직에서 Workplace Analytics 관리자 역할이 할당된 사람을 확인합니다. 또한 데이터 주체의 사서함이 Workplace Analytics에 대한 라이선스가 있는지 확인합니다. 필요한 경우 Workplace Analytics 관리자에게 Microsoft 기술 지원부에 문의하여 다음 DSR 요청을 처리하도록 합니다. 

#### <a name="access-and-export"></a>액세스 및 내보내기

사용자가 만든 Workplace Analytics 인사이트 보고서에는 조직에서 Office 365 데이터를 보완하는 데 사용하는 정보에 따라 조직에서 Workplace Analytics에 대해 라이선스를 허가한 사용자의 개인 데이터가 포함되어 있을 수도 있고 없을 수도 있습니다. Workplace Analytics 관리자는 해당 보고서를 검토하여 사용자의 개인 데이터가 포함되어 있는지 확인해야 합니다. 보고서에 사용자의 개인 데이터가 포함되어 있는 경우 해당 보고서의 복사본을 사용자에게 제공할지 여부를 결정해야 합니다. Workplace Analytics를 사용하여 보고서를 내보낼 수 있습니다. 

#### <a name="rectify"></a>수정

위에서 설명한 것처럼 Workplace Analytics는 Office 365 데이터를 사용자가 제공하는 조직 데이터와 함께 사용하여 관심있는 보고서를 생성합니다. Office 365 데이터는 수정할 수 없습니다. 사용자의 전자 메일 및 일정 활동을 기준으로 합니다. 그러나 보고서를 생성하기 위해 Workplace Analytics에 업로드 한 조직 데이터는 수정할 수 있습니다. 이렇게 하려면 원본 데이터를 수정하고 업로드한 다음 보고서를 다시 실행하여 새 Workplace Analytics 보고서를 생성해야 합니다.

#### <a name="restrict"></a>제한

특정 사용자에 대한 처리를 제한하기 위해 해당 Workplace Analytics 라이선스를 제거할 수 있습니다.

#### <a name="delete"></a>삭제

If a data subject would like to be removed from a Workplace Analytics report or set of reports, you can delete the report. It is your responsibility to delete users from any organizational data that you used to generate the report, and reupload the data. All data about the user is removed when a user account is "hard-deleted" from Azure Active Directory. 

데이터 주체의 개인 데이터를 제거하려면 전역 관리자는 다음 단계를 수행할 수 있습니다. 

1. 데이터 주체에서 Workplace Analytics 라이선스를 제거합니다.
2. Delete the Azure Active Directory (AAD) entry for the data subject. (For more information, see [Delete a user](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user).)
3. Contact support and have support open a ticket for a Data Subject Rights (DSR) user-delete request. In this ticket, identify the data subject by using their User Principal Name (UPN).
4. 회사의 HR 시스템의 HR 데이터 사본을 내보내고([데이터 내보내기 ](https://docs.microsoft.com/workplace-analytics/setup/prepare-organizational-data) 참조) 해당 HR 데이터 파일에서 데이터 주체 정보를 제거한 다음, 편집된 HR 데이터 파일을 .csv 형식으로 Workplace Analytics에 업로드합니다.([조직 데이터 업로드](https://docs.microsoft.com/workplace-analytics/setup/upload-organizational-data) 참조)

## <a name="part-3-responding-to-dsrs-for-system-generated-logs"></a>3부: 시스템 생성 로그에 대한 DSR에 응답

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- 사용자 활동 로그와 같은 제품 및 서비스 사용 데이터
- 사용자 검색 요청 및 쿼리 데이터
- 시스템 기능 및 사용자나 기타 시스템의 상호 작용의 산물로서 제품 및 서비스에서 생성된 데이터

시스템 생성 로그에서 데이터를 제한하거나 수정하는 기능은 지원되지 않습니다. 시스템 생성 로그의 데이터는 Microsoft 클라우드 및 진단 데이터 내에서 수행되는 실제 작업으로 구성되며, 이러한 데이터를 수정하면 작업의 기록 데이터가 손상되어 사기 및 보안 위험이 높아질 수 있습니다.

### <a name="accessing-and-exporting-system-generated-logs"></a>시스템 생성 로그 액세스 및 내보내기

테넌트 관리자는 조직 내에서 특정 사용자의 Office 365 서비스 및 응용 프로그램 사용과 연결된 시스템 생성 로그에 액세스할 수 있는 유일한 사용자입니다. 내보내기 요청에 대해 검색된 데이터는 컴퓨터에서 읽을 수 있는 형식으로 제공되며, 사용자가 데이터가 연결되는 서비스를 알 수 있도록 해주는 파일로 제공됩니다. 앞서 확인한 대로 검색되는 데이터에는 서비스의 보안 혹은 안정성을 손상시킬 수 있는 데이터가 포함되지 않습니다.

시스템 생성 로그에 액세스하여 내보내려면 다음을 수행합니다.

1. Azure 포털에 로그인하고 **모든 서비스**를 선택합니다.
2. 필터에 정책을 입력한 다음 **정책**을 선택합니다.
3. **정책** 블레이드에서 **사용자 개인 정보**를 선택하고 **사용자 요청 관리**를 선택한 후 **내보내기 요청 추가**를 선택합니다.
4. 다음과 같이 **데이터 내보내기 요청**을 완료합니다.

    - **사용자**. 내보내기를 요청한 Azure Active Directory 사용자의 전자 메일 주소를 입력합니다.
    - **구독**. 리소스 사용량을 보고하고 서비스를 청구할 때 사용하는 계정을 선택합니다. 이 계정은 또한 Azure 저장소 계정의 위치입니다.
    - **저장소 계정**. Azure 저장소(Blob)의 위치를 선택합니다. 자세한 내용은 Microsoft Azure 저장소 소개 — Blob 저장소 문서를 참조하세요.
    - **컨테이너**. 사용자가 내보내기 작업을 수행한 개인 정보 데이터의 저장소 위치로서 새 컨테이너를 만들거나 기존 컨테이너를 선택합니다.

5. **만들기**를 선택합니다.

내보내기 요청이 **보류 중** 상태로 변경됩니다. **사용자 개인 정보** > **개요 블레이드**에서 보고서 상태를 볼 수 있습니다.

>[!IMPORTANT]
>개인 데이터는 여러 시스템에서 가져올 수 있으므로 내보내기 프로세스를 완료하는 데 최대 1개월이 소요될 수 있습니다.

### <a name="notify-about-exporting-or-deleting-issues"></a>내보내기 또는 삭제 중 발생하는 문제에 대한 알림

Azure 포털에서 데이터를 내보내거나 삭제하는 동안 문제가 발생하면 Azure 포털 **도움말 + 지원** 블레이드로 이동하여 **구독 관리** > **기타 보안 및 준수 요청** > **개인 정보 보호 블레이드 및 GDPR 요청**에서 새 티켓을 제출합니다.

>[!NOTE]
 >Azure 포털에서 데이터를 내보내면 일부 응용 프로그램에 대한 시스템 생성 데이터는 내보내지지 않습니다. 이러한 응용 프로그램에 대한 데이터를 내보내려면 [시스템 생성 로그 데이터를 내보내는 추가 단계](https://docs.microsoft.com/microsoft-365/compliance/gdpr-system-generated-log-data)를 참조합니다.

아래에 시스템 생성 로그를 액세스하고 내보내는 방법을 요약해서 설명합니다.

- **Azure 포털을 사용한 내보내기 요청을 완료하는 데 걸리는 시간:** 이는 몇 가지 요인에 따라 다를 수 있습니다. 보통 1일이나 2일 후에 완료되지만 최대 30일이 걸릴 수 있습니다.
- **출력 형식:** 컴퓨터에서 읽을 수 있는 구조화된 파일(예: XML, CSV 또는 JSON)로 출력됩니다.
- **Azure 포털에 액세스하여 시스템 생성 데이터에 대한 액세스 요청을 제출할 수 있는 사용자:** Office 365 전역 관리자는 Azure 포털에 액세스할 수 있습니다.
- **내보내기 결과에 반환된 데이터**: 결과에 Microsoft에서 저장하는 시스템 생성 로그가 포함되어 있습니다. 내보낸 데이터는 Office 365, Azure 및 Dynamics를 포함하여 다양한 Microsoft 서비스에 걸쳐져 있습니다. 결과에는 서비스의 보안 또는 안정성을 손상시킬 수 있는 데이터가 포함되지 않습니다.
- **사용자에게 데이터를 반환하는 방식:** 데이터는 조직의 Azure 저장소 위치로 내보내집니다. 이 데이터를 사용자에게 표시/반환하는 방식은 조직의 관리자가 결정합니다.
- **시스템 생성 로그 데이터 형태:** 다음은 데이터를 JSON 형식으로 표시한 예제입니다.

    ```JSON
    [{
    "DateTime": "2017-04-28T12:09:29-07:00",
    "AppName": "SharePoint",
    "Action": "OpenFile",
    "IP": "154.192.13.131",
    "DevicePlatform": "Windows 1.0.1607"
    }]
    ```

Exchange Online, SharePoint Online, 비즈니스용 Skype, Yammer 및 Office 365 그룹과 같이 Microsoft에서 가장 자주 사용하는 일부 제품 및 서비스 사용 데이터는 보안 & 준수 센터에서 Office 365 감사 로그를 검색하여 얻을 수 있습니다. 자세한 내용은 부록 A의 [DSR 조사에서 Office 365 감사 로그 검색 도구 사용](#use-the-audit-log-search-tool-in-dsr-investigations)을 참조합니다. 감사 로그를 사용하면 조직의 다른 사람 (예 : 규정 준수 담당자)에게 권한을 할당해서 이 데이터에 액세스하여 감사 로그를 검색할 수 있기 때문에 사용자가 원하던 것일 수 있습니다.

### <a name="deleting-system-generated-logs"></a>시스템 생성 로그 삭제

To delete system-generated logs retrieved through an access request, you must remove the user from the service and permanently delete their Azure Active Directory account. For instructions about permanently delete a user, see the [Deleting a user section](#deleting-a-user) in this guide. It's important to note that permanently deleting a user account is irreversible once initiated.

영구적으로 사용자 계정을 삭제하면, 서비스의 보안이나 안정성을 손상시킬 수 있는 데이터를 제외하고, 30일 이내에 거의 모든 Office 365 서비스의 시스템 생성 로그에서 사용자의 데이터가 제거됩니다. 

30일 기간에 대한 한 가지 예외는 Exchange Online에서 사용자 계정을 영구적으로 삭제하는 데 30일 이상이 걸리는 것입니다. 이는 Exchange Online 콘텐츠의 중요한 특성으로 인한 이유와 우발적으로 데이터가 손실되는 것을 방지하기 위한 목적입니다. Exchange Online은 사용자 계정이 영구적으로 삭제된 후 최대 60일 동안 의도적으로 데이터를 보관 상태로 유지하도록 설계되었습니다. 30일 기간 내에 사용자의 Exchange Online 데이터를 영구히 삭제하려면 Azure Active Directory에서 사용자 계정을 영구적으로 삭제한 다음, [Microsoft 지원 서비스](https://support.microsoft.com/)에 연락하여 예약된 삭제 프로세스 외부에서 사용자의 Exchange Online 데이터를 수동으로 제거하도록 요청하세요. 자세한 내용은 이 가이드에서 이전에 설명한 [Exchange Online 데이터 제거](#removing-exchange-online-data)를 참조하세요.

Deleting a user's account will not remove system-generated logs for Yammer and Kaizala. To remove the data from these applications, see one of the following:

- Yammer - [Yammer Enterprise에서 GDPR 데이터 주체 요청 관리](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- Kaizala - [Kaizala에서 사용자의 조직 데이터 내보내기 또는 삭제](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

#### <a name="national-clouds"></a>국가별 클라우드

전역 IT 관리자는 다음과 같은 국가별 클라우드에서 시스템 생성 로그를 내보내려면 다음을 수행해야 합니다.

- **Office 365 Germany**: 위 단계를 따릅니다.
- **Office 365 미국 정부**: [Office 365 관리 포털로 이동한 후](https://portal.office365.us) Microsoft 지원 서비스에 요청을 제출합니다.
- **21Vianet에서 운영하는 Office 365(중국)**: [21Vianet에서 운영하는 Office 365 관리 포털로 이동](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage)한 후 **상거래** > **구독** > **개인 정보** > **GDPR**로 가서 필수 정보를 입력합니다.

## <a name="part-4-additional-resources-to-assist-you-with-dsrs"></a>4부: DSR을 지원하는 추가 리소스

### <a name="dsr-guides-for-other-microsoft-enterprise-services"></a>다른 Microsoft 엔터프라이즈 서비스에 대한 DSR 가이드

이 가이드는 Office 365 제품, 서비스 및 관리 도구를 사용할 때 개인 데이터를 찾아서 DSR에 응답하는 방법에 대한 주제를 다룹니다. 다른 Microsoft 엔터프라이즈 서비스에 대한 유사한 가이드에 액세스하려면 [Microsoft 서비스 보안 포털](https://servicetrust.microsoft.com/)로 이동하세요.

### <a name="microsoft-support"></a>Microsoft 지원 서비스

"Support Data" is the data you and your users provide to Microsoft if your organization or your users engage with Microsoft to receive product support related to Office 365 or other Microsoft products and services (for example, to troubleshoot unexpected product behavior). Some of this data may contain personal data. For more information, see [Microsoft Support and Professional Services Data Subject Requests for the GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-prof-services).

### <a name="product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller"></a>Microsoft가 데이터 통제자인 조직 ID로 인증된 제품 및 서비스

이 가이드의 1-3부는 Microsoft가 조직에서 데이터 프로세서 역할을 하는 제품 및 서비스를 제공하므로, DSR 기능을 테넌트 관리자가 사용할 수 있도록 만들 수 있습니다. 조직의 사용자가 회사 또는 학교 계정("Azure Active Directory ID" 또는 "AAD"라고도 함)을 사용하여 Microsoft가 데이터 컨트롤러인 Microsoft 제품 및 서비스에 로그인하는 경우에는 다양한 상황을 고려해야 합니다. 이러한 모든 제품 및 서비스의 경우 사용자는 직접 Microsoft에 자신의 데이터 주체 요청을 시작해야 하며 Microsoft는 사용자에게 직접 요청을 수행합니다. 사용자 제작 콘텐츠의 저장과 관련된 제품 및 서비스를 사용하면 사용자가 제품 고유 기능의 일부로 사용자 제작 콘텐츠에 액세스, 내보내기, 수정 및 삭제할 수 있게 설계되었습니다. 이 시나리오가 적용될 수 있는 경우는 다음과 같습니다.

- **선택적으로 연결된 온라인 서비스:** 엔터프라이즈용 Microsoft 365 앱은 사용자가 선택적으로 연결된 특정 온라인 서비스를 사용할 수 있도록 합니다. 서비스 및 관련 사용자 컨트롤의 목록이 [여기](https://support.office.com/article/microsoft-s-other-connected-services-92c234f1-dc91-4dc1-925d-6c90fc3816d8)에 나열됩니다. 최종 사용자가 이러한 서비스를 사용할 수 있도록 허용할지를 결정할 수 있습니다. 자세한 내용은 관리자가 [엔터프라이즈용 Microsoft 365 앱에서 컨트롤러 서비스를 관리하는 방법](https://docs.microsoft.com/DeployOffice/manage-controller-services-office-365-proplus)을 참조하세요. 이러한 선택적 서비스가 개인 데이터를 처리하는 경우 Microsoft가 이 서비스의 데이터 컨트롤러입니다.
- **사용자 의견:** Microsoft 제품 및 서비스에 대한 피드백을 제공하는 경우 Microsoft는 개인 데이터가 포함된 범위까지 해당 피드백에 대한 데이터 컨트롤러입니다. Microsoft는 사용자에게 피드백 수집 프로세스 동안 개인 데이터를 포함하지 않도록 지시한 경우를 제외하고는 Microsoft에서 수집한 피드백의 데이터 주체 요청(Microsoft 하위 프로세스에서 관리하는 피드백 포함)을 수행합니다. 예외 사항: Microsoft에서 사용자에게 피드백 수집 프로세스 동안 개인 데이터를 포함하지 않도록 지시한 경우, Microsoft는 이 지침을 신뢰하여 개인 데이터가 제공되지 않았다고 가정합니다. 타사 피드백 서비스 공급자와 별도의 계정을 만든 사용자는 해당 공급자와 직접 DSR을 수행해야 합니다.
- **회사 또는 학교 계정을 통해 인증된 Windows:** 조직에서 Windows 라이선스를 구매하고 사용자가 회사 또는 학교 계정으로 조직에서 제공하는 Windows에 인증하는 경우, Microsoft는 데이터 통제자의 역할을 합니다. 
- **사용자 획득 제품 또는 서비스:** 개별 기능으로 작동하는 사용자가 인증에 AAD를 사용하는 Microsoft 제품 또는 서비스(예: Microsoft Store에서 사용할 수 있는 Office 추가 기능 또는 응용 프로그램)를 획득하도록 허용하는 경우, Microsoft가 데이터 컨트롤러일 수 있습니다. 해당 Microsoft 제품 또는 서비스의 경우 사용자가 Microsoft에 직접 문의하여 DSR을 시작해야 합니다.

>[!IMPORTANT]
>If you delete a user as enabled via Azure Active Directory, your (former) user will lose the ability to sign in to any products or services for which he or she formerly relied upon for a work or school account. Additionally, Microsoft will no longer be able to authenticate the user in connection with a DSR request for products or services for which Microsoft is a data controller. If you wish to enable a user to initiate DSRs against such services, it is important you instruct your user to do so before you delete the user's AAD account.

### <a name="personal-accounts"></a>개인 계정

사용자가 Microsoft 계정(즉, 개인 계정)을 사용하여 Microsoft가 데이터 통제자인 제품 및 서비스를 Microsoft에서 개인적인 용도로 구입한 경우 사용자는 [Microsoft 개인 정보 대시보드](https://account.microsoft.com/account/privacy)를 사용하여 DSR 요청을 시작할 수 있습니다.

### <a name="third-party-products"></a>타사 제품

조직 또는 사용자가 개인적으로 타사에서 제품 또는 서비스를 구입하고 Microsoft 회사 또는 학교 계정을 인증에 사용하는 경우에는 모든 데이터 주체 요청을 해당 타사로 전달해야 합니다.

## <a name="appendix-a-preparing-for-dsr-investigations"></a>부록 A: DSR 조사 준비

조직에서 Office 365 서비스를 사용하여 DSR 조사를 준비하도록 도와주려면 다음 권장 사항을 고려하세요.

- 보안 및 준수 센터에서 DSR eDiscovery 사례 도구를 사용하여 DSR 조사를 관리합니다.
- 콘텐츠 검색 범위를 제한하도록 준수 경계를 설정합니다.
- DSR 조사에서 감사 로그 검색 도구를 사용합니다.

### <a name="use-the-dsr-case-tool-to-manage-dsr-investigations"></a>DSR 사례 도구를 사용하여 DSR 조사를 관리합니다.

We recommend that you use the DSR case tool in Security & Compliance Center to manage DSR investigations. By using the DSR case tool, you can:

- 각 DSR 조사에 대한 별도의 사례를 만들 수 있습니다.

- 내장된 기능을 사용하여 특정 데이터 주체와 관련된 모든 컨텐츠를 검색하세요. 사례를 만들고 검색을 시작하면 다음과 같은 콘텐츠 위치가 검색됩니다.

   - 조직의 모든 사서함(모든 Microsoft Teams 및 Microsoft 365 그룹과 연결된 사서함 포함)
   - 조직의 모든 SharePoint Online 사이트 및 비즈니스용 OneDrive 계정
   - 조직의 모든 Microsoft Teams 사이트 및 Microsoft 365 그룹 사이트
   - Exchange Online의 모든 공용 폴더

- 기본 검색 쿼리를 수정하고 검색을 다시 실행하여 검색 결과의 범위를 좁힐 수 있습니다.

- 사례의 구성원으로 사람을 추가하여 사례에 액세스할 수있는 사용자를 제어합니다. 구성원만이 사례에 액세스할 수 있으며 보안 및 규정 준수 센터의 DSR 사례 페이지에있는 사례 목록에서 자신의 사례만을 볼 수 있습니다. 또한 동일한 사례의 다른 구성원에게 다른 사용 권한을 할당할 수 있습니다. 예를 들어 일부 구성원은 콘텐츠 검색의 사례와 결과만 볼 수 있고 다른 구성원은 검색을 만들고 검색 결과를 내보낼 수 있습니다.

- DSR 내보내기 요청에 대한 응답으로 검색 결과를 내보내려면 내보내기 작업을 만듭니다. 콘텐츠 검색에서 반환된 모든 콘텐츠를 내보낼 수 있습니다. 데이터 주체와 관련된 다른 Office 365 데이터도 내보낼 수 있습니다.

- DSR 내보내기 요청에 대한 응답으로 검색 결과를 내보내려면 내보내기 작업을 만듭니다. 콘텐츠 검색에서 반환된 모든 콘텐츠를 내보낼 수 있습니다. Office Roaming 서비스에 대한 시스템 생성 로그를 내보낼 수도 있습니다.

- DSR 조사 프로세스가 완료되면 사례를 삭제하세요. 그러면 사례와 관련된 모든 콘텐츠 검색 및 내보내기 작업이 제거됩니다.

DSR 사례 사용을 시작하려면 보안 및 준수 센터에서 [DSR 사례 도구를 사용하여 GDPR 데이터 주체 요청 관리하기](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool)를 참조하세요.

>[!IMPORTANT]
>An eDiscovery Administrator can view and manage all DSR cases in your organization. For more information about the different roles related to eDiscovery, see [Assign eDiscovery permissions to potential case members](https://docs.microsoft.com/Office365/SecurityCompliance/assign-ediscovery-permissions).

### <a name="set-up-compliance-boundaries-to-limit-the-scope-of-content-searches"></a>콘텐츠 검색 범위를 제한하도록 준수 경계를 설정합니다.

Compliance Boundaries are implemented by using the search permissions filtering functionality in the Security & Compliance Center. Compliance Boundaries create logical search boundaries within an organization that control/limit which content locations (for example Exchange Online mailboxes and SharePoint Online sites) that an IT admin or compliance officer can search. Compliance Boundaries are useful for multi-national organizations that need to respect geographical boundaries, governmental organizations that need to separate different agencies, and business organizations that segregated into business unit or department. For all these scenarios, Compliance Boundaries can be used in DSR investigations to limit which mailboxes and sites can be searched by people involved in the investigation.

준수 경계를 eDiscovery 사례와 함께 사용하여 조사에서 검색할 수 있는 콘텐츠 위치를 기관 또는 비즈니스 단위 내부의 위치로만 제한할 수 있습니다.

DSR 조사에 대한 준수 경계(eDiscovery 사례와 함께)를 구현하는 방법에 대한 대략적인 개요는 다음과 같습니다.

1. 조직에서 준수 경계로 지정할 기관을 결정합니다.

2. Determine which user object attribute in Azure Active Directory will be used to define the compliance boundary. For example, you might choose the Country, CountryCode, or Department attribute, so that members of the admin role group that you create in the next step can only search the content locations of the users that have a specific value for that attribute. This is how you limit who can search for content in a specific agency.

>[!NOTE]
>비즈니스용 OneDrive의 경우 추가 단계를 수행하고 Microsoft 지원에 비즈니스용 OneDrive 계정에 특성을 동기화하도록 요청해야 합니다.

4. Create an admin role group in the Security & Compliance Center for each compliance boundary. We recommend that you create these role groups by copying the built-in eDiscovery Manager role group and then removing any roles as necessary.

5. 특정 역할 그룹 각각에 eDiscovery Mangers로 구성원을 추가합니다. 구성원은 DSR을 조사 및 응답하는 역할을 수행하며, 일반적으로 IT 관리자, 데이터 개인 정보 관리자, 준수 관리자 및 인사 담당자로 구성됩니다.

6. 해당 관리자 역할 그룹의 구성원이 해당 기관 / 규제 준수 범위 내의 사용자에 대해서만 사서함과 사이트를 검색할 수 있도록 각 준수 경계에 대한 검색 권한 필터를 만듭니다. 검색 권한 필터를 사용하면 해당 역할 그룹의 구성원이 기관 / 규정 준수 범위에 해당하는 사용자 개체 특성 값을 사용하여 콘텐츠 위치만을 검색할 수 있습니다.

단계별 지침은 [Office 365에서 eDiscovery 조사에 대한 준수 경계 설정](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries)을 참조하세요.

### <a name="use-the-audit-log-search-tool-in-dsr-investigations"></a>DSR 조사에서 감사 로그 검색 도구를 사용합니다.

IT admins can use the audit log search tool in the Security & Compliance Center to identity documents, files, and other Office 365 resources that users have created, accessed, changed, or deleted. Searching for this kind activity can be useful in DSR investigations. For example, in SharePoint Online and OneDrive for Business, auditing events are logged when users perform these activities:

- 파일에 액세스
- 파일 수정
- 파일 이동
- 파일 업로드 또는 다운로드

특정 활동, 활동 유형, 특정 사용자가 수행 한 활동 및 기타 검색 기준에 대한 감사 로그를 검색 할 수 있습니다. SharePoint Online 및 비즈니스용 OneDrive 활동 외에도 Flow, Power BI 및 Microsoft Teams에서 활동을 검색할 수 있습니다. 감사 기록은 90일간 보존됩니다. 따라서 90일 전에 발생한 사용자 활동은 검색할 수 없습니다. 감사받은 작업의 전체 목록과 감사 로그 검색 방법을 보려면 [보안 및 규정 준수 센터에서 감사 로그 검색하기](search-the-audit-log-in-security-and-compliance.md)를 참조하세요.

>[!TIP]
>위에 설명된 90일 제한 문제를 해결하고 조직의 감사 레코드에 대한 실행 기록을 유지 관리하려면 되풀이되는 일정(예: 30일마다)으로 모든 활동을 내보내 조직의 감사 레코드에 대한 연속 레코드를 만들면 됩니다.

## <a name="appendix-b-change-log"></a>부록 b: 변경 로그

다음 표에서는 2018년 5월 25일에 처음 게시된 이후, 변경된 Office 365 DSR 가이드 내용이 나와 있습니다.

|날짜  |섹션/앱 |변경 사항  |
|:---------|:---------|:---------|
|2018년 9월 18일 | [Whiteboard](#whiteboard) |Whiteboard Preview is no longer in preview and has been released to general availability. Therefore, the section on Whiteboard Preview was renamed to "Whiteboard for PC, Surface Hub, and other platforms"; procedures to access, export, and delete data were removed from this section and replaced with a link to the Whiteboard support article.|
|2018년 11월 8일 | [Workplace Analytics](#workplace-analytics) |Workplace Analytics에서 데이터 주체를 제거하고 Workplace Analytics 보고서에서 데이터 주체에 대한 정보를 제거하는 방법에 대한 단계별 지침이 삭제 섹션에 추가되었습니다.|
|2018년 11월 12일| 모두| 끊어진 책갈피 및 외부 항목에 대한 끊어진 링크를 수정했습니다.|
|2019년 1월 9일| StaffHub |삭제 섹션에서는 사용자 계정을 영구적으로 삭제할 때 발생하는 작업에 대한 설명이 업데이트되었습니다.|
|2019년 5월 8일| [Publisher](#publisher)|Publisher의 DSR에 대한 응답 관련 콘텐츠가 추가되었습니다.|
|2019년 7월 11일| [MyAnalytics](#myanalytics)|모든 사용자가 MyAnalytics 앱에서 해당 데이터를 볼 수 있기 때문에 관리자가 보안 및 준수 센터에서 DSR 사례 도구를 사용하여 MyAnalytics 데이터를 내보내는 기능이 제거되었습니다. |
|2019/11/6|[교육](#education)|PowerShell 스크립트를 사용하여 특정 학생의 수업 목록을 가져온 다음 해당 학생의 데이터를 내보내거나 삭제하는 방법에 대한 새 주제에 연결되었습니다.|
|2020/1/28| 모두 | 문서에서 StaffHub가 제거되었습니다. StaffHub는 사용이 중지되었습니다. |
||||
