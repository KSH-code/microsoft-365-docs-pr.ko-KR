---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 마이그레이션 전 활동
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동하는 경우 사전 작업입니다.'
ms.openlocfilehash: 9c3aff56f5d85cd1b98747ef5b747720af74fe02
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073940"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 마이그레이션 전 활동

다음 링크를 사용하여 조직과 관련된 마이그레이션 전 단계로 이동하세요.

사용 중이면

- **도이치랜드 Microsoft 클라우드의 Office 365** 에서 다음 [단계를 수행합니다.](#general-tenant-migration-considerations)
- **사용자 지정 도메인** 에서 [이 단계를 합니다.](#dns-entries-for-custom-domains)
- **Office 앱**, 이 [단계를 고려하세요.](#office-apps)
- **SharePoint Online** 에서 [이 단계를 합니다.](#sharepoint-online)
- **Exchange Online** 또는 **Exchange 하이브리드** 에서 이 [단계를 합니다.](#exchange-online)
- **비즈니스용 Skype Online** 에서 [이 단계를 진행합니다.](#skype-for-business-online)
- **Dynamics 365** 에서 [이 단계를 진행합니다.](#dynamics365)
- **Power BI**, 이 [단계를 합니다.](#power-bi)

- Azure AD Connect용 **Active Directory Federation Services에서** 다음 [단계를 수행합니다.](#active-directory-federation-services-ad-fs)
-  Office 365와 통합된 타사 서비스 또는 **LOB(LOB)** 앱은 이 [단계를 실행합니다.](#line-of-business-apps)
- 타사 MDM(모바일 장치 관리) 솔루션이 이 [단계를 합니다.](#mobile-device-management)
- **Office** 365 구독이 있는 Azure 서비스 에서 이 [단계를 진행합니다.](#microsoft-azure)

## <a name="general-tenant-migration-considerations"></a>일반적인 테넌트 마이그레이션 고려 사항

**다음에 적용됩니다.** 도이클란드 Microsoft 클라우드 인스턴스에서 Office 365를 사용하는 모든 고객

마이그레이션 중에 Office 365 테넌트 및 사용자 식별자가 보존됩니다. Azure AD 서비스 통화는 도이치클란드 Microsoft 클라우드에서 Office 365 전역 서비스로 리디렉션되고 Office 365 서비스로 투명하게 리디렉션됩니다.

- GDPR(일반 데이터 보호 규정) DSR(데이터 주체 요청)은 향후 요청을 위해 Azure 관리 포털에서 실행됩니다. 도이클란드 Microsoft 클라우드에 있는 레거시 또는 비 고객 진단 데이터는 30일 전 또는 30일 전에 삭제됩니다.
- Microsoft Authenticator를 사용하는 MFA(다단계 인증) 요청은 테넌트가 Office 365 서비스에 복사되는 동안 사용자 ObjectID(GUID)로 표시됩니다. 이러한 표시 동작에도 불구하고 MFA 요청은 예상대로 수행됩니다.  Office 365 서비스 끝점을 사용하여 활성화된 Microsoft Authenticator 계정에 UPN(사용자 계정 이름)이 표시됩니다.  도이치클라드 Microsoft 클라우드 끝점을 사용하여 추가된 계정은 사용자 ObjectID를 표시하지만 도이클란드 Microsoft 클라우드 및 Office 365 서비스 끝점에서 모두 사용할 수 있습니다.

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 마이그레이션 후 클라이언트를 다시 시작하고 클라이언트에서 로그인 및 로그인하는 방법을 사용자에게 알릴 준비를 합니다. | Office 클라이언트 라이선스는 마이그레이션 시 도이치클란드 Microsoft 클라우드에서 Office 365 서비스로 전환됩니다. 클라이언트는 Office 클라이언트에서 로그인한 후 유효한 새 라이선스를 선택 합니다. | 사용자의 Office 제품은 Office 365 서비스에서 라이선스를 새로 고쳐야 합니다. 라이선스를 새로 고치지 않은 경우 Office 제품에서 라이선스 유효성 검사 오류가 발생할 수 있습니다. |
| [Office 365](https://aka.ms/o365urls)서비스 URL 및 IP 주소에 대한 네트워크 연결을 확인합니다. | Office 365 서비스에 액세스하는 데 사용되는 고객이 호스팅하는 모든 클라이언트 및 서비스는 Office 365 전역 서비스 끝점에 액세스할 수 있어야 합니다. <br>사용자 또는 공동 작업 파트너가 Office 365 서비스 URL 및 IP 주소에 나열된 URL 및 IP 주소에 액세스하지 못하게 하는 방화벽 규칙이 있는 경우 [Office 365](https://aka.ms/o365urls) 전역 서비스 끝점에 대한 액세스를 허용하기 위해 방화벽 규칙을 변경해야 합니다.| 4단계 전에 이 단계를 수행하지 않은 경우 서비스 또는 클라이언트 소프트웨어 오류가 발생할 수 있습니다.  |
| 평가판 구독을 취소합니다. | 평가판 구독은 마이그레이션되지 않습니다. 유료 구독의 전송이 차단됩니다. | 취소 후 사용자가 액세스하는 경우 평가판 서비스가 만료되고 작동하지 않습니다. |
| 도이클란드 Microsoft 클라우드와 Office 365 전역 서비스 간의 라이선스 기능 차이를 분석합니다. | Office 365 서비스에는 현재 Microsoft 클라우드 도이치랜드에서 사용할 수 없는 추가 기능 및 서비스가 포함되어 있습니다. 구독을 전송하는 동안 사용자가 새 기능을 사용할 수 있습니다. | <ul><li> 도이클란드 Microsoft 클라우드 및 Office 365 전역 서비스에 대한 라이선스에서 제공하는 다양한 기능을 분석합니다. [Office 365 플랫폼 서비스 설명으로 시작하세요.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> 사용자 또는 사용자 변경 관리에 대한 영향을 제한하기 위해 Office 365 서비스의 새 기능을 처음에 사용하지 않도록 설정해야 하는지 여부를 결정하고 필요한 경우 사용자 라이선스 할당을 변경합니다. </li><li>Office 365 서비스에서 제공하는 새 서비스 및 기능에 대해 사용자 및 지원 센터 직원을 준비합니다. |
| 마이그레이션 중 [](https://docs.microsoft.com/microsoft-365/compliance/retention) 콘텐츠를 무단으로 삭제하는 것을 방지하는 조직 전체 보존 정책을 만들 수 있습니다.  |<ul><li>마이그레이션 중에 최종 사용자가 콘텐츠를 부수적으로 삭제하지 않도록 조직 전체 보존 정책을 사용하도록 설정할 수 있습니다. </li><li>보존은 필요하지는 않습니다. 마이그레이션 중에 언제든지 배치되는 보류는 예상대로 작동해야 하기 때문에 보존 정책을 보유하는 것은 백업 안전 메커니즘입니다. 동시에 일부 고객, 특히 보존이 우려되는 고객은 보존 정책을 사용할 수 없습니다.</li></ul>| 보존 정책 및 보존 레이블에 대해 자세히 설명에 [설명된 보존 정책을 적용합니다.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 서비스 또는 클라이언트 소프트웨어의 오류는 9단계 중 4단계 전에 수행되지 않은 경우 발생할 수 있습니다. </li></ul>|
|||||

## <a name="dns-entries-for-custom-domains"></a>사용자 지정 도메인에 대한 DNS 항목

<!-- before phase 9 -->

**적용 사항:** 자체 DNS 도메인 또는 Exchange Online에 대해 도메인을 사용하여 사용자 지정 _msoid_ CNAME을 설정한 고객

구성된 경우 _msoid_ CNAME은 Office 데스크톱 클라이언트(Microsoft 365 앱, Office 365 ProPlus, Office 2019, 2016, ...)를 사용하는 고객에게만 영향을 미치게 됩니다.

소유한 하나 또는 여러 DNS 네임스페이스에서 _msoid라는_ DNS CNAME을 설정한 경우 8단계가 끝날 때까지 CNAME을 제거해야 합니다. 8단계가 끝나기 전에 CNAME _msoid를_ 제거할 수 있습니다.

DNS 네임스페이스에 CNAME이 설정되어 있는지 확인하려면 아래 단계를  수행하고 contoso.com 도메인 이름으로 대체합니다.

```console
nslookup -querytype=CNAME msoid.contoso.com
```

명령줄에서 DNS 레코드를 반환하는 경우 도메인에서 _msoid_ CNAME을 제거합니다.

> [!NOTE]
> Exchange Online에 대해 사용자 지정 도메인을 사용하는 경우 DNS 호스팅 공급자에 대한 액세스 권한이 필요합니다. DNS 설정에 액세스하고 편집할 수 있는지, 마이그레이션 중에 DNS 레코드를 수정할 수 있는지 확인합니다.

## <a name="office-apps"></a>Office 앱

**적용 방법:** Office 앱을 사용하는 고객, 특히 Windows 클라이언트에서 <br>
**적용된 경우:** 9단계가 시작되기 전의 모든 시간

"독일" 지역으로 전환하는 Office 365 테넌트는 테넌트 마이그레이션이 9단계에 도달한 후 모든 사용자가 Office 365에서 종료하고, 로그인한 후 모든 Office 데스크톱 응용 프로그램(Word, Excel, PowerPoint, Outlook 등)과 비즈니스용 OneDrive 클라이언트에 대해 다시 로그인해야 합니다. 로그인하면 Office 서비스가 전역 Azure AD 서비스에서 새 인증 토큰을 얻을 수 있습니다.

이는 모든 클라이언트에 필요합니다. 원활한 마이그레이션 환경을 보장하기 위해 영향을 받는 모든 사용자에게 이 예정된 활동에 대해 미리 알리고 지시하는 것이 좋습니다.

관리되는 Windows 클라이언트를 사용하는 고객은 [OCCT(Office 클라이언트](https://github.com/microsoft/OCCT)컷오버 도구)를 사용하여 Windows 컴퓨터를 준비할 수 있습니다. OCCT는 테넌트가 마이그레이션의 9단계에 도달할 때까지 Windows 클라이언트에서 주기적으로 실행하도록 디자인되었습니다. 9단계에 도달하면 OCCT는 사용자 조작 없이 자동으로 필요한 모든 변경 작업을 수행하게 됩니다.

9단계 전에 OCCT를 Windows 클라이언트에 배포할 수 있습니다. OCCT에서 마이그레이션 환경을 지원해야 하는 경우 최대한 빨리 배포를 시작하여 최대 클라이언트 수를 설치하는 것이 좋습니다.

## <a name="active-directory-federation-services-ad-fs"></a>AD FS(Active Directory Federation Services)

<!-- before phase 4 -->

**적용 사항:** AD FS를 사용하여 Microsoft Office 365에 연결하는 사용자를 인증하는 고객<br>
**적용된 경우**: 4단계가 시작되기 전의 시간

[ADFS 마이그레이션 단계 읽기 및 적용](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**적용 사항:** SharePoint 2013 사내를 사용하는 고객<br>
**적용된 경우**: 4단계가 시작되기 전의 시간

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| SharePoint Online 마이그레이션 중에 SharePoint 2013 워크플로를 제한합니다. | 전환 전에 SharePoint 2013 워크플로를 줄이고 진행 중 워크플로를 완료합니다. | 비활성으로 인해 사용자에게 혼동을 주며 지원 센터 통화가 있을 수 있습니다. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**적용 사항:** Exchange Online 고객<br>
**적용된 경우:** 9단계가 종료되기 전의 시간

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Office 365 서비스로의 예정된 전환을 외부 파트너에게 알릴 수 있습니다. |  고객은 일정 및 가용성 주소 공간 구성 공유를 사용하도록 설정한 파트너에게 알려야 합니다(Office 365와 약속이 있는/약속이 있는 정보 공유 허용). Exchange Online 마이그레이션이 완료될 때 [Office 365 전](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) 세계 끝점을 사용하려면 가용성 구성을 전환해야 합니다. | 이 작업을 수행하지 못하면 이후 고객 마이그레이션 단계에서 서비스 또는 클라이언트 오류가 발생될 수 있습니다. |
| 필요한 IMAP4/POP3/SMTP 클라이언트 변경 내용을 사용자에게 알릴 수 있습니다. | 클라이언트 프로토콜 IMAP4, POP3, SMTP에 대한 Microsoft 클라우드 끝점에 대한 장치 연결이 있는 사용자는 클라이언트 장치를 수동으로 업데이트하여 Exchange Online 서버 이름으로 전환해야 [합니다.](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes) | 이러한 프로토콜의 사용자에게 이러한 종속성에 대해 미리 전달하고 이 마이그레이션 중에 Outlook 모바일 또는 웹용 Outlook을 사용하기 위해 전환해야 합니다. 클라이언트 끝점을 업데이트하지 못하면 사용자 사서함이 마이그레이션될 때 도이클란드 Microsoft 클라우드에 대한 클라이언트 연결 오류가 발생합니다. |
||||

### <a name="exchange-online-hybrid-customers"></a>Exchange Online 하이브리드 고객

**다음에 적용됩니다.** Exchange 서버가 있는 활성 Exchange 하이브리드 구성을 사용하는 모든 고객<br>
**적용된 경우:** 5단계가 시작되기 전의 시간

Exchange Online의 하이브리드 배포와 하이브리드 배포가 있는 엔터프라이즈 Exchange Server HCW(하이브리드 구성 마법사) 및 AAD Connect를 실행하여 하이브리드 설정을 유지 관리하고 설정할 수 있습니다. Exchange Online 하이브리드 관리자는 이 전환의 일부로  **HCW(하이브리드** 구성 마법사)를 여러 번 실행해야 합니다. 독일 Microsoft 클라우드에서 Office 365 Germany 지역으로 전환할 때 관리자는 Exchange 마이그레이션(5단계)이 시작되기 전에 "Office 365 Germany" 모드에서 HCW의 최신 빌드를 다시 실행해야 합니다. 그런 다음 5단계가 완료된 후 "Office 365 Worldwide" 모드에서 HCW를 다시 실행하여 Office 365 Germany 지역 설정으로 사내 배포를 완료합니다. 5단계에서 HCW 실행을 실행하면 안 되고 5단계가 완료될 때까지 HCW를 실행해야 합니다.
디렉터리 특성은 AAD Connect를 통해 Office 365와 Azure AD 간에 동기화됩니다. 

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Office 365 Germany 설정을 사용하여 HCW 다시 실행 <br><br> <i>Office 365 테넌트 마이그레이션이 시작했다는 메시지 센터 알림을 받은 후 바로 이 활동을 시작할 수 있습니다(1단계).</i>| 5단계 이전의 HCW(17.0.5378.0 이상)를 설치하고 다시 실행하면 Microsoft 클라우드 도이클랜드 사용자와 Office 365 Germany 지역으로 마이그레이션된 사용자와 함께 메일을 보내고 받을 준비가 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 됩니다. <p><li> In the HCW, for the list box below **My Office 365 organization is hosted by**, select Office **365 Germany.** | 5단계[Exchange 마이그레이션]이 시작되기 전에 이 작업을 완료하지 못하면 메일에 대한 NDRS가 해당 프레미스 Exchange 배포와 Office 365 간에 라우팅될 수 있습니다.  
| 공유 사서함 설정 보존 | 일부 하이브리드 고객은 Exchange Online 명령을 사용하여 클라우드 사용자 사서함을 '공유' 사서함으로 변환했습니다. 이 클라우드 사서함 구성은 사서함 및 로컬 Exchange Online 디렉터리에 기록됩니다. 그러나 AAD Connect를 통해 고객의 Active Directory에 다시 동기화되지는 않습니다. 그 결과 RemoteRecipientType 및 RemoteDisplayType 값의 Active Directory 표현과 사서함을 공유로 정의하는 Exchange Online 간의 불일치가 있습니다. <br><br> 고객은 , 또는 를 사용하여 모든 공유 사서함이 제대로 프로비전되었는지 `New-RemoteMailbox -Shared` `Enable-RemoteMailbox -Shared` `Set-RemoteMailbox -Shared` 확인합니다.  하이브리드 환경에서 사용자 사서함을 변환하는 방법에 대한 자세한 내용은 이 [참조를 참조합니다.](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox?view=o365-worldwide)| 5단계 [Exchange Online 마이그레이션] 전에 이 작업을 완료하지 못하면 공유 사서함에 대한 NDRS가 사용이 가능해지며, 이로 인해 사용이 허용되지 않은 사서함으로 다시 변환하고 영향을 받는 사서함에 대한 공유 액세스가 손실될 수 있습니다. [Exchange 하이브리드](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) 배포에서 디렉터리 동기화를 실행하면 공유 사서함이 예기치 않게 사용자 사서함으로 변환됩니다. Exchange Online 마이그레이션이 완료되기 전에 이 문제를 해결하지 못하게 되는 영향을 간략하게 설명합니다.  
||||

## <a name="skype-for-business-online"></a>비즈니스용 Skype Online

<!-- before phase 7 -->

**적용 사항:** 비즈니스용 Skype Online 고객<br>
**적용된 경우**: 7단계가 시작되기 전의 모든 시간

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 독일의 비즈니스용 Skype에 액세스하는 사용자를 위해 Teams 데스크톱 클라이언트를 배포합니다. | 마이그레이션은 공동 작업, 통화 및 채팅을 위해 비즈니스용 Skype 사용자를 Microsoft Teams로 이동합니다. Microsoft Teams 데스크톱 클라이언트를 배포하거나 지원되는 브라우저를 사용할 수 있도록 합니다. | 비활성화하면 Microsoft Teams 공동 작업 서비스를 사용할 수 없게 됩니다. |
| 마이그레이션 관련 DNS 변경 내용을 검토하고 준비합니다. | 비즈니스용 Skype Online에 대한 고객 소유 DNS 영역 변경 |<ul><li>DNS 레코드를 새로 고치기 위해 고객 소유 도메인 DNS 레코드의 TTL(Time-to-Live)을 5분으로 업데이트하는 것이 좋습니다. 그러나 이 DNS와 연결된 Microsoft 관리 컷오버 변경은 제공된 24시간 변경 기간 내에 언제든지 발생할 수 있습니다. </li><li>향후에는 서비스가 중단될 수 있습니다. 사용자는 비즈니스용 Skype에 로그인할 수 없습니다. Office 365 서비스의 마이그레이션된 Teams 환경으로 리디렉션됩니다. </li></ul>|
| Microsoft Teams로의 전환을 위한 최종 사용자 및 관리 교육 및 준비를 준비합니다. | 사용자 커뮤니케이션 및 준비를 계획하여 Skype에서 Teams로 전환하는 데 성공하세요. | <ul><li>클라이언트는 새 서비스와 해당 서비스가 Office 365 서비스로 전환된 후 사용하는 방법을 알고 있어야 합니다. </li><li>고객 베니티 도메인과 초기 도메인에 대해 DNS를 변경한 후 사용자는 비즈니스용 Skype에 로그인하고 이제 Teams로 마이그레이션된 것으로 표시됩니다. 또한 백그라운드에서 Teams용 데스크톱 클라이언트를 다운로드합니다. </li></ul>|
||||

## <a name="mobile-device-management"></a>모바일 디바이스 관리

<!-- before phase 5 -->
**다음에 적용됩니다.** 타사 MDM(모바일 장치 관리) 솔루션을 사용하는 고객<br>
**적용된 경우:** 5단계가 시작되기 전의 모든 시간

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| iOS 및 Android용 Microsoft Outlook에서 계정을 제거하고 다시 추가하는 사용자에 대한 최종 사용자 및 관리 교육을 준비합니다. | Microsoft 클라우드 도이치랜드의 사서함으로 구성된 iOS 및 Android용 Microsoft Outlook 계정을 제거하고 Outlook에 다시 추가해야 새 Office 365 서비스 구성을 제대로 동기화할 수 있습니다. | iOS 및 Android용 Microsoft Outlook 고객 | 이전에 도이치클란드 Microsoft 클라우드에 대해 구성된 Outlook 사서함은 새 Office 365 서비스 구성을 선택하지 않을 수 있으며, 이로 인해 다른 사용자 환경의 오류 및 성능이 저하될 수 있습니다. IT 관리자는 마이그레이션 후 로그인 또는 메일 동기화에 문제가 발생하는 경우 사용자에게 계정을 제거하고 iOS 및 Android용 Microsoft Outlook에 다시 추가하도록 지시하는 문서를 제공하는 것이 권장됩니다. |
| 마이그레이션 후 다시 구성해야 하는지 여부를 판단합니다. | MDM(모바일 장치 관리) 솔루션은 끝점을 `outlook.de` 대상으로 할 수 있습니다. 이 Office 365 서비스로 전환할 때 클라이언트 프로필은 Office 365 서비스 URL 으로 업데이트해야 `outlook.office365.com` 합니다. | Exchange Online 및 MDM 고객 | 끝점에 액세스할 수 있는 동안 클라이언트가 계속 작동하지만 도이치클라드 Microsoft 클라우드 끝점을 더 이상 사용할 수 없는 경우 `outlook.de` 실패합니다. |
|||||

## <a name="line-of-business-apps"></a>업무용 앱

**다음에 적용됩니다.** 도이치클라드 Microsoft 클라우드에서 제공하는 끝점과 함께 LOB(LOB) 앱을 사용하는 고객<br>
**적용된 경우:** 2단계가 완료된 후 9단계가 종료되기 전

Office 365와 통합된 타사 서비스 또는 LOB(LOB) 앱을 사용하는 경우 Microsoft 클라우드 도이치랜드 인스턴스에서 제공하는 끝점에 대한 종속성 문제를 해결해야 합니다. 예를 들어 LOB 앱이 에 연결하는 경우 끝점을 로 `https://graph.microsoft.de/` 변경해야 `https://graph.microsoft.com/` 합니다. 2단계 후에 Microsoft Office 365 전역 서비스의 끝점을 테넌트에서 사용할 수 있습니다.

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 마이그레이션 후 다시 구성해야 하는지 여부를 판단합니다. | Office 365와 통합되는 타사 서비스 및 응용 프로그램은 도이치랜드 Microsoft 클라우드 IP 주소 및 URL을 예상하여 코딩될 수 있습니다. | 필수 작업입니다. 비활성으로 인해 서비스 또는 클라이언트 소프트웨어가 실패할 수 있습니다. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**적용 사항:** Microsoft Dynamics 365를 사용하는 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Dynamics 365 샌드박스 구독의 경우 Dynamics SQL 인스턴스의 프로덕션 환경을 Microsoft 클라우드 도이클랜드의 Dynamics 365 구독에서 다운로드해야 합니다. 샌드박스 마이그레이션 전에 최신 프로덕션 백업을 샌드박스로 복원해야 합니다. | Dynamics 365를 마이그레이션하려면 고객이 샌드박스 환경을 최신 프로덕션 데이터베이스로 새로 고쳐야 합니다. | FastTrack 팀은 고객이 건조 실행을 수행하여 8.x에서 9.1.x로 버전 업그레이드의 유효성을 검사하는 데 도움을 주게 됩니다. |
||||

## <a name="power-bi"></a>Power BI

**적용 사항:** Power BI를 사용하는 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Power BI Microsoft 클라우드 도이클랜드에서 Office 365 서비스로 마이그레이션되지 않는 Power BI 구독에서 개체 제거 | Power BI 서비스를 마이그레이션하려면 데이터 집합 및 대시보드와 같은 특정 아티팩트를 삭제하기 위한 고객 작업이 필요합니다. | <ul><li>관리자는 구독에서 다음 항목을 제거해야 할 수 있습니다. </li><li>Real-Time 데이터 집합(예: 스트리밍 또는 푸시 데이터 집합) </li><li>Power BI 사내 데이터 게이트웨이 구성 및 데이터 원본 </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

도이치랜드 Microsoft 클라우드 인스턴스에서 Office 365 및 Microsoft Azure에 대해 동일한 Azure Active Directory ID 파티션을 사용하는 경우 Microsoft Azure 서비스의 고객 기반 마이그레이션을 준비하고 있는지 확인합니다.

> [!NOTE]
> Office 365 테넌트가 마이그레이션 단계 3에 도달하기 전에 Microsoft Azure 서비스의 마이그레이션을 시작하지 말고 마이그레이션 8단계가 완료되기 전에 완료해야 합니다.

Office 365 및 Azure 리소스(예: 네트워킹, 계산 및 저장소)를 사용하는 고객은 Office 365 서비스 인스턴스로 리소스 마이그레이션을 수행하게 됩니다. 이 마이그레이션은 고객의 책임입니다. 메시지 센터 게시물에 시작 신호가 표시됩니다. Office 365 서비스 환경에서 Azure AD 조직을 완료하기 전에 마이그레이션을 완료해야 합니다. Azure 마이그레이션의 경우 Azure 마이그레이션 플레이북, Azure Germany에 대한 마이그레이션 [지침 개요를 참조하세요.](https://docs.microsoft.com/azure/germany/germany-migration-main)

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 사용하려는 Azure 서비스를 결정하고 파트너와 협력하여 독일에서 Office 365 서비스 테넌트로의 향후 마이그레이션을 준비합니다. Azure 마이그레이션 [플레이북에 설명된 단계를 따릅니다.](/azure/germany/germany-migration-main) |<ul><li>Azure 리소스 마이그레이션은 고객의 책임이 있으며, 정해진 단계에 따라 수동으로 노력해야 합니다. 조직에서 사용하려는 서비스를 이해하는 것은 Azure 서비스의 성공적인 마이그레이션을 위한 핵심입니다. </li><li> 동일한 ID 파티션(조직)에 Azure 구독이 있는 Office 365 Germany 고객은 구독 및 서비스 마이그레이션을 시작할 수 있는 경우 Microsoft에서 정한 순서를 따라야 합니다.</li></ul>|<ul><li>고객은 여러 Azure 구독을 사용할 수 있으며 각 구독에는 인프라, 서비스 및 플랫폼 구성 요소가 포함됩니다. </li><li> 관리자는 이 마이그레이션 이벤트의 일부로 신속한 마이그레이션 및 유효성 검사가 가능하도록 구독 및 관련자를 파악해야 합니다. </li><li>이러한 구독 및 정해진 시간 내에 Azure 구성 요소의 마이그레이션을 성공적으로 완료하지 못하면 Office 및 Azure AD가 Office 365 서비스로의 전환 완료에 영향을 미치며 데이터 손실이 발생하게 될 수 있습니다. </li><li> 메시지 센터 알림은 고객이 주도하는 마이그레이션을 시작할 수 있는 지점을 신호합니다. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>추가 정보

시작:

- [독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 마이그레이션 프로그램 정보](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams 업그레이드 시작하기](/microsoftteams/upgrade-start-here)
