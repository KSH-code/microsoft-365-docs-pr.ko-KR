---
title: DNS 레코드를 추가하여 도메인 연결하기
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: 도메인을 확인하고 등록 기관 계정에서 DNS 레코드를 업데이트하여 DNS 호스팅 공급자의 도메인을 Microsoft 365에 연결합니다.
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
ms.openlocfilehash: ae8dc1c1d2f603e81d2affd723df2be460a873de
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60164815"
---
# <a name="add-dns-records-to-connect-your-domain"></a>DNS 레코드를 추가하여 도메인 연결하기

타사 호스팅 공급자로부터 도메인을 구매한 경우에는 등록 기관 계정에서 DNS 레코드를 업데이트하여 Microsoft 365에 연결할 수 있습니다.

이 단계를 마치면 도메인은 도메인을 구매한 호스트에 등록된 상태로 유지되지만, Microsoft 365는 도메인을 전자 메일 주소(예: user@yourdomain.com) 및 기타 서비스에 사용할 수 있습니다.

도메인을 추가하지 않으면 추가할 때까지 조직의 사용자가 전자 메일 주소로 onmicrosoft.com 도메인을 사용하게 됩니다. 사용자를 두 번 설정하지 않아도 되도록 사용자를 추가하기 전에 도메인을 추가하는 것이 중요합니다.

원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.yml)하세요.

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>1단계: TXT 또는 MX 레코드를 추가하여 도메인을 소유하고 있는지 확인하기

### <a name="recommended-verify-with-a-txt-record"></a>권장: TXT 레코드로 확인

먼저 Microsoft 365에 추가하려는 도메인을 소유하고 있다는 사실을 증명해야 합니다.

1. Microsoft 365 관리 센터에 로그인하고 **모두 표시** > **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**도메인**</a>을 선택합니다.
2. 새 브라우저 탭 또는 창에서 내 DNS 호스팅 공급자에 로그인한 다음 DNS 설정 관리 위치(예: 영역 파일 설정, 도메인 관리, 도메인 관리자, DNS 관리자)를 찾습니다.
3. 공급자의 DNS 관리자 페이지로 이동하고 관리 센터에 표시된 TXT 레코드를 도메인에 추가합니다.

   이 레코드를 추가해도 기존 저낮 메일이나 기타 서비스에 영향을 주지 않으며, 도메인이 Microsoft 365에 연결되면 안전하게 제거할 수 있습니다.

   예제:

   - TXT 이름: `@`
   - TXT 값: MS=ms########(관리 센터의 고유 ID)
   - TTL: `3600`(또는 공급자 기본값)

4. 레코드를 저장하고 관리 센터로 돌아간 다음 **확인** 을 선택합니다. 일반적으로 레코드가 변경 내용을 등록하는 데 15분 정도 걸리지만, 때로는 시간이 더 오래 걸릴 수 있습니다. 시간을 좀 두고 몇 번 정도 시도하면 변경 내용을 적용할 수 있습니다.

Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.

### <a name="verify-with-an-mx-record"></a>MX 레코드로 확인

등록 기관에서 TXT 레코드 추가를 지원하지 않으면 MX 레코드를 추가하여 확인할 수 있습니다.

1. Microsoft 365 관리 센터에 로그인하고 **모두 표시** > **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**도메인**</a>을 선택합니다.
2. 새 브라우저 탭 또는 창에서 내 DNS 호스팅 공급자에 로그인한 다음 DNS 설정 관리 위치(예: 영역 파일 설정, 도메인 관리, 도메인 관리자, DNS 관리자)를 찾습니다.
3. 공급자의 DNS 관리자 페이지로 이동하고 관리 센터에 표시된 MX 레코드를 도메인에 추가합니다.

이 MX 레코드의 **우선 순위** 는 도메인에 대한 모든 기존 MX 레코드의 최상위여야 합니다. 그렇지 않으면 전자 메일 보내기와 받기를 방해할 수 있습니다. 도메인 확인이 완료되면 즉시 이 레코드를 삭제해야 합니다.

필드가 다음 값으로 설정되어 있는지 확인합니다.

- 레코드 종류: `MX`
- 우선 순위: 아직 사용되지 않는 큰 값으로 설정합니다.
- 호스트 이름: `@`
- 대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.
- TTL: `3600`(또는 공급자 기본값)

Microsoft에서 올바른 MX 레코드를 찾으면 도메인이 확인된 것입니다.

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>2단계: DNS 레코드를 추가하여 Microsoft 서비스 연결하기

새 브라우저 탭 또는 창에서 내 DNS 호스팅 공급자에 로그인하여 DNS 설정 관리 위치(예: 영역 파일 설정, 도메인 관리, 도메인 관리자, DNS 관리자)를 찾습니다.

사용하려는 서비스에 따라 여러 가지 유형의 DNS 레코드를 추가합니다.

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>전자 메일에 MX 레코드 추가하기(Outlook, Exchange Online)

**시작 하기 전에**: 사용자가 도메인에 전자 메일(예: user@yourdomain.com)을 이미 가지고 있는 경우에는 MX 레코드를 설정하기 전에 관리 센터에서 사용자의 계정을 만드세요. 그러면 전자 메일을 계속 받게 됩니다. 도메인의 MX 레코드를 업데이트하면 해당 도메인을 사용하는 사용자의 모든 새 전자 메일이 이제 Microsoft 365로 옵니다. [전자 메일 및 연락처를 Microsoft 365로 마이그레이션하기](../setup/migrate-email-and-contacts-admin.md)로 결정한 경우가 아니면, 이미 가지고 있는 전자 메일은 현재 전자 메일 호스트에 남습니다.

관리 센터 도메인 설정 마법사에서 MX 레코드에 대한 정보를 얻을 수 있습니다.

호스팅 공급자의 웹 사이트에서 새 MX 레코드를 추가합니다.
필드가 다음 값으로 설정되어 있는지 확인합니다.

- 레코드 종류: `MX`
- 우선순위: 사용 가능한 가장 높은 값(일반적으로 `0`)으로 설정됩니다.
- 호스트 이름: `@`
- 대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.
- TTL: `3600`(또는 공급자 기본값)

레코드를 저장한 다음 다른 모든 MX 레코드를 제거합니다.

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>CNAME 레코드를 추가하여 다른 서비스(Teams, Exchange Online, AAD, MDM)에 연결하기

관리 센터 도메인 설정 마법사에서 CNAME 레코드에 대한 정보를 얻을 수 있습니다.

호스팅 공급자의 웹 사이트에서 연결할 각 서비스에 대한 CNAME 레코드를 추가합니다.
필드가 각각 다음 값으로 설정되어 있는지 확인합니다.

- 레코드 종류: `CNAME (Alias)`
- 호스트: 여기에 관리 센터에서 복사한 값을 붙여 넣습니다.
- 대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.
- TTL: `3600`(또는 공급자 기본값)

### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>SPF TXT 레코드를 추가하거나 편집하여 전자 메일 스팸 방지하기(Outlook, Exchange Online) 

**시작하기 전에:** 도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요. 대신, 필수 Microsoft 365 값을 호스팅 공급자 웹 사이트의 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다.

호스팅 공급자의 웹 사이트에서 기존 SPF 레코드를 편집하거나 SPF 레코드를 만듭니다.
필드가 다음 값으로 설정되어 있는지 확인합니다.

- 레코드 종류: `TXT (Text)`
- 호스트: `@`
- TXT 값: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600`(또는 공급자 기본값)

레코드를 저장합니다.

이러한 [SPF 유효성 검사 도구](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 중 하나를 사용하여 SPF 레코드의 유효성을 검사합니다.

SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다. 이 같은 기술로부터 보호하려면 SPF를 설정한 후에 Microsoft 365의 DKIM 및 DMARC도 설정해야 합니다.

시작하려면 [DKIM을 사용하여 Microsoft 365의 도메인에서 보낸 발신 전자 메일의 유효성 검사하기](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) 및 [DMARC를 사용하여 Microsoft 365에서 전자 메일의 유효성 검사하기](../../security/office-365-security/use-dmarc-to-validate-email.md)를 참조하세요.

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>커뮤니케이션 서비스(Teams, 비즈니스용 Skype)에 대한 SRV 레코드 추가하기

호스팅 공급자의 웹 사이트에서 연결할 각 서비스에 대한 SRV 레코드를 추가합니다.
필드가 각각 다음 값으로 설정되어 있는지 확인합니다.

- 레코드 종류: `SRV (Service)`
- 이름: `@`
- 대상: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.
- 프로토콜: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.
- 서비스: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.
- 우선순위: `100`
- 가중치: `1`
- 포트: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.
- TTL: `3600`(또는 공급자 기본값)

레코드를 저장합니다.

#### <a name="srv-record-field-restrictions-and-workarounds"></a>SRV 레코드 필드 제한 사항 및 해결 방법

일부 호스팅 공급자는 SRV 레코드 내에서 필드 값에 제한을 둡니다. 이러한 제한 사항에 대한 몇 가지 일반적인 해결 방법은 다음과 같습니다.

##### <a name="name"></a>이름

호스팅 공급자가 이 필드를 **@** 으로 설정하는 것을 허용하지 않는 경우 이 필드를 비워 두세요.  호스팅 공급자에 서비스 및 프로토콜 값에 대한 별도의 필드가 있는 경우 *에만* 이 방법을 사용하세요. 그렇지 않으면 아래의 서비스 및 프로토콜 정보를 참조하십시오.

##### <a name="service-and-protocol"></a>서비스 및 프로토콜

호스팅 공급자가 SRV 레코드에 이러한 필드를 제공하지 않으면 레코드의 **이름** 필드에 **서비스** 및 **프로토콜** 값을 지정해야 합니다. (참고: 호스팅 공급자에 따라 **이름** 필드는 **호스트**, **호스트 이름** 또는 **하위 도메인** 과 같은 다른 이름으로 불릴 수 있습니다.) 이러한 값을 추가하려면 값을 점으로 구분하여 단일 문자열을 만듭니다.

예: `_sip._tls`

##### <a name="priority-weight-and-port"></a>우선순위, 가중치 및 포트

호스팅 공급자가 SRV 레코드에 이러한 필드를 제공하지 않으면 레코드의 **대상** 필드에 이를 지정해야 합니다. (참고: 호스팅 공급자에 따라 **대상** 필드는 **콘텐츠**, **IP 주소** 또는 **대상 호스트** 와 같이 다른 이름으로 불릴 수도 있습니다.)

이러한 값을 추가하려면 공백으로 값을 구분하고 *점으로 끝나는* 단일 문자열을 만드세요(확실하지 않은 경우 제공업체에 문의). 값은 우선 순위, 가중치, 포트, 대상의 순서로 포함되어야 합니다.

- 예제 1: `100 1 443 sipdir.online.lync.com.`
- 예제 2: `100 1 443 sipdir.online.lync.com`

## <a name="related-content"></a>관련 콘텐츠

[모든 도메인 등록 기관에서 Microsoft 365를 설정하도록 네임 서버 변경](change-nameservers-at-any-domain-registrar.md)(문서)\
[도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 수정](find-and-fix-issues.md)(문서)\
[도메인 관리](/admin)(링크 페이지)
