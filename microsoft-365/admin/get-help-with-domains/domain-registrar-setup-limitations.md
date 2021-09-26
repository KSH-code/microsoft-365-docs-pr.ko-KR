---
title: 설정 제한이 있는 도메인 등록 기관
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- MET150
ROBOTS: NOINDEX
description: 일부 도메인 등록 기관은 제한된 서비스를 제공하므로 일부 Microsoft 기능은 일부 도메인에서 작동하지 않습니다.
ms.openlocfilehash: 7fe6b047773e47964b5a00728b8c1443bdeef36e
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774595"
---
# <a name="domain-registrars-with-setup-limitations"></a>설정 제한이 있는 도메인 등록 기관

[DNSMadeEasy에서 Microsoft용 DNS 레코드 만들기](#create-dns-records-at-dnsmadeeasy-for-microsoft)\
[easyDNS에서 Microsoft용 DNS 레코드 만들기](#create-dns-records-at-easydns-for-microsoft)\
[Freenom에서 Microsoft용 DNS 레코드 만들기](#create-dns-records-at-freenom-for-microsoft)\
[MyDomain에서 Microsoft용 DNS 레코드 만들기](#create-dns-records-at-mydomain-for-microsoft)\
[Windows 기반 DNS를 사용하여 Microsoft용 DNS 레코드 만들기](#create-dns-records-for-microsoft-using-windows-based-dns)\
[도메인이 Google에서 관리되는 경우 DNS 레코드 만들기](#create-dns-records-when-your-domain-is-managed-by-google-enom)\
[1&1 IONOS에서 Microsoft용 DNS 레코드 만들기](#create-dns-records-at-11-ionos-for-microsoft)

일부 도메인 등록 기관에는 상당한 서비스 제한이 있으므로 일부 Microsoft 기능은 일부 도메인에서 작동하지 않습니다. 일부 등록 기관에 대한 특정 제한 사항은 이 문서에서 확인할 수 있습니다. 

## <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>DNSMadeEasy에서 Microsoft용 DNS 레코드 만들기

DNSMadeEasy 계정의 경우 추가한 도메인은 별도의 도메인 등록 기관에서 구매한 것입니다. DNSMadeEasy는 도메인 등록 서비스를 제공하지 않습니다. DNSMadeEasy에서 로그인하고 DNS 레코드를 만드는 기능은 소유권의 충분한 증명이 됩니다.

## <a name="create-dns-records-at-easydns-for-microsoft"></a>easyDNS에서 Microsoft용 DNS 레코드 만들기

SRV 레코드는 현재 easyDNS 서비스 패키지에서 사용할 수 없습니다. Teams에 필요한 SRV 레코드를 추가하려면 easyDNS를 사용하여 더 높은 서비스 수준으로 업그레이드해야 할 수 있습니다.

## <a name="create-dns-records-at-freenom-for-microsoft"></a>Freenom에서 Microsoft용 DNS 레코드 만들기

Freenom 웹 사이트에서는 SRV 레코드 추가를 지원하지 않으므로 여러 Teams 및 전자 메일 기능이 작동하지 않습니다. 어떤 Microsoft 플랜을 사용하든 간에 상당한 서비스 제한이 있으며 다른 DNS 호스팅 공급자로 전환하는 것이 좋을 수 있습니다.

## <a name="create-dns-records-at-mydomain-for-microsoft"></a>MyDomain에서 Microsoft용 DNS 레코드 만들기

MyDomain 웹 사이트는 SRV 레코드를 지원하지 않으므로 여러 Teams 및 전자 메일 기능이 작동하지 않습니다. 어떤 Microsoft 플랜을 사용하든, MyDomain에서 DNS 레코드를 관리하는 경우 상당한 서비스 제한이 있으며 다른 DNS 호스팅 공급자로 전환하는 것이 좋을 수 있습니다.

## <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Windows 기반 DNS를 사용하여 Microsoft용 DNS 레코드 만들기

도메인에 대한 DNS 레코드가 있는 페이지로 이동합니다. Windows Server 2008에서 작업하는 경우 **시작**, **실행** 으로 이동합니다. Windows Server 2012에서 작업하는 경우 **Windows 키** 와 **r** 을 누릅니다. **dnsmgmnt.msc** 를 입력한 다음 **확인** 을 선택합니다. DNS 관리자에서 **DNS 서버 이름**, **정방향 조회 영역** 을 확장합니다. 도메인을 선택합니다. 이제 DNS 레코드를 만들 준비가 되었습니다.

## <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>도메인이 Google에서 관리되는 경우 DNS 레코드 만들기

Google Apps for Work 계정에 가입하는 동안 Google을 통해 도메인을 구매한 경우, DNS 레코드는 Google에서 관리되지만 GoDaddy를 통해 등록됩니다. Google 도메인 페이지를 통해 eNom에 액세스하고 DNS를 만들 수 있습니다.

## <a name="create-dns-records-at-11-ionos-for-microsoft"></a>1&1 IONOS에서 Microsoft용 DNS 레코드 만들기

1&1 IONOS에서는 한 도메인이 MX 레코드와 최상위 자동 검색 CNAME 레코드를 모두 보유할 수 없습니다. 이를 통해 Microsoft용 Exchange Online을 구성할 수 있는 방법이 제한됩니다. 해결 방법은 있지만 1&1 IONOS에서 하위 도메인을 만든 경험이 있는 경우에만 이 방법을 사용하는 것이 좋습니다.

서비스 제한 사항에도 불구하고 1&1 IONOS에서 Microsoft DNS 레코드를 관리하려는 경우 이 문서의 단계를 따라 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정하세요.

1&1 IONOS를 사용하려면 Microsoft 전자 메일 서비스에 필요한 CNAME 레코드와 함께 MX 레코드를 사용할 수 있도록 해결 방법이 필요합니다. 이 해결 방법을 사용하려면 1&1 IONOS에서 하위 도메인 집합을 만들어 CNAME 레코드에 할당해야 합니다.

> [!NOTE]
> 이 절차를 시작하기 전에 두 개 이상의 하위 도메인을 사용할 수 있는지 확인합니다. 1&1 IONOS에서 하위 도메인을 만들어 본 경험이 이미 있는 경우에만 이 솔루션을 사용하는 것이 좋습니다.

### <a name="basic-cname-records"></a>기본 CNAME 레코드

1.  시작하려면 1&1 IONOS의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시될 것입니다.

1.  **도메인 관리** 를 선택합니다.

1.  도메인 센터 페이지에서 업데이트하려는 도메인을 찾은 다음 **하위 도메인 관리** 를 선택합니다. 이제 두 개의 하위 도메인을 만들고 각각에 대해 **별칭** 값을 설정합니다(이 작업은 1&1 IONOS는 최상위 CNAME 레코드를 하나만 지원하지만 Microsoft에는 여러 CNAME 레코드가 필요하기 때문에 필요함).

1.  먼저 자동 검색 하위 도메인을 만듭니다. **하위 도메인 개요** 구역에서 **하위 도메인 만들기** 를 선택합니다.

1.  새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)

    |하위 도메인 만들기|별칭|
    |:----|:----|
    |autodiscover|autodiscover.outlook.com|

1.  **하위 도메인 만들기** 를 선택합니다.

1.  **하위 도메인 개요** 구역에서 방금 만든 자동 검색 하위 도메인을 찾은 다음 해당 하위 도메인에 대한 패널(v) 컨트롤을 선택합니다.

1.  **하위 도메인 설정** 영역에서 **DNS 설정 편집** 을 선택합니다.

1.  **A/AAAA 레코드(IP 주소)** 구역의 **IP 주소(A 레코드)** 영역에서 **CNAME** 을 선택합니다.

1. **별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.

    |하위 도메인 만들기|별칭|
    |:----|:----|
    |autodiscover|autodiscover.outlook.com|

1. 고지 사항을 **알고 있음** 에 대한 확인란을 선택합니다.

1. **저장** 을 선택합니다.

### <a name="additional-cname-records"></a>추가 CNAME 레코드

다음 절차의 추가 CNAME 레코드를 통해 비즈니스용 Skype Online 서비스를 사용할 수 있습니다. 이미 만든 2개의 CNAME 레코드를 만들 때와 동일한 단계를 사용합니다.

**세 번째 하위 도메인(Lyncdiscover)을 만들기**

1.  **하위 도메인 개요** 구역에서 **하위 도메인 만들기** 를 선택합니다.

1.  새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)

    |하위 도메인 만들기|별칭|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  **하위 도메인 만들기** 를 선택합니다.

1.  도메인 센터 페이지에서 **하위 도메인 관리** 를 선택합니다.

1.  **하위 도메인 개요** 구역에서 방금 만든 lyncdiscover 하위 도메인을 찾은 다음 해당 도메인에 대한 패널(v) 컨트롤을 선택합니다. **하위 도메인 설정** 영역에서 **DNS 설정 편집** 을 선택합니다.

1.  **A/AAAA 레코드(IP 주소)** 구역의 **IP 주소(A 레코드)** 영역에서 **CNAME** 을 선택합니다.

1.  **별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.

    |하위 도메인 만들기|별칭|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  고지 사항 **알고 있음** 에 대한 확인란을 선택한 다음 **저장** 을 선택합니다.

1.  **DNS 설정 편집** 대화 상자에서 **예** 를 선택합니다.

**네 번째 하위 도메인(SIP)을 만들기**

1.  **하위 도메인 개요** 구역에서 **하위 도메인 만들기** 를 선택합니다.

1.  새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)

    |하위 도메인 만들기|별칭|
    |:----|:----|
    |sip|sipdir.online.lync.com|  

1.  **하위 도메인 만들기** 를 선택합니다.

1.  도메인 센터 페이지에서 **하위 도메인 관리** 를 선택합니다.

1.  **하위 도메인 개요** 구역에서 방금 만든 sip 하위 도메인을 찾은 다음 해당 도메인에 대한 패널(v) 컨트롤을 선택합니다. <br/> **하위 도메인 설정** 영역에서 **DNS 설정 편집** 을 선택합니다.

1.  **A/AAAA 레코드(IP 주소)** 구역의 **IP 주소(A 레코드)** 영역에서 **CNAME** 을 선택합니다.

1.  **별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.

    |하위 도메인 만들기|별칭|
    |:----|:----|
    |sip|sipdir.online.lync.com|

1.  고지 사항 **알고 있음** 에 대한 확인란을 선택한 다음 **저장** 을 선택합니다.

1.  **DNS 설정 편집** 대화 상자에서 **예** 를 선택합니다.

### <a name="cname-records-needed-for-mdm"></a>MDM에 필요한 CNAME 레코드

다른 4개의 CNAME 레코드에 사용한 절차를 따르되 다음 값을 제공합니다.

|하위 도메인 만들기|별칭|
|:----|:----|
|enterpriseregistration|enterpriseregistration.windows.net|
|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|
