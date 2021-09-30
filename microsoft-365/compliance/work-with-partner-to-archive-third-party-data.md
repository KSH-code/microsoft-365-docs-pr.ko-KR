---
title: 타사 데이터를 저장하는 데 파트너와 협력
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Salesforce Chatter, Yahoo Messenger 또는 Yammer.
ms.openlocfilehash: 7e82f114138a8f1f8ac9eb4563ce1434e6c26167
ms.sourcegitcommit: f9e038dd8420e7af2d1b0244d3567b376475c641
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011239"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>타사 데이터를 저장하는 데 파트너와 협력

Microsoft 파트너와 협력하여 타사 데이터 원본에서 데이터 원본으로 데이터를 가져와 보관할 수 Microsoft 365. 파트너는 타사 데이터 원본에서 항목을 추출하여 정기적으로 해당 항목을 가져오도록 구성된 사용자 지정 커넥터를 제공할 수 있습니다. 파트너 커넥터는 데이터 원본에서 전자 메일 메시지 형식으로 항목의 내용을 변환한 다음 사서함에 항목을 저장합니다. 타사 데이터를 가져온 후 소송 보존Microsoft 365 eDiscovery, In-Place 보관, 감사 및 보존 정책과 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.

> [!IMPORTANT]
> 이 [문서의](communication-compliance.md) 통신 준수 Microsoft 365 파트너 커넥터가 가져온 타사 데이터에는 적용할 수 없습니다.

다음은 타사 데이터를 가져오기 위해 Microsoft 파트너와 협력하는 데 필요한 프로세스 및 단계에 대한 개요입니다.

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[2단계: 타사 데이터 사서함 만들기 및 구성](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[4단계: 파트너에게 정보 제공](#step-4-provide-your-partner-with-information)

[5단계: 타사 데이터 커넥터를 등록합니다Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>타사 데이터 가져오기 프로세스의 작동 방식

다음 그림 및 설명은 파트너와 함께 작업할 때 타사 데이터 가져오기 프로세스가 작동하는 방식에 대해 설명합니다.

![타사 데이터 가져오기 프로세스의 작동 방식](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)

1. 고객은 선택한 파트너와 협력하여 타사 데이터 원본에서 항목을 추출한 다음 해당 항목을 가져오는 커넥터를 구성하여 Microsoft 365.

2. 파트너 커넥터는 타사 API(예약 또는 구성에 따라)를 통해 타사 데이터 원본에 연결하고 데이터 원본에서 항목을 추출합니다. 파트너 커넥터는 항목의 내용을 전자 메일 메시지 형식으로 변환합니다. 메시지 형식에 [대한 설명은 추가](#more-information) 정보 섹션을 참조하세요.

3. 파트너 커넥터는 잘 알려진 끝점을 통해 Microsoft 365 EWS(Exchange 웹 서비스)를 사용하여 Exchange Azure 서비스에 연결합니다.

4. 항목은 특정 사용자의 사서함 또는 "범용" 타사 데이터 사서함으로 가져오기됩니다. 항목을 특정 사용자 사서함으로 가져올지 또는 타사 데이터 사서함으로 가져올지는 다음 기준을 기반으로 합니다.

   1. 사용자 계정에 해당하는 사용자 ID가 있는 **항목:** 파트너 커넥터가 타사 데이터 원본에 있는 항목의 사용자 ID를 Microsoft 365 사용자의 복구 가능한 항목 폴더에 있는 제거  폴더에 복사됩니다. 제거 폴더의 항목에는 액세스할 수 없습니다. 그러나 eDiscovery 도구를 사용하여 제거 폴더의 항목을 검색할 수 있습니다.

   1. 사용자 계정에 해당하는 사용자 ID가 없는 **항목:** 파트너 커넥터에서 항목의 사용자 ID를 특정 사용자 ID에 매핑할 수 없는 경우  항목이 타사 데이터 사서함의 받은 편지함 폴더에 복사됩니다. 받은 편지함에 항목을 가져올 수 있으면 관리자 또는 조직의 누군가가 타사 사서함에 로그인하여 이러한 항목을 보고 관리할 수 있으며 파트너 커넥터 구성을 조정해야 하는지 확인할 수 있습니다.

## <a name="step-1-find-a-third-party-data-partner"></a>1단계: 타사 데이터 파트너 찾기

타사 데이터를 보관하는 주요 구성 요소는 Microsoft 365 데이터 원본에서 데이터를 캡처하여 데이터 원본으로 가져오는 전문 Microsoft 파트너를 찾아서 작업하는 Microsoft 365. 데이터를 가져온 후 조직의 다른 Microsoft 데이터(예: 조직의 다른 Microsoft 데이터와 함께 보관 및 보존할 수 Exchange 및 SharePoint 및 문서)비즈니스용 OneDrive. 파트너는 조직의 타사 데이터 원본(예: BlackBerry, Facebook, Google+, Thomson Reuters, Twitter 및 YouTube)에서 데이터를 추출하고 해당 데이터를 전자 메일 메시지로 Exchange 사서함으로 가져오는 Microsoft 365 API에 전달합니다.

다음 섹션에서는 타사 데이터를 보관하기 위한 프로그램에 참여하는 Microsoft 파트너(및 해당 파트너가 지원하는 타사 데이터 원본)를 Microsoft 365.

[17a-4 LLC](#17a-4-llc)

[ArchiveSocial](#archivesocial)

[Veritas](#veritas)

[OpenText](#opentext)

[Smarsh](#smarsh)

[Verba](#verba)

### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC는](https://www.17a-4.com) 다음과 같은 타사 데이터 원본을 지원합니다.

- BlackBerry

- Bloomberg Data Streams

- Cisco Jabber

- FactSet

- HipChat

- InvestEdge

- LivePerson

- MessageLabs Data Streams

- OpenText

- Oracle/ATG 'click-to-call' Live Help

- Pivot IMTRADER

- Microsoft SharePoint

- MindAlign

- Sitrion One(Newsgator)

- 비즈니스용 Skype(Lync/OCS)

- 비즈니스용 Skype Online(Lync Online)

- SQL 데이터베이스

- 스쿼워커

- Thomson Reuters Eikon Messenger

### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial은](https://www.archivesocial.com) 다음과 같은 타사 데이터 원본을 지원합니다.

- Facebook

- Flickr

- 인스 타마

- LinkedIn

- Pinterest

- Twitter

- YouTube

- Vimeo

### <a name="veritas"></a>Veritas

[Veritas는](https://www.globanet.com) 다음과 같은 타사 데이터 원본을 지원합니다.

- AOL with Pivot Client 

- BlackBerry Call Logs(v5, v10, v12)

- BlackBerry Messenger(v5, v10, v12)

- BlackBerry PIN(v5, v10, v12)

- BlackBerry SMS(v5, v10, v12)

- Bloomberg Chat

- Bloomberg Mail

- Box

- CipherCloud for Salesforce Chatter

- Cisco IM &amp; Presence Server(v10, v10.5.1 SU1, v11.0, v11.5 SU2)

- Cisco Webex Teams

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- 사용자 지정으로분할된 텍스트 파일

- 사용자 지정 XML 파일

- Facebook(Pages)

- 팩트 집합

- FXConnect

- ICE Chat/YellowJacket

- Jive

- Macgregor XIP

- Microsoft Exchange Server

- Microsoft 비즈니스용 OneDrive

- Microsoft Teams

- Microsoft Yammer

- Mobile Guard

- Pivot

- Salesforce Chatter

- 비즈니스용 Skype Online

- 비즈니스용 Skype, 버전 2007 R2 - 2016(온-프레미스)

- Slack Enterprise Grid

- Symphony

- Thomson Reuters Eikon

- Thomson Reuters Messenger

- Thomson Reuters Dealings 3000 / FX Trading

- Twitter

- UBS Chat

- YouTube

### <a name="opentext"></a>OpenText

[OpenText는](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) 다음과 같은 타사 데이터 원본을 지원합니다.

- Axs Encrypted

- Axs Exchange

- Axs Local Archive

- Axs PlaceHolder

- Axs Signed

- Bloomberg

- Thomson Reuters

### <a name="smarsh"></a>Smarsh

[Smarsh는](https://www.smarsh.com) 다음과 같은 타사 데이터 원본을 지원합니다.

- AIM

- American Idol

- Apple Juice

- AOL with Pivot client

- Ares

- Bazaar Voice

- Bear Share

- Bit Torrent

- BlackBerry Call Logs(v5, v10, v12)

- BlackBerry Messenger(v5, v10, v12)

- BlackBerry PIN(v5, v10, v12)

- BlackBerry SMS(v5, v10, v12)

- Bloomberg Mail

- CellTrust

- Chat Import

- Chat Real Time Logging and Policy

- Chatter

- Cisco IM &amp; Presence Server(v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)

- Cisco Unified Presence Server(v8.6.3, v8.6.4, v8.6.5)

- Collaboration Import

- Collaboration Real Time Logging

- Direct Connect

- Facebook

- FactSet

- FastTrack

- Gnutella

- Google+

- GoToMyPC

- Hopster

- HubConnex

- IBM Connections(v3.0.1, v4.0, v4.5, v4.5 CR3, v5)

- IBM Connections Chat Cloud

- IBM Connections Social Cloud

- IBM SameTime Advanced 8.5.2 IFR1

- IBM SameTime Communicate 9.0

- IBM SameTime Community(v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)

- IBM SameTime Complete 9.0

- IBM SameTime Conference 9.0

- IBM SameTime Meeting 8.5.2 IFR1

- ICE/YellowJacket

- IM Import

- IM Real Time Logging and Policy

- Indii Messenger

- Instant Bloomberg

- IRC

- Jive

- Jive 6 Real Time Logging(v6, v7)

- Jive Import

- JXTA

- LinkedIn

- Microsoft Lync(2010, 2013)

- MFTP

- Microsoft Lync 2013 Voice

- Microsoft SharePoint(2010, 2013)

- Microsoft SharePoint Online

- Microsoft UC(Unified Communications)

- MindAlign

- Mobile Guard

- MSN

- My Space

- NEONetwork

- Microsoft 365 Lync 전용

- Microsoft 365 공유 IM

- Pinterest

- Pivot

- QQ

- 비즈니스용 Skype 2015

- SoftEther

- Symphony

- Thomson Reuters Eikon

- Thomson Reuters Messenger

- Tor

- TTT

- Twitter

- WinMX

- Winny

- Yahoo

- Yammer

- YouTube


### <a name="verba"></a>Verba

[Verba는](https://www.verba.com) 다음과 같은 타사 데이터 원본을 지원합니다.

- Avaya Aura Video

- Avaya Aura Voice

- Avtec Radio

- Bosch/Telex Radio

- BroadSoft Video

- BroadSoft Voice

- Centile Voice

- Cisco Jabber IM

- Cisco UC Video

- Cisco UC Voice

- Cisco UCCX/UCCE 비디오

- Cisco UCCX/UCCE Voice

- ESChat Radio

- Geoman Contact Expert

- IP Trade Voice

- Luware LUCS Contact Center

- Microsoft UC(Unified Communications)

- Mitel MiContact Center for Lync(prairieFyre)

- Oracle/Acme Packet Session Border Controller Video

- Oracle/Acme Packet Session Border Controller Voice

- Singtel Mobile Voice

- SIPREC Video

-  SIPREC Voice

- 비즈니스용 Skype/Lync IM

- 비즈니스용 Skype/Lync Video

- 비즈니스용 Skype/Lync Voice

- Speakerbus Voice

- Standard SIP/H.323 Video

- Standard SIP/H.323 Voice

- Truphone Voice

- TwistedPair Radio

- Windows 데스크톱 컴퓨터 화면

## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a>2단계: Microsoft 365에서 타사 데이터 사서함 만들기 및 구성

Microsoft 365로 데이터를 가져오기 위한 타사 데이터 사서함을 만들고 구성하는 단계는 다음과 같습니다. 앞서 설명한 것 처럼 파트너 커넥터에서 항목의 사용자 ID를 사용자 계정에 매핑할 수 없는 경우 항목이 이 사서함으로 가져오기됩니다.

 **Microsoft 365 관리 센터에서 이러한 작업 완료**

1. 사용자 계정을 만들고 Exchange Online 계획 2 라이선스를 할당합니다. [Microsoft 365에 사용자 추가를 참조합니다.](../admin/add-users/add-users.md) 계획 2 라이선스는 사서함을 소송 자료 보관에 두거나 저장소 할당량 최대 1.5 TB가 있는 보관 사서함을 사용하도록 설정하는 데 필요합니다.

2. 타사 데이터 사서함의 사용자 계정을 Microsoft 365의 **Exchange 관리자** 역할에 추가합니다. [Microsoft 365에서](../admin/add-users/assign-admin-roles.md)관리자 역할 할당을 참조하세요.

    > [!TIP]
    > 이 사용자 계정의 자격 증명을 기록해 둡니다. 4단계에서 설명한 것처럼 파트너에게 제공해야 합니다.

 **Exchange 관리 센터에서 이러한 작업 완료**

1. 조직의 주소 책 및 기타 주소 목록에서 타사 데이터 사서함을 숨기기 사용자 [사서함 관리를 참조합니다.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 또는 다음 PowerShell 명령을 실행할 수 있습니다.

    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 관리자 또는 준수 관리자가 Outlook 데스크톱 클라이언트에서 타사 데이터 사서함을 열 수 있도록 타사 데이터 사서함에 **FullAccess** 권한을 할당합니다. 받는 [사람에 대한 사용 권한 관리를 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=692104)

3. 타사 데이터 사서함에 대해 다음 준수 관련 기능을 사용하도록 설정하십시오.

    - 보관 사서함을 사용하도록 설정 보관 [사서함 사용 및](enable-archive-mailboxes.md) 자동 확장 보관 사용 [을 참조합니다.](enable-autoexpanding-archiving.md) 이렇게 하면 타사 데이터 항목을 보관 사서함으로 이동하는 보관 정책을 설정하여 기본 사서함의 저장소 공간을 자유롭게 사용할 수 있습니다. 이렇게 하면 타사 데이터에 대해 최대 1.5 TB의 저장소를 사용할 수 있습니다.

    - 타사 데이터 사서함에 소송 보존을 적용합니다. 보안 및 준수 센터에서 Microsoft 365 보존 정책을 적용할 수 있습니다. 이 사서함을 보류하면 타사 데이터 항목이 보존되고(무기한 또는 지정된 기간 동안) 사서함에서 제거되지 않습니다. 다음 항목 중 하나를 참조하세요.

      - [사서함을 소송 자료 보존으로 설정](./create-a-litigation-hold.md)

      - [보존 정책 및 보존 레이블에 대해 알아보기](retention.md)

    - 타사 데이터 사서함에 대한 소유자, 대리인 및 관리자 액세스에 대해 사서함 감사 로깅을 사용하도록 설정 사서함 [감사 사용 을 참조합니다.](enable-mailbox-auditing.md) 이렇게 하면 타사 데이터 사서함에 액세스할 수 있는 사용자가 수행한 모든 활동을 감사할 수 있습니다.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>3단계: 타사 데이터에 대한 사용자 사서함 구성

다음 단계는 타사 데이터를 지원하도록 사용자 사서함을 구성하는 것입니다. Exchange 관리 센터를 사용하여 또는 해당 cmdlet을 사용하여 이러한 Windows PowerShell 완료합니다.

1. 각 사용자에 대해 보관 사서함을 사용하도록 설정 보관 [사서함 사용 및](enable-archive-mailboxes.md) 자동 확장 보관 사용 [을 참조합니다.](enable-autoexpanding-archiving.md)

2. 사용자 사서함에 소송 보존을 적용하거나 Microsoft 365 보존 정책을 적용합니다. 다음 항목 중 하나를 참조하세요.

    - [사서함을 소송 자료 보존으로 설정](./create-a-litigation-hold.md)

    - [보존 정책 및 보존 레이블에 대해 알아보기](retention.md)

    앞서 언급한 것처럼 사서함을 보존하면 타사 데이터 원본의 항목을 보존하는 기간을 설정하거나 항목을 무기한 보존하도록 선택할 수 있습니다.

## <a name="step-4-provide-your-partner-with-information"></a>4단계: 파트너에게 정보 제공

마지막 단계는 파트너가 사용자 사서함 및 타사 데이터 사서함으로 데이터를 가져오도록 조직에 연결하도록 커넥터를 구성할 수 있도록 파트너에게 다음 정보를 제공하는 것입니다.

- Microsoft 365의 Azure 서비스에 연결하는 데 사용되는 끝점:

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 2단계에서 만든 타사 데이터 사서함의 로그인 자격 증명(Microsoft 365 사용자 ID 및 암호)입니다. 이러한 자격 증명은 파트너 커넥터가 항목을 액세스하고 사용자 사서함 및 타사 데이터 사서함으로 가져올 수 있도록 하는 데 필요합니다.

## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>5단계: Azure Active Directory에 타사 데이터 커넥터 등록

2018년 9월 30일부터 Microsoft 365의 Azure 서비스는 Exchange Online의 최신 인증을 사용하여 조직에 연결하여 데이터를 가져오는 타사 데이터 커넥터를 인증합니다. 이러한 변경의 이유는 최신 인증이 Azure 서비스에 연결하기 위해 앞서 설명한 끝점을 사용하는 타사 커넥터에 대한 허용 목록을 기반으로 했던 현재 방법보다 더 많은 보안을 제공하기 위한 것입니다.

타사 데이터 커넥터가 새로운 최신 인증 방법을 사용하여 Microsoft 365에 연결할 수 있도록 설정하려면 조직의 관리자가 커넥터를 Azure Active Directory에서 신뢰할 수 있는 서비스 응용 프로그램으로 등록하는 데 동의해야 합니다. 이 수행은 커넥터가 Azure Active Directory에서 조직의 데이터에 액세스할 수 있도록 허용하는 권한 요청을 수락하여 수행됩니다. 이 요청을 수락하면 타사 데이터 커넥터가 Azure Active Directory에 엔터프라이즈 응용 프로그램으로 추가된 후 서비스 사용자로 표시됩니다. 동의 프로세스에 대한 자세한 내용은 테넌트 관리자 동의 [를 참조하세요.](/skype-sdk/trusted-application-api/docs/tenantadminconsent)

커넥터 등록 요청을 액세스하고 수락하는 단계는 다음과 같습니다.

1. 이 [페이지로 이동하여](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 전역 관리자의 자격 증명을 사용하여 로그인합니다.

   다음 대화 상자가 표시됩니다. 캐터를 확장하여 커넥터에 할당할 사용 권한을 검토할 수 있습니다.

   ![사용 권한 요청 대화 상자가 표시됩니다.](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. **Accept(동의함)** 를 클릭합니다.

요청을 수락하면 [Azure Portal이](https://portal.azure.com) 표시됩니다. 조직의 응용 프로그램 목록을 보려면 **Azure Active Directory Enterprise** 응용 프로그램  >  **을 클릭합니다.** Microsoft 365 타사 데이터 커넥터가 엔터프라이즈 응용 프로그램 **블레이드에 나열됩니다.**

> [!IMPORTANT]
> 2018년 9월 30일 이후에는 Azure Active Directory에 타사 데이터 커넥터를 등록하지 않은 경우 더 이상 타사 데이터를 조직의 사서함으로 가져오지 않습니다. 참고 기존 타사 데이터 커넥터(2018년 9월 30일 전에 만든 커넥터)도 5단계의 절차를 수행하여 Azure Active Directory에 등록해야 합니다.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>타사 데이터 커넥터에 대한 동의 해지

조직에서 Azure Active Directory에 타사 데이터 커넥터를 등록하기 위해 사용 권한 요청에 동의하면 조직에서 해당 동의를 취소할 수 있습니다. 그러나 커넥터에 대한 동의를 해지하면 타사 데이터 원본의 데이터를 더 이상 Microsoft 365로 가져올 수 없습니다.

타사 데이터 커넥터에 대한 동의를 해지하려면 Azure Portal의 엔터프라이즈 응용 프로그램 블레이드를 사용하여 또는  Microsoft 365 PowerShell에서 [Remove-MsolServicePrincipal을](/powershell/module/msonline/remove-msolserviceprincipal) 사용하여 Azure Active Directory에서 해당 서비스 계정을 삭제하여 응용 프로그램을 삭제할 수 있습니다. Azure Active Directory PowerShell에서 [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet을 사용할 수 있습니다.

## <a name="more-information"></a>추가 정보

- 앞서 설명한 것처럼 타사 데이터 원본의 항목을 Exchange 사서함에 전자 메일 메시지로 가져옵니다. 파트너 커넥터는 Microsoft 365 API에 필요한 Schema를 사용하여 항목을 가져올 수 있습니다. 다음 표에서는 타사 데이터 원본 항목을 Exchange 사서함에 전자 메일 메시지로 가져온 후, 타사 데이터 원본 항목에 대한 메시지 속성을 설명합니다. 또한 이 표는 메시지 속성이 필수인지 여부를 나타냅니다. 필수 속성은 채워야 합니다. 필수 속성이 없는 항목은 Microsoft 365로 가져오지 않습니다. 가져오기 프로세스에서는 항목을 가져오지 않은 이유와 누락된 속성을 설명하는 오류 메시지가 반환됩니다.<br/><br/>

    |**메시지 속성**|**필수 여부**|**설명**|**예제 값**|
    |:-----|:-----|:-----|:-----|
    |**보낸 사람** <br/> |예  <br/> |타사 데이터 원본 항목을 처음 만들었거나 보낸 사람입니다. 파트너 커넥터는 원본 항목(예: Twitter 핸들)의 사용자 ID를 모든 참가자(FROM 및 TO 필드의 사용자)에 대한 사용자 계정에 매핑하려고 시도합니다. 메시지 복사본을 모든 참가자의 사서함으로 가져옵니다. 항목의 참가자 중 사용자 계정에 매핑할 수 없는 경우 항목은 해당 항목의 타사 보관 사서함으로 Microsoft 365.  <br/> <br/> 항목의 보낸 사람으로 식별된 참가자는 항목을 가져오는 조직에서 활성 사서함을 가져와야 합니다. 보낸 사람에게 활성 사서함이 없으면 다음과 같은 오류가 반환됩니다.<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**받는 사람** <br/> |예  <br/> |데이터 원본의 항목을 받은 사람입니다(해당되는 경우).  <br/> | `bob@contoso.com` <br/> |
    |**제목** <br/> |아니요  <br/> |원본 항목의 제목입니다.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |예  <br/> |항목을 처음 만들거나 고객 데이터 원본에 게시한 날짜입니다. 예를 들어 Twitter 메시지가 트윗된 날짜입니다.  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |아니요  <br/> |메시지 또는 게시물의 콘텐츠입니다. 일부 데이터 원본의 경우 이 속성의 콘텐츠는 **SUBJECT** 속성의 콘텐츠와 같을 수 있습니다. 가져오기 프로세스 중에 파트너 커넥터는 콘텐츠 원본에서 최대한 완전한 고화성을 유지하려고 시도합니다. 가능한 경우 원본 항목의 본문에서 가져온 파일, 그래픽 또는 기타 콘텐츠가 이 속성에 포함됩니다. 그렇지 않은 경우 원본 항목의 콘텐츠가 **ATTACHMENT** 속성에 포함됩니다. 이 속성의 내용은 파트너 커넥터 및 원본 플랫폼의 기능에 따라 다를 수 있습니다.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**첨부 파일** <br/> |아니요  <br/> |데이터 원본의 항목(예: Twitter의 트윗 또는 인스턴트 메시징 대화)에 첨부 파일이 첨부되거나 이미지가 포함된 경우 파트너 연결은 먼저 **BODY** 속성에 첨부 파일을 포함하려고 시도합니다. If that isn't possible, then it's added to the ** ATTACHMENT ** property. 첨부 파일의 다른 예로는 Facebook의 좋아요, 콘텐츠 원본의 메타데이터, 메시지 또는 게시물에 대한 응답이 있습니다.  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |예  <br/> | 파트너 커넥터가 만들어서 채우는 다중 값 속성입니다. 이 속성의 형식은  `IPM.NOTE.Source.Event` 입니다. (이 속성은 로 시작해야  `IPM.NOTE` 합니다. 이 형식은 메시지 클래스에 대한  `IPM.NOTE.X` 형식과 유사합니다.) 이 속성에는 다음 정보가 포함됩니다.  <br/><br/>`Source`: 타사 데이터 원본을 나타냅니다. 예: Twitter, Facebook 또는 BlackBerry.  <br/> <br/>  `Event`: 항목을 생성한 타사 데이터 원본에서 수행된 활동의 유형을 나타냅니다. 예를 들어 Twitter의 트윗 또는 Facebook의 게시물입니다. 이벤트는 데이터 원본과 관련이 있습니다.  <br/> <br/>  이 속성의 한 가지 목적은 항목이 시작된 데이터 원본이나 이벤트의 유형에 따라 특정 항목을 필터링하는 것입니다. 예를 들어 eDiscovery 검색에서 특정 사용자가 게시한 모든 트윗을 찾는 검색 쿼리를 만들 수 있습니다.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |

- 항목이 사서함에 있는 사서함으로 Microsoft 365 HTTP 응답의 일부로 고유 식별자가 호출자에 반환됩니다. 라는 이 식별자는 파트너가 항목의 종단을 추적하기 위해 후속 문제 해결을 위해 사용할  `x-IngestionCorrelationID` 수 있습니다. 파트너는 이 정보를 수집하고 적절하게 기록해두는 것이 좋습니다. 이 식별자를 나타내는 HTTP 응답의 예는 다음과 같습니다.

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT
    ```

- 보안 및 준수 센터의 콘텐츠 검색 도구를 사용하여 타사 데이터 원본에서 사서함으로 가져온 항목을 검색할 수 있습니다. 이러한 가져온 항목을 구체적으로 검색하기 위해 콘텐츠 검색의 키워드 상자에 다음 메시지 속성-값 쌍을 사용할 수 있습니다.

  - **`kind:externaldata`**: 이 속성-값 쌍을 사용하여 모든 타사 데이터 형식을 검색합니다. 예를 들어 타사 데이터 원본에서 가져온 항목을 검색하고 가져온 항목의 Subject 속성에 "contoso"라는 단어가 포함된 항목을 검색하기 위해 키워드 쿼리를  `kind:externaldata AND subject:contoso` 사용합니다.

  - **`itemclass:ipm.externaldata.<third-party data type>`**: 이 속성-값 쌍을 사용하여 지정한 형식의 타사 데이터만 검색할 수 있습니다. 예를 들어 Subject 속성에 단어 "contoso"가 포함된 Facebook 데이터만 검색하기 위해 키워드 쿼리를  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 사용합니다.

  속성에 대해 타사 데이터 형식에 사용할 값의 전체 목록은 `itemclass` Use Content Search to search [third-party data that was imported to Microsoft 365.](use-content-search-to-search-third-party-data-that-was-imported.md)

   콘텐츠 검색 사용 및 키워드 검색 쿼리를 만드는 방법에 대한 자세한 내용은 다음을 참조하세요.

  - [콘텐츠 검색](content-search.md)

  - [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)