---
title: DAP 파트너용 도메인을 Windows PowerShell 테넌트에 도메인 추가
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: '요약: PowerShell을 사용하여 Microsoft 365 테넌트에 대체 도메인 이름을 추가합니다.'
ms.openlocfilehash: 1a121407ebe242747a693084289e972e56e1cbee
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170526"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>DAP(위임된 액세스 권한) 파트너용 Windows PowerShell을 사용하여 클라이언트 테넌트에 도메인 추가

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

PowerShell을 사용하여 새 도메인을 만들고 고객 테넌트와 연결하여 새 도메인을 Microsoft 365 보다 빠르게 Microsoft 365 관리 센터.

DAP(위임된 액세스 권한) 파트너는 Syndication 및 CSP(클라우드 솔루션 공급자) 파트너입니다. 이러한 공급자는 다른 회사의 네트워크 또는 전자 통신 공급자인 경우가 많습니다. 또한 Microsoft 365 서비스에 구독을 번들로 묶습니다. Microsoft 365 구독을 판매하는 경우 고객 테넌트에 대한 AOBO(관리 대신 관리) 권한이 자동으로 부여되어 고객 테넌트에 대해 관리하고 보고할 수 있습니다.
## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

이 항목의 절차를 수행하려면 [PowerShell을](connect-to-microsoft-365-powershell.md)사용하여 커넥트 Microsoft 365 연결해야 합니다.

파트너 테넌트 관리자 자격 증명도 필요합니다.

다음 정보도 필요합니다.

- 고객이 원하는 FQDN(정규화된 도메인 이름)이 필요합니다.

- 고객의 **TenantId** 가 필요합니다.

- FQDN은 GoDaddy 등의 DNS(인터넷 도메인 이름 서비스) 등록 기관으로 등록해야 합니다. 도메인 이름을 공개적으로 등록하는 방법에 대한 자세한 내용은 [도메인 이름 구입 방법](../admin/get-help-with-domains/buy-a-domain-name.md)을 참조하세요.

- DNS 등록 기관에 대해 TXT 레코드를 등록된 DNS 영역에 추가하는 방법을 알아야 합니다. TXT 레코드를 추가하는 방법에 대한 자세한 내용은 도메인에 연결하기 위해 DNS 레코드 [추가를 참조하세요.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 이러한 절차가 작동하지 않으면 DNS 등록 기관에 대한 절차를 찾아야 합니다.

## <a name="create-domains"></a>도메인 만들기

 고객이 기본\<domain>.onmicrosoft.com도메인을 회사 ID로 표시할 기본 도메인으로 원하지 않으므로 테넌트와 연결할 추가 도메인 만들기를 문의할 수 있습니다. 이 절차를 통해 고객의 테넌트와 연관된 새 도메인 만들기가 진행됩니다.

> [!NOTE]
> 이러한 작업 중 일부를 수행하려면 로그인한 파트너 관리자 계정이 에서  관리자 계정의 세부 정보에서 찾을 수 있는 지원 회사에 대한 관리 액세스 할당 설정의 전체 관리로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터.</a>  파트너 관리자 역할 관리에 대한 자세한 내용은 파트너: 위임된 관리 [제공을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=532435)

### <a name="create-the-domain-in-azure-active-directory"></a>Azure Active Directory에서 도메인 만들기

이 명령은 Azure Active Directory에서 도메인을 만들지만 공개적으로 등록된 도메인으로 연결하지는 않습니다. 엔터프라이즈용 Microsoft 365에 공개적으로 등록된 도메인을 소유하고 Microsoft 365 됩니다.

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다. 이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>DNS TXT 확인 레코드에 대한 데이터 가져오기

 Microsoft 365 DNS TXT 확인 레코드에 저장해야 하는 특정 데이터를 생성합니다. 데이터를 가져오려면 이 명령을 실행합니다.

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

이는 다음과 같은 출력을 제공합니다.

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> 공개적으로 등록된 DNS 영역에서 TXT 레코드를 만들려면 이 텍스트가 필요합니다. 텍스트를 복사하고 저장해야 합니다.

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>TXT 레코드를 공개적으로 등록된 DNS 영역에 추가

Microsoft 365 공개적으로 등록된 도메인 이름으로 연결되는 트래픽을 수락하기 전에 도메인에 대한 관리자 권한을 소유하고 있어야 합니다. 도메인에서 TXT 레코드를 생성하여 도메인 소유를 증명합니다. TXT 레코드는 도메인에서 아무 작업도 수행하지 않으며 도메인 소유권이 설정되고 나면 삭제할 수 있습니다. TXT 레코드를 만들하려면 DNS 레코드 추가의 절차에 [따라 도메인을 연결합니다.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 이러한 절차가 작동하지 않으면 DNS 등록 기관에 대한 절차를 찾아야 합니다.

nslookup을 통해 TXT 레코드가 만들어졌음을 확인합니다. 이 구문을 사용합니다.

```console
nslookup -type=TXT <FQDN of registered domain>
```

이는 다음과 같은 출력을 제공합니다.

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a>도메인에서 도메인 소유권 Microsoft 365

이 마지막 단계에서는 공개적으로 등록된 Microsoft 365 도메인을 소유하는지 검사합니다. 이 단계를 Microsoft 365 새 도메인 이름으로 라우팅된 트래픽 수락을 시작하게 됩니다. 도메인 만들기 및 등록 프로세스를 완료하려면 이 명령을 실행합니다.

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

이 명령은 출력을 반환하지 않으므로 이 작업을 확인하려면 다음 명령을 실행합니다.

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

그러면 다음과 같이 반환됩니다.

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

## <a name="see-also"></a>참고 항목

[파트너를 위한 도움말](https://go.microsoft.com/fwlink/p/?LinkID=533477)
